# Validation Plan

## Purpose
Verify RBAC works as intended and prevents escalation.

## Test Accounts
- Standard user: HL-User-JSmith (OU=UserAccounts -> StandardUsers)
- Helpdesk operator: HL-HD-Tech1 (OU=UserAccounts -> StandardUsers)
  - Member of HL-GG-Helpdesk-Operator-Users-AccountSupport
- Admin account (control): HL-ADM-JSmith (OU=Admins -> Tier2)

## Expected Results Matrix

### Allowed
- Helpdesk resets password for standard users in OU=UserAccounts: PASS
- Helpdesk forces password change at next logon: PASS

### Denied
- Helpdesk modifies group membership: FAIL
- Helpdesk resets admin account password in Admin OU: FAIL
- Helpdesk moves users between OUs: FAIL

## Validation Status
- Conceptual validation documented
- Full end-user testing can be performed by logging in as HL-HD-Tech1 and executing the tasks above
