# Get parks by geo location
You can fetch a list of parks within a custom geo location. Just pass the latitude and longitude values into
the `locationFilter` field and define a radius in meters.

Use following GraphQL query for fetching the id and name of parks (near "Phantasialand", 1500 meters):
```graphql
{
  parkCollection(filter: {
    location: {
      latitude: 50.8015827,
      longitude: 6.8743143,
      radius: 1500
    } 
  }) {
    parks {
      id,
      name
    }
  }
}
```

You can test this query at our [Playground](https://oci.coaster.cloud). The JSON response should be something like that:

```json
{
  "data": {
    "parkCollection": {
      "parks": [
        {
          "id": "f7328b4a-3308-4823-b4b6-58fb9a254199",
          "name": "Phantasialand"
        }
      ]
    }
  }
}
```

You can combine multiple filters. Just look up all supported filters at our [Playground](https://oci.coaster.cloud).