# Get single attraction (e.g. "Taron")
You can fetch every attraction by an **Universally Unique ID** (UUID). Every attraction has an UUID. You can look up the UUID at
[coaster.cloud](https://coaster.cloud). This example use "Taron" and the UUID of "Taron" is `81d663fc-ef37-40fe-b1c7-dc768a5a57f8`.

## Common
We can use following GraphQL query for fetching the name and attributes of "Taron":
```graphql
{
  attraction(id: "81d663fc-ef37-40fe-b1c7-dc768a5a57f8") {
    name,
    attributes {
      label(locale: "en"),
      value
      text(locale: "en"),
    }
  }
}
```

You can test this query at our [Playground](../playground.html). The JSON response should be something like that:

```json
{
  "data": {
    "attraction": {
      "name": "Taron",
      "attributes": [
        {
          "label": "Section",
          "value": [
            "Mystery"
          ],
          "text": "Mystery"
        },
        {
          "label": "FastPass",
          "value": false,
          "text": "No"
        },
        {
          "label": "Single Rider",
          "value": true,
          "text": "Yes"
        },
        {
          "label": "Has pre-show",
          "value": false,
          "text": "No"
        },
        {
          "label": "Restrict season",
          "value": "always",
          "text": "Independent"
        },
        {
          "label": "Weather independent",
          "value": true,
          "text": "Yes"
        },
        {
          "label": "Area type",
          "value": "outdoor",
          "text": "Outdoor"
        },
        {
          "label": "Length",
          "value": 132000,
          "text": "1.320,00 m"
        },
        {
          "label": "Height",
          "value": 3000,
          "text": "30,00 m"
        },
        {
          "label": "Top speed",
          "value": 117,
          "text": "117 km/h"
        },
        {
          "label": "Capacity",
          "value": 1280,
          "text": "1.280 p/h"
        },
        {
          "label": "Number of trains",
          "value": 4,
          "text": "4"
        },
        {
          "label": "Persons per train",
          "value": 16,
          "text": "16"
        },
        {
          "label": "Ride time",
          "value": 101,
          "text": "00:01:41"
        },
        {
          "label": "Seat type",
          "value": "pelvis",
          "text": "Pelvis"
        },
        {
          "label": "Min. outside temperature",
          "value": -1000,
          "text": "-10,0 °C"
        }
      ]
    }
  }
}
```

There are a lot of fields you can fetch for an attraction (safety regulation, elements, history, images, ...). Just look up the documentation
at our [Playground](../playground.html).
