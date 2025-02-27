---
title: Current Weather
permalink: /queries/api/current
---

## Description

The `current` field retrieves real-time weather data from the OpenWeatherMap API.

## Query

```graphql
query ($currentInput: LatLonInput!, $currentOptions: CurrentOptions) {
  api {
    current(input: $currentInput, options: $currentOptions) {
      base
      visibility
      dt
      timezone
      id
      name
      cod
      sys {
        type
        id
        country
        sunrise
        sunset
      }
      clouds {
        all
      }
      rain {
        one_hour
      }
      snow {
        one_hour
      }
      wind {
        speed
        deg
        gust
        max {
          speed
          direction
        }
      }
      main {
        temp
        feels_like
        temp_min
        temp_max
        pressure
        sea_level
        grnd_level
        humidity
        temp_kf
      }
      weather {
        id
        main
        description
        icon
      }
      coord {
        lon
        lat
      }
    }
  }
}
```

## Variables

```json
{
  "currentInput": { "lat": 40.7128, "lon": -74.006 },
  "currentOptions": { "units": "metric", "lang": "en" }
}
```
