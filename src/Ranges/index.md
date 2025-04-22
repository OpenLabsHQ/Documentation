# Lab Ranges

Ranges are deployed instances of lab environments created from templates.

## What are Ranges?

A range is a running instance of a lab environment that contains:

- Virtual private clouds (VPCs)
- Subnets
- Virtual machines
- Network configurations
- Other cloud resources

Ranges are created by deploying a template to a cloud provider.

## Range States

Ranges can be in various states:

- **Deploying**: The range is being created in the cloud provider
- **Running**: The range is active and accessible
- **Failed**: The range deployment encountered an error
- **Destroying**: The range is being removed
- **Destroyed**: The range has been completely removed

## Range Lifecycle

1. **Creation**: A template is deployed to create a range
2. **Configuration**: The range is configured according to the template
3. **Operation**: The range is used for training, testing, or other purposes
4. **Destruction**: The range is destroyed when no longer needed

## Managing Ranges

- [Deploying Ranges](./deploy.md): How to deploy a template to create a range
- [Managing Ranges](./manage.md): Monitoring, accessing, and controlling ranges

## Range Access

Depending on the configuration, ranges can be accessed via:

- SSH
- Web interfaces
- VPN connections
- Remote Desktop Protocol (RDP)
- Custom protocols

## Cost Considerations

Since ranges deploy actual cloud resources, they incur costs from cloud providers. Best practices include:

- Destroying ranges when not in use
- Using cost-effective instance types
- Setting up auto-shutdown policies
- Monitoring usage and costs
- Using spot instances where appropriate