# Release Notes: v[X.Y.Z]

> ISO/IEC 29110-5-1-2 Work Product: Release Notes

---

## Metadata

```yaml
id: release-[VERSION]
project: "[PROJECT_NAME]"
version: "[X.Y.Z]"
release_date: "YYYY-MM-DD"
release_type: "[Major/Minor/Patch/Hotfix]"
author: "[NAME]"
```

---

## Release Summary

**Version:** [X.Y.Z]
**Release Date:** YYYY-MM-DD
**Release Type:** [Major/Minor/Patch/Hotfix]

[One paragraph summary of this release - what's new, why it matters]

---

## Highlights

- [Highlight 1 - Most important feature/change]
- [Highlight 2]
- [Highlight 3]

---

## New Features

### [Feature Name 1]
**Requirement:** FR-XXX

[Description of the feature and how to use it]

### [Feature Name 2]
**Requirement:** FR-YYY

[Description of the feature and how to use it]

---

## Improvements

| Area | Improvement | Benefit |
|------|-------------|---------|
| [Performance] | [Description] | [Benefit] |
| [Usability] | [Description] | [Benefit] |
| [Security] | [Description] | [Benefit] |

---

## Bug Fixes

| ID | Description | Severity |
|----|-------------|----------|
| [BUG-001] | [Fixed issue where...] | High |
| [BUG-002] | [Resolved problem with...] | Medium |
| [BUG-003] | [Corrected behavior of...] | Low |

---

## Breaking Changes

| Change | Impact | Migration |
|--------|--------|-----------|
| [API change] | [Who is affected] | [How to migrate] |
| [Config change] | [Who is affected] | [How to migrate] |

---

## Deprecations

| Feature | Deprecated | Removal Version | Alternative |
|---------|------------|-----------------|-------------|
| [Feature X] | This release | v[X+1.0.0] | [Use Y instead] |

---

## Known Issues

| Issue | Workaround | Fix Planned |
|-------|------------|-------------|
| [Known issue 1] | [Workaround] | v[X.Y.Z+1] |

---

## Upgrade Instructions

### From v[X.Y.Z-1]
```bash
# 1. Backup database
pg_dump ... > backup.sql

# 2. Stop services
docker-compose stop

# 3. Pull new version
docker pull [image]:[X.Y.Z]

# 4. Run migrations
docker-compose run api npm run migrate

# 5. Start services
docker-compose up -d

# 6. Verify
curl /health
```

### Configuration Changes
| Setting | Old Value | New Value | Required |
|---------|-----------|-----------|----------|
| [SETTING] | [old] | [new] | [Yes/No] |

---

## API Changes

### New Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/v1/[resource]` | [Description] |

### Modified Endpoints
| Method | Endpoint | Change |
|--------|----------|--------|
| GET | `/api/v1/[resource]` | [Added field X] |

### Removed Endpoints
| Method | Endpoint | Alternative |
|--------|----------|-------------|
| DELETE | `/api/v1/[old]` | Use `/api/v1/[new]` |

---

## Database Changes

### Migrations
| Migration | Description | Reversible |
|-----------|-------------|------------|
| [001_add_column] | [Added X to Y table] | Yes |
| [002_create_table] | [Created Z table] | Yes |

### Data Changes
- [Description of any data transformations]

---

## Dependencies

### Updated
| Dependency | From | To | Notes |
|------------|------|----| ------|
| [package] | [X.Y.Z] | [A.B.C] | [Security fix] |

### Added
| Dependency | Version | Purpose |
|------------|---------|---------|
| [package] | [X.Y.Z] | [Purpose] |

### Removed
| Dependency | Reason |
|------------|--------|
| [package] | [No longer needed] |

---

## Compatibility

| Component | Minimum Version | Recommended |
|-----------|-----------------|-------------|
| Backend | [X.Y.Z] | [A.B.C] |
| Frontend | [X.Y.Z] | [A.B.C] |
| Mobile | [X.Y.Z] | [A.B.C] |
| Database | [X.Y] | [A.B] |

---

## Contributors

Thanks to the following contributors for this release:
- [Name] - [Contribution]
- [Name] - [Contribution]

---

## Support

For issues or questions:
- **Documentation:** [Link to docs]
- **Support:** [Support channel]
- **Issues:** [Issue tracker link]

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial release notes |

---

*Template follows ISO/IEC 29110-5-1-2 Release Notes format.*
