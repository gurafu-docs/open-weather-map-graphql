---
title: Mock Mode
permalink: /open-weather-map/schema/mock-mode/
toc: false
---

We offer a mock mode for the Open Weather Map GraphQL to help you test your application without making calls to the Open Weather Map API.

<!-- We also track mock calls on a separate quota, so you can test your application without affecting your production quota. -->

### Enable Mock Mode

To enable mock mode, you need to include the `x-gurafu-mock-mode` header in your request with the value `true`. The response will return static mock data instead of making a call to the Open Weather Map API.

Additionally, you can set the optional `x-gurafu-mock-record-index` header to specify the index of the mock data to return. This is useful when you want to test different scenarios.

The default value for `x-gurafu-mock-record-index` is `1`. The range is from `1` to `10`, with different varying responses for each index.

**Note:** Only schema and query validation is carried out on mock requests. We do not mock validation checks that the Open Weather Map API would perform.

See the [Errors](/open-weather-map/schema/errors/) section for more information on error responses.

### Example

```
'x-gurafu-mock-mode': 'true'
'x-gurafu-mock-record-index': '3'
```
