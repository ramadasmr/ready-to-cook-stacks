# ready-to-cook-stacks

A collection of **Docker Compose** configurations for various environments and use cases.  
Each YAML file defines a distinct setup — for quick, ready-to-use deployments.

## 📋 Table of Contents

- [Quick Start](#quick-start)
- [Usage](#usage)
- [Configuration](#configuration)
- [License](#license)

## 🚀 Quick Start

```bash
git clone https://github.com/ramadasmr/ready-to-cook-stacks.git
cd ready-to-cook-stacks/
docker compose -f <application>/single/docker-compose.yaml up -d
```

## 🧰 Requirements

- Docker (latest stable version recommended)
- Docker Compose v2 (`docker compose` CLI)

## 💻 Usage

### Starting a Service

```bash
# Start PostgreSQL
docker compose -f postgres/single/docker-compose.yaml up -d

# Start Redis
docker compose -f redis/single/docker-compose.yaml up -d

# Start Grafana
docker compose -f kafka/single/docker-compose.yaml up -d
```

### Stopping a Service 

```bash
# Stop PostgreSQL
docker compose -f postgres/single/docker-compose.yaml down

# Stop with volumes (removes data)
docker compose -f postgres/single/docker-compose.yaml down -v
```

### Viewing Logs

```bash
# View logs for a service
docker compose -f postgres/single/docker-compose.yaml logs -f
```

### Checking Service Status

```bash
# Check if service is running
docker compose -f postgres/single/docker-compose.yaml ps
```

## ⚙️ Configuration

Most services support environment variables for customization. You can set them in several ways:

### Using Environment Variables

```bash
# Set environment variables before starting
export POSTGRES_USER=myuser
export POSTGRES_PASSWORD=mypassword
docker compose -f postgres/single/docker-compose.yaml up -d
```

### Using .env File

Create a `.env` file in the service directory:

```bash
# postgres/single/.env
POSTGRES_USER=myuser
POSTGRES_PASSWORD=mypassword
POSTGRES_DB=mydatabase
```

### Default Values

All services include sensible defaults, so they can be started without any configuration:

```bash
# Start with defaults
docker compose -f postgres/single/docker-compose.yaml up -d
```

Default credentials and ports are documented in each `docker-compose.yaml` file.

## 🔧 Features

- ✅ **Ready to start** configurations
- ✅ **Health checks** for all services
- ✅ **Persistent volumes** for data storage
- ✅ **Environment variable** support
- ✅ **Network isolation** with named networks
- ✅ **Restart policies** for reliability
- ✅ **Latest stable** versions

## 📄 License

This project is licensed under the terms specified in the [LICENSE](LICENSE) file.

---

**Note**: These configurations are designed for development and testing. For production deployments, please review security settings, resource limits, and backup strategies.
