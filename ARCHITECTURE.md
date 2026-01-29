# NovaCommerce — Architecture

NovaCommerce is a modular e-commerce platform built with a clean separation between backend and frontend, role-based access control, and enterprise-grade structure.

---

## 1. Global Architecture

The project is divided into two main modules:

- **backend/** — Spring Boot 3 (REST API, security, business logic)
- **frontend/** — Angular (UI, guards, role-based navigation)

Communication is done via JSON REST endpoints.

---

## 2. Backend Modules (planned)

- **auth** — JWT minimal, login, /me endpoint
- **users** — user management, roles, permissions
- **products** — products, categories, brands
- **stock** — stock movements, manager/admin rules
- **orders** — order creation, status, history
- **returns** — support role, return workflow
- **admin** — sensitive operations (refunds, deletion)

---

## 3. Frontend Modules (planned)

- **auth** — login, guards, token handling
- **shared** — components, interceptors, services
- **catalog** — product browsing
- **cart** — shopping cart
- **orders** — order history, details
- **admin** — user management, refunds
- **manager** — product & stock management
- **support** — return management

---

## 4. Roles and Permissions

See `/docs/roles-and-permissions.md`.

---

## 5. Authentication Flow

- JWT contains only: `sub`, `email`, `iat`, `exp`
- After login, frontend calls `/me` to retrieve roles
- Backend enforces permissions using `@PreAuthorize`
- Frontend enforces navigation using guards

---

## 6. Database (planned)

PostgreSQL with the following core tables:

- users
- roles
- user_roles
- products
- categories
- brands
- orders
- order_items
- returns
- stock_movements

---

## 7. Roadmap

See `/docs/roadmap.md`.
