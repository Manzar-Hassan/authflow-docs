# Contributing Guidelines

## Code of Conduct
We are committed to providing a welcoming and inspiring community for all. Please read and follow our Code of Conduct.

## Getting Started

### Fork and Clone
1. Fork the repository
2. Clone your fork:
   ```bash
   git clone https://github.com/your-username/authflow.git
   ```
3. Add upstream remote:
   ```bash
   git remote add upstream https://github.com/original/authflow.git
   ```

### Development Setup
1. Install dependencies:
   ```bash
   npm install  # Frontend/Package
   pip install -r requirements.txt  # Backend
   ```
2. Create feature branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```

## Coding Standards

### Frontend/Package
- Use TypeScript for new components
- Follow React hooks best practices
- Maintain component modularity
- Write unit tests for new features
- Use proper prop-types documentation

### Backend
- Follow PEP 8 style guide
- Write docstrings for new functions
- Include unit tests
- Use type hints
- Keep functions focused and small

## Pull Request Process

1. Update documentation for new features
2. Add tests for new functionality
3. Ensure all tests pass
4. Update CHANGELOG.md
5. Submit PR with clear description

### PR Title Format
```
feat: Add new authentication method
fix: Resolve CORS issues
docs: Update API documentation
test: Add unit tests for auth flow
```

## Testing

### Frontend/Package
```bash
npm run test
npm run test:coverage
```

### Backend
```bash
python manage.py test
coverage run manage.py test
coverage report
```

## Documentation

- Update relevant documentation
- Include JSDoc comments
- Update API documentation if endpoints change
- Add examples for new features

## Release Process

1. Version bump following semver
2. Update CHANGELOG.md
3. Create release PR
4. Tag release after merge
5. Deploy to production

## Questions?

Open an issue or contact the maintainers:
- Email: maintainer@authflow.com
- Discord: AuthFlow Community Server