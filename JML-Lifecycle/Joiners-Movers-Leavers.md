# Joiners, Movers, Leavers (JML)

## Core Rule
OU placement represents lifecycle state.
Group membership represents access.

## Joiner (New Hire)
1. Create standard account in:
   - OU=UserAccounts -> OU=StandardUsers
2. Assign baseline attributes:
   - Department, title, manager, UPN
3. Add RBAC group memberships based on role
4. Create separate admin account only if required:
   - OU=Admins -> appropriate tier
5. Do not grant direct permissions to users

## Mover (Role Change)
1. Standard account stays in StandardUsers
2. Update RBAC group memberships:
   - Remove old role groups
   - Add new role groups
3. If admin scope changes, update admin account tier and groups

## Leaver (Termination)
Order matters:
1. Disable standard and admin accounts immediately
2. Remove RBAC group memberships (leave only Domain Users)
3. Move accounts to:
   - OU=UserAccounts -> OU=DisabledUsers
4. Retain for audit per policy before deletion

## Contractors
- Contractors are created in OU=UserAccounts -> Contractors
- Offboarding follows the same leaver process
