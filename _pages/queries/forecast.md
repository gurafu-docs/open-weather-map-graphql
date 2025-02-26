---
title: Forecast
permalink: /queries/api/forecast
---

## Description

The `forecast` field provides hourly, 5-day, 16-day, and 30-day weather forecasts.

## Query

```graphql
query ($hourlyInput: LatLonInput!, $hourlyOptions: HourlyForecastOptions) {
  api {
    forecast {
      hourly(input: $hourlyInput, options: $hourlyOptions) {
        cod
        message
        cnt
        city {
          id
          name
          country
          population
          timezone
          sunrise
          sunset
          coord {
            lon
            lat
          }
        }
        list {
          clouds {
            all
          }
          pop
          rain {
            three_hour
          }
          snow {
            three_hour
          }
          dt
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
          wind {
            speed
            deg
            gust
            max {
              speed
              direction
            }
          }
          visibility
          sys {
            pod
          }
          weather {
            id
            main
            description
            icon
          }
          dt_txt
        }
      }
    }
  }
}
```

## Variables

```json
{
  "hourlyInput": { "lat": 40.7128, "lon": -74.006 },
  "hourlyOptions": { "units": "metric", "lang": "en", "cnt": 5 }
}
```
