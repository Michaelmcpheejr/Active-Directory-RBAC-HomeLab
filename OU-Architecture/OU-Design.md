# OU Architecture (hl.local)

## Goals
- Separate objects by function (users, groups, workstations, servers, admins)
- Make delegation safe and scoped
- Make auditing simple

## OU Layout
- OU=UserAccounts
  - OU=StandardUsers
  - OU=Contractors
  - OU=DisabledUsers
- OU=Workstations
- OU=Servers
  - OU=DomainControllers
  - OU=MemberServers
  - OU=FileServers
- OU=Admins
  - OU=Tier0
  - OU=Tier1
  - OU=Tier2
- OU=Groups
  - OU=SecurityGroups
  - OU=DistributionGroups
- OU=ServiceAccounts
- OU=Quarantine

## OU Categories
### Delegation Eligible
- UserAccounts
- Workstations
- Quarantine

### Restricted (No delegation)
- Admins
- Servers
- DomainControllers

### Structural (Organizational)
- Groups
- ServiceAccounts

## Default Container Redirection
Redirect new objects away from default containers:
- New users go to OU=UserAccounts
- New computers go to OU=Quarantine

Commands used:
- redirusr "OU=UserAccounts,DC=hl,DC=local"
- redircmp "OU=Quarantine,DC=hl,DC=local"
