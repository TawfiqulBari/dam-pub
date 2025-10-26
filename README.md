# DAM System - Public Releases

This repository contains public release artifacts for the DAM (Database Activity Monitoring) System.

## Download Latest Release ✅ **v1.0.3d RECOMMENDED**

```bash
# Download v1.0.3d (RECOMMENDED - includes idempotent migration fix)
wget https://github.com/TawfiqulBari/dam-pub/releases/download/v1.0.3d/dam-deployment-v1.0.3d.tar.gz

# Extract and install
tar -xzf dam-deployment-v1.0.3d.tar.gz
cd dam-deployment-v1.0.3d
sudo ./install.sh
```

**Why v1.0.3d?**
- ✅ **Idempotent migrations** - Safe for repeat installations
- ✅ **No 'relation already exists' errors** - Fixed from v1.0.3c
- ✅ **Fixed migration chain** - No KeyError issues
- ✅ **Generic nginx** - Works with any domain/IP
- ✅ **Optional SSL setup** - Post-installation via `setup_ssl.sh`

**Previous Versions:**
- v1.0.3c - ⚠️ Not idempotent (fails on repeat installations)
- v1.0.3b - ❌ Broken migration chain
- v1.0.3a - ❌ Broken docker-compose references
- v1.0.3 - Old release (superseded by v1.0.3d)

## Docker Images

All Docker images are available on Docker Hub:
- `tawfiqulbari/dam-api:v1.0.3d` (also: v1.0.3, latest)
- `tawfiqulbari/dam-frontend:v1.0.3d`
- `tawfiqulbari/dam-collector:v1.0.3d`
- `tawfiqulbari/dam-parser:v1.0.3d`
- `tawfiqulbari/dam-policy:v1.0.3d`
- `tawfiqulbari/dam-alerts:v1.0.3d`

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

## License

Enterprise Database Activity Monitoring System  
Copyright © 2025 Tawfiqul Bari
