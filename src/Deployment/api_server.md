# Deploying the API Server

This guide covers the deployment of the OpenLabs API server component.

## Overview

The API server is the core backend component of OpenLabs, providing:

- REST API endpoints for all operations
- Database interaction
- Authentication and authorization
- Cloud provider integrations
- Template processing and deployment

## Prerequisites

- Linux server (Ubuntu 20.04+ recommended)
- Python 3.8+
- Docker (optional, for containerized deployment)
- PostgreSQL 13+ database
- Network access to cloud providers (AWS, Azure)

## Deployment Methods

### Docker Deployment (Recommended)

1. Clone the OpenLabs repository:
   ```bash
   git clone https://github.com/yourusername/openlabs.git
   cd openlabs/API
   ```

2. Configure environment variables in `.env` file:
   ```
   DATABASE_URL=postgresql://user:password@dbhost:5432/openlabs
   SECRET_KEY=your-secure-secret-key
   ALLOWED_ORIGINS=https://yourdomain.com
   ```

3. Start the API server using Docker Compose:
   ```bash
   docker-compose up -d
   ```

### Direct Deployment

1. Clone the OpenLabs repository:
   ```bash
   git clone https://github.com/yourusername/openlabs.git
   cd openlabs/API
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Configure environment variables:
   ```bash
   export DATABASE_URL="postgresql://user:password@dbhost:5432/openlabs"
   export SECRET_KEY="your-secure-secret-key"
   export ALLOWED_ORIGINS="https://yourdomain.com"
   ```

5. Start the API server:
   ```bash
   uvicorn src.app.main:app --host 0.0.0.0 --port 8000
   ```

## Configuration Options

### Database Configuration

The API server requires a PostgreSQL database:

```
DATABASE_URL=postgresql://user:password@dbhost:5432/openlabs
```

For production, use TLS:

```
DATABASE_URL=postgresql://user:password@dbhost:5432/openlabs?sslmode=require
```

### Security Configuration

Set a secure, random secret key:

```
SECRET_KEY=your-secure-random-key
```

Configure CORS allowed origins:

```
ALLOWED_ORIGINS=https://yourdomain.com,https://admin.yourdomain.com
```

### Cloud Provider Configuration

For AWS integration:

```
AWS_DEFAULT_REGION=us-west-2
```

For Azure integration:

```
AZURE_LOCATION=eastus
```

## First-Time Setup

After deployment, create the initial admin user:

```bash
# Using Docker
docker-compose exec api python -m src.scripts.create_admin --username admin --password secure_password --email admin@example.com

# Direct deployment
python -m src.scripts.create_admin --username admin --password secure_password --email admin@example.com
```

## Health Check

Verify the API server is running:

```bash
curl http://localhost:8000/api/v1/health/ping
```

Expected response:
```json
{"status":"ok","message":"pong"}
```

## Security Considerations

- Use HTTPS in production
- Set up a reverse proxy (Nginx, Traefik)
- Use strong, unique passwords
- Implement IP restrictions if possible
- Keep the server updated with security patches

## Monitoring

Monitor the API server using:

- Application logs
- System metrics (CPU, memory, disk)
- Request metrics

## Troubleshooting

Common issues:

- Database connection failures
- Permission issues with cloud providers
- Network connectivity problems

Check logs for detailed error messages:

```bash
# Docker logs
docker-compose logs api

# Direct deployment logs
tail -f api_server.log
```