# Control Evidence: Data Protection (DAT)

## Assessment Details
* **Assessor:** Terrance
* **Target Environment:** AWS S3 Storage Infrastructure

---

## Control Findings

### DAT-01: Prevent Public S3 Exposure & Enforce Encryption
* **Requirement:** Storage buckets containing operational or portfolio data must strictly prohibit public access and enforce encryption at rest.
* **Implementation:**
  * Provisioned dedicated S3 bucket (`terrance-grc-portfolio-bucket`) for portfolio baseline.
  * Explicitly enabled "Block All Public Access" at the bucket level to prevent unauthorized exposure.
  * Applied default Server-Side Encryption (SSE-S3) to enforce encryption at rest for all stored objects.
* **Validation:** Verified active security settings in the AWS S3 Console (Permissions & Properties tabs).
