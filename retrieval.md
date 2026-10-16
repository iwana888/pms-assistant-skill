# Knowledge Retrieval Specification

This file defines how the PMS Assistant finds and trusts the sources it answers
from. It is product-agnostic and assumes the user has connected their own
knowledge base (official docs, SOPs, runbooks).

## Valid source types (in priority order)
1. **Official vendor documentation** for the exact product and version the user
   runs. Preferred over everything else for click-level steps.
2. **Hotel-approved SOP / training material** — internal procedures authorized
   by the property. Use when it overrides or supplements vendor docs.
3. **Interface runbooks** — property-specific instructions for door-lock,
   payment, call accounting, ID verification integrations.
4. **Version-agnostic overviews** — only when explicitly labeled as not confirmed
   for the user's version, and never for high-risk click-level steps.

## Required source metadata
Every reference in the knowledge base should carry:
- `product` and `version` (e.g., "Hostelix Cloud 2025")
- `title` and `url` or internal identifier
- `chapter` / `page` if applicable
- `date_checked`
- `status`: `verified` (official) | `hotel-approved` (SOP) | `unverified`

## Retrieval procedure
1. From the user query, extract the intended **action** (e.g., "check in walk-in")
   and confirm **product+version** (see `versioning.md`).
2. Query the knowledge base filtered by `product` + `version` + action keyword.
3. Prefer a `verified` source for that version. If only a different version's doc
   exists, flag the mismatch and require re-verification before answering
   click-level steps.
4. For high-risk actions (payments, deposits, day-close), require a `verified` or
   `hotel-approved` source — do not answer from an `unverified` overview.
5. Attach the source id to every operational claim in the answer.

## Citation requirement
- Every menu path, button, field, and parameter name in the answer must trace to
  a source present in the knowledge base.
- If a claim cannot be sourced, omit it or label it explicitly as
  "not confirmed for your version."

## Missing-source protocol
When no matching source exists:
- Do **not** answer click-level steps from memory.
- Respond: the step is unverified for the stated version; ask the user to provide
  the official documentation page or their SOP.
- Optionally give a clearly labeled version-agnostic overview only when safe and
  non-financial.

## Copyright & redistribution
- Do not ingest or redistribute third-party copyrighted manuals unless a license
  or permission allows it.
- When not licensed to embed a vendor document, reference it by **title and URL
  only** (a pointer), not by copied text or screenshots.
- Keep vendor docs and customer data in the user's local/private knowledge base,
  outside any shared or open-source artifact.
