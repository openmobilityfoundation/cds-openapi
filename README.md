# CDS OpenAPI
**Status: WGSC Review**

_Last updated on Oct 2 2023_

---
## Overview

This is the OpenAPI schema for [CDS](https://github.com/openmobilityfoundation/curb-data-specification) (Curb Data Specification) data feeds, managed by the [Open Mobility Foundation](https://github.com/openmobilityfoundation). 

The OpenAPI documentation for the CDS APIs is visible on the [OMF's Interactive Documentation on Stoplight]([https://openmobilityfnd.stoplight.io/settings/cds-openapi](https://openmobilityfnd.stoplight.io/docs/cds-openapi/)) hosted on the Open Mobility Foundation's publicly accessible GitHub repo ([openmobilityfoundation / cds-openapi](https://github.com/openmobilityfoundation/cds-openapi)). 

---
## Organization

The CDS schema versions are documented as different branches in the underlying GitHub project repo. The branch naming will only include the major and minor semantic versions. 

### Public Releases
Any work on future releases of CDS will be completed in a development branch and will be identified by the `-dev` suffix in the repo name. For example, as CDS version 1.0 is available, users may view this version of the OpenAPI schema by choosing the `v1.0` branch.

### Upcoming Releases
After the ratification and approval of a new version, such as CDS v1.1, a `v1.1-dev` branch will be created to demonstrate it is a work in progress. Once complete, the `v1.1-dev` branch will be merged into a `v1.1` branch and the latest version of the spec will exist within the `main` branch of the repo.
