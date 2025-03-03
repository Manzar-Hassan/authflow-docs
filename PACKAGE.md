# @manzar-hassan/authflow Package Documentation

## Overview
A React/Next.js authentication package that provides pre-built components and utilities for handling authentication flows.

## Installation
```bash
npm install @manzar-hassan/authflow
```

## Requirements
- React >=18.0.0
- React DOM >=18.0.0
- TailwindCSS >=3.4.17
- react-hot-toast >=2.5.2

## Components

### Card
Basic card component for content display.
```tsx
import { Card } from "@manzar-hassan/authflow";

<Card
  title="Your Title"
  description="Your Description"
  className="custom-class" // Optional
/>
```

### SignIn/SignUp
Authentication form components with built-in state management.
```tsx
import { SignIn, SignUp } from "@manzar-hassan/authflow";

<SignIn
  onSuccess={(response) => {}}
  onError={(error) => {}}
  className="custom-class"
/>

<SignUp
  onSuccess={(response) => {}}
  onError={(error) => {}}
  className="custom-class"
/>
```

### CustomToast
Toast notification wrapper for react-hot-toast.
```tsx
import { CustomToast } from "@manzar-hassan/authflow";

<CustomToast message="Operation successful" type="success" />
```

## Hooks

### useAuth
Authentication state management hook.
```tsx
const { signIn, signUp, signOut, isLoading, isAuthenticated } = useAuth({
  baseUrl: "YOUR_API_URL",
  navigation: {
    navigate: (path) => {}
  }
});
```

## Build Configuration
The package uses tsup for building, supporting both ESM and CommonJS formats:
- Entry point: src/index.tsx
- Output: dist/index.mjs (ESM), dist/index.js (CJS)
- TypeScript definitions included
- External dependencies: react, react-dom
