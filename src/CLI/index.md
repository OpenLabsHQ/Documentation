# OpenLabs CLI

The OpenLabs Command Line Interface (CLI) provides a powerful tool for interacting with the OpenLabs platform from your terminal.

## Overview

The CLI allows you to:

- Manage your OpenLabs account
- Create and deploy lab environments
- Work with templates
- Manage workspaces and users
- Configure cloud provider credentials

## Installation

For installation instructions, see the [Installation Guide](./installation.md).

## Basic Usage

```bash
openlab [command] [subcommand] [flags]
```

For example:

```bash
# List all templates
openlab template list

# Deploy a lab environment
openlab range deploy --template-id abc123

# Get information about your user
openlab user info
```

## Available Commands

- [User Management](./users.md): Managing users and authentication
- [Template Operations](./templates.md): Working with templates
- [Range Operations](./ranges.md): Deploying and managing lab environments
- [Secrets Management](./secrets.md): Managing cloud provider credentials
- [Configuration](./config.md): CLI configuration
- [Plugins](./plugins.md): Extending CLI functionality

## Getting Help

To get help for any command, add the `--help` flag:

```bash
openlab --help
openlab template --help
```