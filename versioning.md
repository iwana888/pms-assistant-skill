# Versioning & Product Identification

PMS products differ greatly across vendors *and* across versions of the same
vendor. A procedure valid on one version may be wrong or impossible on another.
This file defines how to identify and record the product+version before answering.

## Why version matters
- Menu paths, button labels, and field names change between major versions.
- Cloud vs on-prem deployments often have different screens and options.
- Regional builds and custom configurations can alter available features.
- Answering for the wrong version can cause wrong (sometimes high-risk) actions.

## How to identify the product and version
1. **Ask the user** when not stated: "Which PMS and version are you on?"
2. **Inspect UI cues** if a screenshot or screen text is provided: the help/about
   screen, login banner, or footer often shows product and build.
3. **Detect deployment model**: Cloud (browser) vs on-prem (installed) changes
   navigation and terminology.
4. **Record it** in the answer and in any reference metadata (see
   `retrieval.md`).

## Recording version
Every reference and every answer should state the `product` and `version` it
applies to. Example metadata header for a reference:
```
product: Hostelix
version: Cloud 2025
title: Walk-in Check-in
status: verified
```

## Handling version mismatch
- If the user's version differs from the only available source, **flag it** and
  do not present click-level steps as confirmed.
- If Cloud vs on-prem differs, re-verify the specific screen before instructing.
- When uncertain, fall back to the missing-source protocol in `retrieval.md`.

## Illustrative version matrix (fictional — Hostelix)
This is an original, fictional example to show the shape of version differences.
It is NOT real vendor data.

| Capability            | Hostelix Cloud 2025        | Hostelix On-Prem 6.0        |
|----------------------|----------------------------|-----------------------------|
| Walk-in entry        | `Front Desk › Arrivals › + Walk-in` | `Reservations › New › Walk-in` |
| Room move            | `In-House › Room › Move`   | `In-House › Exchange Room`  |
| Day close            | `Night › Close Day` (auto) | `End of Day › Run Audit`    |
| Deposit handling     | Digital receipt by default | Printed voucher by default  |

The point: the *same task* sits in different places per version. Always confirm
before answering.
