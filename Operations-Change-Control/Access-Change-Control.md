# Operations and Change Control

## Purpose
Ensure RBAC remains clean over time and access changes are auditable.

## Roles
- Requestor: manager or system owner
- Approver: manager for user role changes, IT leadership for admin roles
- Implementer: IT/IAM admin who applies RBAC groups
- Reviewer: security/IT lead who performs periodic reviews

## Change Types
- Standard: onboarding, basic role assignment
- Normal: tier changes, new admin account creation
- Emergency: break-glass access with follow-up review

## Minimum Logging Requirements
For every access change record:
- Who requested
- Who approved
- Who implemented
- What RBAC groups changed
- Date and business reason

## Access Reviews
- Admin accounts reviewed quarterly
- Users reviewed semi-annually
- Remove access that no longer matches role
