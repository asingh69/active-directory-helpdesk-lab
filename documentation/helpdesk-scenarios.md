# Active Directory Help Desk Lab - Troubleshooting Scenarios

## Scenario 1 - Password Reset

### Issue
A user forgot their password and was unable to sign in to the domain.

### Diagnosis
Located the user account in Active Directory Users and Computers and confirmed the account was active.

### Resolution
Reset the user's password and enabled "User must change password at next logon."

### Tools Used
- Active Directory Users and Computers
- Windows Server 2025
- Windows 11 client

---

## Scenario 2 - Account Lockout

### Issue
A user account became locked after multiple failed login attempts.

### Diagnosis
Checked the user's account status in Active Directory Users and Computers and confirmed the account was locked.

### Resolution
Unlocked the user account and verified that the user could successfully sign in again.

### Tools Used
- Active Directory Users and Computers
- Group Policy
- Windows 11 client

---

## Scenario 3 - Disabled User Account

### Issue
A user account needed to be disabled as part of an offboarding process.

### Diagnosis
Located the user account inside the correct departmental OU.

### Resolution
Disabled the account and moved it to the Disabled Users OU.

### Tools Used
- Active Directory Users and Computers

---

## Scenario 4 - User Re-enabled

### Issue
A previously disabled account needed to be restored.

### Diagnosis
Located the disabled user in the Disabled Users OU.

### Resolution
Re-enabled the account and moved the user back into the correct department OU.

### Tools Used
- Active Directory Users and Computers

---

## Scenario 5 - Group Membership Change

### Issue
A user changed departments and required different access permissions.

### Diagnosis
Checked the user's existing group memberships.

### Resolution
Removed the user from the old department security group and added the user to the new department security group.

### Tools Used
- Active Directory Users and Computers
- Security Groups

---

## Scenario 6 - Group Policy Application

### Issue
A user policy needed to be applied to domain users.

### Diagnosis
Created and linked a Group Policy Object to the Users OU and verified that the user account was located inside the correct OU.

### Resolution
Configured the policy, forced a Group Policy update using gpupdate /force, and verified the applied policy using gpresult /r.

### Tools Used
- Group Policy Management
- gpupdate
- gpresult
- Windows 11 client

---

## Scenario 7 - DNS Misconfiguration

### Issue
The Windows 11 client could not resolve the domain name.

### Diagnosis
Used ipconfig /all and nslookup to identify that the client was configured with an incorrect DNS server address.

### Resolution
Changed the preferred DNS server back to the domain controller at 10.10.10.10, flushed the DNS cache, and confirmed successful domain name resolution.

### Commands Used
- ipconfig /all
- nslookup helpdesklab.local
- ipconfig /flushdns
- ping HD-DC01

### Tools Used
- Windows 11 network settings
- Command Prompt
- DNS

---

## Scenario 8 - Active Directory Verification with PowerShell

### Issue
Needed to verify users, groups, and account information from the command line.

### Diagnosis
Used PowerShell Active Directory cmdlets to query directory objects.

### Resolution
Successfully retrieved users, groups, and group membership information from Active Directory.

### Commands Used
- Get-ADUser -Filter *
- Get-ADGroup -Filter *
- Get-ADUser ecarter -Properties *
- Get-ADPrincipalGroupMembership ecarter

### Tools Used
- Windows PowerShell
- Active Directory PowerShell module

---

## Skills Demonstrated

- Active Directory administration
- User account management
- Password resets
- Account lockout troubleshooting
- User onboarding and offboarding
- Security group management
- Group Policy
- DNS troubleshooting
- Windows 11 domain support
- PowerShell
- Help Desk documentation