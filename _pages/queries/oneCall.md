---
title: One Call API
permalink: /queries/api/onecall
---

## Description

The `oneCall` field provides aggregated weather data, including forecasts, historical data, and alerts.

## Query

```graphql
query (
  $currentAndForecastInput: LatLonInput!
  $currentAndForecastOptions: OneCallOptions
) {
  api {
    oneCall {
      currentAndForecast(
        input: $currentAndForecastInput
        options: $currentAndForecastOptions
      ) {
        lat
        lon
        timezone
        timezone_offset
        current {
          dt
          sunrise
          sunset
          temp
          feels_like
          pressure
          humidity
          dew_point
          clouds
          uvi
          visibility
          wind_speed
          wind_gust
          wind_deg
          rain {
            one_hour
          }
          snow {
            one_hour
          }
          weather {
            id
            main
            description
            icon
          }
        }
        minutely {
          dt
          precipitation
        }
        hourly {
          dt
          temp
          feels_like
          pressure
          humidity
          dew_point
          uvi
          clouds
          visibility
          wind_speed
          wind_gust
          wind_deg
          pop
          rain {
            one_hour
          }
          snow {
            one_hour
          }
          weather {
            id
            main
            description
            icon
          }
        }
        daily {
          dt
          sunrise
          sunset
          moonrise
          moonset
          moon_phase
          summary
          temp {
            morn
            day
            eve
            night
            min
            max
          }
          feels_like {
            morn
            day
            eve
            night
            min
            max
          }
          pressure
          humidity
          dew_point
          wind_speed
          wind_gust
          wind_deg
          clouds
          uvi
          pop
          rain
          snow
          weather {
            id
            main
            description
            icon
          }
        }
      }
    }
  }
}
```

## Variables

```json
{
  "currentAndForecastInput": { "lat": 40.7128, "lon": -74.006 },
  "currentAndForecastOptions": {}
}
```
