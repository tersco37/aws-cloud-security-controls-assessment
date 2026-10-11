# AWS Cloud Security & GRC Baseline Portfolio

## Executive Summary
This project demonstrates the design, implementation, and audit verification of a foundational **Governance, Risk, and Compliance (GRC)** security baseline on Amazon Web Services (AWS). 

Following industry standards such as **NIST SP 800-53** and **CIS AWS Foundations Benchmarks**, this repository documents five core controls implemented across identity, networking, storage, and audit logging domains.

---

## Security Controls Baseline Summary

| Control ID | Domain | Control Objective | AWS Implementation | Status |
| :--- | :--- | :--- | :--- | :--- |
| **IAM-01** | Identity & Access | Root Account Protection | Enforced Root MFA; deleted root access keys | **100% Compliant** |
| **IAM-02** | Identity & Access | Enforce Least Privilege | Created dedicated administrative user (`terrance-admin`) with MFA | **100% Compliant** |
| **NET-01** | Network Security | Ingress Access Control | Implicit-deny Security Groups restricting management ports (22/3389) | **100% Compliant** |
| **DAT-01** | Data Protection | Prevent S3 Data Exposure | S3 Block Public Access & default SSE-S3 (AES-256) encryption | **100% Compliant** |
| **LOG-01** | Monitoring & Audit | Centralize Activity Logging | Multi-region AWS CloudTrail continuous API logging | **100% Compliant** |

---

## Detailed Audit Evidence & Documentation
Comprehensive evidence files, testing methodologies, and verification logs are maintained in the [`docs/`](./docs) directory:

* 📋 [Controls Matrix Matrix](./docs/controls-matrix.md) — Central tracking of all baseline safeguards.
* 🔐 [Identity & Access Evidence (`IAM`)](./docs/evidence-iam.md) — Documentation for IAM-01 and IAM-02 controls.
* 🌐 [Network Security Evidence (`NET`)](./docs/evidence-net.md) — Firewall rules and ingress security analysis.
* 🛡️ [Data Protection Evidence (`DAT`)](./docs/evidence-dat.md) — S3 security and encryption validation.
* 📜 [Monitoring & Audit Evidence (`LOG`)](./docs/evidence-log.md) — CloudTrail audit configuration details.

---

## Architecture Overview
```mermaid
graph TD
    %% Styling
    classDef rootStyle fill:#ff9999,stroke:#cc0000,stroke-width:2px,color:#000;
    classDef iamStyle fill:#ffcc99,stroke:#d97706,stroke-width:2px,color:#000;
    classDef netStyle fill:#99ccff,stroke:#2563eb,stroke-width:2px,color:#000;
    classDef datStyle fill:#99ff99,stroke:#16a34a,stroke-width:2px,color:#000;
    classDef logStyle fill:#e2e8f0,stroke:#475569,stroke-width:2px,color:#000;

    subgraph AWS ["AWS Account"]
        
        subgraph IAM ["IAM Domain"]
            Root["Root Account - MFA Enforced"]:::rootStyle
            AdminUser["IAM Admin - terrance-admin"]:::iamStyle
        end

        subgraph Network ["Network and Edge"]
            SG["Security Group NET-01"]:::netStyle
            CloudFront["CloudFront Distribution - OAC"]:::netStyle
        end

        subgraph Data ["Storage Domain"]
            S3Bucket["Portfolio Bucket DAT-01"]:::datStyle
        end

        subgraph Audit ["Logging Domain"]
            CloudTrail["AWS CloudTrail LOG-01"]:::logStyle
            LogsBucket["Logs Bucket terrance-logs-portfolio-bucket"]:::logStyle
        end

    end

    AdminUser --> SG
    AdminUser --> S3Bucket
    CloudFront --> S3Bucket
    S3Bucket --> LogsBucket
    CloudTrail --> LogsBucket
```

---

## Author
* **Terrance** — *Cloud Security & GRC Engineering Portfolio*
