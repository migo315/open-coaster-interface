# Get waiting times (e.g. "Efteling")
You can fetch waiting times for some parks by an **Universally Unique ID** (UUID). Every park has an UUID. You can look up the 
UUID at [coaster.cloud](https://coaster.cloud). This example use "Efteling" and the UUID of "Efteling" is `49f00560-9b8d-4c11-a3ed-f548192ef5d9`.

## Common
We can use following GraphQL query for fetching the name and waiting times of "Efteling" (sorted by minutes desc):
```graphql
{
  park(id: "49f00560-9b8d-4c11-a3ed-f548192ef5d9") {
    name,
    waitingTimes(sort: MINUTES_DESC) {
      name,
      minutes
    }
  }
}
```

You can test this query at our [Playground](../playground.html). The JSON response should be something like that:
```json
{
  "data": {
    "park": {
      "name": "Efteling",
      "waitingTimes": [
        {
          "name": "Baron 1898",
          "minutes": 30
        },
        {
          "name": "Symbolica: Paleis der Fantasie",
          "minutes": 25
        },
        {
          "name": "De Vliegende Hollander",
          "minutes": 15
        },
        {
          "name": "Droomvlucht",
          "minutes": 15
        },
        {
          "name": "Spookslot",
          "minutes": 10
        },
        {
          "name": "Joris en de Draak",
          "minutes": 10
        },
        {
          "name": "Fata Morgana",
          "minutes": 10
        },
        {
          "name": "Monsieur Cannibale",
          "minutes": 5
        },
        {
          "name": "Carnaval Festival",
          "minutes": 5
        },
        {
          "name": "Pagode",
          "minutes": 5
        },
        {
          "name": "Vogel Rok",
          "minutes": 5
        },
        {
          "name": "Villa Volta",
          "minutes": 5
        },
        {
          "name": "Sprookjesbos",
          "minutes": 0
        },
        {
          "name": "Kleuterhof",
          "minutes": 0
        },
        {
          "name": "Stoomcarrousel",
          "minutes": 0
        },
        {
          "name": "Anton Pieck Plein",
          "minutes": 0
        },
        {
          "name": "Efteling Museum",
          "minutes": 0
        },
        {
          "name": "Halve Maen",
          "minutes": 0
        },
        {
          "name": "Polka Marina",
          "minutes": 0
        },
        {
          "name": "De Oude Tufferbaan",
          "minutes": 0
        },
        {
          "name": "Droomvlucht (Virtual Reality)",
          "minutes": 0
        },
        {
          "name": "Diorama",
          "minutes": 0
        },
        {
          "name": "Python",
          "minutes": 0
        },
        {
          "name": "Kindervreugd",
          "minutes": 0
        },
        {
          "name": "Stoomtreinm (Mararijk)",
          "minutes": 0
        },
        {
          "name": "Pirana",
          "minutes": 0
        },
        {
          "name": "Volk van Laaf",
          "minutes": 0
        },
        {
          "name": "Monorail",
          "minutes": 0
        },
        {
          "name": "Avonturen Doolhof",
          "minutes": 0
        },
        {
          "name": "PandaDroom",
          "minutes": -1
        },
        {
          "name": "Bob",
          "minutes": -1
        },
        {
          "name": "Bob (Single Rider)",
          "minutes": -1
        },
        {
          "name": "Stoomtreinm (Ruigrijk)",
          "minutes": -1
        },
        {
          "name": "Symbolica: Paleis der Fantasie (Single Rider)",
          "minutes": -1
        },
        {
          "name": "Gondoletta",
          "minutes": -1
        },
        {
          "name": "Kinderspoor",
          "minutes": -1
        },
        {
          "name": "Bob (FastPass)",
          "minutes": -2
        },
        {
          "name": "Symbolica: Paleis der Fantasie (FastPass)",
          "minutes": -2
        },
        {
          "name": "Baron 1898 (FastPass)",
          "minutes": -2
        },
        {
          "name": "Joris en de Draak (FastPass)",
          "minutes": -2
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
          "name": "De Vliegende Hollander (Single Rider)",
          "minutes": -2
        }
      ]
    }
  }
}
```

`-1` indicates that the attraction is closed and `-2` if we don't have any current data for that attraction.
