# Sharing Blueprints

This guide covers how to share blueprints with other users and manage blueprint permissions.

## Blueprint Sharing Overview

Sharing blueprints allows team members to:
- Reuse infrastructure designs
- Collaborate on blueprint development
- Deploy consistent environments

## Sharing Methods

### Via Web Interface

1. Navigate to Blueprints
2. Select the blueprint you want to share
3. Click "Manage Permissions"
4. Add users or workspaces to share with
5. Set permission levels
6. Save changes

### Via CLI

```bash
# Share a blueprint with a user
openlab blueprint permission add --blueprint-id <blueprint-id> --user <username> --permission VIEW

# Share a blueprint with a workspace
openlab blueprint permission add --blueprint-id <blueprint-id> --workspace <workspace-id> --permission EDIT
```

## Permission Levels

Blueprints support different permission levels:

- **OWNER**: Full control, including deletion
- **EDIT**: Can modify the blueprint
- **DEPLOY**: Can deploy but not modify
- **VIEW**: Can only view the blueprint

## Managing Permissions

### Adding Permissions

```bash
# Give a user edit permission
openlab blueprint permission add --blueprint-id <blueprint-id> --user <username> --permission EDIT
```

### Updating Permissions

```bash
# Update a user's permission
openlab blueprint permission update --blueprint-id <blueprint-id> --user <username> --permission DEPLOY
```

### Removing Permissions

```bash
# Remove a user's access
openlab blueprint permission remove --blueprint-id <blueprint-id> --user <username>
```

### Listing Permissions

```bash
# List all permissions for a blueprint
openlab blueprint permission list --blueprint-id <blueprint-id>
```

## Workspace Sharing

Sharing with workspaces gives access to all workspace members:

```bash
# Share with a workspace
openlab blueprint permission add --blueprint-id <blueprint-id> --workspace <workspace-id> --permission VIEW
```

Workspace members will have access based on:
1. The permission level assigned to the workspace
2. Their role within the workspace

## Blueprint Visibility

Blueprints can have different visibility levels:

- **Private**: Only visible to users with explicit permissions
- **Workspace**: Visible to all members of specified workspaces
- **Public**: Visible to all OpenLabs users

Change visibility via:

```bash
# Make a blueprint visible to workspace members
openlab blueprint update <blueprint-id> --visibility WORKSPACE

# Make a blueprint private
openlab blueprint update <blueprint-id> --visibility PRIVATE
```

## Best Practices

- Regularly audit blueprint permissions
- Use workspaces for team sharing
- Grant the minimum necessary permissions
- Document sharing decisions
- Consider creating blueprint copies for significant modifications
- Use clear naming to indicate shared blueprints