# Troubleshooting Guide

## Authentication Issues

### Login Failures
**Problem:** Unable to log in with correct credentials
**Solution:**
1. Check server logs for authentication debug messages
2. Verify user exists in database
3. Ensure password was properly set during registration
4. Clear browser storage and try again

### Registration Issues
**Problem:** User registration not working
**Solution:**
1. Verify all required fields are provided
2. Check for existing users with same username
3. Ensure password meets complexity requirements
4. Check server logs for detailed error messages

### Debug Logging
To diagnose authentication issues, check server logs for:
- Login attempt messages
- User existence verification
- Authentication results
- Detailed error messages

### Common Error Messages
- "Invalid credentials": Username/password mismatch
- "User does not exist": Username not found
- "Both username and password are required": Missing fields
- "An unexpected error occurred": Server-side issue (check logs)

## Frontend Issues

### CORS Errors
**Problem:** API requests failing due to CORS policy
**Solution:**
1. Check backend CORS configuration
2. Verify API URL in frontend environment
3. Ensure proper headers are set:
   ```javascript
   headers: {
     'Content-Type': 'application/json',
     'Authorization': `Bearer ${token}`
   }
   ```

### Authentication Issues
**Problem:** Token persistence issues after refresh
**Solution:**
1. Check localStorage/sessionStorage implementation
2. Verify token refresh logic
3. Clear browser storage and re-login

### Build Errors
**Problem:** Failed builds with package dependencies
**Solution:**
1. Clear node_modules and package-lock.json
2. Run `npm install` fresh
3. Check package versions compatibility

## Backend Issues

### Database Migrations
**Problem:** Migration conflicts
**Solution:**
1. Reset migrations:
   ```bash
   python manage.py migrate --fake
   python manage.py makemigrations
   python manage.py migrate
   ```

### JWT Token Issues
**Problem:** Token validation failing
**Solution:**
1. Check token expiration settings
2. Verify SECRET_KEY configuration
3. Clear token blacklist

### Server 500 Errors
**Problem:** Unexpected server errors
**Solution:**
1. Check server logs
2. Verify database connections
3. Monitor server resources

## Package Issues

### Installation Failures
**Problem:** Package fails to install
**Solution:**
1. Check npm version
2. Verify peer dependencies
3. Clear npm cache:
   ```bash
   npm cache clean --force
   ```

### Component Styling Issues
**Problem:** Tailwind styles not applying
**Solution:**
1. Check tailwind.config.js content paths
2. Rebuild CSS with:
   ```bash
   npm run build:css
   ```
3. Verify style imports
