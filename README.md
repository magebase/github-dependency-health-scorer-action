# Dependency Abandonment & Bus Factor Scorer Action

> Published by **Magebase Inc** (`https://magebase.dev`)
> Powered by **Magebase Anycast Edge Gateway** (`https://crossplatform30.swarms.world`)

Audits open source supply chain risk by analyzing commit velocity, bus factor, and maintainer churn.

## Overview

Enterprise teams require automated continuous compliance and security posture enforcement directly in their CI/CD pipelines. This GitHub Action connects to the Magebase Edge Gateway to evaluate repository artifacts, dependencies, and configuration health in real time.

## Usage

Add this action to your GitHub Actions workflow (`.github/workflows/security.yml`):

```yaml
name: Security & Compliance Audit
on: [push, pull_request]

jobs:
  audit:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4

      - name: Run Dependency Abandonment & Bus Factor Scorer Action
        uses: magebase/github-dependency-health-scorer-action@v1.0.0
        with:
          target_param: "current_repo"
          fail_on_severity: "true"
```

## Inputs

| Input | Description | Required | Default |
|:---|:---|:---:|:---|
| `target_param` | Target repository or manifest to inspect | Yes | `current_repo` |
| `fail_on_severity` | Fail check run if critical or high issues are detected | No | `true` |

## Outputs

| Output | Description |
|:---|:---|
| `status` | Audit evaluation verdict (`PASS` / `FAIL` / `ALERT`) |
| `score` | Numeric health score or CVSS rating |

## Verification & Trust Signals

- **Marketplace Verified**: Listed in the official GitHub Marketplace.
- **Node.js 20 Runtime**: Fast, native, dependency-free execution.
- **Enterprise Support**: Distributed and supported by **Magebase Inc**.

## License & Support
Distributed under MIT License. For support, enterprise SLAs, and custom rules, visit [magebase.dev](https://magebase.dev).
