# CDS OpenAPI

_Last updated 2026-06-02_

CDS Version 1.1

---

## Overview

This repository contains **OpenAPI 3.1 representations** of the [Curb Data Specification (CDS)](https://github.com/openmobilityfoundation/curb-data-specification), an open standard for sharing curb-related data managed by the [Open Mobility Foundation](https://github.com/openmobilityfoundation). For more details about CDS, visit the [specification repository](https://github.com/openmobilityfoundation/curb-data-specification).

This repository maintains OpenAPI schema definitions to support interactive API documentation and tooling. The OpenAPI specs here represent the APIs and data models defined in the CDS specification.

**Important:** The authoritative source of truth for the CDS specification is the [curb-data-specification](https://github.com/openmobilityfoundation/curb-data-specification) repository. If the OpenAPI spec becomes out of sync with the canonical specification, or if you encounter formatting issues, please create an issue in this repository.

Interactive OpenAPI documentation is available on Stoplight at [OMF's Interactive Documentation](https://openmobilityfnd.stoplight.io/docs/cds-openapi/).

## Versions

Each CDS version has its own branch. Version branches are independent — changes to one version do not affect another.

- [v1.0](https://github.com/openmobilityfoundation/cds-openapi/tree/v1.0)
- [v1.1](https://github.com/openmobilityfoundation/cds-openapi/tree/main)

## Reporting Issues

If you find a problem with the OpenAPI schema (formatting issues, missing fields, incorrect types, or misalignment with the CDS spec), please create a GitHub issue:

1. Go to [https://github.com/openmobilityfoundation/cds-openapi](https://github.com/openmobilityfoundation/cds-openapi)
2. Click the **Issues** tab
3. Click **New Issue**
4. Give your issue a clear title (e.g., "Events API missing required field" or "v1.1 schema out of sync with spec")
5. In the description, include:
   - Which CDS version branch this affects (e.g., `v1.1`)
   - The specific problem (e.g., "Field `foo` is marked required but the spec says it's optional")
   - A link to the relevant section in the [CDS specification](https://github.com/openmobilityfoundation/curb-data-specification) if applicable
6. Click **Submit new issue**

We review and prioritize issues regularly. Thank you for helping us keep the spec accurate!

---

## Maintenance

### Making Changes

Changes to the OpenAPI schema are made via pull requests to the appropriate version branch (e.g., `v1.0`, `v1.1`). Each pull request should target a single CDS version. 

To contribute:

1. Clone the repository and check out the version branch you want to modify (e.g., `git checkout v1.1`)
2. Create a feature branch from the version branch (e.g., `git checkout -b fix/events-api-schema`)
3. Make your changes to the YAML files, following [STYLE_CONVENTIONS.md](STYLE_CONVENTIONS.md)
4. Validate your changes (see below)
5. Commit with a clear, conventional-commit style message (e.g., `fix: align Events API with spec`, `feat: add missing field to Curbs API`)
6. Push your branch and open a pull request to the version branch
7. Address any review feedback

### Validating Your Changes

This project uses **Spectral**, an OpenAPI linter, to catch formatting errors and spec violations.

1. Install dependencies:
   ```bash
   npm install
   ```

2. Validate the OpenAPI files:
   ```bash
   spectral lint "APIs/*.yaml"
   ```

3. Fix any reported errors before committing your changes.

All pull requests must pass linting before they can be merged.
