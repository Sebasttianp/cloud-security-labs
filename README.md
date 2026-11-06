# Cloud Security Labs

Hands on labs covering identity and access management in Microsoft Azure and Entra ID.

## Labs

| Lab | What it covers | Write up |
|---|---|---|
| IAM, MFA and Least Privilege in Entra ID | User creation, MFA enforcement, privilege audit, least privilege validation | [Azure-EntraID-IAM-MFA.md](Labs/Azure-EntraID-IAM-MFA.md) |

## Lab summary: IAM, MFA and Least Privilege in Entra ID

Environment: a school managed Microsoft 365 tenant with two test accounts, `lab-admin` and `lab-user`. The tenant limited role assignment, even for administrators, and the write up documents that constraint.

What I did:
1. **Created two users** and forced a password change at first sign in.
2. **Enforced MFA** with Microsoft Authenticator and confirmed the MFA prompt appeared at sign in, which checks enforcement and not just configuration.
3. **Audited privileges.** I found that `lab-user` was a member of an administrative group it should not have been in, and removed it.
4. **Validated least privilege.** After the fix, the standard user could not change role assignments, edit other users, or reach privileged role settings.

Key findings:
- Group membership is an easy place for hidden privilege to build up.
- MFA being configured is different from MFA being enforced, so test the sign in.
- Tenant restrictions are normal in real environments, and they belong in the documentation.

Skills shown: IAM, MFA, RBAC, least privilege, privilege audit, secure onboarding, security documentation.

[Read the full lab write up](Labs/Azure-EntraID-IAM-MFA.md)

## Related projects

- [Azure Secure Network Lab](https://github.com/Sebasttianp/azure-secure-network-lab): VNet segmentation and NSG configuration
- [Cloud Security Anomaly Detection](https://github.com/Sebasttianp/cloud-security-anomaly-detection): planned, code not yet committed
