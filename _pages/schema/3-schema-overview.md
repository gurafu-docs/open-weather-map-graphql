---
title: Schema Overview
permalink: /open-weather-map/schema/overview/
toc: false
---

These are the mappings of the Open Weather Map API endpoints to the GraphQL schema.

Every reference to each of these fields in any query will return the data from the corresponding endpoint and contribute to the usage limits set by Open Weather Map. See the [Queries](/open-weather-map/queries) section for field details.

```graphql
query {
  api {
    current # /weather
    oneCall {
      currentAndForecast # /onecall
      daySummary # /onecall/day_summary
      overview # /onecall/overview
      timeMachine # /onecall/timemachine
    }
    airPollution {
      current # /air_pollution
      forecast # /air_pollution/forecast
      history # /air_pollution/history
    }
    forecast {
      hourly # /forecast/hourly
      five # /forecast
      sixteen # /forecast/daily
      thirty # /forecast/climate
    }
    geocoding {
      direct # /direct
      zip # /zip
      reverse # /reverse
    }
    trigger {
      list # /triggers
      get # /triggers/{id}
      history {
        list # /history
        get # /history/{historyId}
      }
    }
  }
}
```

```graphql
mutation {
  api {
    trigger {
      add # /triggers
      update # /triggers/{id}
      delete # /triggers/{id}
    }
  }
}
```
