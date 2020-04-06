# Get parks by geo location
You can fetch a list of parks within a custom geo location. Just pass the latitude and longitude values into
the `locationFilter` field and define a radius in meters.

Use following GraphQL query for fetching the id and name of parks (near "Düssldorf", 100km):
```graphql
{
  parkCollection(filter: {
    location: {
      latitude: 51.2383712,
      longitude: 6.6742681,
      radius: 100000
    }
  }) {
    parks {
      id,
      name
    }
  }
}
```

You can test this query at our [Playground](../playground.html). The JSON response should be something like that:

```json
{
  "data": {
    "parkCollection": {
      "parks": [
        {
          "id": "10eae83d-314a-48bf-86c1-560c4666bc4a",
          "name": "Alpincenter Bottrop"
        },
        {
          "id": "f70ebd46-2644-4ea6-aa65-c2c69d890537",
          "name": "Schloss Beck"
        },
        {
          "id": "a5fb81f1-cc4e-4a7e-8419-98cc523487e3",
          "name": "Movie Park Germany"
        },
        {
          "id": "f7328b4a-3308-4823-b4b6-58fb9a254199",
          "name": "Phantasialand"
        },
        {
          "id": "1e9d6114-1f82-43f5-9b38-9b3e98efa223",
          "name": "Toverland"
        },
        {
          "id": "dc246574-3aca-4657-ae08-cb74a6a3fde4",
          "name": "Wunderland Kalkar"
        }
      ]
    }
  }
}
```

You can combine multiple filters. Just look up all supported filters at our [Playground](../playground.html).

## Sorting
The result is sorted by nearest park. But you can define a different sorting if needed (e.g. by name):

```graphql
{
  parkCollection(filter: {
    location: {
      latitude: 51.2383712,
      longitude: 6.6742681,
      radius: 100000
    }
  }, sort: NAME_DESC) {
    parks {
      id,
      name
    }
  }
}
```

You can test this query at our [Playground](../playground.html). The JSON response should be something like that:

```json
{
  "data": {
    "parkCollection": {
      "parks": [
        {
          "id": "dc246574-3aca-4657-ae08-cb74a6a3fde4",
          "name": "Wunderland Kalkar"
        },
        {
          "id": "1e9d6114-1f82-43f5-9b38-9b3e98efa223",
          "name": "Toverland"
        },
        {
          "id": "f70ebd46-2644-4ea6-aa65-c2c69d890537",
          "name": "Schloss Beck"
        },
        {
          "id": "f7328b4a-3308-4823-b4b6-58fb9a254199",
          "name": "Phantasialand"
        },
        {
          "id": "a5fb81f1-cc4e-4a7e-8419-98cc523487e3",
          "name": "Movie Park Germany"
        },
        {
          "id": "10eae83d-314a-48bf-86c1-560c4666bc4a",
          "name": "Alpincenter Bottrop"
        }
      ]
    }
  }
}
```
