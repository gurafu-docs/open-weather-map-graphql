---
title: Current Weather
permalink: /queries/api
---

## Description

The `api` field sites at the root of the query. It can take an optional `appid` argument to set the API key for the query.

If not provided, the API key must be set as the request header `x-owm-appid`.

## Query

```graphql
query ($appid: String) {
  api(appid: $appid) {
    # ... rest of the query
  }
}
```

## Variables

```json
{
  "appid": "<API_KEY>"
}
```
