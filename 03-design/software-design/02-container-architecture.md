# Container Architecture (C4 Level 2)

> ISO/IEC 29110-5-1-2 Work Product: Software Design - Container Architecture

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

## Purpose

This document zooms into [PROJECT_NAME] to show the high-level containers (applications, services, databases) that make up the system and how they interact.

---

## Container Diagram

```mermaid
C4Container
    title Container Diagram - [PROJECT_NAME]

    Person(patient, "Patient", "Mobile app user")
    Person(staff, "Staff", "Web app user")

    Container_Boundary(system, "[PROJECT_NAME]") {
        Container(mobile_app, "Mobile App", "Flutter/React Native", "Patient-facing mobile application")
        Container(web_app, "Web Application", "React/Next.js", "Staff-facing web application")
        Container(api_gateway, "API Gateway", "Kong/AWS API GW", "API routing, rate limiting, auth")
        Container(backend_api, "Backend API", "Node.js/Python", "Core business logic and REST APIs")
        Container(worker, "Background Worker", "Node.js/Python", "Async job processing")
        ContainerDb(database, "Database", "PostgreSQL", "Primary data store")
        ContainerDb(cache, "Cache", "Redis", "Session and data caching")
        ContainerDb(queue, "Message Queue", "RabbitMQ/SQS", "Async job queue")
        ContainerDb(storage, "File Storage", "S3/GCS", "Documents and media")
    }

    System_Ext(auth, "Auth Provider", "OAuth2 authentication")
    System_Ext(email, "Email Service", "Transactional emails")
    System_Ext(sms, "SMS Gateway", "OTP and notifications")

    Rel(patient, mobile_app, "Uses", "HTTPS")
    Rel(staff, web_app, "Uses", "HTTPS")

    Rel(mobile_app, api_gateway, "API calls", "HTTPS/JSON")
    Rel(web_app, api_gateway, "API calls", "HTTPS/JSON")

    Rel(api_gateway, backend_api, "Routes to", "HTTP")
    Rel(backend_api, database, "Reads/Writes", "TCP/5432")
    Rel(backend_api, cache, "Reads/Writes", "TCP/6379")
    Rel(backend_api, queue, "Publishes", "AMQP")
    Rel(backend_api, storage, "Stores files", "HTTPS")

    Rel(worker, queue, "Consumes", "AMQP")
    Rel(worker, database, "Reads/Writes", "TCP/5432")
    Rel(worker, email, "Sends via", "HTTPS")
    Rel(worker, sms, "Sends via", "HTTPS")

    Rel(backend_api, auth, "Validates tokens", "HTTPS")
```

---

## Container Descriptions

### Frontend Containers

| Container | Technology | Purpose | Scaling |
|-----------|------------|---------|---------|
| **Mobile App** | [Flutter/React Native] | Patient mobile interface | N/A (client-side) |
| **Web App** | [React/Next.js] | Staff web interface | CDN + Static hosting |

### Backend Containers

| Container | Technology | Purpose | Scaling | Port |
|-----------|------------|---------|---------|------|
| **API Gateway** | [Kong/AWS API GW] | Routing, auth, rate limiting | Horizontal | 443 |
| **Backend API** | [Node.js/Python] | Business logic, REST APIs | Horizontal | 3000 |
| **Background Worker** | [Node.js/Python] | Async processing | Horizontal | N/A |

### Data Containers

| Container | Technology | Purpose | Persistence | Backup |
|-----------|------------|---------|-------------|--------|
| **Database** | [PostgreSQL] | Primary data store | Persistent | Daily |
| **Cache** | [Redis] | Sessions, caching | Ephemeral | N/A |
| **Message Queue** | [RabbitMQ/SQS] | Job queue | Persistent | N/A |
| **File Storage** | [S3/GCS] | Documents, media | Persistent | Cross-region |

---

## Container Interactions

### Synchronous Interactions

| From | To | Method | Purpose |
|------|----|----- --|---------|
| Mobile App | API Gateway | HTTPS/REST | API requests |
| API Gateway | Backend API | HTTP | Request routing |
| Backend API | Database | TCP | Data operations |
| Backend API | Cache | TCP | Session/cache |

### Asynchronous Interactions

| From | To | Method | Purpose |
|------|----|----- --|---------|
| Backend API | Queue | AMQP | Job publishing |
| Worker | Queue | AMQP | Job consumption |
| Worker | Email Service | HTTPS | Send emails |

---

## Technology Decisions

| Decision | Choice | Rationale | ADR |
|----------|--------|-----------|-----|
| Backend Language | [Node.js] | [Team expertise, async I/O] | ADR-001 |
| Database | [PostgreSQL] | [ACID, JSON support] | ADR-002 |
| Cache | [Redis] | [Speed, pub/sub] | ADR-003 |
| Frontend | [React] | [Component ecosystem] | ADR-004 |

---

## Deployment Overview

```
┌─────────────────────────────────────────────────────────────┐
│                        Cloud Provider                        │
├─────────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐          │
│  │   CDN       │  │ Load        │  │ API Gateway │          │
│  │ (Static)    │  │ Balancer    │  │             │          │
│  └─────────────┘  └──────┬──────┘  └──────┬──────┘          │
│                          │                 │                 │
│         ┌────────────────┴─────────────────┘                │
│         ▼                                                    │
│  ┌─────────────────────────────────────────────────────┐    │
│  │              Kubernetes / Container Service          │    │
│  │  ┌─────────┐  ┌─────────┐  ┌─────────┐              │    │
│  │  │ API x3  │  │ Worker  │  │ Worker  │              │    │
│  │  │ pods    │  │ pod     │  │ pod     │              │    │
│  │  └─────────┘  └─────────┘  └─────────┘              │    │
│  └─────────────────────────────────────────────────────┘    │
│                          │                                   │
│         ┌────────────────┴─────────────────┐                │
│         ▼                                  ▼                 │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐          │
│  │ PostgreSQL  │  │   Redis     │  │   S3/GCS    │          │
│  │ (Managed)   │  │ (Managed)   │  │ (Storage)   │          │
│  └─────────────┘  └─────────────┘  └─────────────┘          │
└─────────────────────────────────────────────────────────────┘
```

---

## Related Documents

- **System Context:** `01-system-context.md`
- **Component Design:** `03-component-design.md`
- **Deployment Architecture:** `04-deployment-architecture.md`
- **API Design:** `api-design/`

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial container architecture |

---

*Diagram follows C4 Model Level 2 (Container) format.*
