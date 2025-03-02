# Authflow Backend Documentation

## Overview
Django-based backend API providing authentication endpoints and user management.

## Tech Stack
- Django
- Django REST Framework
- SimpleJWT for JWT authentication

## API Endpoints

### Authentication
- `POST /api/auth/signup/` - Register new user
  - Now uses Django's built-in password hashing
  - Improved error handling and validation
- `POST /api/auth/signin/` - User login
  - Enhanced error messages
  - Added debug logging
  - Improved user verification
- `POST /api/token/` - Obtain JWT tokens
- `POST /api/token/refresh/` - Refresh JWT token

### Authentication Flow
1. User Registration (`/api/auth/signup/`):
   - Validates username and password
   - Creates user with properly hashed password using `create_user`
   - Returns success response with user details

2. User Login (`/api/auth/signin/`):
   - Verifies user existence
   - Authenticates credentials
   - Issues JWT tokens upon success
   - Provides detailed error messages on failure

### Error Handling
- Non-existent user: Returns 401 with specific message
- Invalid credentials: Returns 401 with authentication failure message
- Missing fields: Returns 400 with required fields message
- Server errors: Returns 500 with error details (in debug mode)

### Debugging
Added logging for authentication process:
- Login attempts
- User existence checks
- Authentication results
- Error details

## Security Considerations
- Passwords are properly hashed using Django's password hasher
- No plain text passwords in responses
- JWT token-based authentication
- Proper error handling to prevent information leakage

### Protected Routes
- `GET /api/dashboard/` - Protected dashboard data (requires authentication)

## Setup

1. Create virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run migrations:
```bash
python manage.py migrate
```

4. Start development server:
```bash
python manage.py runserver
```

## Authentication Flow
1. User registers via `/api/auth/signup/`
2. User logs in via `/api/auth/signin/`
3. JWT tokens are issued
4. Access protected routes using JWT token in Authorization header

## Models
- Uses Django's default User model
- Custom serializers for registration and authentication

## Security
- JWT-based authentication
- Token blacklisting supported
- CORS configuration included
