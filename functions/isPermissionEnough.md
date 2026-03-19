[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / isPermissionEnough

# Function: isPermissionEnough()

> **isPermissionEnough**(`requiredPermission`, `permission?`): `boolean`

Checks if a user's board permission level meets or exceeds a required permission level.

Compares permission levels using the Alleo permission hierarchy:
Viewer < Contributor < Editor < Owner (Developer is treated as Owner).
Use this to control feature access based on user permissions.

## Parameters

### requiredPermission

`BoardMemberPermission`

The minimum required permission level.

### permission?

`BoardMemberPermission` = `haptic.currentUser.permission`

The user's permission to check (defaults to current user).

## Returns

`boolean`

True if the user's permission is sufficient, false otherwise.

## Example

```typescript
// Check if current user can edit
if (isPermissionEnough(BoardMemberPermission.Editor)) {
  showEditButton();
}

// Check if specific permission allows action
const canDelete = isPermissionEnough(
  BoardMemberPermission.Owner,
  userPermission
);

// Viewers can always view
isPermissionEnough(BoardMemberPermission.Viewer); // Always true
```
