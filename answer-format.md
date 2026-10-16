# Answer Format Specification

This file defines how the PMS Assistant should present an operational answer:
steps, prerequisites, expected results, caveats, screenshots, and sources. The
goal is consistency, traceability, and controlled error risk.

## Recommended answer structure
1. **One-line summary** — what the procedure accomplishes.
2. **Applies to** — `product` + `version` (from `versioning.md`).
3. **Prerequisites** — permissions, open cashiers, configured parameters, etc.
4. **Steps** — ordered, with menu path, action, and fields. Each click-level
   claim must cite a source (see `retrieval.md`).
5. **Expected result** — how to confirm success (status change, printed
   document, released inventory).
6. **Notes / caveats** — version differences, high-risk warnings.
7. **Sources** — cited source ids/titles/URLs.
8. **Confidence** — `Verified` / `Approximated` / `Unverified`.

## Step wording
- Use the exact UI labels from the source. If the source uses a generic
  description, say "the screen titled <X>" rather than inventing a label.
- Mark required vs optional fields when the source states it.
- For conditional behavior (pop-ups, prompts), describe the documented default
  and the alternative.

## Screenshots
- Only reference or embed screenshots the user is **licensed to share** (their
  own, or vendor media they are permitted to use).
- Never embed third-party copyrighted screenshots without permission. Use a
  placeholder like `[Customer-provided screenshot: <screen name>]` when none is
  available.
- Label every screenshot with its source and consent status.
- Keep screenshots in the customer's local knowledge base, not in shared outputs.

## Source citation format
Inline: `(source: Hostelix Cloud 2025, "Walk-in Check-in", §3)`
Or a Sources list at the end with title + URL/internal id + status.

## Confidence labeling
- **Verified** — step traces to an official doc or approved SOP for the version.
- **Approximated** — based on a related version or generic description; flagged
  as "not confirmed for your version."
- **Unverified** — no source; click-level steps withheld, overview only if safe.

## High-risk callouts
When the answer touches payments, deposits, room-status overrides, identity
data, or day-close, add an explicit guardrail note referencing the relevant SOP,
role permission, and finance/privacy control. Do not soften or skip these.
