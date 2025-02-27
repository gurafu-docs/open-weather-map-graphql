---
title: Authentication
permalink: /open-weather-map/authentication/
---

### RapidAPI

You can access the Open Weather Map API through RapidAPI. See the [RapidAPI Open Weather Map API](https://rapidapi.com/community/api/open-weather-map) for more information.

### Open Weather Map

To authenticate your requests, you need to provide your Open Weather Map `appid`. You can do this in one of two ways:

1. Include the `appid` in the request header as `x-owm-appid`.
2. Pass the `appid` as an argument in the `api` field.

```graphql
query {
  api(appid: "<APP_ID>") {
    # ... rest of the query
  }
}
```
