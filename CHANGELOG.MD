# CDS OpenAPI – Change Log

This change log tracks how the CDS **OpenAPI schema** (this repo) reflects changes in the upstream
[CDS specification](https://github.com/openmobilityfoundation/curb-data-specification).

---

## [1.1.0] – 2025-10-27

**Upstream spec:** CDS 1.1.0 ([release notes](https://github.com/openmobilityfoundation/curb-data-specification/releases/tag/1.1.0))  
**CDS versions:** From CDS 1.0.x → CDS 1.1.0

### High‑Level Features

- **Objects**
  - Add Curb Object data model to describe physical assets at or near the curb (e.g., signs, meters, sensors, devices).
  - Add Curbs API endpoints for listing and retrieving objects.
  - Include geometry (Point and LineString), ownership, external IDs/URLs, policy references, and other properties.

- **Enforcement**
  - Extend Events and Metrics definitions to capture violations, citations, double‑parking, and enforcement actions.
  - Add enforcement‑related metrics (e.g., total enforcement events) to Metrics aggregates/demand data.

- **Payment Methods & Channels**
  - Add fields to Events to capture payment method, payment channel, and payment transaction IDs.

- **Real‑Time Events (Push)**
  - Add an optional POST Events endpoint for pushing events as they occur, in addition to existing pull/query endpoints.

- **External References**
  - Introduce a reusable External Reference structure to link CDS data to external systems/specs (e.g., WZDx, CWZ, GBFS, GTFS, MDS, websites, documents).
  - Add external reference fields to relevant data objects (e.g., Events, Objects, Policies).

- **Custom Attributes**
  - Add a Custom Attribute Dictionary definition.
  - Allow custom_attributes on core data objects (e.g., Events, Objects, Policies/Metrics) to support implementation‑specific fields.

- **Authorization**
  - Clarify that Curbs (and Events) endpoints may require authorization by the public agency.
  - Note that event authorization is recommended but not strictly required so events can be made public when appropriate.

- **Lines (LineString Geometry)**
  - Allow Curb Zones to be defined with GeoJSON LineString geometry in addition to polygons.
  - Update examples and descriptive text describing geometry preference and usage.

- **New Curb Context Data**
  - Add descriptive Curb‑level fields such as description, jurisdiction, owner name, address number, and available/available_spaces counts.

- **Policy & Rule Enhancements**
  - Policies:
    - Add name and description fields.
    - Add color and pattern fields to support real‑world and digital representations.
    - Clarify that policy data must be unique and non‑duplicative.
  - Rules:
    - Add name and description.
    - Extend temporal logic (weeks of the month, refined designated_period_except behavior).

- **Temporal & Designation Updates**
  - Update designated_period_except and related fields based on design and guidance.
  - Add support for specifying weeks of the month when policies apply.

- **Event Authorization Guidance**
  - Clarify that event authorization is **recommended** but not required, to support public events data.

- **Vehicle Properties & Computer Vision**
  - Expand vehicle attributes (e.g., make, model, year, color, company).
  - Add computer‑vision‑oriented fields such as confidence scores for detected properties.

- **MDS Alignment**
  - Update vehicle types and propulsion types to align with the latest Mobility Data Specification (MDS) enums.

- **Metrics Event Tracking**
  - Add new metrics fields for total event counts (including enforcement events) in Sessions/Aggregates.