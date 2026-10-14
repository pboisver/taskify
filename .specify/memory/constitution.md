<!--
Sync Impact Report
Version change: unversioned → 1.0.0 (initial constitution)
Modified principles: None; established five initial principles.
Added sections: Architecture and Security Constraints; Development Workflow.
Removed sections: None.
Follow-up TODOs: Confirm the original ratification date.
-->
# Taskify Constitution

## Core Principles

### I. Security First
Security MUST be considered during design, implementation, review, and release. Services
MUST use secure defaults, least privilege, and appropriate safeguards for sensitive data
and credentials. Security-impacting changes MUST receive a risk assessment and tests
proportionate to that risk. These controls reduce the likelihood and impact of vulnerabilities
throughout the service lifecycle.

### II. Validate Every Input
Every value crossing a trust boundary, including user input and data received from other
services, MUST be validated against explicit type, shape, range, and business-rule
requirements before use. Validation MUST occur on the server even when a client also
validates. Invalid input MUST be rejected with a safe, explicit error; data rendered or
inserted into output contexts MUST be appropriately encoded.

### III. Explicit Microservice Boundaries
Each service MUST have a defined responsibility and documented ownership. Services MUST
communicate through explicit, documented API or event contracts; consumers MUST NOT
depend on another service's internal implementation. Contract changes MUST preserve
compatibility or include a coordinated versioning and migration path.

### IV. Documented Code
Production code MUST document its purpose and public interfaces. Service APIs, events,
configuration, security-sensitive behavior, and non-obvious logic MUST have documentation
that enables maintainers to use and change them safely. Documentation MUST be updated in
the same change as the behavior or contract it describes.

### V. Verifiable Changes
Production changes MUST include automated tests for their behavior. Changes affecting
service boundaries MUST include relevant contract or integration tests, and security-sensitive
changes MUST include appropriate security regression coverage. Required tests and static
checks MUST pass before a change is accepted.

## Architecture and Security Constraints

Services MUST enforce authentication and authorization at protected boundaries and MUST
not expose secrets in source code, responses, or logs. Service-owned data MUST be accessed
through the owning service's documented contract, not by reaching into another service's
storage. Logs and errors MUST avoid exposing credentials, tokens, and other sensitive values.

## Development Workflow

Changes MUST be reviewed for compliance with this constitution. Reviews MUST verify input
validation, security impact, service-contract compatibility, relevant test coverage, and
documentation updates. Changes that do not meet a principle MUST be revised or receive an
explicit, documented exception through the governance process.

## Governance

This constitution governs project practices and takes precedence over conflicting local
guidance. Amendments MUST be proposed as documented changes, reviewed for their impact
on existing services and practices, and approved by the project's designated maintainers
before adoption. Amendments MUST update this document and its version metadata.

Versioning follows semantic versioning: MAJOR for incompatible changes to principles or
governance, MINOR for new or materially expanded principles or sections, and PATCH for
clarifications that do not change requirements. Every change MUST include a compliance
review; proposals and reviews MUST identify any non-compliance and document approved
exceptions and their rationale. Compliance MUST also be checked during change review.

**Version**: 1.0.0 | **Ratified**: TODO(RATIFICATION_DATE): Confirm original adoption date. | **Last Amended**: 2026-10-14
