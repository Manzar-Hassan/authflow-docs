# Changelog

## [Unreleased]

### Fixed
- Authentication issues in backend:
  - Removed redundant password hashing in user registration
  - Added proper error handling and debug logging in login flow
  - Fixed password verification process

### Changed
- Updated user registration flow to use Django's `create_user` directly
- Enhanced login endpoint with better error messages and logging
- Improved authentication debugging capabilities

### Added
- Debug logging in authentication process
- User existence verification before authentication attempt
- More detailed error responses in login flow