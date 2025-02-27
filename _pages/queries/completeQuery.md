---
title: Complete Query
permalink: /queries/complete/
---

### Complete Query

This is the complete query. Remember that this will make 18 calls to the Open Weather Map API, so be careful with your usage.

You must have the relevant Open Weather Map plan to access certain fields. For example, the `oneCall` field requires the `One Call API` plan.

#### Query

[Go to Variables](#variables)

```graphql
query (
  $currentInput: LatLonInput!
  $forecastInput: LatLonInput!
  $historyInput: AirPollutionHistoryInput!
  $currentInput1: LatLonInput!
  $currentOptions: CurrentOptions
  $hourlyInput: LatLonInput!
  $hourlyOptions: HourlyForecastOptions
  $sixteenInput: LatLonInput!
  $sixteenOptions: Forecast16Options
  $thirtyInput: LatLonInput!
  $thirtyOptions: Forecast30Options
  $fiveInput: LatLonInput!
  $fiveOptions: Forecast5Options
  $directInput: DirectInput
  $zipZip: String!
  $reverseInput: ReverseInput
  $currentAndForecastInput: LatLonInput!
  $currentAndForecastOptions: OneCallOptions
  $daySummaryInput: DaySummaryInput!
  $daySummaryOptions: OneCallOptions
  $overviewInput: LatLonInput!
  $overviewOptions: OverviewOptions
  $timeMachineInput: TimeMachineInput!
  $timeMachineOptions: OneCallOptions
  $getId: ID!
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
    current(input: $currentInput1, options: $currentOptions) {
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
    geocoding {
      direct(input: $directInput) {
        name
        lat
        lon
        country
        state
        local_names {
          ascii
          feature_name
          ms
          gu
          is
          wa
          mg
          gl
          om
          ku
          tw
          mk
          ee
          fj
          gd
          ky
          yo
          zu
          bg
          tk
          co
          sh
          de
          kl
          bi
          km
          lt
          fi
          fy
          ba
          sc
          ja
          am
          sk
          mr
          es
          sq
          te
          br
          uz
          da
          sw
          fa
          sr
          cu
          ln
          na
          wo
          ig
          to
          ta
          mt
          ar
          su
          ab
          ps
          bm
          mi
          kn
          kv
          os
          bn
          li
          vi
          zh
          eo
          ha
          tt
          lb
          ce
          hu
          it
          tl
          pl
          sm
          en
          vo
          el
          sn
          fr
          cs
          io
          hi
          et
          pa
          av
          ko
          bh
          yi
          sa
          sl
          hr
          si
          so
          gn
          ay
          se
          sd
          af
          ga
          or
          ia
          ie
          ug
          nl
          gv
          qu
          be
          an
          fo
          hy
          nv
          bo
          id
          lv
          ca
          no
          nn
          ml
          my
          ne
          he
          cy
          lo
          jv
          sv
          mn
          tg
          kw
          cv
          az
          oc
          th
          ru
          ny
          bs
          st
          ro
          rm
          ff
          kk
          uk
          pt
          tr
          eu
          ht
          ka
          ur
        }
      }
      zip(zip: $zipZip) {
        zip
        name
        lat
        lon
        country
      }
      reverse(input: $reverseInput) {
        name
        lat
        lon
        country
        local_names {
          ascii
          feature_name
          ms
          gu
          is
          wa
          mg
          gl
          om
          ku
          tw
          mk
          ee
          fj
          gd
          ky
          yo
          zu
          bg
          tk
          co
          sh
          de
          kl
          bi
          km
          lt
          fi
          fy
          ba
          sc
          ja
          am
          sk
          mr
          es
          sq
          te
          br
          uz
          da
          sw
          fa
          sr
          cu
          ln
          na
          wo
          ig
          to
          ta
          mt
          ar
          su
          ab
          ps
          bm
          mi
          kn
          kv
          os
          bn
          li
          vi
          zh
          eo
          ha
          tt
          lb
          ce
          hu
          it
          tl
          pl
          sm
          en
          vo
          el
          sn
          fr
          cs
          io
          hi
          et
          pa
          av
          ko
          bh
          yi
          sa
          sl
          hr
          si
          so
          gn
          ay
          se
          sd
          af
          ga
          or
          ia
          ie
          ug
          nl
          gv
          qu
          be
          an
          fo
          hy
          nv
          bo
          id
          lv
          ca
          no
          nn
          ml
          my
          ne
          he
          cy
          lo
          jv
          sv
          mn
          tg
          kw
          cv
          az
          oc
          th
          ru
          ny
          bs
          st
          ro
          rm
          ff
          kk
          uk
          pt
          tr
          eu
          ht
          ka
          ur
        }
        state
      }
    }
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
      overview(input: $overviewInput, options: $overviewOptions) {
        lat
        lon
        tz
        date
        units
        weather_overview
      }
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
          weather {
            id
            main
            description
            icon
          }
        }
      }
    }
    trigger {
      list {
        _v
        _id
        time_period {
          start {
            expression
            amount
          }
          end {
            expression
            amount
          }
        }
        conditions {
          name
          expression
          amount
          _id
        }
        area {
          _id
          type
          coordinates
        }
        alerts
      }
      get(id: $getId) {
        _v
        _id
        time_period {
          start {
            expression
            amount
          }
          end {
            expression
            amount
          }
        }
        conditions {
          name
          expression
          amount
          _id
        }
        area {
          _id
          type
          coordinates
        }
        alerts
      }
    }
  }
}
```

#### Variables

[Go to Query](#query)

```json
{
  "currentInput": {
    "lat": 40.7128,
    "lon": -74.006
  },
  "forecastInput": {
    "lat": 40.7128,
    "lon": -74.006
  },
  "historyInput": {
    "lat": 40.7128,
    "lon": -74.006,
    "start": 1700000000,
    "end": 1700100000
  },
  "currentInput1": {
    "lat": 40.7128,
    "lon": -74.006
  },
  "currentOptions": {
    "units": "metric",
    "lang": "en"
  },
  "hourlyInput": {
    "lat": 40.7128,
    "lon": -74.006
  },
  "hourlyOptions": {
    "units": "standard",
    "lang": "en",
    "cnt": 5
  },
  "sixteenInput": {
    "lat": 40.7128,
    "lon": -74.006
  },
  "sixteenOptions": {
    "units": "standard",
    "lang": "en",
    "cnt": 5
  },
  "thirtyInput": {
    "lat": 40.7128,
    "lon": -74.006
  },
  "thirtyOptions": {
    "units": "standard",
    "lang": "en",
    "cnt": 5
  },
  "fiveInput": {
    "lat": 40.7128,
    "lon": -74.006
  },
  "fiveOptions": {
    "units": "metric",
    "lang": "en",
    "cnt": 5
  },
  "directInput": {
    "q": "New York",
    "limit": 5
  },
  "zipZip": "10001",
  "reverseInput": {
    "lat": 40.7128,
    "lon": -74.006,
    "limit": 5
  },
  "hourlyForecastInput": {
    "lat": 40.7128,
    "lon": -74.006
  },
  "hourlyForecastOptions": {
    "units": "metric",
    "lang": "en",
    "cnt": 48
  },
  "currentAndForecastInput": {
    "lat": -58.98647823782459,
    "lon": 3.67210260248928
  },
  "currentAndForecastOptions": {
    "units": "standard",
    "lang": "en"
  },
  "daySummaryInput": {
    "lat": -58.98647823782459,
    "lon": 3.67210260248928,
    "date": "2020-01-01"
  },
  "daySummaryOptions": {
    "units": "standard",
    "lang": "en"
  },
  "overviewInput": {
    "lat": -58.98647823782459,
    "lon": 3.67210260248928
  },
  "overviewOptions": {
    "date": "2020-01-01",
    "units": "standard"
  },
  "timeMachineInput": {
    "lat": -58.98647823782459,
    "lon": 3.67210260248928,
    "dt": 1643803200
  },
  "timeMachineOptions": {
    "units": "standard",
    "lang": "en"
  },
  "getId": "<insert trigger id>"
}
```
