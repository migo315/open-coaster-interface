# Get waiting times (e.g. "Efteling")
You can fetch waiting times for some parks by an **Universally Unique ID** (UUID). Every park has an UUID. You can look up the 
UUID at [coaster.cloud](https://coaster.cloud). This example use "Efteling" and the UUID of "Efteling" is `49f00560-9b8d-4c11-a3ed-f548192ef5d9`.

## Common
We can use following GraphQL query for fetching the name, city / country and the type of "Efteling":
```graphql
{
  park(id: "49f00560-9b8d-4c11-a3ed-f548192ef5d9") {
    name,
    waitingTimes {
      name,
      minutes
    }
  }
}
```

You can test this query at our [Playground](https://oci.coaster.cloud). The JSON response should be something like that:
```json
{
  "data": {
    "park": {
      "name": "Efteling",
      "waitingTimes": [
        {
          "name": "Anton Pieck Plein",
          "minutes": 0
        },
        {
          "name": "Avonturen Doolhof",
          "minutes": 0
        },
        {
          "name": "Baron 1898",
          "minutes": 60
        },
        {
          "name": "Baron 1898 (FastPass)",
          "minutes": -2
        },
        {
          "name": "Bob",
          "minutes": -1
        },
        {
          "name": "Bob (FastPass)",
          "minutes": -2
        },
        {
          "name": "Bob (Single Rider)",
          "minutes": -1
        },
        {
          "name": "Carnaval Festival",
          "minutes": 10
        },
        {
          "name": "De Oude Tufferbaan",
          "minutes": -1
        },
        {
          "name": "De Vliegende Hollander",
          "minutes": 20
        },
        {
          "name": "De Vliegende Hollander (Single Rider)",
          "minutes": -2
        },
        {
          "name": "Diorama",
          "minutes": 0
        },
        {
          "name": "Droomvlucht",
          "minutes": -1
        },
        {
          "name": "Droomvlucht (Virtual Reality)",
          "minutes": 10
        },
        {
          "name": "Efteling Museum",
          "minutes": -1
        },
        {
          "name": "Fata Morgana",
          "minutes": 5
        },
        {
          "name": "Gondoletta",
          "minutes": -1
        },
        {
          "name": "Halve Maen",
          "minutes": -1
        },
        {
          "name": "Joris en de Draak",
          "minutes": 20
        },
        {
          "name": "Joris en de Draak (FastPass)",
          "minutes": -2
        },
        {
          "name": "Kinderspoor",
          "minutes": -1
        },
        {
          "name": "Kindervreugd",
          "minutes": 0
        },
        {
          "name": "Kleuterhof",
          "minutes": 0
        },
        {
          "name": "Monorail",
          "minutes": -1
        },
        {
          "name": "Monsieur Cannibale",
          "minutes": -1
        },
        {
          "name": "Pagode",
          "minutes": -1
        },
        {
          "name": "PandaDroom",
          "minutes": -1
        },
        {
          "name": "Pirana",
          "minutes": -1
        },
        {
          "name": "Polka Marina",
          "minutes": -1
        },
        {
          "name": "Python",
          "minutes": 10
        },
        {
          "name": "Python (FastPass)",
          "minutes": -2
        },
        {
          "name": "Python (Single Rider)",
          "minutes": -2
        },
        {
          "name": "Spookslot",
          "minutes": -1
        },
        {
          "name": "Sprookjesbos",
          "minutes": -1
        },
        {
          "name": "Stoomcarrousel",
          "minutes": -1
        },
        {
          "name": "Stoomtreinm (Mararijk)",
          "minutes": -1
        },
        {
          "name": "Stoomtreinm (Ruigrijk)",
          "minutes": -1
        },
        {
          "name": "Symbolica: Paleis der Fantasie",
          "minutes": 50
        },
        {
          "name": "Symbolica: Paleis der Fantasie (FastPass)",
          "minutes": -2
        },
        {
          "name": "Symbolica: Paleis der Fantasie (Single Rider)",
          "minutes": -1
        },
        {
          "name": "Villa Volta",
          "minutes": -1
        },
        {
          "name": "Vogel Rok",
          "minutes": -1
        },
        {
          "name": "Volk van Laaf",
          "minutes": -1
        }
      ]
    }
  }
}
```
