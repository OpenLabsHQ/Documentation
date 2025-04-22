# Blueprints

Blueprints are the foundation of OpenLabs environments. They define the infrastructure components that make up a lab environment.

## What are Blueprints?

Blueprints are reusable definitions that describe cloud infrastructure components such as:

- Virtual Private Clouds (VPCs)
- Subnets
- Host machines
- Network configurations

Blueprints allow you to design complex lab environments once and deploy them repeatedly with consistent configurations.

## Blueprint Types

OpenLabs supports several blueprint types:

- **Range Blueprints**: Define the overall lab environment structure
- **VPC Blueprints**: Define Virtual Private Cloud configurations
- **Subnet Blueprints**: Define network subnet configurations 
- **Host Blueprints**: Define virtual machine configurations

## Blueprint Management

Blueprints can be:

- Created through the web interface or CLI
- Shared with other users
- Versioned and updated
- Deployed to create running lab environments

## Next Steps

- [Creating Blueprints](./create_blueprint.md)
- [Sharing Blueprints](./share_blueprint.md)