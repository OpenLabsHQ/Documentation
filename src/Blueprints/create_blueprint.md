# Creating Blueprints

This guide walks through the process of creating blueprints in OpenLabs.

## Blueprint Hierarchy

OpenLabs blueprints have a hierarchical structure:

1. **Range Blueprint**: The top-level container
   - Contains VPC Blueprints
     - Contains Subnet Blueprints
       - Contains Host Blueprints

## Creating a Range Blueprint

A range blueprint is the foundation for a lab environment.

### Via Web Interface

1. Navigate to Blueprints > Create
2. Enter basic information:
   - Name
   - Description
   - Provider (AWS, Azure)
   - Region
3. Define networking parameters
4. Add VPCs, subnets, and hosts
5. Review and create the blueprint

### Via CLI

```bash
# Create a range blueprint
openlab blueprint create range --name "My Lab" --description "Test environment" --provider aws --region us-west-2
```

## Adding VPC Blueprints

VPCs (Virtual Private Clouds) isolate network resources.

### Via Web Interface

1. In blueprint creation, select "Add VPC"
2. Define VPC properties:
   - Name
   - CIDR block (e.g., 10.0.0.0/16)
   - Additional VPC settings

### Via CLI

```bash
# Create a VPC blueprint
openlab blueprint create vpc --range-id <range-id> --name "Main VPC" --cidr 10.0.0.0/16
```

## Adding Subnet Blueprints

Subnets segment your VPC network.

### Via Web Interface

1. Select a VPC and click "Add Subnet"
2. Define subnet properties:
   - Name
   - CIDR block (e.g., 10.0.1.0/24)
   - Public or private
   - Availability zone

### Via CLI

```bash
# Create a subnet blueprint
openlab blueprint create subnet --vpc-id <vpc-id> --name "Web Subnet" --cidr 10.0.1.0/24 --public true
```

## Adding Host Blueprints

Host blueprints define virtual machines in your lab.

### Via Web Interface

1. Select a subnet and click "Add Host"
2. Define host properties:
   - Name
   - Operating system
   - Instance type
   - Disk size
   - Software packages
   - Configuration scripts

### Via CLI

```bash
# Create a host blueprint
openlab blueprint create host --subnet-id <subnet-id> --name "Web Server" --os ubuntu --type t3.medium --disk 40
```

## Advanced Blueprint Features

### Custom Scripts

Add custom scripts to run during host provisioning:

```bash
# Add a script to a host blueprint
openlab blueprint update host <host-id> --add-script "path/to/script.sh"
```

### Blueprint Variables

Define variables for flexible deployments:

```bash
# Add a variable to a blueprint
openlab blueprint update range <range-id> --add-var "instance_type=t3.medium"
```

## Exporting and Importing Blueprints

Share blueprints between users or environments:

```bash
# Export a blueprint
openlab blueprint export <blueprint-id> --output my-blueprint.json

# Import a blueprint
openlab blueprint import --file my-blueprint.json
```

## Blueprint Validation

Validate blueprints before deployment:

```bash
# Validate a blueprint
openlab blueprint validate <blueprint-id>
```

## Best Practices

- Use descriptive names for all components
- Include detailed descriptions
- Define sensible network CIDR ranges
- Document blueprint purpose and requirements
- Test blueprints with small deployments first
- Use the smallest instance types that meet your needs