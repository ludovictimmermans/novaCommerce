# NovaCommerce — Security Model

NovaCommerce uses a secure, role-based access control system with a minimal JWT strategy.

---

## 1. JWT Strategy

The JWT contains only:

- `sub` (user ID)
- `email`
- `iat`
- `exp`

No roles are stored in the token.

---

## 2. Role Retrieval

Roles are retrieved via:
GET/api/auth/me

This ensures:

- role changes take effect immediately
- no need to regenerate tokens
- reduced attack surface

---

## 3. Backend Authorization

Spring Security with:

- `@PreAuthorize("hasRole('ADMIN')")`
- `@PreAuthorize("hasAnyRole('MANAGER','ADMIN')")`

Sensitive actions (refunds, deletion, stock decrease) are restricted to ADMIN.

---

## 4. Frontend Authorization

Angular guards enforce:

- route protection
- role-based navigation
- hiding restricted UI elements

---

## 5. Sensitive Actions

Restricted to ADMIN:

- delete product/category/brand
- decrease stock
- refund orders
- manage user roles
- disable accounts

---

## 6. Audit Logging (planned)

Critical actions will be logged:

- refunds
- deletions
- role changes
- stock decreases
