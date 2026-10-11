# Control Evidence: Monitoring & Audit (LOG)

## Assessment Details
* **Assessor:** Terrance
* **Target Environment:** AWS CloudTrail & Logging Infrastructure

---

## Control Findings

### LOG-01: Centralize Activity Logging & Log Integrity
* **Requirement:** All management API activities across the AWS environment must be continuously recorded to a secure log repository.
* **Implementation:**
  * Provisioned multi-region AWS CloudTrail via streamlined console configuration.
  * Configured automatic S3 log storage integration for centralized activity tracking.
* **Validation:** Verified active logging state (`Logging`) and confirmed multi-region trail configuration within the AWS CloudTrail Console.
