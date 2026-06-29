# CLAUDE.md

Read [AGENTS.MD](AGENTS.MD) for full project context, structure, conventions, and workflow instructions.

## Quick Reference

- **What this repo is:** OpenAPI 3.1 specification for the Curb Data Specification (CDS), an open standard for curb data managed by the Open Mobility Foundation
- **Versioning:** One branch per version (e.g., `v1.1`, `v1.2`). Version branches are independent.
- **Upstream spec:** https://github.com/openmobilityfoundation/curb-data-specification

## Workflow

When making changes:

1. Confirm which version branch the changes should be made to (e.g., `v1.1`, `v1.2`)
2. Cross-reference the upstream CDS spec for exact field definitions
3. Edit the YAML files, following the style conventions in [AGENTS.MD](AGENTS.MD)
4. Run `npm install && spectral lint "APIs/*.yaml"` to validate your changes
5. Open a pull request to the appropriate version branch with a conventional-commit style message
