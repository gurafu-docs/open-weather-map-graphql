---
title: Forecast
permalink: /queries/api/forecast
---

## Description

The `forecast` field provides hourly, 5-day, 16-day, and 30-day weather forecasts.

## Hourly

### Query

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
            one_hour
          }
          snow {
            one_hour
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
          feels_like {
            day
            night
            eve
            morn
          }
          temp {
            day
            min
            max
            night
            eve
            morn
          }
          dt_txt
        }
      }
    }
  }
}
```

### Variables

```json
{
  "hourlyInput": {
    "lat": 40.7128,
    "lon": -74.006
  },
  "hourlyOptions": {
    "units": "standard",
    "lang": "sq",
    "cnt": 5
  }
}
```

## 5-Day

### Query

```graphql
query ($fiveInput: FiveInput!, $fiveOptions: FiveOptions) {
  api {
    forecast {
      five(input: $fiveInput, options: $fiveOptions) {
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
          feels_like {
            day
            night
            eve
            morn
          }
          temp {
            day
            min
            max
            night
            eve
            morn
          }
          dt_txt
        }
      }
    }
  }
}
```

### Variables

```json
{
  "fiveInput": {
    "lat": 40.7128,
    "lon": -74.006
  },
  "fiveOptions": {
    "units": "metric",
    "lang": "en",
    "cnt": 5
  }
}
```

## 16-Day

```graphql
query ($sixteenInput: SixteenInput, $sixteenOptions: SixteenOptions) {
  api {
    forecast {
      sixteen(input: $sixteenInput, options: $sixteenOptions) {
        cod
        message
        cnt
        list {
          dt
          sunrise
          sunset
          pressure
          humidity
          speed
          deg
          gust
          clouds
          pop
          rain
          snow
          weather {
            id
            main
            description
            icon
          }
          feels_like {
            day
            night
            eve
            morn
          }
          temp {
            day
            min
            max
            night
            eve
            morn
          }
        }
        city {
          id
          name
          country
          population
          timezone
          coord {
            lon
            lat
          }
        }
      }
    }
  }
}
```

### Variables

```json
{
  "sixteenInput": {
    "lat": 40.7128,
    "lon": -74.006
  },
  "sixteenOptions": {
    "units": "standard",
    "lang": "sq",
    "cnt": 5
  }
}
```

## 30-Day

```graphql
query ($thirtyInput: ThirtyInput!, $thirtyOptions: ThirtyOptions) {
  api {
    forecast {
      thirty(input: $thirtyInput, options: $thirtyOptions) {
        code
        message
        cnt
        list {
          dt
          sunrise
          sunset
          pressure
          humidity
          speed
          deg
          clouds
          rain
          snow
          weather {
            id
            main
            description
            icon
          }
          feels_like {
            day
            night
            eve
            morn
          }
          temp {
            day
            min
            max
            night
            eve
            morn
          }
        }
        city {
          id
          name
          country
          population
          timezone
          coord {
            lon
            lat
          }
        }
      }
    }
  }
}
```

### Variables

```json
{
  "thirtyInput": {
    "lat": 40.7128,
    "lon": -74.006
  },
  "thirtyOptions": {
    "units": "standard",
    "lang": "sq",
    "cnt": 5
  }
}
```
