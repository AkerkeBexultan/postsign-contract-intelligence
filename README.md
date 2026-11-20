# Postsign — Post-signature contract intelligence

> Contracts get all the attention before they're signed, then get forgotten. Postsign keeps signed contracts live: AI flags the risks, each role sees what matters to them, and every insight becomes a tracked action.

*Product case study by Akerke Bexultan · Originally developed for a Signit product challenge, June 2026*

---

## The problem

Companies invest heavily in tools for *before* a contract is signed: legal review, negotiation, e-signature. Once a contract is executed, attention drops, but its obligations, deadlines and risks stay active for the whole life of the agreement.

Two things go wrong:

- **Coordination:** Legal owns clause risk, Procurement owns renewals, Finance owns commitments, and they don't share a common view. Contract knowledge lives in shared drives, email threads and spreadsheets.
- **Intelligence:** critical terms such as auto-renewals, uncapped liability or price escalators are buried in long documents. Tracking them across hundreds of contracts by hand isn't realistic.

**The data already exists in the contracts. What's missing is the layer that turns contract text into visibility and action.**

## Who it's for

| Role | What they need from a signed contract |
|---|---|
| **Legal Counsel** | Clause-level risk: liability exposure, auto-renewal traps |
| **Procurement Manager** | Renewal pipeline, real notice deadlines, negotiation leverage |
| **Executive / CFO** | Portfolio value, financial exposure, risk summary for the board |

## The solution

**One contract, one source of truth, a different lens for each role.**

AI summaries, clause extraction and search are now commodity features. Postsign treats them as the baseline and differentiates on three things:

1. **Role-based views.** The same contract shows different risks, data and actions depending on who's looking.
2. **Insight to action.** Users can highlight a clause and attach a task, reminder, escalation or note to it, linked to the source text instead of lost in email.
3. **Human-managed risk.** A signed contract can't be rewritten, but its risk can be managed. When a risk is mitigated (for example, insurance obtained), a user can lower its level, with a required note and a full audit trail. The AI's original assessment is always kept.

| | |

## Key product decisions

| Decision | Why |
|---|---|
| **Focus only on post-signature** | Pre-signature (negotiation, redlining, authoring) is well served. The gap and the value are after signing. |
| **Roles assigned by IT, not chosen by users** | Access control has to be enforced at the account level in a legal context. (The prototype has a persona switcher only so reviewers can see all three views.) |
| **The AI is an assistant, not an authority** | Every flag shows the clause that triggered it and a confidence level. Low-confidence results are marked "needs review", and missing data is shown as "not detected". |
| **Human overrides never erase the AI** | Trust and auditability: who changed the risk, when, to what and why. |
| **Structured search instead of pure semantic search** | Natural-language questions are converted into filters on structured clause data, so results are repeatable and auditable. |
| **Deadlines account for notice windows** | A contract renewing in 90 days with a 60-day cancellation window really has a 30-day deadline. |
| **Out of scope for v1:** counterparty access, contract authoring | They add a lot of complexity (authentication, data residency) without testing the core idea. |

## How it works: the core loop

Every session follows the same four steps, whatever the role:

**Open** (search, upload or a notification) → **Review** (through your role's lens) → **Highlight** (the clause that matters) → **Act** (task, reminder, escalation or note linked to the clause)

**Example:** a Legal Counsel gets a notification about an uncapped liability clause in a Salesforce contract (risk score 92). She creates a task to negotiate a liability cap at renewal, visible to Procurement. Three weeks later, insurance is obtained, so she lowers the risk from Critical to Medium with a note. Everyone opening the contract sees the current risk and why it changed. No emails or disconnected tickets are needed.

## Try the prototype in 2 minutes

1. Open the **[live prototype]([LIVE_PROTOTYPE_LINK](https://contract-intelligence-hub-AkerkeBexultan.replit.app)**. All data is mocked.
2. Use the persona switcher in the top navigation to compare the **Legal**, **Procurement** and **Executive** views.
3. Open the **Salesforce CRM Enterprise** contract. Find the flagged liability clause and create a task from it.
4. In **Contracts → Risk Exposure**, click a risk badge to adjust it, then check the audit trail on the contract page.
5. As Procurement, open the **Renewals** view to see the pipeline sorted by real deadline.

## How I'd measure success

The core value: **shorten the time between a risk becoming live in a contract and someone acting on it.**

- **North-star metric:** median time from a risk being flagged to an owned action (task, escalation or override)
- **Supporting metrics:** % of critical flags with an owner within 7 days · % of renewals actioned before the notice window closes · weekly active users per role
- **Guardrail:** AI flag precision (share of flags users confirm rather than dismiss)

## What's next

1. **Contracts arrive automatically:** sync with DocuSign, Adobe Sign, Google Drive and SharePoint
2. **Tasks flow into existing tools:** two-way sync with Jira, Linear and Asana
3. **Finance and compliance integrations:** NetSuite, SAP, Xero; Vanta, Drata
4. **Negotiation memory:** "We negotiated a liability cap in 7 of 9 similar contracts. Here's the wording that worked."
5. **Accountability signal:** show leadership not just which risks exist, but how the organisation responded to them

## My role and how it was built

I led the product work end to end: problem framing, user personas and scenarios, solution scope, prioritisation, interaction design and the AI approach. The working prototype was built with **Replit Agent** (React, TypeScript, Tailwind CSS) from my product specification and iterated through testing.

---

© 2026 Akerke Bexultan. All rights reserved. Shared for portfolio viewing only.
