---
title: Road Risk
permalink: /open-weather-map/queries/api/road-risk/
---

The `roadRisk` field allows access to road risk data such as weather data and national alerts at the point of destination and along a route.

### Query

```graphql
query ($roadRiskInput: RoadRiskInput!) {
  api {
    roadRisk(input: $roadRiskInput) {
      dt
      alerts {
        sender_name
        event
        event_level
      }
      road {
        state
        temp
      }
      weather {
        temp
        wind_speed
        wind_deg
        precipitation_intensity
        dew_point
      }
      coord
    }
  }
}
```

### Variables

```json
{
  "roadRiskInput": {
    "track": [
      {
        "lat": 30.680439786468128,
        "lon": -88.81896972656251,
        "dt": 1602702000
      },
      {
        "lat": 30.56699087315334,
        "lon": -89.44519042968751,
        "dt": 1602702000
      }
    ]
  }
}
```
