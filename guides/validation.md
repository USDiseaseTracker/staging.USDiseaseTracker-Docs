---
title: Validation
permalink: /docs/validation/
---

# Validation

??? info "**Version 2.0.0** (updated 2026-05-18)"
    
    - Updated validation references to reflect the current supported disease set.
    - Clarified disease-specific cross-field expectations for `confirmation_status` and `disease_subtype`.
    - Aligned validation guidance language with current standards and templates.


---

The validation process checks:

- File format and structure
- Required field presence
- Data type compliance
- Valid value adherence
- Logical consistency
- Cross-field rules

Validation errors will be reported back to submitters with specific error descriptions.

<br>

## Validation Rules

### Format Validation

- File must be valid CSV format
- Required fields must be present in all rows
- Field names must match specification exactly (case-sensitive)

### Data Type Validation

- Dates must be in YYYY-MM-DD format
- Counts must be positive integers
- String fields must use exact valid values (case-sensitive)

### Logical Validation

- `report_period_end` must be after `report_period_start`
- Date ranges must align with MMWR week boundaries
- Geographic units must be consistent with reporting jurisdiction
- Age group required for age-stratified aggregations
- Disease subtype only valid for applicable diseases

### Cross-Field Validation

- Measles, Hepatitis A, Perinatal Hepatitis B, and Influenza-Associated Pediatric Mortality confirmation_status must be `confirmed`
- Pertussis, Meningococcus, Acute Hepatitis B, Mumps, Mpox, and Varicella confirmation_status must be `confirmed and probable`
- All diseases require weekly time_unit submissions
