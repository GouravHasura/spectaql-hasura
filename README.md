
# SpectaQL Documentation

## Overview

SpectaQL is a tool for generating static documentation for GraphQL APIs using introspection and user-defined configuration. This guide provides steps to set up and use SpectaQL with a custom GraphQL endpoint.

---

## Method 1: Quick Setup

### Step 1: Install SpectaQL Globally
To install SpectaQL globally on your system, run the following command:

```bash
npm install -g spectaql
```

### Step 2: Configure Your GraphQL Endpoint
Create a `spectaql-config.yaml` file and include your GraphQL endpoint along with any required headers. Here’s an example configuration:

```yaml
spectaql:
  logoFile: ./logo.svg

introspection:
  url: 'REPLACE_WITH_YOUR_GRAPHQL_ENDPOINT'
  headers:
     x-hasura-admin-secret: 'REPLACE_WITH_YOUR_API_KEY'

info:
  title: test-hasura
  description:
    'spectaql-test-hasura'

servers:
  - url: 'REPLACE_WITH_YOUR_GRAPHQL_ENDPOINT'
    description: Production
    production: true
```

- Replace `REPLACE_WITH_YOUR_GRAPHQL_ENDPOINT` with your actual GraphQL API endpoint.
- Replace `REPLACE_WITH_YOUR_API_KEY` with your authentication token or admin secret.

### Step 3: Start Development Mode
Run the following command to generate the documentation and start the development mode:

```bash
spectaql -d spectaql-config.yaml
```

This command will generate and serve the documentation locally, allowing you to preview changes in real-time.

---

## Notes
- Ensure your GraphQL endpoint supports introspection queries for SpectaQL to work properly.
- You can customize the `spectaql-config.yaml` file further to include additional details, such as custom descriptions, examples, or logos.

## Resources
- [SpectaQL Documentation](https://github.com/anvilco/spectaql)
- [GraphQL Introspection](https://graphql.org/learn/introspection/)

---

Happy Documenting!
