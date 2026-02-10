# Active Directory RBAC Program (hl.local)

## Purpose
Implement a simple, enterprise-style Role Based Access Control (RBAC) model in Active Directory that:
- Limits access by role and scope
- Prevents privilege creep
- Separates standard user identity from admin identity
- Supports Joiners, Movers, Leavers (JML) lifecycle operations

## Environment
- Domain: hl.local
- Core concepts used:
  - OU based organization
  - RBAC security groups
  - Delegation of control (OU scoped)
  - Tiered admin model (Tier 0, Tier 1, Tier 2)
  - JML lifecycle workflow

## Design Summary
- RBAC groups live in a single location for easy audit
- Delegation is OU scoped, not domain wide
- One person can have multiple accounts, one purpose per account:
  - Standard user account for daily work
  - Admin account for privileged tasks

## High-Level Outcomes
- Helpdesk role can support users without admin privileges
- Tier 2 admin role is limited to workstation administration
- Tier 1 admin accounts exist separately and receive permissions only when server RBAC is defined
- JML process enforces consistent onboarding, role changes, and offboarding
