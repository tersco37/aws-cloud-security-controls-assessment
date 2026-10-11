# Control Evidence: Network Security (NET)

## Assessment Details
* **Assessor:** Terrance
* **Target Environment:** AWS VPC & Security Groups

---

## Control Findings

### NET-01: Restricted Ingress Access (Firewall Hygiene)
* **Requirement:** Administrative management ports (e.g., SSH Port 22, RDP Port 3389) must not be exposed to the public internet (`0.0.0.0/0`).
* **Implementation:**
  * Inspected active Security Group inbound configurations within the primary VPC.
  * Verified inbound rules for Port 80 (HTTP) and Port 443 (HTTPS) are provisioned to support web hosting requirements.
  * Confirmed zero explicit allow rules exist for administrative protocols (Port 22 / Port 3389) from `0.0.0.0/0`.
* **Validation:** Verified via AWS Security Group implicit-deny evaluation that administrative management ports remain blocked to all inbound internet traffic.
