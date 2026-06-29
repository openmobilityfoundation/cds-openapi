# Working with the CDS OpenAPI Project

This document describes how to collaborate with an AI agent (or human contributor) on the `cds-openapi` project.

## Project Purpose

This repository maintains an **OpenAPI 3.1 specification** for the [Curb Data Specification (CDS)](https://github.com/openmobilityfoundation/curb-data-specification), managed by the Open Mobility Foundation. The spec is hosted publicly via Stoplight and serves as an interactive API browser for implementers.

## Repository Structure

```
cds-openapi/
  APIs/
    Curbs API.yaml        # Curb zones, areas, spaces, policies, objects
    Events API.yaml       # Curb events and sensor status
    Metrics API.yaml      # Sessions and aggregates
  Shared Data Models/     # Reusable YAML schemas (curb_zone, curb_event, etc.)
  Rest Responses/         # Common API response header schemas
  toc.json                # Stoplight table of contents
  .spectral.mjs           # Linting rules
  .stoplight.json         # Stoplight platform config
```

## Branch Strategy

Each CDS version has its own branch (e.g., `v1.1`, `v1.2`). Changes to a specific version should be made to that version's branch and merged back to it. Version branches are independent — changes to one version do not affect another.

## How to Make Changes

### Workflow for editing the spec

1. **Read the upstream spec on `main`** at https://github.com/openmobilityfoundation/curb-data-specification for the relevant section to confirm exact field names, types, enums, descriptions, and required/optional status
2. **Edit the YAML files** — maintain the existing style conventions:
   - Use `$ref` for shared models rather than inline definitions
   - Include `description` on every field
   - Use `x-stoplight: id:` annotations if present on surrounding fields (Stoplight generates these)
   - Keep `required` arrays up to date
3. **Validate** — run the Spectral linter (`.spectral.mjs`) after all changes. Install dependencies with `npm install` and validate with `spectral lint "APIs/*.yaml"`.
4. **Commit** — use conventional-commit style messages

See [STYLE_CONVENTIONS.md](STYLE_CONVENTIONS.md) for detailed style conventions, field type conventions, guidance on adding new shared models, and key gotchas.

## Validation

The project uses Spectral for OpenAPI linting:

```bash
npm install
spectral lint "APIs/*.yaml"
```

The `.spectral.mjs` config extends a remote Stoplight ruleset. Run the linter after all changes are made. Always lint and fix any errors before committing. When a task adds or edits standalone shared model files, lint those touched files as well in addition to the API documents.

