---
title: Air Pollution
permalink: /queries/api/air-pollution
---

## Description

The `airPollution` field provides air quality data, including current conditions, forecasts, and historical data.

## Query

```graphql
query ($currentInput: LatLonInput!) {
  api {
    airPollution {
      current(input: $currentInput) {
        list {
          dt
          components {
            co
            no
            no2
            o3
            so2
            pm2_5
            pm10
            nh3
          }
          main {
            aqi
          }
        }
        coord {
          lon
          lat
        }
      }
    }
  }
}
```

## Variables

```json
{
  "currentInput": { "lat": 40.7128, "lon": -74.006 }
}
```
