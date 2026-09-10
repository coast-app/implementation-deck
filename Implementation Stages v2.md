# Implementation Stages (v2 — draft)

Replaces the current Implementation Stages page. Rewritten so the internal process matches what we now tell customers in the implementation guide.

---

## What changed, and why

**The AE schedules the Implementation Planning Meeting before handoff.** We were losing customers in the gap between signing and starting. The old stages assumed the implementation specialist made first contact and chased a booking; that work now happens before the specialist ever sees the account. Two old stages — *Initial Contact Made* and *Kickoff Call Scheduled* — collapse into one.

**Data has one deadline, and we agree its scope at the IPM.** Rather than publishing a generic list, the specialist confirms at the planning meeting exactly which data the customer's workflows need. Everything agreed is due together, 5 business days later. One date is easier for the customer to hold and easier for us to chase than a staggered set.

**Implementation completes after the Launch Review, not after training.** Customers only surface real questions once they've used Coast on live work. We now give them a week of real use and close out on a scheduled call. The old *Completed* definition — "completed training and started using Coast" — marked us done at exactly the moment customers needed us most.

**Escalation thresholds are published.** Customers now see the follow-up and pause schedule in the implementation guide. Our internal stages need to match it exactly, or we lose credibility the first time we deviate.

**The kickoff call is now the Implementation Planning Meeting (IPM).** The name change is not cosmetic — it tells the customer, and us, that the meeting exists to decide things: the project owner, the data we need, and the dates. "Kickoff" implied a welcome; "planning meeting" implies output.

**Two tracks.** Standard setup runs 5 weeks; custom configuration runs 7. Most of our customers are custom, and quoting one number we miss on the majority is worse than quoting two we hit.

---

## Stage list

| # | Stage | Owner | Typical duration |
|---|---|---|---|
| 1 | Handoff Received | Implementation Specialist | 1–2 business days |
| 2 | IPM Scheduled | Implementation Specialist | Until the IPM |
| 3 | Awaiting Data | Customer | 5 business days |
| 4 | Configuration in Progress | Implementation Specialist | 5–15 business days |
| 5 | Configuration Review | Customer + Specialist | 3–10 business days |
| 6 | Training Scheduled | Implementation Specialist | Until training date |
| 7 | Go-Live Week | Customer | 5 business days |
| 8 | Completed | — | — |

**Exception states:** Unresponsive · Implementation Paused · Implementation Cancelled

---

## 1. Handoff Received

**Definition.** The AE has closed the deal, booked the Implementation Planning Meeting (IPM), and handed the account to an implementation specialist with internal notes.

**Owner.** Implementation Specialist.

**On entering this stage:**

- Confirm the IPM is actually on the calendar with the right attendees. If the AE hasn't booked it, send it back to them — do not book it yourself. The whole point of the change is that the customer commits while they're still talking to the person who sold to them.
- Review the handoff notes and flag the track: **standard** or **custom**.
- Check payment status in Stripe / Salesforce:
  - **Monthly terms** — if unpaid, implementation does not start. Send a payment link using the existing SOP and let the AE know the IPM may need to move.
  - **Annual subscription** — if unpaid, notify the Billing Team in Billing Support and continue with implementation. Chasing payment is Billing's responsibility, not yours.
- Send the customer the implementation guide link with their parameters filled in (company, project owner if known, IPM date, track, your name).

**Exit criteria.** IPM confirmed on the calendar, payment status resolved or escalated, implementation guide sent.

---

## 2. IPM Scheduled

**Definition.** The Implementation Planning Meeting is booked and confirmed. We're waiting for the date.

**Owner.** Implementation Specialist.

**Next steps.**

- Prepare an agenda from the handoff notes. For custom accounts, come with the requirements already understood — the customer should not have to explain their business twice.
- Send a reminder 24 hours before with the guide link attached again.
- If the customer reschedules more than twice, or goes silent before the meeting, move to **Unresponsive**.

**Exit criteria.** IPM held.

---

## 3. Awaiting Data

**Definition.** The IPM is done. We're waiting on the data we agreed we need so configuration can begin.

**Owner.** Customer.

**Four things must be decided at the IPM before you leave it:**

1. **The project owner.** One named person. Not a team, not a distribution list.
2. **The data we need.** Go through the customer's workflows and name exactly which data those workflows require. This is the whole point of calling it a planning meeting — do not hand over a generic list and hope.
3. **The data due date.** Set live in the meeting — 5 business days out. Do not email it afterwards.
4. **The target launch date.** Computed from the track, agreed out loud.

Also in the meeting: open the data template and fill in the first few rows together. Format questions are a common stall and they cost thirty seconds to prevent.

**Escalation — this must match what the customer sees in the guide:**

| Trigger | Action |
|---|---|
| Due date + 1 business day | Friendly check-in from the specialist |
| + 3 business days | Second follow-up, email *and* phone |
| + 5 business days | Loop in the AE to help unblock |
| + 10 business days | Move to **Implementation Paused** |

**Exit criteria.** Everything agreed at the IPM received in a usable format.

> **Note on custom accounts.** Custom workflows, automations, and integrations often need data beyond the standard set. Identify all of it at the IPM and put it on the same due date — don't discover it in week 3.

---

## 4. Configuration in Progress

**Definition.** The data has landed. We're importing it and building the account.

**Owner.** Implementation Specialist.

**Our commitment.** Configuration ready for customer review within **5 business days** of receiving the data. This is published in the customer guide. If you are going to miss it, tell the customer before the deadline, not after.

**Next steps.**

- Import the data and sanity-check it before building on top of it.
- Build the configuration. For custom accounts this runs longer; keep the customer updated at least weekly even when there's nothing to show.
- Book the configuration review call while you're building, not after.

**Exit criteria.** Configuration complete and a review call booked.

---

## 5. Configuration Review

**Definition.** The customer has walked through the configured account and we're applying their changes.

**Owner.** Shared.

**Next steps.**

- Walk the account with the project owner and whoever knows the operation best.
- Capture requested changes in writing and confirm scope. Changes that expand the original scope are a conversation with the AE, not a silent yes.
- Standard accounts: one revision round. Custom accounts: expect two.
- Book both training sessions before this stage closes.

**Exit criteria.** Customer confirms the configuration is ready for training, and training is on the calendar.

---

## 6. Training Scheduled

**Definition.** Training is booked. Sessions are being delivered.

**Owner.** Implementation Specialist.

**Next steps.**

- Confirm attendee names in advance. "We'll see who can make it" is how sessions get rescheduled.
- Session 1 — admins. Session 2 — the wider team.
- Share recordings and materials after each session.
- **Book the Launch Review before the training session ends.** A week out. This is the single most important step in this stage — it is the same mechanism that fixed our pre-IPM drop-off, and it only works if it happens while you still have their attention.
- Set up somewhere for the customer to collect questions during Go-Live Week. A Coast workspace is ideal — they get practice in the product during the exact week the habit needs to form.

**Exit criteria.** Both sessions delivered and the Launch Review is on the calendar.

---

## 7. Go-Live Week

**Definition.** The customer is using Coast on real work. We're on standby and heading toward the Launch Review.

**Owner.** Customer.

**Next steps.**

- Check in mid-week. Light touch — you're making sure they've actually started, not managing them.
- Answer questions as they come, and add anything structural to the Launch Review agenda.
- If the customer hasn't started using Coast by mid-week, find out why. This is usually a signal that training missed, not that they're busy.

**Exit criteria.** Launch Review held.

---

## 8. Completed

**Definition.** The Launch Review has been held, outstanding tweaks are applied, and the customer confirms Coast is doing what they need.

**This is a change.** We previously marked customers complete after training. We now complete after they've used the product on real work and told us it works.

**Next steps.**

- Apply anything agreed on the Launch Review.
- Hand over to ongoing support and set the check-in cadence.
- For phased implementations, this closes **Phase 1 only**. Scope and schedule the next phase separately.
- Log what went well and what didn't. If the implementation ran long, note where the time went — we need that for the delay conversations below.

---

## Exception states

### Unresponsive

**Definition.** The customer has gone silent before the IPM has happened.

**Criteria.** No response to daily follow-ups by email and phone across 7 consecutive business days.

**Next steps.** Escalate to the AE and account management. The AE booked this meeting and has the warmest relationship — they are the right person to re-engage.

> This definition has narrowed. It used to mean "hasn't scheduled a kickoff call." Since the AE now schedules it, Unresponsive means the customer is not showing up to something already booked — which is a different and more serious signal.

### Implementation Paused

**Definition.** The customer has gone quiet during implementation, or the data is 10 business days overdue.

**Criteria.** Either of:

- Data more than 10 business days past its due date.
- No customer activity for 2 consecutive weeks, with at least weekly follow-up attempts throughout.

**Next steps.**

- Tell the customer plainly that the project is paused and exactly what restarts it. Pausing is not cancelling and the message should say so.
- Escalate internally and notify the AE.
- Remove the account from your active caseload so your capacity goes to customers who are moving.

> Renamed from *Implementation Stalled*. "Paused" is what we now tell customers in the guide, and the internal name should match the external one so nobody has to translate.

### Implementation Cancelled

**Definition.** The customer has cancelled their account or abandoned implementation before completion.

**Next steps.** Escalate internally, gather the churn reason from the customer, and update Churn Details.

---

## Delay accommodation requests

Unchanged in substance, but the accounting is now easier because the thresholds are published.

When a customer asks for a discount, free months, or a refund because implementation ran long:

- Loop in the Billing Team.
- Send Billing an accounting of where the time went. If the delay traces to the customer — late data, missed reviews, no project owner — we do not give accommodations. If it traces to Coast, we may. Billing Managers decide.
- The published escalation timeline in the customer guide is your evidence. If we followed it and documented the follow-ups, the accounting writes itself.

See the existing SOP: *Request for extension of renewal date or free months due to delays in implementation*.

---

## Migrating from the old stages

| Old stage | New stage |
|---|---|
| Review Customer Account | Handoff Received |
| Initial Contact Made | Handoff Received *(merged)* |
| Kickoff Call Scheduled | IPM Scheduled |
| Data Collection in Progress | Awaiting Data → Configuration in Progress *(split)* |
| — | Configuration Review *(new)* |
| Training Sessions Scheduled/Conducted | Training Scheduled |
| — | Go-Live Week *(new)* |
| Completed | Completed *(definition changed)* |
| Unresponsive | Unresponsive *(definition narrowed)* |
| Implementation Stalled | Implementation Paused *(renamed)* |
| Implementation Cancelled | Implementation Cancelled |

Accounts currently sitting in *Data Collection in Progress* need to be split by hand: those still waiting on data go to **Awaiting Data**, those we're actively building go to **Configuration in Progress**.

---

## Open questions for the team

1. Who enforces the AE booking the IPM, and what happens when it doesn't get booked? The process assumes the specialist can send it back, which needs sales leadership behind it.
2. Do we need a separate stage for phased implementations, or is a property on the account enough? Recommend a property — otherwise every phase duplicates eight stages.
3. Is 5 business days for configuration realistic across current specialist caseloads? It is published to customers now, so it needs to be a number we hit rather than a number we aim at.
4. Who owns keeping the customer guide's thresholds in sync with this page when they change?
