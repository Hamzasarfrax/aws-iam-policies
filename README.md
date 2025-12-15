

Cloud-Security-Policies

Dec 2025 - Dec 2025Dec 2025 - Dec 2025
👥 IAM Roles & Policies Designed

🔴 Admin Users
✔ MFA enforced for high-risk services (IAM, EC2, S3, RDS, Lambda, KMS)
✔ Trusted IP access using explicit deny (Zero Trust)
✔ Region-restricted workloads (excluding global services)
✔ Explicit billing & cost management deny to prevent insider risk
✔ Scoped admin permissions (no blanket wildcards)

🟡 Manager Users
✔ Limited service access (no IAM / billing permissions)
✔ MFA enforced
✔ Region-based access control
✔ Read-only visibility for monitoring & reporting

🟢 Staff Users
✔ Application-level access only
✔ No admin, billing, or security-sensitive permissions
✔ Strict least-privilege enforcement

Each policy is attached via IAM Groups, not hardcoded, making the design scalable and audit-friendly.













<!-- I designed a layered IAM policy following a deny-first security approach. I implemented DenyIfNoMFA to enforce MFA without locking users out of fixing MFA issues, demonstrating correct NotAction and BoolIfExists usage. I explored DenyRootAccountUsage to understand deny precedence, while knowing in production root access should remain MFA-only. DenyFromUntrustedIP applies zero-trust thinking with /32 IP restriction and NotIpAddressIfExists, balancing security with console usability considering ISP NAT issues. I added DenyOutsideApprovedRegions to control region-specific access with NotAction and global service exceptions, and DenyBillingAccess to mitigate insider threats, a practice rarely seen in junior setups. Finally, AllowAdminAllServices ensures explicit allow after layered denies, showing deep understanding of IAM evaluation order. I validated all conditions using IAM Policy Simulator, CloudTrail, and Access Analyzer to ensure precise and secure policy enforcement -->