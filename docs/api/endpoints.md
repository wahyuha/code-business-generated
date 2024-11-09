# API Endpoints

## Authentication

### POST /auth/login
Authenticates a user and returns a session token.

#### Request
```json
{
  "username": "string",
  "password": "string"
}
```

#### Response
```json
{
  "token": "string",
  "user": {
    "id": "integer",
    "username": "string",
    "email": "string",
    "roles": ["string"]
  }
}
```

### POST /auth/logout
Invalidates the current session token.

## Users

### GET /users
Returns a list of users (requires admin privileges).

#### Response
```json
{
  "users": [
    {
      "id": "integer",
      "username": "string",
      "email": "string",
      "status": "string",
      "roles": ["string"]
    }
  ],
  "total": "integer",
  "page": "integer"
}
```

### POST /users
Creates a new user account.

#### Request
```json
{
  "username": "string",
  "email": "string",
  "password": "string"
}
```

### GET /users/{id}
Retrieves details for a specific user.

#### Response
```json
{
  "id": "integer",
  "username": "string",
  "email": "string",
  "status": "string",
  "roles": ["string"],
  "created_at": "datetime",
  "updated_at": "datetime"
}
```

## Roles

### GET /roles
Returns a list of available roles.

#### Response
```json
{
  "roles": [
    {
      "id": "integer",
      "name": "string",
      "description": "string",
      "permissions": ["string"]
    }
  ]
}
```

### POST /roles
Creates a new role (requires admin privileges).

#### Request
```json
{
  "name": "string",
  "description": "string",
  "permissions": ["string"]
}
```

## Permissions

### GET /permissions
Returns a list of all system permissions.

#### Response
```json
{
  "permissions": [
    {
      "id": "integer",
      "name": "string",
      "description": "string"
    }
  ]
}
```