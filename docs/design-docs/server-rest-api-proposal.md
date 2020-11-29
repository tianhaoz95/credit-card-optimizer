# Server REST API Proposal

## Objective

Propose a set of REST API that the server should support.

## Design

### User

#### Create a user profile

```json
{
    "token": "The authentication token",
    "payload": "[User Object]"
}
```

#### Update a user profile

```json
{
    "targetId": "The target user ID to be updated",
    "token": "The authentication token",
    "payload": "[User Object]"
}
```

#### Remove a user

```json
{
    "targetId": "The target user ID to be deleted",
    "token": "The authentication token"
}
```

### Store

#### Create a store

```json
{
    "type": "private|public",
    "id": "The store ID",
    "displayName": "The store name"
}
```

### Category

### Promotion

### Credit Card
