# Deploying Lab Ranges

This guide covers the process of deploying a blueprint to create a running lab environment (range).

## Prerequisites

Before deploying a range, ensure you have:

1. A valid OpenLabs account
2. Access to a workspace
3. [Cloud provider credentials](../Secrets/index.md) configured
4. A blueprint to deploy

## Deployment Methods

### Web Interface

1. Navigate to the Blueprints page
2. Select the blueprint you want to deploy
3. Click the "Deploy" button
4. Enter a name for your range
5. Select deployment options:
   - Cloud provider region
   - Instance types (if customizable)
   - Deployment parameters
6. Click "Deploy" to start the deployment

### CLI

Deploy a range using the OpenLabs CLI:

```bash
# Deploy with default parameters
openlab range deploy --blueprint-id <blueprint-id> --name "My Range"

# Deploy with custom parameters
openlab range deploy --blueprint-id <blueprint-id> --name "My Range" --region us-west-2 --param key=value
```

## Deployment Process

1. OpenLabs validates the blueprint and parameters
2. Cloud resources are provisioned according to the blueprint
3. Network configuration is applied
4. Virtual machines are created and configured
5. Post-deployment scripts are executed
6. The range becomes available when all resources are provisioned

## Monitoring Deployment Progress

### Web Interface

1. Navigate to the Ranges page
2. Find your range in the list
3. Monitor the status and deployment logs

### CLI

```bash
# Get range status
openlab range status <range-id>

# Get range logs
openlab range logs <range-id>
```

## Troubleshooting Deployment Issues

If your deployment fails:

1. Check the deployment logs for error messages
2. Verify cloud provider credentials are valid
3. Ensure you have sufficient quota in your cloud account
4. Check network connectivity to the cloud provider
5. Verify blueprint validity

## Post-Deployment

After successful deployment:

1. Access information will be available in the range details
2. Use the access methods specified in the blueprint
3. Connect to resources using provided credentials
4. Begin using your lab environment

## Destroying Ranges

When you're done with a range, destroy it to avoid unnecessary costs:

```bash
# Using the CLI
openlab range destroy <range-id>
```

Or use the "Destroy" button in the web interface.