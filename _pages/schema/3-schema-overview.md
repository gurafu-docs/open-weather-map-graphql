---
title: Schema Overview
permalink: /open-weather-map/schema/overview/
---

### Endpoint Breakdown

These are the mappings of the Open Weather Map API endpoints to the GraphQL schema. Every reference to each of these fields in any query will return the data from the corresponding endpoint and contribute to the usage limits set by Open Weather Map. See the [Complete Query](/open-weather-map/queries) section for a complete query example.

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

### Response Structure

For the most part, the response structure of the GraphQL API mirrors that of the REST API. However, certain fields have been renamed due to GraphQL schema restrictions. These fields are as follows:

#### Current

- current.rain.1h -> one_hour
- current.snow.3h -> three_hour

#### Forecast

- forecast.five.rain.1h -> one_hour
- forecast.five.snow.3h -> three_hour

#### Trigger

- trigger.\_\_v -> \_v

Additionally, there are options available for the `area.coordinates` field in the `trigger` mutation request. These are:

- `point_coordinates`
- `multi_point_coordinates`
- `polygon_coordinates`
- `polygon_with_hole_coordinates`
- `multi_polygon_coordinates`

For more details, go to the [Trigger Area](/open-weather-map/schema/overview/trigger-area) docs.
