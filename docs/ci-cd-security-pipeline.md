# CI/CD Security Pipeline Documentation

## Overview

The project uses GitHub Actions to integrate security checks into the software development lifecycle. The security pipeline performs static analysis, dependency scanning, secrets detection and container image scanning.

## Security Gates

The pipeline contains four main security checks:

| Gate | Tool | Purpose |
|---|---|---|
| SAST | Semgrep | Detect insecure source-code patterns |
| SCA | npm audit | Identify vulnerable dependencies |
| Secrets Scanning | Gitleaks | Detect potential exposed secrets |
| Container Scanning | Trivy | Identify HIGH and CRITICAL vulnerabilities in the container image |

## SAST

Semgrep is used to perform static application security testing against selected application files. The pipeline uses the OWASP Top Ten ruleset to identify potentially insecure coding patterns.

## Software Composition Analysis

`npm audit` is used to identify vulnerabilities in project dependencies. The security pipeline evaluates dependency vulnerabilities and records the results.

## Secrets Scanning

Gitleaks scans the repository for potential credentials, tokens and other sensitive values. The gate is configured to return a non-zero exit code when findings are detected.

## Container Scanning

Trivy scans the built Juice Shop container image for HIGH and CRITICAL vulnerabilities. The scan is configured as a blocking security gate by returning a non-zero exit code when qualifying vulnerabilities are detected.

## Security Gate Failure

The pipeline was tested with genuine security findings. Gitleaks detected potential secret findings and returned exit code 1. A separate pipeline run also demonstrated a Trivy container scan failure caused by HIGH/CRITICAL vulnerabilities.

## Conclusion

The GitHub Actions pipeline integrates multiple security controls into the development workflow, allowing security issues to be identified before deployment.
