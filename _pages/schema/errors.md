---
title: Errors
permalink: /open-weather-map/schema/errors/
toc: false
---

Open Weather Map GraphQL attempts to provide helpful error messages when something goes wrong. Key information can be found in the `errors.message` field.

## Error Response

When an error occurs, the response will contain an `errors` array with one or more error objects. Each error object will contain the following fields:

- `message`: A human-readable description of the error.
- `locations`: An array of locations within the query that caused the error.
- `path`: An array of field names that were traversed to reach the error.
- `extensions`: An object containing additional information about the error.

If the Open Weather Map API returns an error other than `200` or `404`, the error code and response body will be available in the `errors.extensions.info.response` field.

The `errors.message` will contain the error message returned by the Open Weather Map API for ease of debugging.

Here is an example of an error response:

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
