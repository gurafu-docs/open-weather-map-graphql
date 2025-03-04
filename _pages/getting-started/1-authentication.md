---
title: Authentication
permalink: /open-weather-map/authentication/
toc: false
---

To use the Open Weather Map GraphQL endpoint, you need to authenticate your requests with our service via RapidAPI and Open Weather Map.

### RapidAPI

You can access the Open Weather Map API through RapidAPI. See the [RapidAPI Open Weather Map API](https://rapidapi.com/gurafu/api/open-weather-map-graphql) for more information.

### Open Weather Map

So we can retrieve the data from the Open Weather Map API, you need to provide your Open Weather Map `appid`. You can do this in one of two ways:

1. Include the `appid` in the request header as `x-owm-appid`.
2. Pass the `appid` as an argument in the `api` field.

```graphql
query {
  api(appid: "<APP_ID>") {
    # ... rest of the query
  }
}
```

You only need to provide the `appid` using one of the methods above.
