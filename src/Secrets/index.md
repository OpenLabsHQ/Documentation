# Cloud Provider Secrets

OpenLabs requires credentials to deploy and manage infrastructure on cloud providers. These credentials are stored securely as secrets in the OpenLabs platform.

## Overview

Secrets are required to:

- Deploy lab environments to cloud providers
- Manage cloud resources
- Authenticate with cloud provider APIs

## Supported Cloud Providers

OpenLabs currently supports secrets for the following cloud providers:

- [AWS](./aws_secrets.md)
- [Azure](./azure_secrets.md)

## Security Considerations

OpenLabs implements several security measures for handling cloud credentials:

- Credentials are encrypted at rest
- Credentials are never exposed in logs or API responses
- Access to credentials is restricted to authorized users only
- Credentials are never shared between users

## Best Practices

- Use dedicated IAM roles or service accounts with limited permissions
- Regularly rotate credentials
- Monitor usage for unusual activity
- Use the principle of least privilege when creating cloud credentials

## Managing Secrets

You can manage your cloud provider secrets through:

- The OpenLabs web interface
- The [OpenLabs CLI](../CLI/secrets.md)

```bash
# Add AWS secrets using the CLI
openlab secrets aws add --access-key AKIA... --secret-key abcd1234...
```