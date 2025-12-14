

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