# claude-api-integration-specialist-skill

A Claude Code skill for integrating third-party APIs and external services with secure authentication, resilient requests, and predictable error handling.

## Overview

This skill supports the full lifecycle of API integration, from authentication and client setup to request transformation, retries, webhooks, and production monitoring.

It is intended for integrations where external service behavior, rate limits, and partial failures must be handled deliberately.

## Main Capabilities

- Integrate REST and GraphQL APIs.
- Build reusable API clients.
- Configure API keys, OAuth 2.0, and JWT-based authentication.
- Handle request and response transformation.
- Implement webhooks and event-driven integrations.
- Apply rate limits and bounded retries.
- Use timeouts and circuit breakers.
- Validate external responses.
- Diagnose integration failures.
- Protect credentials and sensitive payloads.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-api-integration-specialist-skill.git ~/.claude/skills/api-integration-specialist
```

## Usage

Invoke the skill when integrating an external API:

```text
/api-integration-specialist
```

Provide the service name, API version, authentication method, target framework, expected request volume, and error-handling requirements.

## Recommended Integration Workflow

1. Review the API contract and required permissions.
2. Select the authentication flow.
3. Store credentials securely.
4. Build a focused client wrapper.
5. Validate inputs before sending requests.
6. Apply timeouts and bounded retries.
7. Handle rate limits and provider errors.
8. Validate and normalize responses.
9. Verify webhook signatures where applicable.
10. Add logs, metrics, and integration tests.

## Reliability Patterns

- Retry only operations that are safe to retry.
- Use idempotency keys for supported write operations.
- Respect rate-limit responses.
- Apply exponential backoff with a maximum retry budget.
- Use circuit breakers for repeated provider failures.
- Keep provider-specific response handling behind a stable application interface.
- Handle webhook duplicates and out-of-order delivery.

## Security Checklist

- API keys are never hard-coded.
- OAuth scopes are limited to required access.
- Tokens are stored and refreshed securely.
- TLS is used for network communication.
- Webhook signatures are verified.
- Sensitive payloads are not logged unnecessarily.
- External responses are treated as untrusted input.
- Access and error behavior are tested.

## Repository Contents

- `SKILL.md`: Main API integration workflow and implementation guidance.
- `README.md`: Setup, reliability, and security checklist.

## Practical Principle

An integration is not production-ready just because the happy path works. Test expired credentials, rate limits, timeouts, malformed responses, duplicate webhooks, and provider outages.
