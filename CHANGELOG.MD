# CDS OpenAPI – Change Log

This change log tracks how the CDS **OpenAPI schema** (this repo) reflects changes in the upstream
[CDS specification](https://github.com/openmobilityfoundation/curb-data-specification).

---

## [1.1.0] – 2025-10-27

**Upstream spec:** CDS 1.1.0 ([release notes](https://github.com/openmobilityfoundation/curb-data-specification/releases/tag/1.1.0))
**Upstream PR:** [#201](https://github.com/openmobilityfoundation/curb-data-specification/pull/201)

### New Data Models

- **Curb Object** — new first-class model for physical infrastructure at or near the curb (bollards, planters, cameras, pay stations, lockers, etc.) with Point and LineString geometry, ownership, policy references, and external links.
- **Enforcement** — nested object on events capturing enforcement actions with citation IDs, warning flags, action taken, and cost.
- **Violation** — nested object within enforcement for individual violation codes, names, and costs.
- **Payment Channel** — enum for payment medium (meter, mobile_app, website, sms, telephone).
- **Payment Method** — enum for payment instrument (cash, credit_card, debit_card, digital_wallet, transit_card, prepaid_account, permit).

### New API Endpoints

- `GET /curbs/objects` — query curb objects by area, zone, space, time, and operator.
- `GET /curbs/objects/{id}` — fetch a single curb object by ID.
- `POST /events/events` — optional push endpoint for submitting events in real time.

### Curb Event Changes

- Add `payment_channel`, `payment_method`, `payment_transaction_id` fields.
- Add `enforcement` object (with nested violations).
- Add `curb_object_id` reference.
- Add vehicle computer-vision fields: `vehicle_license_plate_jurisdiction`, `vehicle_license_plate_confidence`, `vehicle_type_confidence`, `vehicle_color`, `vehicle_color_confidence`, `vehicle_company_name`, `vehicle_company_name_confidence`, `vehicle_run_id`, `vehicle_run_id_confidence`.
- Add `data_source_device_name`.
- Add `vehicle_type` as a direct field reference.
- Add `event_time` query parameter to `GET /events/events` (ISO 8601 UTC hour format).

### Curb Zone Changes

- Add optional `geometry_line` (GeoJSON LineString) alongside the existing polygon geometry.
- Add `curb_object_ids` array linking zones to physical objects.
- Add context fields: `description`, `jurisdiction_type` (public/private/other), `owner_name`, `address_number`.
- Add `external_references` and `custom_attributes`.

### Curb Space Changes

- Add `curb_object_ids` array (conditionally required).
- Add `external_references` and `custom_attributes`.

### Curb Area Changes

- Add `external_references` and `custom_attributes`.

### Policy & Rule Changes

- Add `name`, `description`, and `primary_color` to curb policies.
- Loosen priority constraint: overlapping policies may share priority if they apply to disjoint user classes or activities.
- Add `name` and `description` to rules.

### Temporal Changes

- Add `weeks_of_month` to time spans for week-of-month scheduling.
- Update `designated_period_except` behavior per v1.1 guidance.
- Fix `days_of_week` from single string to array type.

### Enumeration Updates

- **Event types:** add `vehicle_detected`, `vehicle_violation_start`, `vehicle_violation_end`, `citation_issued`.
- **Vehicle types:** add `bus`, `delivery_robot`, `scooter_standing`, `scooter_seated`; fix `bicyle` → `bicycle`.
- **Propulsion types:** add `combustion_diesel`, `hybrid`, `hydrogen_fuel_cell`, `plug_in_hybrid`.
- **User classes (rules):** replace `handicap-accessible` with `accessible`; add `disabled_parking_permit`.

### External References

- Add reusable `external_reference` schema for linking CDS data to external systems (WZDx, CWZ, MDS, GBFS, GTFS, websites, documents).
- Wire `external_references` array onto curb zones, areas, spaces, events, policies, and objects.

### Custom Attributes

- Add reusable `custom_attributes` schema for implementation-specific key/value data.
- Wire onto curb zones, areas, spaces, events, policies, sessions, aggregates, and objects.

### Metrics Changes

- Add `curb_object_id` to session model.
- Add enforcement-related metric types to aggregates (e.g., `total_events`, `total_enforcement_events`).

### Authorization & API Behavior

- Clarify that Curbs and Events endpoints may require authorization by the public agency.
- Event authorization is recommended but not required, allowing public event data.
- Standardize 501 Not Implemented responses on all optional endpoints.
- Add `operator` query parameter to Curbs API endpoints.

---

## [1.0.0]

Initial OpenAPI 3.1 specification for CDS 1.0. See the `v1.0` branch for this version.
