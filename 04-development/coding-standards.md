# Coding Standards

> Development Guidelines: Code conventions, patterns, and best practices

---

## Metadata

```yaml
project: "[PROJECT_NAME]"
version: "1.0"
last_updated: "YYYY-MM-DD"
author: "[TECH_LEAD_NAME]"
status: "Draft"
```

---

## 1. Overview

### 1.1 Purpose

This document defines coding standards and conventions for [PROJECT_NAME]. Consistent code style improves readability, maintainability, and team collaboration.

### 1.2 Scope

| Applies To | Description |
|------------|-------------|
| Languages | TypeScript, JavaScript, CSS/SCSS |
| Frameworks | [Framework names] |
| Repositories | `[project]-code`, `[project]-api` |

### 1.3 Enforcement

| Method | Tool | When |
|--------|------|------|
| Linting | ESLint | Pre-commit, CI |
| Formatting | Prettier | On save, Pre-commit |
| Type checking | TypeScript | Pre-commit, CI |
| Code review | GitHub PR | Before merge |

---

## 2. General Principles

### 2.1 Core Values

| Principle | Description |
|-----------|-------------|
| **Clarity** | Code should be self-documenting |
| **Consistency** | Follow established patterns |
| **Simplicity** | Prefer simple solutions over clever ones |
| **Testability** | Write code that is easy to test |

### 2.2 Code Smells to Avoid

- [ ] Functions longer than 30 lines
- [ ] Files longer than 300 lines
- [ ] More than 3 levels of nesting
- [ ] Magic numbers without constants
- [ ] Commented-out code
- [ ] Duplicate code blocks

---

## 3. Naming Conventions

### 3.1 General Rules

| Type | Convention | Example |
|------|------------|---------|
| Variables | camelCase | `userName`, `isLoading` |
| Constants | SCREAMING_SNAKE_CASE | `MAX_RETRIES`, `API_URL` |
| Functions | camelCase (verb prefix) | `getUserById`, `calculateTotal` |
| Classes | PascalCase | `UserService`, `PaymentGateway` |
| Interfaces | PascalCase (I-prefix optional) | `User`, `IUserRepository` |
| Types | PascalCase | `UserRole`, `ApiResponse` |
| Enums | PascalCase | `OrderStatus`, `PaymentMethod` |
| Files (components) | PascalCase | `UserProfile.tsx` |
| Files (utilities) | kebab-case | `date-utils.ts` |
| Folders | kebab-case | `user-management/` |

### 3.2 Boolean Naming

```typescript
// Good - clear intent
const isLoading = true;
const hasPermission = false;
const canEdit = true;
const shouldRefresh = false;

// Bad - unclear
const loading = true;
const permission = false;
const edit = true;
```

### 3.3 Function Naming

| Action | Prefix | Example |
|--------|--------|---------|
| Get data | `get`, `fetch` | `getUser()`, `fetchOrders()` |
| Create | `create`, `add` | `createOrder()`, `addItem()` |
| Update | `update`, `set` | `updateUser()`, `setStatus()` |
| Delete | `delete`, `remove` | `deleteUser()`, `removeItem()` |
| Check | `is`, `has`, `can` | `isValid()`, `hasAccess()` |
| Convert | `to`, `from` | `toJSON()`, `fromDTO()` |
| Handle events | `handle`, `on` | `handleClick()`, `onSubmit()` |

---

## 4. TypeScript Standards

### 4.1 Type Definitions

```typescript
// Good - explicit types
interface User {
  id: string;
  email: string;
  role: UserRole;
  createdAt: Date;
}

type UserRole = 'admin' | 'user' | 'guest';

// Bad - implicit any
const user: any = { ... };
```

### 4.2 Type Preferences

| Use | Instead Of | Reason |
|-----|------------|--------|
| `interface` | `type` (for objects) | Extendable, better errors |
| `type` | `interface` (for unions) | More flexible |
| `unknown` | `any` | Type-safe |
| `readonly` | mutable | Prevent accidental mutation |

### 4.3 Null Handling

```typescript
// Good - explicit null checks
function getUser(id: string): User | null {
  const user = users.find(u => u.id === id);
  return user ?? null;
}

// Good - optional chaining
const userName = user?.profile?.name ?? 'Unknown';

// Bad - truthy checks for non-boolean
if (userName) { ... }  // '' is falsy but valid
```

---

## 5. React/Component Standards

### 5.1 Component Structure

```typescript
// Recommended order within component file
// 1. Imports (external, then internal)
// 2. Types/Interfaces
// 3. Constants
// 4. Component definition
// 5. Styles (if CSS-in-JS)

import { useState, useEffect } from 'react';
import { Button } from '@/components/ui';
import type { User } from '@/types';

interface UserCardProps {
  user: User;
  onSelect: (id: string) => void;
}

const CARD_VARIANTS = ['default', 'compact'] as const;

export function UserCard({ user, onSelect }: UserCardProps) {
  // 1. Hooks
  const [isExpanded, setIsExpanded] = useState(false);

  // 2. Derived state
  const displayName = user.firstName + ' ' + user.lastName;

  // 3. Effects
  useEffect(() => {
    // ...
  }, [user.id]);

  // 4. Handlers
  const handleClick = () => {
    onSelect(user.id);
  };

  // 5. Render
  return (
    <div onClick={handleClick}>
      {displayName}
    </div>
  );
}
```

### 5.2 Component Rules

| Rule | Description |
|------|-------------|
| One component per file | Except small helper components |
| Named exports | `export function X` not `export default` |
| Props interface | Always define props type |
| Destructure props | In function signature |
| No inline functions in JSX | Define handlers outside return |

### 5.3 Hooks Rules

```typescript
// Good - custom hook for reusable logic
function useUser(id: string) {
  const [user, setUser] = useState<User | null>(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetchUser(id).then(setUser).finally(() => setLoading(false));
  }, [id]);

  return { user, loading };
}

// Usage
const { user, loading } = useUser(userId);
```

---

## 6. API & Data Standards

### 6.1 API Response Handling

```typescript
// Standard API response wrapper
interface ApiResponse<T> {
  data: T;
  meta?: {
    page: number;
    total: number;
  };
}

interface ApiError {
  code: string;
  message: string;
  details?: Record<string, string>;
}

// Standard fetch pattern
async function fetchUsers(): Promise<User[]> {
  const response = await api.get<ApiResponse<User[]>>('/users');
  return response.data;
}
```

### 6.2 Error Handling

```typescript
// Good - specific error handling
try {
  await createOrder(orderData);
} catch (error) {
  if (error instanceof ValidationError) {
    showValidationErrors(error.details);
  } else if (error instanceof NetworkError) {
    showToast('Network error. Please try again.');
  } else {
    logger.error('Unexpected error', error);
    showToast('Something went wrong.');
  }
}
```

---

## 7. Testing Standards

### 7.1 Test File Structure

| Pattern | Location | Example |
|---------|----------|---------|
| Unit tests | `__tests__/` folder | `UserService.test.ts` |
| Component tests | Same folder | `Button.test.tsx` |
| E2E tests | `/e2e/` root folder | `checkout.spec.ts` |

### 7.2 Test Naming

```typescript
describe('UserService', () => {
  describe('createUser', () => {
    it('should create user with valid data', async () => {
      // ...
    });

    it('should throw ValidationError for invalid email', async () => {
      // ...
    });

    it('should hash password before saving', async () => {
      // ...
    });
  });
});
```

### 7.3 Test Patterns

| Pattern | Use Case |
|---------|----------|
| AAA (Arrange, Act, Assert) | Unit tests |
| Given-When-Then | BDD-style tests |
| Page Object Model | E2E tests |

---

## 8. Git & Version Control

### 8.1 Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <subject>

<body>

<footer>
```

| Type | Description |
|------|-------------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `style` | Formatting (no code change) |
| `refactor` | Code restructure (no behavior change) |
| `test` | Adding/updating tests |
| `chore` | Maintenance, dependencies |

### 8.2 Branch Naming

```
<type>/<issue-number>-<short-description>

Examples:
feature/123-user-authentication
fix/456-cart-total-calculation
refactor/789-extract-payment-service
```

---

## 9. Documentation Standards

### 9.1 Code Comments

```typescript
// Good - explains WHY, not WHAT
// Cache user for 5 minutes to reduce API calls during session
const CACHE_TTL = 5 * 60 * 1000;

// Bad - explains WHAT (obvious from code)
// Set cache TTL to 5 minutes
const CACHE_TTL = 5 * 60 * 1000;
```

### 9.2 JSDoc for Public APIs

```typescript
/**
 * Creates a new order from cart items.
 *
 * @param userId - The ID of the user placing the order
 * @param items - Array of cart items to include
 * @returns The created order with calculated totals
 * @throws {ValidationError} If cart is empty
 * @throws {InsufficientStockError} If items are out of stock
 *
 * @example
 * const order = await createOrder('user-123', cartItems);
 */
async function createOrder(
  userId: string,
  items: CartItem[]
): Promise<Order> {
  // ...
}
```

---

## 10. Security Standards

### 10.1 Input Validation

| Rule | Implementation |
|------|----------------|
| Validate all inputs | Use Zod or Yup schemas |
| Sanitize user content | DOMPurify for HTML |
| Parameterize queries | Never concatenate SQL |
| Escape output | Framework handles in JSX |

### 10.2 Sensitive Data

```typescript
// Never log sensitive data
logger.info('User logged in', { userId: user.id }); // Good
logger.info('User logged in', { user }); // Bad - may include password

// Never expose in client
const config = {
  apiUrl: process.env.NEXT_PUBLIC_API_URL, // Good - public
  dbPassword: process.env.DB_PASSWORD, // Bad - server only
};
```

---

## 11. Performance Guidelines

### 11.1 React Performance

| Technique | When to Use |
|-----------|-------------|
| `useMemo` | Expensive calculations |
| `useCallback` | Callbacks passed to children |
| `React.memo` | Pure components receiving same props |
| `lazy` + `Suspense` | Code splitting |

### 11.2 General Performance

- [ ] Avoid N+1 queries
- [ ] Use pagination for large lists
- [ ] Implement caching strategies
- [ ] Optimize images (WebP, lazy loading)
- [ ] Bundle analysis before release

---

## 12. Tooling Configuration

### 12.1 ESLint Config

```json
{
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:react-hooks/recommended",
    "prettier"
  ],
  "rules": {
    "@typescript-eslint/no-unused-vars": "error",
    "@typescript-eslint/explicit-function-return-type": "off",
    "react-hooks/exhaustive-deps": "warn"
  }
}
```

### 12.2 Prettier Config

```json
{
  "semi": true,
  "singleQuote": true,
  "tabWidth": 2,
  "trailingComma": "es5",
  "printWidth": 100
}
```

---

## 13. Related Documents

| Document | Location |
|----------|----------|
| Repository Structure | `03-design/infrastructure/01-repository-structure.md` |
| CI/CD Pipelines | `03-design/infrastructure/03-ci-cd-pipelines.md` |
| Developer Onboarding | `03-design/infrastructure/04-developer-onboarding.md` |
| Code Review Template | `04-development/code-review/_template.md` |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial document |

---

*Development standards for ISO/IEC 29110-5-1-2 compliance.*
