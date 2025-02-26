---
title: Trigger Area
permalink: /schema/trigger-area/
---

Due to the loose structure of the `area.coordinates` on a `trigger` object, there are multiple options of handling the values during querying and mutation. Below are some useful examples of queries and query variables to help you get started.

##### Queries

To access the `coordinates` field in the `area` object, you can either us the `coordinates` field which returns a generic JSON value, or use the more specific fields for type hinting.

Within Typescript, using the `coordinates` field can keep your code leaner, with some type checking / casting on the client side. However, using the more specific fields can make your code more readable and will require just a non-null check.

This query shows how to choose between the two options:

```graphql
query triggerQuery($appid: String) {
  api(appid: $appid) {
    trigger {
      list {
        ...triggerFragment
      }
    }
  }
}

fragment triggerFragment on Trigger {
  area {
    __typename
    type
    coordinates
    ... on Point {
      point_coordinates
    }
    ... on MultiPoint {
      multi_point_coordinates
    }
    ... on Polygon {
      polygon_coordinates
    }
    # ... Other types
  }
}
```

Would result in something like this:

```json
{
  "data": {
    "api": {
      "trigger": {
        "list": [
          {
            "area": [
              {
                "__typename": "Point",
                "type": "Point",
                "coordinates": [53, 37],
                "point_coordinates": [53, 37]
              }
            ]
          },
          {
            "area": [
              {
                "__typename": "MultiPoint",
                "type": "MultiPoint",
                "coordinates": [
                  [80, 45],
                  [-80, 90]
                ],
                "multi_point_coordinates": [
                  [80, 45],
                  [-80, 90]
                ]
              }
            ]
          },
          {
            "area": [
              {
                "__typename": "Polygon",
                "type": "Polygon",
                "coordinates": [
                  [
                    [0, 0],
                    [0, 10],
                    [10, 10],
                    [10, 0],
                    [0, 0]
                  ]
                ],
                "polygon_coordinates": [
                  [
                    [0, 0],
                    [0, 10],
                    [10, 10],
                    [10, 0],
                    [0, 0]
                  ]
                ]
              }
            ]
          }
        ]
      }
    }
  }
}
```

##### Mutation Query Variables

The coordinates can be input usings the standard `coordinates` field, but there are additional fields with more specific names to help you input the coordinates in a more structured way. This should make it clearer what type of coordinates are being input.

These types can still be messy due to the input fields being an array. For example, the difference between a Polygon with a Hole and one without isn't a type but an additional array of coordinates. If this doesn't suit you're needs, there is always the escape hatch of using the standard `coordinates` field, which will accept any JSON value. Validation is still carried out by the Open Weather Map API, so only valid values will be accepted.

The same structure is available in both the `mutation.trigger.add` and `mutation.trigger.update` fields.

For example, to add a trigger with a Polygon area:

```graphql
mutation addTrigger($addInput: TriggerInput!) {
  api {
    trigger {
      add(input: $addInput) {
        _v
        _id
      }
    }
  }
}
```

can use this variable...

```json
{
  "addInput": {
    "area": [
      {
        "type": "MultiPolygon",
        "multi_polygon_coordinates": [
          [
            [
              [0.0, 0.0],
              [0.0, 90.0],
              [180.0, 90.0],
              [180.0, 0.0],
              [0.0, 0.0]
            ]
          ]
        ]
        // ... Other fields
      }
    ]
  }
}
```

or this variable...

```json
{
  "addInput": {
    "area": [
      {
        "type": "MultiPolygon",
        "coordinates": [
          [
            [
              [0.0, 0.0],
              [0.0, 90.0],
              [180.0, 90.0],
              [180.0, 0.0],
              [0.0, 0.0]
            ]
          ]
        ]
        // ... Other fields
      }
    ]
  }
}
```
