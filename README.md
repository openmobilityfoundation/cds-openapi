# CDS OpenAPI
**Status: Approved for v1.0**

_Last updated on Feb 9 2024_

## Overview

This repository contains **OpenAPI 3.1 representations** of the [Curb Data Specification (CDS)](https://github.com/openmobilityfoundation/curb-data-specification), an open standard for sharing curb-related data managed by the [Open Mobility Foundation](https://github.com/openmobilityfoundation). For more details about CDS, visit the [specification repository](https://github.com/openmobilityfoundation/curb-data-specification).

This repository maintains OpenAPI schema definitions to support interactive API documentation and tooling. The OpenAPI specs here represent the APIs and data models defined in the CDS specification.

**Important:** The authoritative source of truth for the CDS specification is the [curb-data-specification](https://github.com/openmobilityfoundation/curb-data-specification) repository. If the OpenAPI spec becomes out of sync with the canonical specification, or if you encounter formatting issues, please create an issue in this repository.

Interactive OpenAPI documentation is available on Stoplight at [OMF's Interactive Documentation](https://openmobilityfnd.stoplight.io/docs/cds-openapi/).

## Versions

Each CDS version has its own branch. Version branches are independent. Changes to one version do not affect another.

- [v1.0](https://github.com/openmobilityfoundation/cds-openapi/tree/v1.0)
- [v1.1](https://github.com/openmobilityfoundation/cds-openapi/tree/v1.1)

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
