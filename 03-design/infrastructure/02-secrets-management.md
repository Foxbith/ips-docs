# Secrets Management

> Infrastructure Design: Secrets, credentials, and environment configuration

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

## 1. Overview

### 1.1 Secret Categories

| Category | Examples | Storage |
|----------|----------|---------|
| Application Secrets | API keys, JWT secrets | Vault/Secrets Manager |
| Database Credentials | DB username/password | Vault/Secrets Manager |
| Infrastructure Secrets | Cloud credentials | CI/CD secrets |
| Encryption Keys | AES keys, RSA keys | KMS |
| Third-party API Keys | Stripe, SendGrid | Vault/Secrets Manager |
| Certificates | SSL/TLS certs | Certificate Manager |

### 1.2 Environments

| Environment | Purpose | Secret Source |
|-------------|---------|---------------|
| Local | Developer machines | `.env` file (from template) |
| Development | Shared dev server | GitHub Secrets / Vault |
| Staging | Pre-production testing | GitHub Secrets / Vault |
| Production | Live system | Vault / Cloud Secrets Manager |

---

## 2. Secret Storage

### 2.1 Storage Solution

- [ ] **GitHub Secrets** - For CI/CD pipelines
- [ ] **AWS Secrets Manager** - For AWS deployments
- [ ] **GCP Secret Manager** - For GCP deployments
- [ ] **HashiCorp Vault** - Self-hosted secret management
- [ ] **Azure Key Vault** - For Azure deployments
- [ ] **Doppler** - Cross-platform secrets management

### 2.2 Secret Hierarchy

```
[PROJECT_NAME]/
├── common/                    # Shared across environments
│   ├── THIRD_PARTY_API_KEY
│   └── ENCRYPTION_KEY
├── development/
│   ├── DATABASE_URL
│   ├── REDIS_URL
│   └── JWT_SECRET
├── staging/
│   ├── DATABASE_URL
│   ├── REDIS_URL
│   └── JWT_SECRET
└── production/
    ├── DATABASE_URL
    ├── REDIS_URL
    └── JWT_SECRET
```

---

## 3. Secret Naming Convention

### 3.1 Naming Pattern

```
{SERVICE}_{TYPE}_{IDENTIFIER}
```

| Component | Description | Example |
|-----------|-------------|---------|
| SERVICE | Service or integration name | `DATABASE`, `STRIPE`, `AWS` |
| TYPE | Type of secret | `URL`, `KEY`, `SECRET`, `PASSWORD` |
| IDENTIFIER | Optional qualifier | `READ`, `WRITE`, `ADMIN` |

### 3.2 Examples

| Secret Name | Description |
|-------------|-------------|
| `DATABASE_URL` | Database connection string |
| `DATABASE_PASSWORD` | Database password only |
| `REDIS_URL` | Redis connection string |
| `JWT_SECRET` | JWT signing secret |
| `JWT_REFRESH_SECRET` | JWT refresh token secret |
| `AWS_ACCESS_KEY_ID` | AWS access key |
| `AWS_SECRET_ACCESS_KEY` | AWS secret key |
| `STRIPE_SECRET_KEY` | Stripe API secret key |
| `STRIPE_WEBHOOK_SECRET` | Stripe webhook signing secret |
| `SENDGRID_API_KEY` | SendGrid email API key |
| `SENTRY_DSN` | Sentry error tracking DSN |

---

## 4. Secret Inventory

### 4.1 Application Secrets

| Secret Name | Description | Rotation | Owner |
|-------------|-------------|----------|-------|
| `JWT_SECRET` | JWT signing key | Quarterly | DevOps |
| `JWT_REFRESH_SECRET` | Refresh token key | Quarterly | DevOps |
| `ENCRYPTION_KEY` | Data encryption | Annually | Security |
| `SESSION_SECRET` | Session encryption | Quarterly | DevOps |

### 4.2 Database Credentials

| Secret Name | Database | Access Level | Rotation |
|-------------|----------|--------------|----------|
| `DATABASE_URL` | PostgreSQL | Read/Write | Quarterly |
| `DATABASE_URL_READ` | PostgreSQL (replica) | Read-only | Quarterly |
| `REDIS_URL` | Redis | Full | Quarterly |

### 4.3 Third-Party API Keys

| Secret Name | Service | Permissions | Rotation |
|-------------|---------|-------------|----------|
| `STRIPE_SECRET_KEY` | Stripe | Payments | Annually |
| `STRIPE_WEBHOOK_SECRET` | Stripe | Webhooks | On change |
| `SENDGRID_API_KEY` | SendGrid | Email send | Annually |
| `CLOUDINARY_URL` | Cloudinary | Media upload | Annually |
| `FIREBASE_SERVICE_ACCOUNT` | Firebase | Admin | Annually |

### 4.4 Infrastructure Secrets

| Secret Name | Service | Scope | Rotation |
|-------------|---------|-------|----------|
| `AWS_ACCESS_KEY_ID` | AWS | CI/CD | Quarterly |
| `AWS_SECRET_ACCESS_KEY` | AWS | CI/CD | Quarterly |
| `GCP_SERVICE_ACCOUNT` | GCP | Deployment | Annually |
| `DOCKER_REGISTRY_TOKEN` | Docker Hub/GCR | Push/Pull | Annually |

---

## 5. Environment Variables Template

### 5.1 `.env.example` File

```bash
# ===========================================
# [PROJECT_NAME] Environment Variables
# ===========================================
# Copy this file to .env and fill in values
# NEVER commit .env to version control
# ===========================================

# Application
NODE_ENV=development
PORT=3000
API_URL=http://localhost:3000

# Database
DATABASE_URL=postgresql://user:password@localhost:5432/dbname
REDIS_URL=redis://localhost:6379

# Authentication
JWT_SECRET=your-jwt-secret-here
JWT_REFRESH_SECRET=your-refresh-secret-here
JWT_EXPIRES_IN=15m
JWT_REFRESH_EXPIRES_IN=7d

# Third-Party Services
STRIPE_SECRET_KEY=sk_test_xxx
STRIPE_WEBHOOK_SECRET=whsec_xxx
SENDGRID_API_KEY=SG.xxx

# Storage
CLOUDINARY_URL=cloudinary://xxx:xxx@xxx
# or
AWS_S3_BUCKET=your-bucket-name
AWS_REGION=ap-southeast-1

# Monitoring
SENTRY_DSN=https://xxx@sentry.io/xxx

# Feature Flags (optional)
FEATURE_NEW_DASHBOARD=false
```

### 5.2 Required vs Optional

| Variable | Required | Default | Notes |
|----------|----------|---------|-------|
| `DATABASE_URL` | Yes | - | Must be set |
| `JWT_SECRET` | Yes | - | Must be set |
| `REDIS_URL` | No | `redis://localhost:6379` | Has default |
| `SENTRY_DSN` | No | - | Optional monitoring |

---

## 6. Secret Rotation

### 6.1 Rotation Schedule

| Frequency | Secrets |
|-----------|---------|
| **Monthly** | Compromised secrets (immediate) |
| **Quarterly** | JWT secrets, database passwords, AWS keys |
| **Annually** | Third-party API keys, encryption keys |
| **On Event** | Webhook secrets (when endpoint changes) |

### 6.2 Rotation Procedure

```mermaid
flowchart TD
    A[Generate New Secret] --> B[Update in Vault/Manager]
    B --> C[Deploy to Staging]
    C --> D{Test Staging}
    D -->|Pass| E[Deploy to Production]
    D -->|Fail| F[Rollback & Investigate]
    E --> G[Verify Production]
    G --> H[Revoke Old Secret]
    H --> I[Document in Change Log]
```

### 6.3 Rotation Checklist

- [ ] Generate new secret value
- [ ] Update in secrets manager (all environments)
- [ ] Deploy to staging
- [ ] Test staging functionality
- [ ] Deploy to production
- [ ] Verify production functionality
- [ ] Revoke/delete old secret
- [ ] Update documentation
- [ ] Notify team

---

## 7. Access Control

### 7.1 Role-Based Access

| Role | View Secrets | Create/Update | Delete | Rotate |
|------|--------------|---------------|--------|--------|
| Developer | Dev only | No | No | No |
| Senior Dev | Dev + Staging | Dev only | No | No |
| DevOps | All | All | Staging/Dev | All |
| SA | All | All | All | All |
| PM | No | No | No | No |

### 7.2 Access Request Process

1. Developer requests access via [Ticket System]
2. SA/DevOps reviews request
3. Access granted with expiry date
4. Access reviewed quarterly

---

## 8. Security Best Practices

### 8.1 Do's

- ✅ Use secrets manager, never hardcode
- ✅ Rotate secrets regularly
- ✅ Use different secrets per environment
- ✅ Encrypt secrets at rest and in transit
- ✅ Audit secret access
- ✅ Use short-lived tokens when possible

### 8.2 Don'ts

- ❌ Never commit secrets to Git
- ❌ Never share secrets via Slack/email
- ❌ Never use production secrets in development
- ❌ Never log secrets in application logs
- ❌ Never store secrets in client-side code

### 8.3 Git Protection

```gitignore
# .gitignore
.env
.env.local
.env.*.local
*.pem
*.key
credentials.json
service-account.json
```

---

## 9. Incident Response

### 9.1 Secret Compromise Procedure

| Step | Action | Owner | Timeline |
|------|--------|-------|----------|
| 1 | Identify compromised secret | Anyone | Immediate |
| 2 | Rotate secret immediately | DevOps | < 1 hour |
| 3 | Deploy rotated secret | DevOps | < 2 hours |
| 4 | Revoke old secret | DevOps | < 2 hours |
| 5 | Audit access logs | Security | < 24 hours |
| 6 | Post-mortem | SA | < 1 week |

### 9.2 Notification

| Severity | Notify |
|----------|--------|
| Critical (prod DB, payment keys) | CTO, SA, DevOps immediately |
| High (prod API keys) | SA, DevOps within 1 hour |
| Medium (staging/dev secrets) | DevOps within 24 hours |

---

## 10. Related Documents

| Document | Location |
|----------|----------|
| Repository Structure | `01-repository-structure.md` |
| CI/CD Pipelines | `03-ci-cd-pipelines.md` |
| Developer Onboarding | `04-developer-onboarding.md` |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial document |

---

*Infrastructure design for ISO/IEC 29110-5-1-2 compliance.*
