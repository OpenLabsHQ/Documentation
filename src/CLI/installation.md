# Installing the OpenLabs CLI

This guide covers the installation and initial setup of the OpenLabs CLI.

## System Requirements

- Operating Systems:
  - Linux (recommended)
  - macOS
  - Windows 10/11
- Disk Space: 50 MB minimum
- Network: Internet connection for API server communication

## Installation Methods

### Binary Installation (Recommended)

1. Download the latest binary for your platform from the [releases page](https://github.com/yourusername/openlabs-cli/releases).

2. For Linux/macOS:
   ```bash
   # Make the binary executable
   chmod +x openlab

   # Move to a directory in your PATH
   sudo mv openlab /usr/local/bin/
   ```

3. For Windows:
   - Download the Windows executable (.exe)
   - Add it to a location in your PATH or run it directly

4. Verify installation:
   ```bash
   openlab --version
   ```

### Building from Source

Requirements:
- Go 1.19 or later
- Git

Steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/openlabs-cli.git
   cd openlabs-cli
   ```

2. Build the CLI:
   ```bash
   make build
   ```

3. Install the binary:
   ```bash
   make install
   ```

4. Verify installation:
   ```bash
   openlab --version
   ```

## Initial Configuration

After installation, configure the CLI to connect to your OpenLabs server:

```bash
openlab config set --server-url https://api.youropenlabs.com
```

## Authentication

Log in to your OpenLabs account:

```bash
openlab login
```

You'll be prompted for your username and password.

Alternatively, you can use a token:

```bash
openlab login --token your-api-token
```

## Configuration File

The CLI configuration is stored in:

- Linux/macOS: `~/.openlab/config.yaml`
- Windows: `%USERPROFILE%\.openlab\config.yaml`

Example configuration:

```yaml
server:
  url: https://api.youropenlabs.com
  
auth:
  token: your-api-token
  
default_workspace: my-workspace

output_format: json
```

## Environment Variables

You can also configure the CLI with environment variables:

```bash
export OPENLAB_SERVER_URL=https://api.youropenlabs.com
export OPENLAB_TOKEN=your-api-token
```

## Troubleshooting

### Connection Issues

If you have trouble connecting to the server:

```bash
# Verify configuration
openlab config get

# Test server connection
openlab health ping
```

### Authentication Issues

If you have authentication problems:

```bash
# Re-login
openlab login

# Check authentication status
openlab user info
```

## Next Steps

After installation and configuration:

- [CLI Command Reference](./commands.md)
- [User Management](./users.md)
- [Working with Templates](./templates.md)
- [Deploying Ranges](./ranges.md)