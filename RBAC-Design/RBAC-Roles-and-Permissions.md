# RBAC Roles and Permissions

## Naming Standard
HL-GG-[Role]-[Scope]-[Action]

Examples:
- HL-GG-Helpdesk-Operator-Users-AccountSupport
- HL-GG-IT-Admin-Workstations-LocalAdmin

## Group Placement Rule
All RBAC security groups are stored in:
- OU=Groups -> OU=SecurityGroups

## RBAC Roles

### 1) Helpdesk: Account Support
Group:
- HL-GG-Helpdesk-Operator-Users-AccountSupport

Scope:
- OU=UserAccounts (StandardUsers, Contractors as allowed by policy)

Allowed:
- Reset passwords
- Unlock accounts (operationally aligned with account support)
- Force password change at next logon

Denied:
- Modify group membership
- Create/delete users
- Move users between OUs
- Manage admin or service accounts

### 2) Tier 2: Workstation Local Admin
Group:
- HL-GG-IT-Admin-Workstations-LocalAdmin

Scope:
- Workstations only (intended to apply to OU=Workstations)

Allowed:
- Local admin on workstations
- Install software as part of workstation administration

Denied:
- Server administration
- Domain controller administration
- Domain Admin membership

### 3) Audit: Directory Read (optional role)
Group:
- HL-GG-Audit-Read-AD-DirectoryRead

Scope:
- Read-only visibility (domain or selected OUs)

Allowed:
- Read users, groups, computers
- Read memberships and structure

Denied:
- Any write operation
- Any password or privilege changes
