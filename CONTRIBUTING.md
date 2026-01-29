# Contributing Guidelines — NovaCommerce

This project follows a professional Git workflow.

---

## 1. Branch Strategy

- `main` — stable production-ready code
- `develop` — integration branch
- `feature/*` — new features
- `fix/*` — bug fixes
- `docs/*` — documentation updates

---

## 2. Commit Convention

Format:
type(scope): message

Examples:

- `feat(auth): add /me endpoint`
- `docs(roles): update admin permissions`
- `fix(stock): correct stock adjustment logic`

Allowed types:

- feat
- fix
- docs
- refactor
- test
- chore

---

## 3. Pull Requests

Each PR must include:

- clear description
- linked issue (if applicable)
- tests passing
- documentation updated
- no console logs or unused code

---

## 4. Code Style

- Java: standard Spring Boot conventions
- Angular: ESLint + Angular style guide
- Use meaningful names and modular structure
