---
title: Trigger API
permalink: /queries/api/trigger
---

## Description

The `trigger` field allows access to weather-based triggers and alert histories.

## Query

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

## Variables

```json
{
  "getId": "<insert trigger id>"
}
```
