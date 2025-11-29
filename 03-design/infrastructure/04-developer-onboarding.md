# Developer Onboarding

> Infrastructure Design: Developer environment setup and access provisioning

---

## Metadata

```yaml
project: "[PROJECT_NAME]"
version: "1.0"
last_updated: "YYYY-MM-DD"
author: "[SA_NAME]"
status: "Draft"
```

---

## 1. Onboarding Checklist

### 1.1 Day 1 Checklist

| Task | Owner | Status |
|------|-------|--------|
| GitHub organization invite | DevOps | [ ] |
| Add to repository teams | DevOps | [ ] |
| Slack workspace invite | PM | [ ] |
| Add to relevant Slack channels | PM | [ ] |
| Jira/Linear project access | PM | [ ] |
| Google Workspace / Email | Admin | [ ] |
| 1Password / Vault access | DevOps | [ ] |
| Schedule intro meeting | Tech Lead | [ ] |

### 1.2 Week 1 Checklist

| Task | Owner | Status |
|------|-------|--------|
| Clone repositories | Developer | [ ] |
| Local environment setup | Developer | [ ] |
| Run application locally | Developer | [ ] |
| Review codebase architecture | Developer | [ ] |
| Review coding standards | Developer | [ ] |
| Complete first PR (small fix) | Developer | [ ] |
| Meet team members | Developer | [ ] |

---

## 2. Access Provisioning

### 2.1 Required Accounts

| Service | Purpose | Request Via |
|---------|---------|-------------|
| GitHub (Foxbith org) | Code repositories | DevOps |
| Slack | Team communication | PM |
| Jira / Linear | Issue tracking | PM |
| Figma | Design files | Design Lead |
| 1Password | Secrets access | DevOps |
| AWS Console (if needed) | Cloud resources | SA |
| Sentry | Error monitoring | DevOps |
| Datadog / Grafana | Observability | DevOps |

### 2.2 GitHub Team Assignment

| Team | Access Level | Who |
|------|--------------|-----|
| `@foxbith/developers` | Write (code repos) | All developers |
| `@foxbith/frontend` | Write (frontend repos) | Frontend devs |
| `@foxbith/backend` | Write (backend repos) | Backend devs |
| `@foxbith/devops` | Admin (infra repos) | DevOps engineers |
| `@foxbith/reviewers` | Review access | Senior devs |

### 2.3 Access Request Form

| Field | Value |
|-------|-------|
| Name | [Developer Name] |
| Email | [Email] |
| Role | [Frontend/Backend/Fullstack/DevOps] |
| Start Date | [Date] |
| Manager | [Manager Name] |
| Required Access | [List services] |
| Requested By | [Requester] |

---

## 3. Development Environment

### 3.1 Required Software

| Software | Version | Purpose | Install |
|----------|---------|---------|---------|
| Node.js | 20.x LTS | JavaScript runtime | `nvm install 20` |
| pnpm | 8.x | Package manager | `npm install -g pnpm` |
| Docker | Latest | Containerization | [docker.com](https://docker.com) |
| Git | Latest | Version control | `brew install git` |
| VS Code | Latest | IDE | [code.visualstudio.com](https://code.visualstudio.com) |
| PostgreSQL | 15.x | Database (optional) | `brew install postgresql@15` |
| Redis | 7.x | Cache (optional) | `brew install redis` |

### 3.2 Recommended VS Code Extensions

| Extension | Purpose |
|-----------|---------|
| ESLint | Linting |
| Prettier | Formatting |
| GitLens | Git visualization |
| Docker | Container management |
| Thunder Client / REST Client | API testing |
| Tailwind CSS IntelliSense | CSS utilities |
| Prisma | Database ORM |
| Error Lens | Inline errors |

### 3.3 VS Code Settings

```json
// .vscode/settings.json (committed to repo)
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "typescript.preferences.importModuleSpecifier": "relative",
  "files.exclude": {
    "node_modules": true,
    ".next": true
  }
}
```

---

## 4. Local Setup Guide

### 4.1 Clone Repositories

```bash
# Create project directory
mkdir -p ~/Projects/[PROJECT_NAME]
cd ~/Projects/[PROJECT_NAME]

# Clone repositories
git clone git@github.com:Foxbith/[project]-code.git
git clone git@github.com:Foxbith/[project]-docs.git

# Enter code directory
cd [project]-code
```

### 4.2 Environment Setup

```bash
# Copy environment template
cp .env.example .env

# Get development secrets from 1Password
# - Open 1Password
# - Search for "[PROJECT_NAME] Dev Secrets"
# - Copy values to .env file

# Or use 1Password CLI
op read "op://Development/[PROJECT_NAME]/DATABASE_URL"
```

### 4.3 Install Dependencies

```bash
# Install dependencies
pnpm install

# Setup database (if using local DB)
pnpm db:migrate
pnpm db:seed

# Or use Docker for services
docker-compose up -d postgres redis
```

### 4.4 Run Application

```bash
# Development mode
pnpm dev

# Application available at:
# - Frontend: http://localhost:3000
# - API: http://localhost:4000
# - Database: localhost:5432
```

### 4.5 Verify Setup

```bash
# Run tests
pnpm test

# Run linting
pnpm lint

# Build application
pnpm build

# All should pass before starting work
```

---

## 5. Docker Setup (Alternative)

### 5.1 Using Docker Compose

```bash
# Start all services
docker-compose up -d

# View logs
docker-compose logs -f api

# Stop all services
docker-compose down
```

### 5.2 Docker Compose File

```yaml
# docker-compose.yml
version: '3.8'

services:
  api:
    build: .
    ports:
      - "4000:4000"
    environment:
      - DATABASE_URL=postgresql://user:pass@postgres:5432/app
      - REDIS_URL=redis://redis:6379
    depends_on:
      - postgres
      - redis
    volumes:
      - .:/app
      - /app/node_modules

  postgres:
    image: postgres:15
    ports:
      - "5432:5432"
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: pass
      POSTGRES_DB: app
    volumes:
      - postgres_data:/var/lib/postgresql/data

  redis:
    image: redis:7-alpine
    ports:
      - "6379:6379"

volumes:
  postgres_data:
```

---

## 6. Coding Standards

### 6.1 Code Style

| Aspect | Standard |
|--------|----------|
| Formatting | Prettier (auto-format on save) |
| Linting | ESLint with project config |
| Naming | camelCase (vars), PascalCase (components) |
| Commits | Conventional Commits |
| Branch names | `feature/123-short-desc` |

### 6.2 Commit Message Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
| Type | Description |
|------|-------------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation |
| `style` | Formatting (no code change) |
| `refactor` | Code restructure |
| `test` | Adding tests |
| `chore` | Maintenance tasks |

**Example:**
```
feat(auth): add social login with Google

- Implement Google OAuth flow
- Add login button to UI
- Store OAuth tokens securely

Closes #123
```

### 6.3 PR Guidelines

- [ ] PR title follows commit format
- [ ] Description explains what and why
- [ ] Tests added/updated
- [ ] No console.log or debug code
- [ ] Self-reviewed before requesting review
- [ ] Small, focused PRs (< 400 lines preferred)

---

## 7. Development Workflow

### 7.1 Daily Workflow

```mermaid
flowchart TD
    A[Pull latest develop] --> B[Create feature branch]
    B --> C[Write code + tests]
    C --> D[Run lint + tests locally]
    D --> E{Pass?}
    E -->|No| C
    E -->|Yes| F[Push & create PR]
    F --> G[CI runs]
    G --> H{Pass?}
    H -->|No| C
    H -->|Yes| I[Request review]
    I --> J[Address feedback]
    J --> K[Merge to develop]
```

### 7.2 Useful Commands

```bash
# Create feature branch
git checkout develop
git pull origin develop
git checkout -b feature/123-my-feature

# Push and create PR
git push -u origin feature/123-my-feature
gh pr create --fill

# Update from develop
git fetch origin
git rebase origin/develop

# Run specific test
pnpm test -- --grep "my test"

# Type check only
pnpm type-check
```

---

## 8. Getting Help

### 8.1 Resources

| Resource | Location |
|----------|----------|
| Project Wiki | [Link to wiki] |
| API Documentation | [Link to Swagger/docs] |
| Design System | [Link to Storybook] |
| Architecture Docs | `03-design/` in docs repo |

### 8.2 Who to Ask

| Question About | Contact |
|----------------|---------|
| Codebase / Architecture | Tech Lead |
| Frontend | [Frontend Lead] |
| Backend | [Backend Lead] |
| DevOps / Infra | [DevOps Engineer] |
| Product / Requirements | PM |
| Design / UI | Design Lead |

### 8.3 Slack Channels

| Channel | Purpose |
|---------|---------|
| `#[project]-dev` | Development discussions |
| `#[project]-general` | General project chat |
| `#[project]-alerts` | CI/CD and monitoring alerts |
| `#[project]-support` | Customer support escalations |

---

## 9. Common Issues

### 9.1 Troubleshooting

| Issue | Solution |
|-------|----------|
| `npm install` fails | Clear cache: `npm cache clean --force` |
| Port already in use | Kill process: `lsof -ti:3000 \| xargs kill` |
| Docker out of space | Prune: `docker system prune -a` |
| DB connection fails | Check `.env` DATABASE_URL |
| Tests timeout | Increase timeout or check async handling |

### 9.2 Environment Issues

```bash
# Reset node_modules
rm -rf node_modules
pnpm install

# Reset database
pnpm db:reset

# Full Docker reset
docker-compose down -v
docker-compose up -d
```

---

## 10. Offboarding Checklist

### 10.1 Access Removal

| Task | Owner | Status |
|------|-------|--------|
| Remove from GitHub org | DevOps | [ ] |
| Revoke Slack access | Admin | [ ] |
| Remove from Jira/Linear | PM | [ ] |
| Revoke 1Password access | DevOps | [ ] |
| Revoke AWS access | SA | [ ] |
| Remove from monitoring tools | DevOps | [ ] |
| Rotate shared secrets (if needed) | DevOps | [ ] |

---

## 11. Related Documents

| Document | Location |
|----------|----------|
| Repository Structure | `01-repository-structure.md` |
| Secrets Management | `02-secrets-management.md` |
| CI/CD Pipelines | `03-ci-cd-pipelines.md` |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial document |

---

*Infrastructure design for ISO/IEC 29110-5-1-2 compliance.*
