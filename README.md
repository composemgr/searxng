## 👋 Welcome to searxng 🚀

Privacy-respecting metasearch engine

## 📋 Description

Privacy-respecting metasearch engine

## 🚀 Services

- **app**: docker.io/searxng/searxng:latest
- **valkey**: docker.io/valkey/valkey:8-alpine

## 📦 Installation

### Option 1: Quick Install
```bash
curl -q -LSsf "https://raw.githubusercontent.com/composemgr/searxng/main/docker-compose.yaml" -o compose.yml
```

### Option 2: Git Clone
```bash
git clone "https://github.com/composemgr/searxng" ~/.local/srv/docker/searxng
cd ~/.local/srv/docker/searxng
docker compose up -d
```

### Option 3: Using composemgr
```bash
composemgr install searxng
```

## 🔧 Configuration

### Environment Variables

```shell
BASE_HOST_NAME=search.local
SECRET_KEY=change_me_in_production
UWSGI_WORKERS=4
UWSGI_THREADS=4
SEARXNG_DEBUG=false
SEARXNG_INSTANCE_NAME=SearXNG
SEARXNG_SAFE_SEARCH=2
SEARXNG_AUTOCOMPLETE=duckduckgo
SEARXNG_LIMITER=true
SEARXNG_IMAGE_PROXY=true
# ... see docker-compose.yaml for more
```

See `docker-compose.yaml` for complete list of configurable options.

## 🌐 Access

- **Web Interface**: http://172.17.0.1:59089

## 📂 Volumes

- `./rootfs/config/searngx` - Data storage
- `./rootfs/data/db/valkey` - Data storage

## 🔐 Security

- Change all default passwords before deploying to production
- Use strong secrets for all authentication tokens
- Configure HTTPS using a reverse proxy (nginx, traefik, caddy)
- Regularly update Docker images for security patches
- Backup your data regularly

## 🔍 Logging

```shell
docker compose logs -f app
```

## 🛠️ Management

```bash
# Start services
docker compose up -d

# Stop services
docker compose down

# Update to latest images
docker compose pull && docker compose up -d

# View logs
docker compose logs -f

# Restart services
docker compose restart
```

## 📋 Requirements

- Docker Engine 20.10+
- Docker Compose V2+

## 🤝 Author

🤖 casjay: [Github](https://github.com/casjay) 🤖  
🦄 composemgr: [Github](https://github.com/composemgr) 🦄
