# Product Operation Guide

> ISO/IEC 29110-5-1-2 Work Product: Product Operation Guide

---

## Metadata

```yaml
project: "[PROJECT_NAME]"
version: "1.0"
last_updated: "YYYY-MM-DD"
author: "[NAME]"
status: "Draft"
```

---

## 1. Introduction

### 1.1 Purpose
This guide provides instructions for installing, deploying, configuring, and operating [PROJECT_NAME] in production environments.

### 1.2 Audience
| Audience | Sections |
|----------|----------|
| DevOps/SRE | All sections |
| System Admin | 2, 3, 5, 6 |
| Support Team | 4, 6, 7 |

### 1.3 Related Documents
| Document | Location |
|----------|----------|
| Architecture | `03-design/software-design/` |
| User Guide | `06-support/user-documentation/` |
| API Reference | `03-design/software-design/api-design/` |

---

## 2. System Requirements

### 2.1 Hardware Requirements
| Component | Minimum | Recommended | Notes |
|-----------|---------|-------------|-------|
| CPU | [X] cores | [X] cores | |
| Memory | [X] GB | [X] GB | |
| Storage | [X] GB | [X] GB | SSD recommended |
| Network | [X] Mbps | [X] Mbps | |

### 2.2 Software Requirements
| Software | Version | Purpose |
|----------|---------|---------|
| OS | [Ubuntu 22.04 / etc.] | Host operating system |
| Docker | [X.X]+ | Container runtime |
| [Database] | [X.X]+ | Data persistence |
| [Other] | [X.X]+ | [Purpose] |

### 2.3 Network Requirements
| Port | Protocol | Direction | Purpose |
|------|----------|-----------|---------|
| 443 | HTTPS | Inbound | API/Web traffic |
| 5432 | TCP | Internal | Database |
| 6379 | TCP | Internal | Redis cache |

---

## 3. Installation

### 3.1 Pre-Installation Checklist
- [ ] Hardware requirements met
- [ ] Software prerequisites installed
- [ ] Network ports available
- [ ] Credentials/secrets prepared
- [ ] SSL certificates ready

### 3.2 Installation Steps

#### Option A: Docker Installation (Recommended)
```bash
# 1. Clone deployment repository
git clone [DEPLOYMENT_REPO_URL]
cd [project]-deploy

# 2. Configure environment
cp .env.example .env
# Edit .env with your settings

# 3. Start services
docker-compose up -d

# 4. Verify installation
docker-compose ps
curl http://localhost:3000/health
```

#### Option B: Manual Installation
```bash
# 1. Install dependencies
npm install --production  # or pip install -r requirements.txt

# 2. Configure environment
export DATABASE_URL="postgresql://..."
export REDIS_URL="redis://..."
# ... other environment variables

# 3. Run database migrations
npm run migrate  # or python manage.py migrate

# 4. Start application
npm start  # or gunicorn app:app
```

### 3.3 Post-Installation Verification
| Check | Command | Expected |
|-------|---------|----------|
| API Health | `curl /health` | `{"status": "ok"}` |
| Database | `curl /health/db` | `{"status": "ok"}` |
| Cache | `curl /health/cache` | `{"status": "ok"}` |

---

## 4. Configuration

### 4.1 Environment Variables
| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `DATABASE_URL` | Yes | - | Database connection string |
| `REDIS_URL` | Yes | - | Redis connection string |
| `JWT_SECRET` | Yes | - | JWT signing secret |
| `LOG_LEVEL` | No | `info` | Logging level |
| `NODE_ENV` | No | `production` | Environment |

### 4.2 Configuration Files
| File | Purpose | Location |
|------|---------|----------|
| `.env` | Environment variables | Root directory |
| `config.yaml` | Application config | `/config/` |
| `nginx.conf` | Reverse proxy | `/nginx/` |

### 4.3 Feature Flags
| Flag | Default | Description |
|------|---------|-------------|
| `FEATURE_X_ENABLED` | `false` | Enable feature X |

---

## 5. Deployment

### 5.1 Deployment Environments
| Environment | URL | Purpose |
|-------------|-----|---------|
| Development | localhost | Local development |
| Staging | staging.example.com | Testing/QA |
| Production | app.example.com | Live system |

### 5.2 Deployment Process

#### CI/CD Pipeline (Recommended)
```yaml
# .github/workflows/deploy.yml
deploy:
  - Checkout code
  - Run tests
  - Build Docker image
  - Push to registry
  - Deploy to Kubernetes/ECS
  - Run smoke tests
  - Notify team
```

#### Manual Deployment
```bash
# 1. Pull latest code
git pull origin main

# 2. Build application
npm run build  # or docker build

# 3. Run migrations
npm run migrate

# 4. Restart services
pm2 restart all  # or docker-compose restart

# 5. Verify deployment
curl https://app.example.com/health
```

### 5.3 Rollback Procedure
```bash
# 1. Identify last working version
git log --oneline -10

# 2. Revert to previous version
git checkout [COMMIT_SHA]

# 3. Redeploy
docker-compose up -d --force-recreate

# 4. Verify rollback
curl /health
```

---

## 6. Operations

### 6.1 Daily Operations
| Task | Frequency | Procedure |
|------|-----------|-----------|
| Health check | Hourly (automated) | Monitor dashboard |
| Log review | Daily | Check error logs |
| Backup verification | Daily | Verify backup completed |

### 6.2 Startup/Shutdown

**Startup Sequence:**
1. Start database
2. Start cache (Redis)
3. Start message queue
4. Start application servers
5. Start background workers
6. Verify health checks

```bash
# Startup
docker-compose up -d postgres redis
sleep 10
docker-compose up -d api worker
```

**Shutdown Sequence:**
1. Stop accepting new connections (drain)
2. Wait for in-flight requests
3. Stop application servers
4. Stop workers
5. Stop cache
6. Stop database

```bash
# Graceful shutdown
docker-compose stop api worker
docker-compose stop redis
docker-compose stop postgres
```

### 6.3 Monitoring

#### Metrics to Monitor
| Metric | Warning | Critical | Tool |
|--------|---------|----------|------|
| CPU Usage | > 70% | > 90% | [Prometheus/CloudWatch] |
| Memory Usage | > 80% | > 95% | [Prometheus/CloudWatch] |
| Response Time | > 500ms | > 2s | [APM tool] |
| Error Rate | > 1% | > 5% | [APM tool] |
| Disk Usage | > 70% | > 90% | [Monitoring] |

#### Alerting
| Alert | Channel | Escalation |
|-------|---------|------------|
| Critical | PagerDuty | Immediate |
| Warning | Slack | Within 1 hour |
| Info | Email | Next business day |

### 6.4 Logging

**Log Locations:**
| Log Type | Location | Retention |
|----------|----------|-----------|
| Application | `/var/log/app/` | 30 days |
| Access | `/var/log/nginx/access.log` | 30 days |
| Error | `/var/log/nginx/error.log` | 90 days |

**Log Format:**
```
[TIMESTAMP] [LEVEL] [REQUEST_ID] [MESSAGE]
```

---

## 7. Maintenance

### 7.1 Backup Procedures

**Database Backup:**
```bash
# Automated daily backup
pg_dump -h $DB_HOST -U $DB_USER $DB_NAME | gzip > backup_$(date +%Y%m%d).sql.gz

# Upload to S3/GCS
aws s3 cp backup_*.sql.gz s3://backups/db/
```

**File Storage Backup:**
```bash
# Sync to backup location
aws s3 sync s3://production-files s3://backup-files
```

### 7.2 Restore Procedures

**Database Restore:**
```bash
# 1. Stop application
docker-compose stop api worker

# 2. Restore database
gunzip -c backup_20250101.sql.gz | psql -h $DB_HOST -U $DB_USER $DB_NAME

# 3. Start application
docker-compose start api worker

# 4. Verify
curl /health
```

### 7.3 Scheduled Maintenance
| Task | Frequency | Window | Procedure |
|------|-----------|--------|-----------|
| Security patches | Monthly | Sunday 2-4 AM | Apply OS updates |
| DB maintenance | Weekly | Sunday 3 AM | VACUUM, REINDEX |
| Log rotation | Daily | Midnight | Automatic (logrotate) |
| Certificate renewal | Before expiry | As needed | Let's Encrypt auto |

### 7.4 Security Maintenance
- [ ] Rotate secrets quarterly
- [ ] Review access logs monthly
- [ ] Update dependencies monthly
- [ ] Run security scans before release

---

## 8. Troubleshooting

### 8.1 Common Issues

| Issue | Symptoms | Resolution |
|-------|----------|------------|
| API Timeout | 504 errors | Check DB connections, increase timeout |
| Out of Memory | OOM kills | Increase memory, check for leaks |
| High Latency | Slow responses | Check DB queries, add caching |
| Connection Refused | 502 errors | Restart services, check ports |

### 8.2 Diagnostic Commands
```bash
# Check container status
docker-compose ps

# View logs
docker-compose logs -f api

# Check database connections
psql -c "SELECT count(*) FROM pg_stat_activity;"

# Check memory usage
docker stats

# Check disk space
df -h
```

### 8.3 Escalation Path
| Level | Contact | When |
|-------|---------|------|
| L1 | On-call engineer | First response |
| L2 | Senior engineer | Complex issues |
| L3 | Tech Lead | Critical/Architecture |
| L4 | Vendor support | External dependencies |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial guide |

---

*Template follows ISO/IEC 29110-5-1-2 Product Operation Guide requirements.*
