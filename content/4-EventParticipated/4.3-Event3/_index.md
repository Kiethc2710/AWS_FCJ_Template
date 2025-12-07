---
title: "Event 3"
date: 2025-09-10
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---


# “Reinventing DevSecOps” Report

### Event Purpose

- Redefine the secure software development process (DevSecOps Lifecycle) from planning to operations.
- Introduce a comprehensive toolchain to integrate security into every stage of CI/CD.
- Build a "Security-First" mindset for development and operations teams.

### Organizer

- **CMC Global**

### Highlights

#### 1. The DevSecOps Lifecycle

The process is divided into 7 closed stages, ensuring security is not a "bottleneck" but part of the flow:

1.  **PLAN:**
    - Identify security requirements & risks right from the start.
    - Align goals between Dev, Sec, and Ops.
    - Create a security roadmap aligned with project goals.
2.  **CODE:**
    - Apply clean code and secure coding standards.
    - Use **SAST** (Static Application Security Testing) directly in the IDE to detect errors early.
    - Form a "Security-first" mindset for developers.
3.  **BUILD:**
    - Automate security checks in the CI/CD Pipeline.
    - Perform dependency and binary scans.
    - Ensure secure and consistent builds (Immutable Artifacts).
4.  **TEST:**
    - Run vulnerability scans and **DAST** (Dynamic Application Security Testing).
    - Perform Penetration Testing.
5.  **DEPLOY:**
    - Check configuration and **IaC** (Infrastructure as Code) before deployment.
    - Monitor runtime configuration.
6.  **OPERATE:**
    - Automate patching and continuous security updates.
    - Have an incident response process.
7.  **MONITOR:**
    - Continuously monitor for threats.
    - Use Real-time Analytics and alerting tools.

#### 2. DevSecOps Toolchain Overview

A robust DevSecOps system requires the coordination of many specialized tools:

- **Pre-commit & Code Quality:**
    - *SonarQube, Codacy*: Check code quality.
    - *GitLeaks*: Scan and prevent leaking Secrets/Keys in code before commit.
- **Dependency & SBOM Scanning:**
    - *Syft, Grype, Dependency-Track*: Manage software packages and detect vulnerabilities in 3rd party libraries.
- **IaC & Policy-as-Code:**
    - *Checkov, Tfsec*: Scan for security errors in Terraform/Kubernetes files.
    - *OPA Gatekeeper, Kyverno*: Enforce compliance policies automatically on Clusters.
- **SAST / DAST & Security Tests:**
    - *Trivy, Checkmarx*: Detect comprehensive vulnerabilities from Code to Runtime.
- **CI/CD Integration:**
    - *Jenkins, GitHub Actions, GitLab CI, ArgoCD*: Platforms to automate the entire process above.
- **Monitoring & Logging:**
    - *Prometheus, Grafana, Loki*: Monitor system health (Observability).
- **Alerting & Governance:**
    - *Slack, Email, AI Anomaly Detection*: Instant alerts when issues occur.

### What I Learned

#### "Shift Left" Mindset

- Security should not be left to the end (Test/Operate stage) but must be shifted left - meaning done right from the **Plan** and **Code** stages. Detecting errors early saves repair costs significantly.

#### The Importance of Automation

- Security cannot be done manually in the Cloud era. Scanning tools need to be integrated into the Pipeline to block faulty builds automatically.

#### Supply Chain Security Risk Management

- By scanning Dependencies (SBOM), we can prevent attacks on 3rd party libraries (similar to the Log4j incident).

### Application to Work

- **Integrate GitLeaks**: Install pre-commit hook immediately to prevent accidentally pushing AWS Access Keys to GitHub.
- **Deploy SonarQube**: Integrate into current CI process to measure technical debt and security vulnerabilities.
- **Apply IaC Scanning**: Use **Checkov** to scan CloudFormation/Terraform files before applying infrastructure to AWS.
- **Monitoring**: Set up Grafana Dashboard to monitor real-time application status.

### Event Experience

Although only participating by following the materials, the content from CMC Global provided a very systematic view of DevSecOps.

#### Clarity in process

- The slide on **DevSecOps Lifecycle** helped me visualize the big picture clearly, knowing what needs to be done at each stage instead of just focusing on coding as before.

#### Practical Toolchain

- The **Toolchain** slide is a real "treasure". It provides a list of Industry Standard tools that I can research and apply immediately to my MiniMarket project (for example, using Trivy to scan Docker Images).

  > The event emphasized that: In the AI and Cloud era, Security is not a feature, but a culture that needs to be built from the very first lines of code.