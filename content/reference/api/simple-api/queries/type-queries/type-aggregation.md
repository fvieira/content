---
alias: choh5leigh
path: /docs/reference/simple-api/type-aggregation
layout: REFERENCE
shorttitle: Type Aggregation Queries
description: For every available type in your GraphQL schema, certain queries are automatically generated.
simple_relay_twin:
tags:
  - simple-api
  - queries
  - type
related:
  further:
  more:
---

# Type Aggregation Queries in the Simple API

For every type in your GraphQL schema, different aggregation queries are available.

## Fetch the number of all nodes

> Count the number of all `User` nodes:

```graphql
---
endpoint: https://api.graph.cool/simple/v1/cixne4sn40c7m0122h8fabni1
disabled: false
---
query {
  _allUsersMeta {
    count
  }
}
---
{
  "data": {
    "_allUsersMeta": {
      "count": 3
    }
  }
}
```

## Count the number of nodes matching a certain filter condition

> Count the number of all `User` nodes with `accessRole` `ADMIN`:

```graphql
---
endpoint: https://api.graph.cool/simple/v1/cixne4sn40c7m0122h8fabni1
disabled: false
---
query {
  _allUsersMeta(filter: {
    accessRole: ADMIN
  }) {
    count
  }
}
---
{
  "data": {
    "_allUsersMeta": {
      "count": 1
    }
  }
}
```

## More Aggregation Options

Currently, count is the only available aggregation. For specific use cases, you can use [functions]() to precalculate certain aggregations and update them when data changes.

Please join the discussion on [GitHub](https://github.com/graphcool/feature-requests/issues/70) if you are interested in a specific aggregation.
