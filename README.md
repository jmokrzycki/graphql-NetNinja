### BUILD:

npm install

### RUN:

nodemon

### EXAMPLE QUERIES:

```
query ExampleQuery {
  games {
    title,
    platform
  }
}
```

```
query ExampleQuery($id: ID!) {
  author(id: $id) {
    name
    reviews {
      rating
      content
    }
  }
}

{
    "id": "2"
}
```

```
query ExampleQuery($id: ID!) {
  review(id: $id) {
    rating,
    game {
      reviews {
        rating
      }
    }
  }
}

{
    "id": "2"
}
```

```
mutation DeleteMutation($id: ID!) {
    deleteGame(id: $id) {
      id,
      title,
      platform
    }
}

{
    "id": "2"
}
```

```
mutation AddMutation($game: AddGameInput!) {
    addGame(game: $game) {
      id,
      title,
      platform
    }
}

{
    "game": {
      "title": "new game 2",
      "platform": ["xbox", "pc"]
    }
}
```

```
mutation EditMutation($edits: EditGameInput!, $id: ID!) {
    updateGame(edits: $edits, id: $id) {
      title,
      platform
    }
}

{
    "edits": {
      "title": "updated game"
    },
    "id": "3"
}
```
