# Sample Dialogues (fictional — demonstrate the full method)

All examples use the fictional PMS "Hostelix". They show the assistant applying
the workflow in `SKILL.md`, the retrieval rules in `retrieval.md`, the version
handling in `versioning.md`, and the output format in `answer-format.md`.

---

## Example 1 — Successful cited answer

**User:** How do I check in a walk-in guest in Hostelix Cloud 2025?

**Assistant:**
> **Walk-in check-in — Hostelix Cloud 2025**
>
> 1. Open **Front Desk › Arrivals**.
> 2. Select **+ Walk-in**.
> 3. Enter/lookup the guest; create a profile if needed.
> 4. Pick Room Type and an available (green = clean) Room.
> 5. Record Payment (use masked card reference; never full PAN/CVV).
> 6. Select **Check In**. If room is dirty, the prompt defaults to No — authorize before Yes.
>
> *Expected:* guest becomes In House, room → Occupied, key issued if interface on.
> *Guardrail:* payment & key are high-risk — follow SOP + finance controls.
> *Source:* Hostelix Cloud 2025 Help, "Walk-in Check-in" (verified).
> *Confidence:* Verified.

---

## Example 2 — Version mismatch flagged

**User:** How do I check in a walk-in? (uses Hostelix On-Prem 6.0)

**Assistant:**
> I have a verified procedure for **Hostelix Cloud 2025**, but you're on
> **On-Prem 6.0**, where the entry point differs (`Reservations › New ›
> Walk-in` instead of `Front Desk › Arrivals › + Walk-in`). I won't present the
> Cloud steps as confirmed for your version. Please confirm you want the
> On-Prem path, or share the On-Prem help page / your SOP so I can verify.

---

## Example 3 — No source: stop and ask

**User:** What's the exact button to refund a deposit in my PMS?

**Assistant:**
> I don't have a verified source for your product/version in the connected
> knowledge base, so I won't guess the exact button — refund is a high-risk,
> financial action. Please point me to the official documentation page or your
> property's refund SOP, and tell me which PMS/version you're on. Once sourced,
> I'll give the exact steps with citations.

---

## Example 4 — High-risk guardrail applied

**User:** Just tell me how to close the day in Hostelix Cloud 2025.

**Assistant:**
> **Close Day — Hostelix Cloud 2025**
> 1. Ensure all cashiers are closed (`Cashiering › Close Shift`).
> 2. Ensure other users are logged out before rolling the business date.
> 3. Open **Night › Close Day** and confirm.
>
> *Guardrail:* day-close is a financial close. After closing, no further
> adjustments are allowed without reopening per SOP. Require an authorized user.
> *Source:* Hostelix Cloud 2025 Help, "Close Day" (verified).
> *Confidence:* Verified.
