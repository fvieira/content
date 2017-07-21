---
alias: aizoong9ah
path: /docs/reference/relay-api/overview
layout: REFERENCE
description: Relay API is supposed to be consumed by Facebook's GraphQL client Relay. Other GraphQL clients such as Apollo Client can be used as well.
simple_relay_twin: heshoov3ai
tags:
  - relay-api
related:
  further:
    - heshoov3ai
  more:
---

# API

The **Relay API*** offers many ways to interact with the data in your Graphcool project. Different options exist to [make requests to the Relay API](!alias-thaiph8ung).

The foundation for the API are the automatically generated CRUD-style operations that are based on your [data schema](). Additionally, you can use [Schema Extensions]() to enhance your GraphQL schema with additional operations. There are three categories of available operations:

* [GraphQL Queries](!alias-oiviev0xi7) are used to fetch data
* [GraphQL Mutations](!alias-vah0igucil) are used to modify data
* [GraphQL Subscriptions](!alias-eih4eew7re) are used to get notified of data changes in realtime.

The Relay API offers an [error handling](!alias-looxoo7avo) concept as well.

> Note: The Relay API is conforming with the Relay specification. If you don't use Relay as a GraphQL client, check the [Simple API](!alias-heshoov3ai) instead. The two APIs don't differ too much in features, but mostly in usage.
