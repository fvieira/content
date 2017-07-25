---
alias: koo4eevun4
path: /docs/reference/simple-api/sending-graphql-requests
layout: REFERENCE
shorttitle: Sending GraphQL Requests
description: Requests to the Simple API can be done with Apollo Client, graphql-request or plain HTTP.
simple_relay_twin: thaiph8ung
tags:
  - simple-api
  - apollo
  - plain-http
related:
  further:
  more:
---

# Sending GraphQL Requests to the Simple API

The Simple API is supposed to be consumed by GraphQL clients such as Apollo Client or  `graphql-request` and can be also consumed with plain HTTP requests.

## Playground

The [Graphcool Playground]() can be used to explore and run GraphQL mutations, queries and subscriptions.

Before diving into a specific implementation, **it's often better to get familiar with the available operations in the playground first**.

## Apollo Client

### Usage

To set up the client with your endpoint:

```javascript
import ApolloClient, { createNetworkInterface } from 'apollo-client'

const client = new ApolloClient({
  networkInterface: createNetworkInterface({ uri: 'https://api.graph.cool/simple/v1/__PROJECT_ID__' }),
})
```

Now you can use Apollo to do queries and mutations. If you are unsure about the setup, check the [quickstart](https://www.graph.cool/docs/quickstart/).

## graphql-request

[`graphql-=request`](https://github.com/graphcool/graphql-request) is a minimal GraphQL client supporting Node and browsers for server-side scripts or simple applications.

### Usage

To set up the client with your endpoint and use the `request` method to send a GraphQL query or mutation:

```javascript
const { request } = require('graphql-request')

const query = `{
  Movie(title: "Inception") {
    releaseDate
    actors {
      name
    }
  }
}`

request('https://api.graph.cool/simple/v1/movies', query).then(data => console.log(data))
```

## Plain HTTP

You can also communicate with the Simple API by using plain HTTP POST requests. For example, to query `allUsers`, do a POST request to your endpoint `https://api.graph.cool/simple/v1/__PROJECT_ID__`.

With `curl` you can query like this:

```bash
curl 'https://api.graph.cool/simple/v1/movies' -H 'content-type: application/json' --data-binary '{"query":"query {allMovies {id title}}"}' --compressed
```

returning

```json
{
  "data": {
    "allMovies": [
      {
        "id": "cixos5gtq0ogi0126tvekxo27",
        "title": "Inception"
      },
      {
        "id": "cixxhjs04pm0h015815qnrkyu",
        "title": "The Dark Knight"
      },
      {
        "id": "cixxhneo4qd4e01503f08d2hc",
        "title": "Batman Begins"
      },
      {
        "id": "cixxhupwksrq50150i50j3lha",
        "title": "The Dark Knight Rises"
      }
    ]
  }
}
```

Mutations work similarly (note the `query` property in the passed body):

```bash
curl 'https://api.graph.cool/simple/v1/movies' -H 'content-type: application/json' --data-binary '{"query":"mutation {createMovie(releaseDate: \"2016-11-18\" title: \"Moonlight\") {id}}"}' --compressed
```

With `fetch` you could do:

```javascript
const response = await fetch('https://api.graph.cool/simple/v1/__PROJECT_ID__', {
  method: 'post',
  headers: {
    'content-type': 'application/json'
  },
  body: JSON.stringify({
    query: `
      query {
        allMovies {
          id
          title
        }
      }
    `
  })
})

const responseJSON = await response.json()
const data = responseJSON.data
```

### Subscriptions

Subscriptions can be created using WebSockets. Read more about [the GraphQL Subscription Protocol]().
