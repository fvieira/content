---
alias: yoo8vaifoa
path: /docs/reference/relay-api/nested-mutations
layout: REFERENCE
shorttitle: Nested Mutations
description: Create or connect multiple nodes across relations all in a single mutation.
simple_relay_twin: ubohch8quo
tags:
  - relay-api
  - mutations
related:
  further:
    - oodoi6zeit
    - uath8aifo6
    - ek8eizeish
    - thaiph8ung
    - da7pu3seew
  more:
    - cahzai2eur
    - dah6aifoce
    - vietahx7ih
---

# Nested Mutations in the Relay API

When creating or updating nodes, you can execute _nested mutations_ to interact with connected parts of your type schema.

* to **create and connect to a new node** on the other side of a relation, you can use [nested create mutations](!alias-ma6eijae7a).
* to **connect to an existing node** on the other side of a relation, you can use [nested connect mutations](!alias-ec6aegaiso).

## Limitations

Different limitations and improvement suggestions are available. Please join the discussion on GitHub!

* [Nested delete mutations](https://github.com/graphcool/feature-requests/issues/42) are not available yet. Neither are [cascading deletes](https://github.com/graphcool/feature-requests/issues/47).
* Currently, the [maximum nested level is 3](https://github.com/graphcool/feature-requests/issues/313). If you want to nest more often than that, you need to split up the nested mutations into two separate mutations.

Many other [suggestions and improvements](https://github.com/graphcool/feature-requests/issues/127) are currently being discussed.
