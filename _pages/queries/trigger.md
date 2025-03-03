---
title: Trigger API
permalink: /open-weather-map/queries/api/trigger/
---

The `trigger` field allows access to weather-based triggers and alert histories.

## List Triggers

### Query

```graphql
query {
  api {
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
    }
  }
}
```

## Get Trigger

### Query

```graphql
query ($getId: ID!) {
  api {
    trigger {
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

### Variables

```json
{
  "getId": "<insert trigger id>"
}
```
