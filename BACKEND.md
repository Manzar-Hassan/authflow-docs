# Authflow Backend Documentation

## Overview
Django-based authentication API with JWT support.

## Tech Stack
- Django
- Django REST Framework
- SimpleJWT
- Gunicorn (Production)

## API Endpoints

### Authentication
- `POST /api/auth/signup/` - User registration
  ```json
  {
    "username": "string",
    "email": "string",
    "password": "string"
  }
  ```
- `POST /api/auth/signin/` - User login
- `POST /api/token/` - JWT token generation
- `POST /api/token/refresh/` - Token refresh

### Protected Routes
- `GET /api/dashboard/` - Protected dashboard data

## Deployment Options

### Ubuntu/Nginx
Full setup process in DEPLOYMENT.md

### Render
Using render.yaml configuration:
- Region: Ohio
- Python version: 3.9.0
- Build: pip install -r requirements.txt
- Start: gunicorn app.wsgi:application

### Heroku
Using Procfile configuration:
- web: gunicorn app.wsgi:application

## Security Considerations
- Passwords are properly hashed using Django's password hasher
- No plain text passwords in responses
- JWT token-based authentication
- Proper error handling to prevent information leakage

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
