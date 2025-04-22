# Getting Started

## Installation

### API Server

```bash
git clone https://github.com/OpenLabsHQ/API
cd API
docker compose up -d
```

### CLI Tool

#### Download Binary
You can download the pre-built binary for your platform from the releases page.

#### Build from Source
```bash
git clone https://github.com/OpenLabsHQ/CLI
cd CLI
go build -o openlabs main.go
```

## Configuration

### CLI Configuration

The CLI uses a JSON configuration file located at `~/.openlabs/config.json`:

```json
{
  "api_url": "http://localhost:8000",
  "auth_token": "",
  "enc_key": ""
}
```

You can set configuration values using the config commands:

```bash
# View current configuration
openlabs config get

# Set API URL
openlabs config set-api-url http://localhost:8000

# Set auth token manually
openlabs config set-token [your-token]

# Set encryption key
openlabs config set-enckey [your-key]
```

## Authentication

```bash
# Register a new user
openlabs user register

# Login
openlabs user login
```
