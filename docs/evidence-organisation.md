# Security Evidence Organisation

## Overview

Security testing evidence was organised to support the technical report and demonstrate the implementation and verification of the security controls.

## Vulnerability Evidence

Evidence was collected for each of the four assessed vulnerabilities:

- SQL injection authentication bypass
- Broken access control (IDOR)
- DOM-based cross-site scripting
- Improper rating validation

For each vulnerability, evidence covers the vulnerable behaviour, remediation and re-test result.

## SAST Evidence

Evidence was collected for the Semgrep before-and-after analysis and the targeted SAST verification of the modified application files.

## CI/CD Evidence

Pipeline evidence was collected for:

- Semgrep SAST
- npm audit SCA
- Gitleaks secrets scanning
- Trivy container scanning

Security gate failures were retained as evidence where applicable.

## Secrets Evidence

Evidence demonstrates the use of GitHub Actions encrypted secrets without exposing the actual secret value.

## Report Integration

Evidence was placed alongside the relevant technical sections of the report so that implementation claims can be linked to supporting screenshots and results.
