# Authflow Frontend Documentation

## Overview
Next.js frontend application demonstrating @manzar-hassan/authflow package implementation.

## Tech Stack
- Next.js 15.2.0
- React 19.0.0
- TailwindCSS 3.4.17
- TypeScript 5.7.3

## Project Structure
```
authflow-frontend/
├── app/                # Next.js app directory
│   ├── page.js        # Home page
│   ├── signin/        # Sign-in route
│   ├── signup/        # Sign-up route
│   └── layout.js      # Root layout
├── public/            # Static assets
└── tailwind.config.js # Tailwind configuration
```

## Development
1. Install dependencies:
```bash
npm install
```

2. Run development server:
```bash
npm run dev
```

## Deployment
Supports multiple deployment options:

### Vercel (Recommended)
1. Push to GitHub
2. Connect to Vercel
3. Configure build settings:
   - Build Command: npm run build
   - Output Directory: .next
   - Install Command: npm install

### Manual/VPS
1. Build: `npm run build`
2. Install PM2: `npm install -g pm2`
3. Start: `pm2 start npm --name "authflow-frontend" -- start`
