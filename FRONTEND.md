# Authflow Frontend Documentation

## Overview
Next.js frontend application showcasing the implementation of @manzar-hassan/authflow package.

## Tech Stack
- Next.js 15.2.0
- React 19.0.0
- TailwindCSS 3.4.17
- TypeScript 5.7.3

## Getting Started

1. Install dependencies:
```bash
npm install
```

2. Run development server:
```bash
npm run dev
```

The application will be available at http://localhost:3000

## Project Structure
```
authflow-frontend/
├── app/
│   ├── page.js          # Home page
│   ├── signin/          # Sign-in route
│   ├── signup/          # Sign-up route
│   └── layout.js        # Root layout
├── public/              # Static assets
└── tailwind.config.mjs  # Tailwind configuration
```

## Routes
- `/` - Home page with demo card
- `/signin` - Authentication sign-in page
- `/signup` - User registration page

## Configuration
- TailwindCSS is configured to scan both local components and @manzar-hassan/authflow components
- Uses Geist font family for typography
- Includes custom toast notifications setup