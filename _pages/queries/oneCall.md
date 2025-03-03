---
title: One Call API
permalink: /open-weather-map/queries/api/onecall/
---

The `oneCall` field provides aggregated weather data, including forecasts, historical data, and alerts.

## Current and Forecast

### Query

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
        alerts {
          sender_name
          event
          start
          end
          description
          tags
        }
      }
    }
  }
}
```

### Variables

```json
{
  "currentAndForecastInput": {
    "lat": 40.748817,
    "lon": -73.985428
  },
  "currentAndForecastOptions": {
    "units": "standard",
    "lang": "en"
  }
}
```

## Day Summary

```graphql
query ($daySummaryInput: LatLonDateInput!, $daySummaryOptions: OneCallOptions) {
  api {
    oneCall {
      daySummary(input: $daySummaryInput, options: $daySummaryOptions) {
        lat
        lon
        tz
        date
        units
        wind {
          speed
          deg
          gust
          max {
            speed
            direction
          }
        }
        pressure {
          afternoon
        }
        temperature {
          min
          max
          afternoon
          night
          evening
          morning
        }
        precipitation {
          total
        }
        humidity {
          afternoon
        }
        cloud_cover {
          afternoon
        }
      }
    }
  }
}
```

### Variable

```json
{
  "daySummaryInput": {
    "lat": 40.748817,
    "lon": -73.985428,
    "date": "2020-01-01"
  },
  "daySummaryOptions": {
    "units": "standard",
    "lang": "en"
  }
}
```

## Overview

```graphql
query ($overviewInput: LatLonInput!, $overviewOptions: OneCallOptions) {
  api {
    oneCall {
      overview(input: $overviewInput, options: $overviewOptions) {
        lat
        lon
        tz
        date
        units
        weather_overview
      }
    }
  }
}
```

### Variable

```json
{
  "overviewInput": {
    "lat": 40.748817,
    "lon": -73.985428
  },
  "overviewOptions": {
    "date": "2020-01-01",
    "units": "standard"
  }
}
```

## Time Machine

```graphql
query (
  $timeMachineInput: LatLonDateInput!
  $timeMachineOptions: OneCallOptions
) {
  api {
    oneCall {
      timeMachine(input: $timeMachineInput, options: $timeMachineOptions) {
        lat
        lon
        timezone
        timezone_offset
        data {
          dt
          sunrise
          sunset
          temp
          feels_like
          pressure
          humidity
          dew_point
          uvi
          clouds
          visibility
          wind_speed
          wind_deg
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
      }
    }
  }
}
```

### Variable

```json
{
  "timeMachineInput": {
    "lat": 40.748817,
    "lon": -73.985428,
    "dt": 1643803200
  },
  "timeMachineOptions": {
    "units": "standard",
    "lang": "en"
  }
}
```
