---
title: "Update todos - mutation"
metaTitle: "Mutation to update todos | GraphQL React Apollo Typescript Tutorial"
metaDescription: "GraphQL Mutation to update existing personal todos. Try the mutation in GraphiQL, passing the Authorization token to mark a todo as completed"
---

In this part of the tutorial, you will learn how to mark an existing todo as completed by using GraphQL Mutations.

Let's define a graphql query to do a mutation into todos.

```graphql
  mutation toggleTodo ($id: Int!, $isCompleted: Boolean!) {
    update_todos(where: {id: {_eq: $id}}, _set: {is_completed: $isCompleted}) {
      affected_rows
      returning {
        id
        title
        is_completed
      }
    }
  }
```
You will also need to pass in the values for the variables.

[Try this mutation in GraphiQL](https://learn.hasura.io/graphql/graphiql) against the application database to see what the response looks like.

Let's now integrate this graphql mutation into our react app.
