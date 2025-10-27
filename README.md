# DAM System - Public Releases

This repository contains public release artifacts for the DAM (Database Activity Monitoring) System.

## Download Latest Release ✅ **v1.0.10 RECOMMENDED**

```bash
# Download v1.0.10 (RECOMMENDED - includes validation fix)
wget https://github.com/TawfiqulBari/dam-pub/releases/download/v1.0.10/dam-deployment-v1.0.10.tar.gz

# Verify checksum (optional but recommended)
echo "666a728958c990a1e623f5f829ece036241882b2ebee45851fec8a6d1da64e26  dam-deployment-v1.0.10.tar.gz" | sha256sum -c

# Extract and install
tar -xzf dam-deployment-v1.0.10.tar.gz
cd dam-deployment-v1.0.10
sudo ./install.sh
```

**Why v1.0.10?**
- 🔧 **Critical Fix**: install.sh validation bug resolved
- ✅ **Zero-touch deployment** - Migrations and RBAC seeding fully automated
- ✅ **No manual steps** - Everything handled by install.sh automatically
- ✅ **Production-ready** - True zero-intervention deployment on client VMs

**What's New in v1.0.9:**
- Fixed migration transaction aborts using direct SQL for metadata inspection
- Added PostgreSQL DO blocks for idempotent ENUM, index, and constraint operations
- Enhanced install.sh with migration health checks and automatic recovery
- Validates critical tables after migrations complete
- Safe for both new deployments and upgrades from all previous versions

## Upgrade from Previous Versions

**From v1.0.8 or earlier:**
```bash
# Backup your database first
docker compose exec postgres pg_dump -U dam_user dam_db > backup_$(date +%Y%m%d).sql

# Pull new images
docker compose pull

# Restart services
docker compose up -d

# Run migrations (now with automatic error recovery)
docker compose exec api alembic upgrade head
```

## Docker Images

All Docker images are available on Docker Hub (v1.0.10 uses v1.0.9 images):
- `tawfiqulbari/dam-api:v1.0.9` (also: `latest`)
- `tawfiqulbari/dam-frontend:v1.0.9`
- `tawfiqulbari/dam-collector:v1.0.9`
- `tawfiqulbari/dam-parser:v1.0.9`
- `tawfiqulbari/dam-policy:v1.0.9`
- `tawfiqulbari/dam-alerts:v1.0.9`

**Pull latest images:**
```bash
docker pull tawfiqulbari/dam-api:latest
docker pull tawfiqulbari/dam-frontend:latest
docker pull tawfiqulbari/dam-collector:latest
docker pull tawfiqulbari/dam-parser:latest
docker pull tawfiqulbari/dam-policy:latest
docker pull tawfiqulbari/dam-alerts:latest
```

## System Requirements

- **OS:** Ubuntu 20.04+, Debian 10+, CentOS 7+, RHEL 7+
- **RAM:** 8GB+ recommended (4GB minimum)
- **Disk:** 20GB+ free space
- **CPU:** 4+ cores recommended
- **Docker:** 20.10.0+
- **Docker Compose:** 2.0.0+

## Default Credentials

- **Username:** admin
- **Password:** AdminPass2025!

**⚠️ Change the admin password immediately after first login!**

## Features

- **Multi-Database Support:** Oracle, MySQL, PostgreSQL, MS SQL Server, MariaDB, MongoDB
- **122+ Compliance Rules:** PCI-DSS, SOX, GDPR, HIPAA, and more
- **Real-Time Monitoring:** Live session tracking and anomaly detection
- **Professional Dashboard:** Interactive charts and system metrics
- **Compliance Reports:** PDF/CSV export for 7 compliance frameworks
- **SIEM Integration:** Splunk HEC support
- **ML/UEBA:** Isolation Forest anomaly detection
- **RBAC:** Role-based access control with JWT authentication

## Documentation

- **Installation Guide:** See release notes for detailed instructions
- **API Documentation:** Available at `/docs` endpoint after installation
- **Support:** https://github.com/TawfiqulBari/dam-pub/issues

## Version History

- **v1.0.10** (2025-10-27) - install.sh validation fix ✅ **CURRENT**
- **v1.0.9** (2025-10-27) - Migration transaction fixes
- **v1.0.8** (2025-10-27) - PostgreSQL password mismatch fix
- **v1.0.7** (2025-10-27) - Table partitioning fix
- **v1.0.6** (2025-10-27) - CORS and email fixes
- **v1.0.5** (2025-10-27) - Fresh installation fix
- **v1.0.4** (2025-10-26) - Idempotent migrations
- **v1.0.3d** (2025-10-26) - Migration improvements
- **v1.0.3c** (2025-10-26) - Migration fixes
- **v1.0.3b** (2025-10-26) - Zero-touch installation
- **v1.0.3a** (2025-10-26) - Initial public release

## License

Enterprise Database Activity Monitoring System
Copyright © 2025 Tawfiqul Bari
