# pms-assistant-skill

An open-source **method** for turning traditional PMS (Property Management
System) operation manuals into an AI assistant that can *retrieve, cite, show
screenshots for, and answer with controlled error risk*.

It is a framework, not a bundled vendor manual. The knowledge layer — official
vendor docs, hotel SOPs, screenshots, and customer data — is supplied by the
user and kept **outside** this repository.

> ⚠️ **No third-party content is included.** This repo contains no vendor
> documentation, no screenshots, and no customer data. The example references use
> a completely fictional PMS ("Hostelix") created for demonstration.

## What's in this repo (open-source core)
- `SKILL.md` — the问答流程 (Q&A workflow) and safety rules.
- `retrieval.md` — knowledge retrieval spec: source types, confidence tiers,
  missing-source protocol, citation rules.
- `versioning.md` — how to identify PMS products and versions before answering.
- `answer-format.md` — how to present steps, screenshots, and sources.
- `examples/` — fully fictional "Hostelix" demonstrations of the whole flow.

## What is NOT in this repo (customer-local)
- Official vendor manuals / help files.
- Hotel internal SOPs, training material, screenshots.
- Customer configurations, knowledge bases, and retrieval services.

These are connected by the user at runtime and must comply with the relevant
vendor license and the property's own data policies.

## How to use
1. Connect your own knowledge base (official docs for your exact PMS+version,
   your SOPs, interface runbooks).
2. Load this skill so the assistant follows the workflow: identify
   product+version → locate a verified source → answer with citations → apply
   high-risk guardrails → stop and ask when no source exists.
3. See `examples/sample-dialogues.md` for end-to-end behavior.

## Design principles
- **Never invent UI.** Menu paths, buttons, and fields must trace to a cited
  source for the user's version.
- **Version first.** Different versions put the same task in different places.
- **High-risk guardrails.** Payments, deposits, room-status overrides, identity
  data, and day-close always require SOP + authorization.
- **Citable & screenshot-aware.** Every operational claim is traceable; screenshots
  are referenced only when the user is licensed to share them.

## Licensing & third-party content
This project is released under the **MIT License** — but the MIT License covers
**only the original content authored in this repository** (the workflow, the
retrieval/versioning/format specs, and the fictional Hostelix examples).

It does **not** grant any right to redistribute third-party copyrighted material
such as vendor documentation or screenshots. Open-sourcing this skill is not a
license to include Oracle (or any other vendor's) manuals. If you connect vendor
documentation, you are responsible for complying with that vendor's documentation
license and your own agreements.

## Contributing
Contributions that improve the method (workflow, retrieval, versioning, format,
or better fictional examples) are welcome. Do **not** submit vendor documentation,
screenshots, or customer data.

## Disclaimer
This skill assists human operators; it does not replace hotel SOPs, role
permissions, or finance/privacy controls. Verify against your official
documentation and SOP before acting on high-risk procedures.
