---
title: Response Structure
permalink: /open-weather-map/schema/response-structure/
---

For the most part, the response structure of the GraphQL API mirrors that of the REST API. However, certain fields have been renamed due to GraphQL schema restrictions. These fields are as follows:

#### Current

- current.rain.1h -> one_hour
- current.snow.3h -> three_hour

#### Forecast

- forecast.five.rain.1h -> one_hour
- forecast.five.snow.3h -> three_hour

#### Trigger

- trigger.\_\_v -> \_v

There are also additional options available for the `area.coordinates` field in the `trigger` query and mutation requests. These are:

- `point_coordinates`
- `multi_point_coordinates`
- `polygon_coordinates`
- `polygon_with_hole_coordinates`
- `multi_polygon_coordinates`

For more details, go to the [Trigger Area](/open-weather-map/schema/trigger-area) docs.
