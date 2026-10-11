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
  * **Static Hosting & Edge Audit Addendum ($0 Free Tier Compliant):** Implemented S3 Server Access Logging targeting a dedicated, immutable log bucket (`terrance-logs-portfolio-bucket/s3-access-logs/`). Pivoted from CloudFront paid edge logging to S3-level access logging to adhere strictly to AWS Free Tier constraints while maintaining a complete, centralized audit trail for web visitor traceability.
* **Validation:** Verified active logging state (`Logging`) for CloudTrail, confirmed multi-region trail configuration, and verified bucket-level access target routing in the Amazon S3 Console.
