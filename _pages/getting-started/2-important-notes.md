---
title: Important Notes
permalink: /open-weather-map/important-notes/
---

Some key information to keep in mind when using the Open Weather Map GraphQL API.

### Types

If using TypeScript or JSDoc, you can install the types from npm: [open-weather-map-graphql-types](https://www.npmjs.com/package/@gurafu/open-weather-map-types) - `npm install --save-dev @gurafu/open-weather-map-types`.

### Rate Limits

The GraphQL API is a wrapper around the Open Weather Map REST API. As such, the API is subject to the same rate limits and restrictions as the REST API. Please refer to the Open Weather Map documentation for more information.

It is recommended you create a separate API key for the GraphQL API to track usage and avoid rate limits.

### Data Accuracy

This GraphQL API is a passthrough to the Open Weather Map REST API. All data is fetched in real-time from the Open Weather Map servers. It does not store or cache any data outside of the request/response cycle.
