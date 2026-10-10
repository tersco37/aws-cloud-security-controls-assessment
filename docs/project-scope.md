# Project Scope & Assessment Boundaries (Draft)

## 1. Objective
Build a basic AWS environment, implement core security controls, test those controls, and document the findings to demonstrate practical cloud security and GRC skills.

## 2. Planned Learning & Hands-On Scope
As I build and test this environment, I will document controls in the following areas:
* **Identity & Access Management (IAM):** Users, roles, and access controls.
* **Network Security:** Virtual Private Cloud (VPC) and firewall settings (Security Groups).
* **Data Security: ** Securing Amazon S3 storage.
* **Logging:** Tracking events using AWS CloudTrail.

# Control Evidence: Identity & Access Management (IAM)

## Assessment Details
* **Assessor: ** Terrance Scott
*  **Target Environment: ** AWS Baseline Account

---

## Control Findings

### IAM-01: Root Account Security
* **Requirement:** Root account must be protected with Multi-Factor Authentication (MFA) and must not have active access to keys.
* **Implementation:**
  * MFA enabled on Root account.
  * Verified 0 active access keys for Root.
* **Validation:** Verified via IAM Console security recommendations dashboard.

### IAM-02: Administrative Account Provisioning
* **Requirement:** Daily operational activities must be performed using an individual IAM user rather than the root account.
* **Implementation:**
  * Created user 'Terrance-admin' with console access.
  * Attached 'AdministratorAccess' manage policy.
  * Enforced MFA on 'Terrance-admin'.
* **Validation:** Successfully signed out of Root, authenticated as 'Terrance-admin' using MFA, and verified admin privileges.


*(Note: This scope document will be updated with technical details as each phase of the AWS environment is built and tested.)*
