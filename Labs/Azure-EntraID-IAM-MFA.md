# Cloud Security Labs — IAM, MFA & Least Privilege in Azure Entra ID

Hands-on implementation of Identity and Access Management (IAM) using Microsoft Entra ID. This lab covers user lifecycle management, MFA enforcement, privilege auditing, and least-privilege validation — core skills for any cloud security or SOC analyst role.

What makes this lab realistic: it was conducted in a school-managed Microsoft 365 tenant with real organizational restrictions in place, mirroring the constrained environments you encounter in actual enterprise security work.

---

## 🎯 Objectives

- Create and manage Entra ID user accounts with secure credential practices
- Enforce Multi-Factor Authentication (MFA) using Microsoft Authenticator
- Audit and remediate excessive group-based permissions
- Validate least-privilege access through controlled permission testing
- Document tenant-level security constraints the way a real security analyst would

---

## 🏗️ Environment

| Component | Details |
|---|---|
| Platform | Microsoft Entra ID (formerly Azure Active Directory) |
| Tenant Type | School-managed Microsoft 365 tenant |
| Test Account 1 | `lab-admin` — administrative user |
| Test Account 2 | `lab-user` — standard user |
| Notable Constraint | School-managed tenant restricts full role assignment, even for Global Admins |

---

## 🔬 Lab Walkthrough

### 1. User Creation & Secure Onboarding
- Created `lab-admin` and `lab-user` accounts in Entra ID
- Verified successful login for both accounts
- Enforced password change on first login to simulate secure onboarding practices

### 2. MFA Enforcement
- Enabled Microsoft Authenticator as the primary authentication method
- Required MFA registration for both test accounts
- Verified MFA prompt was triggered correctly during login — confirming enforcement was active, not just configured

### 3. Privilege Audit & Remediation
- Discovered `lab-user` was a member of the `MSFT` administrative group — an inherited privilege that should not have been there
- Removed `lab-user` from the group to eliminate unintended elevated access
- This mirrors a real-world privilege escalation finding: users accumulating permissions through group membership over time

### 4. Least-Privilege Validation

**lab-user (Standard User) — Post-Remediation**
- ✅ Can sign in and view limited directory info
- ❌ Cannot add or remove role assignments
- ❌ Cannot modify other users
- ❌ Cannot access security or privileged role settings

**lab-admin (Admin User)**
- ✅ Can create and manage users
- ✅ Can enforce MFA policies
- ⚠️ Role assignment actions restricted by school tenant policy — documented as an environmental constraint

---

## 🛠️ Tools & Technologies

`Microsoft Azure` `Microsoft Entra ID` `Azure Active Directory` `IAM` `MFA` `Microsoft Authenticator` `RBAC` `Least Privilege` `Identity Security` `Cloud Security`

---

## 💡 Key Takeaways

- **Group membership is a hidden privilege vector.** Users can accumulate elevated permissions through groups without it being immediately obvious — regular audits are essential.
- **MFA configuration ≠ MFA enforcement.** Verifying that MFA actually triggers during login is a separate and necessary step.
- **Tenant-level constraints are normal.** In enterprise, education, and regulated environments, even admins operate within guardrails. Documenting those constraints is part of professional security work, not a failure.
- **Least privilege is an ongoing practice, not a one-time setup.** Permissions drift over time and need to be audited regularly.

---

## 🔍 Security Concepts Demonstrated

`Identity and Access Management (IAM)` `Multi-Factor Authentication (MFA)` `Least Privilege` `Group-Based Access Control` `Privilege Escalation Detection` `Tenant Security Constraints` `Secure User Onboarding`

---

## 🗺️ What's Next

This lab was conducted in a constrained tenant to reflect real-world enterprise conditions. A future iteration will replicate the same scenarios in a fully unrestricted tenant to explore the complete range of role assignment and policy enforcement capabilities.

---

## 🔗 Related Projects

- [Azure Secure Network Lab](https://github.com/Sebasttianp/azure-secure-network-lab) — VNet segmentation and NSG configuration
- [Cloud Security Anomaly Detection](https://github.com/Sebasttianp/cloud-security-anomaly-detection) — ML-based detection for cloud audit logs
