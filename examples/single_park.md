# Get single park (e.g. "Phantasialand")
You can fetch every park by an **Universally Unique ID** (UUID). Every park has an UUID. You can look up the UUID at
[coaster.cloud](https://coaster.cloud). This example use "Phantasialand" and the UUID of "Phantasialand" is `f7328b4a-3308-4823-b4b6-58fb9a254199`.

## Common
We can use following GraphQL query for fetching the name, city / country and the type of "Phantasialand":
```graphql
{
  park(id: "f7328b4a-3308-4823-b4b6-58fb9a254199") {
    name,
    types {
      label(locale: "en")
    },
    address {
      city,
      country {
        label(locale: "en")
      }
    }
  }
}
```

You can test this query at our [Playground](../playground.html). The JSON response should be something like that:

```json
{
  "data": {
    "park": {
      "name": "Phantasialand",
      "types": [
        {
          "label": "Themepark"
        }
      ],
      "address": {
        "city": "Brühl",
        "country": {
          "label": "Germany"
        }
      }
    }
  }
}
```

There are a lot of fields you can fetch for a park (attractions, attributes, history, full address, images, ...). Just look up the documentation
at our [Playground](../playground.html).
