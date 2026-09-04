<!-- markdownlint-disable -->

# Hardening Report: pozil--auto-assign-issue/v4.0.1

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **pozil--auto-assign-issue/v4.0.1** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The workflow file .github/workflows/ci.yml references three GitHub Actions using mutable version tags instead of pinned full-length SHA digests. This exposes the workflow to supply-chain attacks if any of these tags are moved to point to malicious code. Failing references:
- `actions/checkout@v6` (line 14)
- `actions/cache@v5` (line 17)
- `codecov/codecov-action@v6` (line 37)

Each should be replaced with a full 40-character commit SHA, e.g. `actions/checkout@<40-char-sha> # v6`.

Locations:

- `.github/workflows/ci.yml:14`
- `.github/workflows/ci.yml:17`
- `.github/workflows/ci.yml:37`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all three unpinned action references in hardened/action/.github/workflows/ci.yml:
- actions/checkout@v6 → actions/checkout@d23441a48e516b6c34aea4fa41551a30e30af803 # v6
- actions/cache@v5 → actions/cache@caa296126883cff596d87d8935842f9db880ef25 # v5
- codecov/codecov-action@v6 → codecov/codecov-action@fb8b3582c8e4def4969c97caa2f19720cb33a72f # v6
Original version tags preserved as inline comments for readability.

