# API Response Examples

## Authentication Endpoints

### POST /api/auth/signup/
**Request:**
```json
{
  "username": "johndoe",
  "email": "john@example.com",
  "password": "securePassword123"
}
```

**Success Response (201 Created):**
```json
{
  "id": 1,
  "username": "johndoe",
  "email": "john@example.com",
  "created_at": "2024-02-20T10:00:00Z"
}
```

**Error Response (400 Bad Request):**
```json
{
  "email": ["User with this email already exists."],
  "password": ["Password must be at least 8 characters long."]
}
```

### POST /api/auth/signin/
**Request:**
```json
{
  "email": "john@example.com",
  "password": "securePassword123"
}
```

**Success Response (200 OK):**
```json
{
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9...",
  "refresh_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9...",
  "user": {
    "id": 1,
    "username": "johndoe",
    "email": "john@example.com"
  }
}
```

**Error Response (401 Unauthorized):**
```json
{
  "detail": "Invalid credentials"
}
```

### GET /api/dashboard/
**Headers:**
```
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9...
```

**Success Response (200 OK):**
```json
{
  "user_data": {
    "total_logins": 5,
    "last_login": "2024-02-20T10:00:00Z",
    "settings": {
      "notifications_enabled": true,
      "theme": "dark"
    }
  }
}
```

**Error Response (401 Unauthorized):**
```json
{
  "detail": "Invalid token or token expired"
}
```