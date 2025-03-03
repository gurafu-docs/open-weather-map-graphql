---
title: Quick Start
permalink: /open-weather-map/quick-start/
toc: false
---

Here's a quick start guide to get you up and running with the Open Weather Map GraphQL API.

1. Get an Open Weather Map API Key from the Open Weather Map [API Keys Dashboard](https://home.openweathermap.org/api_keys).

2. Sign up to the [RapidAPI Open Weather Map API](https://rapidapi.com/gurafu/api/open-weather-map-graphql).

3. Run your first query in the RapidAPI Playground (Don't forget to replace `<API_KEY>` with your Open Weather Map `appid`):

```graphql
query {
  api(appid: "<API_KEY>") {
    current(input: { lat: 40.7128, lon: -74.006 }) {
      base
      visibility
      dt
      timezone
      id
      name
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
    }
  }
}
```

And there you have it! You've just made your first query to the Open Weather Map GraphQL API. 🥳🎉🌤️

See the [Queries](/open-weather-map/queries/) and [Mutations](/open-weather-map/mutations/) sections for more information on how to interact with the API.
