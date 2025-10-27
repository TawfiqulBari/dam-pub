# DAM System - Public Releases

This repository contains public release artifacts for the DAM (Database Activity Monitoring) System.

## Download Latest Release ✅ **v1.0.8 RECOMMENDED**

```bash
# Download v1.0.8 (RECOMMENDED - includes password mismatch fix)
wget https://github.com/TawfiqulBari/dam-pub/releases/download/v1.0.8/dam-deployment-v1.0.8.tar.gz

# Verify checksum (optional but recommended)
echo "3948e6bfbbfedc02985b6015e197e03537db4e826825caa8a66cb3ca07c9baf2  dam-deployment-v1.0.8.tar.gz" | sha256sum -c

# Extract and install
tar -xzf dam-deployment-v1.0.8.tar.gz
cd dam-deployment-v1.0.8
sudo ./install.sh
```

**Why v1.0.8?**
- 🔧 **Critical Fix**: PostgreSQL password mismatch on fresh installations
- ✅ **Automatic cleanup** - Detects and removes stale .env files
- ✅ **Volume detection** - Prompts to clean existing PostgreSQL volumes
- ✅ **Clear warnings** - .env.template now has obvious placeholder values
- ✅ **Production-ready** - Permanent solution for password authentication errors

**What's New in v1.0.8:**
- Fixed password authentication failures on client installations
- Added `cleanup_existing_installation()` function to install.sh
- Improved .env.template with `__GENERATED_BY_INSTALLER__` placeholders
- Enhanced README with password troubleshooting section
- Safe for both new deployments and upgrades from all previous versions

## Upgrade from Previous Versions

**From v1.0.4:**
```bash
docker compose pull
docker compose up -d
# No migration needed - your database is already partitioned
```

**From v1.0.3d or earlier:**
```bash
# Backup your database first
docker compose exec postgres pg_dump -U dam_user dam_db > backup_$(date +%Y%m%d).sql

# Pull new images
docker compose pull

# Restart services
docker compose up -d

# Run migrations
docker compose exec api alembic upgrade head
```

## Docker Images

All Docker images are available on Docker Hub:
- `tawfiqulbari/dam-api:v1.0.8` (also: `latest`)
- `tawfiqulbari/dam-frontend:v1.0.8`
- `tawfiqulbari/dam-collector:v1.0.8`
- `tawfiqulbari/dam-parser:v1.0.8`
- `tawfiqulbari/dam-policy:v1.0.8`
- `tawfiqulbari/dam-alerts:v1.0.8`

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

- **v1.0.5** (2025-10-27) - Fresh installation fix ✅ **CURRENT**
- **v1.0.3d** (2025-10-26) - Idempotent migrations
- **v1.0.3c** (2025-10-26) - Migration fixes
- **v1.0.3b** (2025-10-26) - Zero-touch installation
- **v1.0.3a** (2025-10-26) - Initial public release

## License

Enterprise Database Activity Monitoring System
Copyright © 2025 Tawfiqul Bari
