# @manzar-hassan/authflow Package Documentation

## Overview
A React/Next.js authentication package that provides pre-built components and utilities for handling authentication flows.

## Installation
```bash
npm install @manzar-hassan/authflow
```

## Requirements
- .npmrc file
- React ^19.0.0
- React DOM ^19.0.0
- Tailwindcss >=3.4.17
- react-hot-toast >=2.5.2

## Components

### Card
A simple card component for displaying content.

```jsx
import { Card } from "@manzar-hassan/authflow";

<Card
  title="Your Title"
  description="Your Description"
/>
```

### SignIn
Pre-built sign-in component with form handling.

```jsx
import { SignIn } from "@manzar-hassan/authflow";

<SignIn />
```

### SignUp
Pre-built sign-up component with form handling.

```jsx
import { SignUp } from "@manzar-hassan/authflow";

<SignUp />
```

### CustomToast
Toast notification component built on react-hot-toast.

```jsx
import { CustomToast } from "@manzar-hassan/authflow";

<CustomToast />
```

## Utilities

### createRouteMatcher
Utility for route matching and navigation.

### useAuth
Custom hook for handling authentication state and operations.