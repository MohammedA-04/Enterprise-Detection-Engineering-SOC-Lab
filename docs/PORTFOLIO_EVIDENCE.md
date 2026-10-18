# Cybersecurity Portfolio Evidence

## Project overview

**Enterprise Detection Engineering SOC Lab**

GitHub repository: https://github.com/MohammedA-04/Enterprise-Detection-Engineering-SOC-Lab

This project explores security operations centre (SOC) engineering, security detection rules, OpenSearch, alert automation, and attack simulation.

My work focuses on troubleshooting, validating detection logic, improving Linux compatibility, and documenting technical findings.

## Work completed

### 1. Brute-force detection

- Reviewed the Sigma and ElastAlert2 brute-force detection rules.
- Aligned the alert threshold with the intended detection logic.
- Added support for `event_id` and `EventID` field variants.
- Used `src_ip` to group related events by source IP address.

**Evidence:** The offline detection test harness passed 5 out of 5 scenarios. Live alert delivery has not yet been verified.

### 2. Sigma rule compilation

- Ran the Sigma-to-OpenSearch transpilation tool.
- Confirmed that all 13 available Sigma rules compiled successfully.

**Evidence:** 13 out of 13 rules compiled. Successful compilation alone does not prove that the queries work against live indexed events.

### 3. OpenSearch certificate testing on Linux

- Replaced Windows-specific OpenSSL commands with the system OpenSSL installation.
- Added certificate-chain verification.
- Improved certificate subject-name checks for OpenSSL output formatting.
- Made the certificate scripts executable so they can be invoked directly.

**Evidence:** The certificate-generation test passed on Ubuntu. The node 1, node 2, and admin certificates all verified successfully.

### 4. Git and GitHub

- Committed and pushed the Linux compatibility changes to my GitHub fork.
- Latest recorded commit: `5bc7c75`
- Commit message: `Fix OpenSearch certificate test for Linux`

## Skills demonstrated

- Linux command-line troubleshooting
- Bash scripting and file permissions
- OpenSSL certificate verification
- YAML-based security configuration
- Sigma detection rules
- OpenSearch and ElastAlert2 concepts
- Automated testing
- Git and GitHub version control
- Technical documentation

## Outstanding work

- Verify live log ingestion into OpenSearch.
- Test detection queries against indexed events.
- Confirm end-to-end alert delivery to the response workflow.
- Capture screenshots and reproducible test evidence.
- Review outstanding security and deployment risks.

## Lab limitations

The offline tests do not establish that the complete SOC stack works end to end. Live ingestion, indexing, and alert delivery remain unverified.

The Ubuntu virtual machine has 8 GB RAM, so full-stack testing must be planned carefully rather than starting all services simultaneously.

Never include credentials, private keys, or `.env` contents in public portfolio documentation.

## Reproducing the certificate test

Run the following command from the repository root:

`bash tools/test-opensearch-certs.sh`

## Evidence integrity

This document records results observed during development. Rerun the relevant tests when reproducing the results on another machine.
