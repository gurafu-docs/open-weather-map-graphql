---
title: Triggers
permalink: /open-weather-map/mutations/triggers/
---

Allows you to add, update and delete triggers in the Open Weather Map API.

## Add

Add a trigger to the Open Weather Map API. You will need to provide the following input fields:

### Query

```graphql
mutation ($addInput: TriggerInput!) {
  api {
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

### Variables

```json
{
  "addInput": {
    "time_period": {
      "start": {
        "expression": "after",
        "amount": 132000000
      },
      "end": {
        "expression": "after",
        "amount": 432000000
      }
    },
    "conditions": [
      {
        "name": "temp",
        "expression": "$gt",
        "amount": 270
      }
    ],
    "area": [
      {
        "type": "Point",
        "coordinates": [50, 30]
      }
    ]
  }
}
```

## Update

Update a trigger in the Open Weather Map API. As with creating a trigger, you will need to provide all the fields in the input.

### Query

```graphql
mutation ($updateId: ID!, $updateInput: TriggerInput!) {
  api {
    trigger {
      update(id: $updateId, input: $updateInput) {
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

### Variables

```json
{
  "updateId": "<TRIGGER ID>",
  "updateInput": {
    "time_period": {
      "start": {
        "expression": "after",
        "amount": 132000000
      },
      "end": {
        "expression": "after",
        "amount": 132000000
      }
    },
    "conditions": [
      {
        "name": "temp",
        "expression": "$lt",
        "amount": 200
      }
    ],
    "area": [
      {
        "type": "Point",
        "coordinates": [53, 37]
      }
    ]
  }
}
```

## Delete

The deletion of a trigger is not currently supported due to a limitation in the Open Weather Map API. There is currently an ticket open to add this feature, but it is not yet implemented.

Come back soon for updates!

## Error Handling

On invalid input data, Open Weather Map API responds in a text format. When this is the case, the text will be returned in the GraphQL `errors` array in the `message` field.

Details about the response code can be found in `errors.extensions.info.response.status`.

```json
{
  "errors": [
    {
      "message": "Point should to have 2 elements - lon and lat.",
      "locations": [
        {
          "line": 8,
          "column": 4
        }
      ],
      "path": ["api", "trigger", "add"],
      "extensions": {
        "code": "INVALID_RESPONSE",
        "info": {
          "response": {
            "status": 400,
            "body": "Point should to have 2 elements - lon and lat."
          }
        }
      }
    }
  ]
}
```
