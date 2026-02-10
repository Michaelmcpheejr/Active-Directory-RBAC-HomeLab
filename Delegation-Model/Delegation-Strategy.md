# Delegation Strategy

## Principles
- Delegate at the OU level, not domain wide
- Use least privilege
- Prefer supported delegation tasks in ADUC
- Keep admin OUs and server OUs restricted

## Implemented Delegation (Phase 4)

### Helpdesk Account Support Delegation
Target OU:
- OU=UserAccounts

Group:
- HL-GG-Helpdesk-Operator-Users-AccountSupport

Delegation Method:
- Active Directory Users and Computers
- Delegate Control Wizard
- Task: Reset user passwords and force password change at next logon

Notes:
- Fine-grained attribute delegation was not used to keep delegation supported and consistent through ADUC UI
- Helpdesk role is intentionally limited to user account support and cannot change group memberships or admin objects

## Guardrails
No delegation is applied to:
- OU=Admins
- OU=Servers
- OU=DomainControllers
