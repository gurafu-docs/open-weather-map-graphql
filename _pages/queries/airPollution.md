---
title: Air Pollution
permalink: /open-weather-map/queries/api/air-pollution/
---

## Description

The `airPollution` field provides air quality data, including current conditions, forecasts, and historical data.

### Current

#### Query

```graphql
query ($currentInput: LatLonInput!) {
query (
  $currentInput: LatLonInput!
) {
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

### Variables

```json
{
  "currentInput": { "lat": 40.7128, "lon": -74.006 }
}
```

### Forecast

#### Query

```graphql
query ($forecastInput: LatLonInput!) {
  api {
    airPollution {
      forecast(input: $forecastInput) {
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

### Variables

```json
{
  "forecastInput": { "lat": 40.7128, "lon": -74.006 }
}
```

### History

#### Query

```graphql
query ($historyInput: AirPollutionHistoryInput!) {
  api {
    airPollution {
      history(input: $historyInput) {
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

### Variables

```json
{
  "historyInput": {
    "lat": 40.7128,
    "lon": -74.006,
    "start": 1700000000,
    "end": 1700100000
  }
}
```
