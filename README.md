# Authflow Documentation

## Project Overview
Authflow is a comprehensive authentication solution consisting of three main components:
- A React/Next.js authentication package (`@manzar-hassan/authflow`)
- A demo frontend application (`authflow-frontend`)
- A Django-based backend service (`authflow-backend`)

## Quick Links
- [Package Documentation](./PACKAGE.md)
- [Frontend Documentation](./FRONTEND.md)
- [Backend Documentation](./BACKEND.md)
- [API Responses](./API_RESPONSES.md)
- [Deployment Guides](./DEPLOYMENT.md)
- [Troubleshooting](./TROUBLESHOOTING.md)
- [Contributing Guidelines](./CONTRIBUTING.md)
- [Changelog](./CHANGELOG.md)

## Tech Stack

### Package (@manzar-hassan/authflow)
- React >=18.0.0
- TypeScript 5.7.3
- TailwindCSS >=3.4.17
- react-hot-toast >=2.5.2

### Frontend Demo (authflow-frontend)
- Next.js 15.2.0
- React 19.0.0
- TailwindCSS 3.4.17
- TypeScript 5.7.3

### Backend (authflow-backend)
- Django
- Django REST Framework
- SimpleJWT
- Gunicorn (Production)

## Getting Started

### Package Usage
```bash
npm install @manzar-hassan/authflow
```

### Frontend Demo Setup
```bash
cd authflow-frontend
npm install
npm run dev
```

### Backend Setup
```bash
cd authflow-backend
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

## Authentication Flow
1. User registers via `/api/auth/signup/`
2. User logs in via `/api/auth/signin/`
3. JWT tokens are issued
4. Access protected routes using JWT token

## Deployment Options

### Frontend
- Vercel (Recommended)
- Manual/VPS deployment with PM2

### Backend
- Ubuntu/Nginx
- Render
- Heroku

### Package
- Published on npm as `@manzar-hassan/authflow`

## Contributing
Please read our [Contributing Guidelines](./CONTRIBUTING.md) before submitting any changes.

## Support
- Open an issue in the repository
- Email: maintainer@authflow.com
- Discord: AuthFlow Community Server

## License
MIT License - see LICENSE file for details

## Version History
See [CHANGELOG.md](./CHANGELOG.md) for detailed version history and upcoming changes.