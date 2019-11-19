# Get list of parks
You can fetch a list of parks. Normally you are searching for a specific park or filtering. 

## Common
Use following GraphQL query for fetching the id and name of parks (limited to 10 parks):
```graphql
{
  parkCollection(itemsPerPage: 10) {
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

There are a lot of fields you can fetch for a park (attributes, history, full address, images, ...). Just look up the documentation
at our [Playground](https://oci.coaster.cloud).

## Searching
Use following GraphQL query for fetching the id and name of parks which begins with "efte" (limited to 10 parks):
```graphql
{
  parkCollection(itemsPerPage: 10, filter: {search: "efte"}) {
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
          "id": "49f00560-9b8d-4c11-a3ed-f548192ef5d9",
          "name": "Efteling"
        }
      ]
    }
  }
}
```

## Filter
Use following GraphQL query for fetching the id and name of parks in spain (limited to 10 parks):
```graphql
{
  parkCollection(itemsPerPage: 10, filter: {country: "ES"}) {
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
          "id": "06b919c3-1b6a-4793-90ac-4fde511747b2",
          "name": "PortAventura World"
        },
        {
          "id": "1ab2dae0-108f-4b3b-a25c-ccde4daed052",
          "name": "Isla Mágica"
        },
        {
          "id": "0c0488bb-cc04-4399-9a69-76d5f94e1468",
          "name": "Parque de Atracciones Madrid"
        },
        {
          "id": "ec71e8a2-2c69-42bc-8a7d-88b5dfe9a1d1",
          "name": "Parque Warner Madrid"
        },
        {
          "id": "536bf772-5daa-48f6-80b2-b720da102ebc",
          "name": "Ferrari Land"
        }
      ]
    }
  }
}
```

You can combine multiple filters. Just look up all supported filters at our [Playground](https://oci.coaster.cloud).