# Sandbox / Tests

This directory is used for **executing and validating** Agent Skills developed in `sandbox/dev/`.

## Usage

1. Create or copy your skill in `sandbox/dev/` (following the `skills/` specification)
2. Write test scripts or run commands in this directory to validate the skill
3. Once testing passes, move the skill to `skills/` for release

## Directory Structure

```
tests/
├── README.md          # This file
├── fixtures/          # Test fixtures / mock data (optional)
└── run.ps1            # Batch test script (optional)
```