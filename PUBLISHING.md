# Publishing Instructions

## Publishing npm Packages

### Client Library

```bash
cd packages/client
npm run build
npm publish --access public
```

### Express Middleware

```bash
cd packages/server-express
npm run build
npm publish --access public
```

### Fastify Plugin

```bash
cd packages/server-fastify
npm run build
npm publish --access public
```

## Publishing Python Package

### FastAPI Middleware

```bash
cd packages/server-fastapi
python -m build
python -m twine upload dist/*
```

## Versioning

Use [Semantic Versioning](https://semver.org/):
- MAJOR version for incompatible API changes
- MINOR version for new functionality with backward compatibility
- PATCH version for bug fixes

## Pre-Publishing Checklist

1. Ensure all tests pass
2. Verify examples work correctly
3. Update version in package.json/pyproject.toml
4. Update CHANGELOG.md
5. Create git tag: `git tag v1.0.0`

