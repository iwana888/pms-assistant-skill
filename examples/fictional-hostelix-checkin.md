---
product: Hostelix
version: Cloud 2025
title: Walk-in Check-in (fictional example reference)
status: verified (fictional sample — for demonstration only)
note: This is an ORIGINAL, FICTIONAL document created to demonstrate the
      reference format. "Hostelix" is not a real product and no real vendor
      documentation is reproduced here.
---

# Walk-in Check-in — Hostelix Cloud 2025 (fictional sample)

## Applies to
Hostelix Cloud 2025. For Hostelix On-Prem 6.0, see the version matrix in
`versioning.md` (entry point differs).

## Prerequisites
- User has the `FrontDesk.Arrivals` permission.
- A room of the requested type is available and clean (or user is authorized to
  override a dirty room).
- Payment method recorded before completing check-in (property policy).

## Steps
1. From the home screen, open **Front Desk › Arrivals**.
2. Select **+ Walk-in** (top-right). The *New Stay* panel opens.
3. In **Guest**, enter last name; if profile exists, pick it from the lookup.
   Otherwise choose **Create profile** and fill name, ID type, and contact.
4. In **Room Type**, choose the type; in **Room**, pick an available room from
   the list (a green dot means clean & inspected).
5. In **Payment**, select a method. For card, enter the masked card reference
   from the profile or tap the terminal; do not type full card numbers.
6. Select **Check In**. If the room is dirty, Hostelix prompts
   "Room is not clean. Continue?" — default **No**; choose **Yes** only with
   authorization.
7. On success, status becomes *In House* and a key card is offered if the
   door-lock interface is enabled.

## Expected result
- Guest appears under In-House Guests.
- Room status flips to Occupied.
- (If enabled) key card printed / mobile key issued.

## Notes / caveats
- High-risk: payment and key issuance. Follow property SOP and finance controls.
- Do not expose full card numbers or CVV in chat or logs.

## Sources
- Hostelix Cloud 2025 Help, "Walk-in Check-in" (fictional sample).
- Property SOP: Front Desk — Arrivals (customer-provided).
