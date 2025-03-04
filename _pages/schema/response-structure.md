---
title: Response Structure
permalink: /open-weather-map/schema/response-structure/
---

For the most part, the response structure of the GraphQL API mirrors that of the REST API. However, certain fields have been renamed due to GraphQL schema restrictions.

If migrating from the REST API to the GraphQL API, you may need to update your code to reflect these changes.

The fields are as follows:

### Current

- current.rain.1h -> one_hour
- current.snow.1h -> one_hour

e.g.,

```json
{
  "api": {
    "current": {
      "rain": {
        // "1h": 0.1
        "one_hour": 0.1
      },
      "snow": {
        // "1h": 0.2
        "one_hour": 0.2
      }
    }
  }
}
```

### Forecast

- forecast.hourly.rain.1h -> one_hour
- forecast.hourly.snow.1h -> one_hour
- forecast.five.rain.3h -> three_hour
- forecast.five.snow.3h -> three_hour

e.g.,

```json
{
  "api": {
    "forecast": {
      "hourly": {
        "rain": {
          // "1h": 0.1
          "one_hour": 0.1
        },
        "snow": {
          // "1h": 0.2
          "one_hour": 0.2
        }
      },
      "five": {
        "rain": {
          // "3h": 0.1
          "three_hour": 0.1
        },
        "snow": {
          // "3h": 0.2
          "three_hour": 0.2
        }
      }
    }
  }
}
```

### One Call

- oneCall.currentAndForecast.rain.1h -> one_hour
- oneCall.currentAndForecast.snow.1h -> one_hour
- oneCall.timeMachine.rain.1h -> one_hour
- oneCall.timeMachine.snow.1h -> one_hour

e.g.,

```json
{
  "api": {
    "oneCall": {
      "currentAndForecast": {
        "rain": {
          // "1h": 0.1
          "one_hour": 0.1
        },
        "snow": {
          // "1h": 0.2
          "one_hour": 0.2
        }
      },
      "timeMachine": {
        "rain": {
          // "1h": 0.1
          "one_hour": 0.1
        },
        "snow": {
          // "1h": 0.2
          "one_hour": 0.2
        }
      }
    }
  }
}
```

### Trigger

- trigger.\_\_v -> \_v

e.g.,

```json
{
  "api": {
    "trigger": {
      "list": [
        {
          // "__v": 0
          "_v": 0
        }
      ]
    }
  }
}
```

There are also additional options available for the `area.coordinates` field in the `trigger` query and mutation requests. These are:

- `point_coordinates`
- `multi_point_coordinates`
- `polygon_coordinates`
- `polygon_with_hole_coordinates`
- `multi_polygon_coordinates`

For more details, go to the [Trigger Area](/open-weather-map/schema/trigger-area) docs.
