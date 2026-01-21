# Azure Entra ID — IAM, MFA, Least Privilege

## Overview
This lab demonstrates hands-on implementation of **Identity and Access Management (IAM)** using **Microsoft Entra ID**.  
The focus is on **user management, MFA enforcement, and least-privilege validation** in a real-world constrained environment.

---

## Environment
- Platform: Microsoft Entra ID (formerly Azure Active Directory)
- Tenant type: School-managed Microsoft 365 tenant
- Accounts created:
  - `lab-admin` — administrative test account
  - `lab-user` — standard user account
- Noted constraint:
  - School-managed tenant restricts full role assignment capabilities, even for Global Administrators

---

## Objectives
- Create and manage Entra ID users
- Enforce Multi-Factor Authentication (MFA)
- Validate least-privilege access
- Identify and document tenant-based security limitations

---

## Lab Steps

### 1. User Creation
- Created two users:
  - `lab-admin`
  - `lab-user`
- Verified successful login for both accounts
- Secured temporary credentials and forced password change on first login

---

### 2. MFA Configuration
- Enabled Microsoft Authenticator as an authentication method
- Required MFA registration for both users
- Verified MFA enforcement during login

---

### 3. Least Privilege Enforcement
- Identified that `lab-user` was a member of an administrative group (`MSFT`)
- Removed `lab-user` from the group to eliminate inherited elevated permissions
- Confirmed `lab-user` could no longer perform administrative actions

---

### 4. Permission Validation

#### lab-user (Standard User)
- Can sign in successfully
- Can view limited directory information
- Cannot:
  - Add or remove role assignments
  - Modify users
  - Access security or privileged role settings
- Administrative actions are disabled or unavailable

#### lab-admin (Admin User)
- Can create and manage users
- Can enforce MFA policies
- Role assignment actions are restricted due to school tenant limitations

---

## Observations & Lessons Learned
- IAM permissions can be inherited through group membership
- Removing users from privileged groups is critical to enforcing least privilege
- Tenant-level restrictions are common in enterprise, education, and regulated environments
- Even with administrative titles, actual permissions may be limited by organizational policy
- Proper documentation of constraints is part of real-world security work

---

## Security Concepts Demonstrated
- Identity and Access Management (IAM)
- Multi-Factor Authentication (MFA)
- Least Privilege
- Group-based access control
- Tenant-level security restrictions

---

## Resume / Interview Summary
Implemented identity and access management in Microsoft Entra ID by creating administrative and standard users, enforcing multi-factor authentication, auditing group-based privileges, and validating least-privilege access. Adapted lab execution to a school-managed tenant with restricted role assignment capabilities, reflecting real-world enterprise constraints.

---

## Screenshots (Optional)
Add screenshots here if desired:
- User creation
- MFA registration prompt
- lab-user restricted access view
- Group membership removal

---

## Notes
This lab was conducted in a constrained tenant environment to mirror real-world organizational security controls.  
Future iterations will be replicated in a fully unrestricted tenant for comparison.


