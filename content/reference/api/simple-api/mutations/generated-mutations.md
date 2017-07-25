---
alias: ol0yuoz6go
path: /docs/reference/simple-api/mutations
layout: REFERENCE
description: A GraphQL mutation is used to modify data at a GraphQL endpoint.
simple_relay_twin: vah0igucil
tags:
  - simple-api
  - mutations
related:
  further:
    - wooghee1za
    - fasie2rahv
    - cahkav7nei
  more:
    - dah6aifoce
---

# Mutations

A *GraphQL mutation* is used to modify data at a GraphQL [endpoint](!alias-yahph3foch#project-endpoints). This is an example mutation:

```graphql
---
endpoint: https://api.graph.cool/simple/v1/cixne4sn40c7m0122h8fabni1
disabled: true
---
mutation {
  createPost(
    title: "My great Vacation"
    slug: "my-great-vacation"
    published: true
    text: "Read about my great vacation."
  ) {
    id
    slug
  }
}
---
{
  "data": {
    "createPost": {
      "id": "cixneo7zp3cda0134h7t4klep",
      "slug": "my-great-vacation"
    }
  }
}
```

Here's a list of available mutations. To explore them, use the [playground](!alias-oe1ier4iej) inside your project.

* For every [type](!alias-ij2choozae) in your [GraphQL schema](!alias-ahwoh2fohj), so called type mutations will be generated. They can be used to [create](), [update]() and [delete]() nodes of that type.
* For every [relation](!alias-goh5uthoc1) in your [GraphQL schema](!alias-ahwoh2fohj), [relation mutations]() will be generated. They can be used to connect or disconnect nodes in that relation.
* Furthermore, [nested mutations]() can be used to executed multiple mutations across types at the same time.
* Additionally, [custom mutations]() can be added to your API using [Schema Extensions]().
