# Blueprint Operations with CLI

This guide covers using the OpenLabs CLI to work with blueprints.

## Listing Blueprints

List all blueprints you have access to:

```bash
# List all blueprints
openlab blueprint list

# List blueprints with pagination
openlab blueprint list --limit 10 --offset 20

# List blueprints in a specific workspace
openlab blueprint list --workspace <workspace-id>

# Filter blueprints by name
openlab blueprint list --filter "name=My Blueprint"
```

## Creating Blueprints

Create different types of blueprints:

```bash
# Create a range blueprint
openlab blueprint create range --name "Web Application" --description "Complete web app stack" --provider aws --region us-west-2

# Create a VPC blueprint
openlab blueprint create vpc --range-id <range-id> --name "App VPC" --cidr 10.0.0.0/16

# Create a subnet blueprint
openlab blueprint create subnet --vpc-id <vpc-id> --name "App Subnet" --cidr 10.0.1.0/24 --public true

# Create a host blueprint
openlab blueprint create host --subnet-id <subnet-id> --name "Web Server" --os ubuntu --type t3.medium --disk 40
```

## Viewing Blueprint Details

Get detailed information about blueprints:

```bash
# Get range blueprint details
openlab blueprint get range <blueprint-id>

# Get VPC blueprint details
openlab blueprint get vpc <vpc-id>

# Get subnet blueprint details
openlab blueprint get subnet <subnet-id>

# Get host blueprint details
openlab blueprint get host <host-id>
```

## Updating Blueprints

Modify existing blueprints:

```bash
# Update a range blueprint
openlab blueprint update range <blueprint-id> --name "Updated Web App" --description "Updated description"

# Update a VPC blueprint
openlab blueprint update vpc <vpc-id> --name "New VPC Name" --cidr 10.1.0.0/16

# Update a subnet blueprint
openlab blueprint update subnet <subnet-id> --name "New Subnet Name" --cidr 10.1.1.0/24

# Update a host blueprint
openlab blueprint update host <host-id> --name "New Host Name" --os ubuntu --type t3.large
```

## Deleting Blueprints

Remove blueprints from the system:

```bash
# Delete a range blueprint (removes all child resources)
openlab blueprint delete range <blueprint-id>

# Delete a VPC blueprint
openlab blueprint delete vpc <vpc-id>

# Delete a subnet blueprint
openlab blueprint delete subnet <subnet-id>

# Delete a host blueprint
openlab blueprint delete host <host-id>
```

## Exporting and Importing Blueprints

Share blueprints between environments:

```bash
# Export a blueprint to a file
openlab blueprint export <blueprint-id> --output my-blueprint.json

# Import a blueprint from a file
openlab blueprint import --file my-blueprint.json
```

## Managing Blueprint Permissions

Control access to blueprints:

```bash
# List permissions
openlab blueprint permission list --blueprint-id <blueprint-id>

# Add permission
openlab blueprint permission add --blueprint-id <blueprint-id> --user <username> --permission EDIT

# Update permission
openlab blueprint permission update --blueprint-id <blueprint-id> --user <username> --permission VIEW

# Remove permission
openlab blueprint permission remove --blueprint-id <blueprint-id> --user <username>
```

## Blueprint Validation

Check blueprint validity before deployment:

```bash
# Validate a blueprint
openlab blueprint validate <blueprint-id>

# Get detailed validation report
openlab blueprint validate <blueprint-id> --detailed
```

## Working with Blueprint Variables

Manage variables for customizable deployments:

```bash
# List variables
openlab blueprint vars list <blueprint-id>

# Add a variable
openlab blueprint vars add <blueprint-id> --name "instance_type" --default "t3.medium" --description "EC2 instance type"

# Remove a variable
openlab blueprint vars remove <blueprint-id> --name "instance_type"
```