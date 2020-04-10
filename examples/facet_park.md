# Get facets for parks
You are able to create a [facet search](https://en.wikipedia.org/wiki/Faceted_search) when you fetching a list of parks or attraction.

## Common
Use following GraphQL query for fetching the id and name of parks (limited to 10 parks) and a facet results for countries:
```graphql
{
  parkCollection(itemsPerPage: 10, facet: [COUNTRY]) {
    facets {
      name,
      terms {
        label(locale: "en"),
        quantity
      }
    }
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
      "facets": [
        {
          "name": "PARK_COUNTRY",
          "terms": [
            {
              "label": "Germany",
              "quantity": 43
            },
            {
              "label": "Spain",
              "quantity": 5
            },
            {
              "label": "Netherlands",
              "quantity": 3
            },
            {
              "label": "Belgium",
              "quantity": 2
            },
            {
              "label": "United Arab Emirates",
              "quantity": 1
            },
            {
              "label": "United Kingdom",
              "quantity": 1
            },
            {
              "label": "Japan",
              "quantity": 1
            },
            {
              "label": "Malaysia",
              "quantity": 1
            },
            {
              "label": "United States",
              "quantity": 1
            }
          ]
        }
      ],
      "parks": [
        {
          "id": "4a1bb550-b890-4144-9711-494a0b4ce6c9",
          "name": "Freizeitpark Lochmühle"
        },
        {
          "id": "6c1a20a0-d9a0-4590-8ce7-3b5c9331df79",
          "name": "Steinwasen Park"
        },
        {
          "id": "06830bb6-8c16-4db1-bf8e-0a408734cc09",
          "name": "Freizeit-Land Geiselwind"
        },
        {
          "id": "480c6af2-b795-4995-a941-f3c234d57ed0",
          "name": "Magic Park Verden"
        },
        {
          "id": "11f4d46a-d14c-40d3-a076-dfe24334e2d4",
          "name": "Wild- und Freizeitpark Klotten/Cochem"
        },
        {
          "id": "8e87a50a-bb38-4cc8-a4e0-af0a9dda68f3",
          "name": "Karls Erlebnis-Dorf Rövershagen"
        },
        {
          "id": "cc8c5891-5be7-4409-8a27-a15ac4586539",
          "name": "Filmpark Babelsberg"
        },
        {
          "id": "682b4268-6a8d-4d50-9b8c-42457e37ec28",
          "name": "Freizeitpark Traumland auf der Bärenhöhle"
        },
        {
          "id": "5323f689-0b9b-42f6-95db-3450d73c246f",
          "name": "Walibi Holland"
        },
        {
          "id": "6736db15-7482-4e43-b46c-1caf866e0db2",
          "name": "Hansa-Park"
        }
      ]
    }
  }
}
```

As you can see, the results contains a facet result besides the park result. Every available country and the amount of matched parks
will be returned. You can combine multiple facets and filters.

Just look up all supported facets at our [Playground](../playground.html).
