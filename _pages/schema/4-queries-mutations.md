---
title: Queries and Mutations
permalink: /open-weather-map/schema/queries-and-mutations/
---

### Query

The API provides various queries to fetch weather data. Below are some examples:

#### Fetch Current Weather

```graphql
query allWeatherMap(
  $input: LatLonInput!
  $appid: String!
  $lang: String!
  $units: Units!
) {
  api(appid: $appid) {
    current(input: $input, options: { units: $units, lang: $lang }) {
      base
      visibility
      dt
      timezone
      id
      name
      cod
      weather {
        id
        main
        description
        icon
      }
    }
  }
}
```

#### Query variables

```json
{
  "input": {
    "lat": 51.5156177,
    "lon": 0.0919983
  },
  "appid": "<APPID>",
  "lang": "en",
  "units": "imperial"
}
```

### Mutation

You can also perform mutations to interact with the API. Below is an example of a mutation to add a weather trigger:

#### Manage Weather Triggers

```graphql
mutation addTrigger($addInput: TriggerInput!, $appid: String!) {
  api(appid: $appid) {
    trigger {
      add(input: $addInput) {
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
          type
          _id
          coordinates
        }
        alerts
      }
    }
  }
}
```

#### Query variables

```json
{
  "addInput": {
    "area": [{ "type": "Point", "coordinates": [51.5156177, 0.0919983] }],
    "conditions": [{ "name": "temperature", "expression": ">", "amount": 30 }],
    "time_period": {
      "start": { "expression": ">", "amount": 0 },
      "end": { "expression": "<", "amount": 24 }
    }
  },
  "appid": "<API KEY>"
}
```
