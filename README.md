# Nexus Core Auth Microservice ⚡

`nexus-core-auth` is a high-performance Python microservice designed for OAuth2 token issuance, claim verification, rate-limited scopes, and customer credit ledger calculations.

## Architecture

- **`src/models.py`**: Dataclasses for `User`, `AuthToken`, and `BillingAccount`.
- **`src/auth_service.py`**: Token lifecycle management, scope authorization, and cryptographic lifetime validation.
- **`src/billing_service.py`**: Tier-based pricing, credit deposits/deductions, and tax/discount invoice calculations.

## Running Tests

Ensure you have `pytest` installed:

```bash
pip install pytest
pytest
```

## Known Defects / SDLC Demonstration

This repository contains edge-case logical defects specifically tailored for automated AI static analysis, AST symbol graph resolution, and self-healing test execution:

1. **`src/auth_service.py`**:
   - `verify_token`: Inverted comparison operator (`>`) on token expiration check rejecting active tokens.
2. **`src/billing_service.py`**:
   - `calculate_invoice_total`: Discount calculation erroneously adds discount amount instead of subtracting it from the subtotal.
