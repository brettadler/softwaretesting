# Gerkin Style

# The following rules guide the expected behavior in scenarios above.

Rule: Required fields on Create
  - Name, Primary Contact, Email, Status are required.

Rule: Status values
  - Allowed values: Active, Archived.
  - Default on create: Active.

Rule: Email validation
  - Must be RFC 5322-conformant (basic format check is acceptable for UI).
  - Case-insensitive uniqueness is not required, but duplicate detection should warn on same Email or highly similar Name.

Rule: Archived behavior
  - Archived clients are excluded by default from the list.
  - Archived clients are read-only until unarchived.

Rule: Sorting
  - Sort is toggleable ascending/descending.
  - Default sort: Created At desc.
  - Stable sort maintained for equal keys.

Rule: Pagination
  - Default page size 25; options include 25/50/100.

Rule: Search
  - Case-insensitive; trims whitespace.
  - Matches Name, Primary Contact, Email, Tags.

Rule: Filters
  - Status (Active/Archived), Created At (date range), Tags (multi-select).
  - Multiple filters combine with AND; within a multi-select filter, values combine with OR.

Rule: Export
  - Formats: CSV (UTF-8, comma-separated, quoted as needed).
  - Respects current sort, search, and filters.
  - Row limit: 50,000; show message when exceeded.
  - Column headers included; dates exported as ISO 8601 UTC.

Rule: Concurrency
  - Optimistic locking via entity version.
  - On conflict, show reload message and block overwrite.

Rule: Audit logging
  - Record actor, action, target, timestamp UTC, and field-level deltas for edits.
