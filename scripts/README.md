# Scripts

Utility scripts for repo maintenance, validation, and tooling.

Scripts here validate that skills and agents meet the quality bar
before they ship. CI runs these — so should you before pushing.

## Adding a script

- One script = one file, self-contained
- Must run from repo root
- Zero dependencies beyond what's in a standard Linux/macOS box
- Exit 0 on success, non-zero on failure, print errors to stderr
