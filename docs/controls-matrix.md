# AWS Security Controls Baseline Matrix

This document tracks the foundational security controls implemented and evaluated as part of this project.

| Control ID | Domain | Control Objective | AWS Safeguard / Configuration | Testing Method | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **IAM-01** | Identity & Access | Protect Root Account | Enable MFA on Root; eliminate root access keys | Console Audit & Verification | **Implemented & Tested** |
| **IAM-02** | Identity & Access | Enforce Least Privilege | Create dedicated IAM Admin user (`terrance-admin`) with MFA | Login verification & Root sign-out | **Implemented & Tested** |
| **NET-01** | Network Security | Restrict Ingress Access | Security Group restricting management access (SSH/RDP) while allowing HTTP/HTTPS | Inbound Rule Audit & Rule Verification | **Implemented & Tested** |
| **DAT-01** | Data Protection | Prevent Public S3 Exposure | Enable S3 "Block Public Access" & KMS Encryption | Attempt Public S3 Bucket Read | **Implemented & Tested** |
| **LOG-01** | Monitoring & Audit | Centralize Activity Logging | Enable multi-region AWS CloudTrail with log integrity | Trigger event & inspect CloudWatch | **Implemented & Tested** |

---

## Progress Summary
* **Total Controls Defined:** 5
* **Implemented & Tested:** 5 / 5 (100% Complete)
