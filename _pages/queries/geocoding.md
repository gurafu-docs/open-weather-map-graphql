---
title: Geocoding
permalink: /queries/api/geocoding
---

## Description

The `geocoding` field provides location-based services, including direct, reverse, and ZIP code lookup.

## Query

```graphql
query ($directInput: DirectInput) {
  api {
    geocoding {
      direct(input: $directInput) {
        name
        lat
        lon
        country
        state
      }
    }
  }
}
```

## Variables

```json
{
  "directInput": { "q": "New York", "limit": 5 }
}
```
