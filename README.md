# DAM System - Public Releases

This repository contains public release artifacts for the DAM (Database Activity Monitoring) System.

## Download Latest Release

```bash
# Download v1.0.3
wget https://github.com/TawfiqulBari/dam-pub/releases/download/v1.0.3/dam-deployment-v1.0.3.tar.gz

# Verify checksum
echo "6bc0dcd83fda220aeb04386f6222ae711069ceeec8794ad028fea3e95d019ad9  dam-deployment-v1.0.3.tar.gz" | sha256sum -c

# Extract and install
tar -xzf dam-deployment-v1.0.3.tar.gz
cd dam-deployment-v1.0.3
sudo ./install.sh
```

## Docker Images

All Docker images are available on Docker Hub:
- `tawfiqulbari/dam-api:v1.0.3`
- `tawfiqulbari/dam-frontend:v1.0.3`
- `tawfiqulbari/dam-collector:v1.0.3`
- `tawfiqulbari/dam-parser:v1.0.3`
- `tawfiqulbari/dam-policy:v1.0.3`
- `tawfiqulbari/dam-alerts:v1.0.3`

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
