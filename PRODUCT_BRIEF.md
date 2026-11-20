# Postsign — Product Brief

**Product case study · Akerke Bexultan · June 2026**

---

## 1. Problem Analysis

### The core observation

Contracts receive enormous attention before they are signed — legal review, negotiation, redlining, approvals. The moment a contract is executed, that attention largely disappears. But the obligations, risks, deadlines, and liabilities it contains don't disappear with it. They become active and live, and they stay that way for the entire duration of the agreement.

The industry has invested heavily in pre-signature tooling (CLMs, e-sign, negotiation platforms). Post-signature intelligence is underbuilt relative to the value at stake.

### Two levels of the problem

**At the business process level:**

Accountability for a contract is fragmented across roles. Legal owns the clause risk. Procurement owns the renewal and commercial terms. Finance owns the financial commitments. But none of them share a common surface. Data is decentralised — stored in shared drives, email threads, spreadsheet trackers. There is no single place where everyone who is accountable to the same contract can see what is happening and what still needs to happen.

The result is a transparency and coordination failure: roles that should be making connected decisions are operating in isolation, without visibility into what the other is doing — or not doing — with the same document.

**At the intelligence layer:**

Even when accountable people do find time to review a contract, it is hard work. Contracts are long. Critical clauses are buried in schedules, defined terms, and cross-references. Important provisions — an auto-renewal clause, an uncapped liability carve-out, a price escalator — are easy to miss on a single reading and nearly impossible to track systematically across a portfolio of dozens or hundreds of agreements.

The problem compounds at scale: keeping track of renewal dates, flagged clauses, open obligations, and negotiation history across an entire supplier base is beyond what any team can do manually.

### What this means for a solution

The problem is not that data doesn't exist. The data is in the contracts. The problem is that nobody has built the layer that translates contract text into the visibility, coordination, and action that the people accountable to it need.

---

## 2. Solution Overview

### The thesis

One platform, one contract, multiple perspectives. The data is common — every stakeholder is working with the same document. But what each role needs to *see* in that document, and what they need to *do* because of it, is different. The system should hold one shared source of truth and render it through each user's lens based on their role and responsibilities.

### What is baseline and what is the real product

AI-generated contract summaries, clause extraction, a query bar, and portfolio-level insights are now commodity capabilities in this space. They are necessary but not sufficient. They are the starting point, not the differentiator.

What Postsign adds on top of that baseline:

**1. Role-based multi-view, provisioned by IT**
Each user account is set up by the IT administrator with a defined role (Legal, Procurement, Executive). The user sees only the lens appropriate to their responsibilities. They cannot switch to another persona's view. The same contract surfaces different data, different risk signals, and different required actions depending on who is looking at it. Access control is not a feature users configure — it is enforced at the account level.

**2. Contracts that stay current**
A contract enters Postsign either by direct upload or through integration with e-sign platforms (DocuSign, Adobe Sign) and document stores (Google Drive, SharePoint). The moment a contract is executed, it is in the system. There is no manual filing step, no lag between signature and visibility.

**3. Interaction layer — from insight to action**
This is the core of the product. Finding a risk in a contract is only useful if the person who finds it can do something about it. Postsign gives every user a set of actions they can attach directly to a clause or contract:

- **Highlight and annotate** — mark the exact clause, add context for colleagues
- **Create a task** — assign a specific action to a named person with a due date and priority
- **Set a reminder** — attach a deadline alert to a clause or renewal date
- **Escalate** — route a flagged issue to a decision-maker with one click
- **Adjust the risk level** — once a risk has been mitigated (insurance obtained, a side letter agreed, business behaviour changed), a user can manually override the AI-assessed level, select the new severity, and record the specific action taken. A required mitigation note and full audit trail are attached: who changed it, to what, when, and why. The AI's original assessment is always preserved at the base of the history.
- **Track history** — every action taken on a contract is logged; nothing is lost in email

**What you can do when you find a risk (and can't change the contract)**

A signed contract cannot be rewritten. But the risk it contains can be managed. The action model is about *responding* to what is in the contract, not fixing it:

- Internally: create a remediation task, escalate to a decision-maker, request a legal opinion, flag for renegotiation at renewal
- Operationally: adjust business behaviour to limit exposure (cap usage before a liability threshold triggers, obtain insurance cover for an uncapped risk)
- Toward the counterparty: request a side letter or amendment, raise in a quarterly business review, use as a negotiation anchor at renewal

Postsign does not pretend the risk goes away. It gives users the scaffolding to manage their response to it — and creates a paper trail showing they did.

### What is deliberately out of scope

- Pre-signature workflow (negotiation, redlining, approvals) — this is a well-served space
- Contract authoring — Postsign starts where authoring tools end
- External counterparty access — adds significant complexity (auth, audit trails, data residency) that is out of scope for v1

---

## 3. User Flows and Interaction Model

### The core loop

Every session in Postsign follows the same four-step pattern, regardless of persona:

1. **Open** — find a contract via search, upload a new one, or arrive from a notification
2. **Review** — read the contract through your role's lens; AI flags surface the highest-priority issues
3. **Highlight** — mark the specific clause or provision that requires attention
4. **Act** — create a task, set a reminder, escalate, or annotate; all actions are linked to the source clause

### Scenario A — Legal Counsel: Uncapped liability to tracked action

Sarah receives a notification: "Salesforce CRM Enterprise — uncapped liability clause flagged, risk score 92." She opens the contract. The clause is highlighted with an AI annotation: *"No liability cap defined. Exposure is unlimited in the event of breach. Market standard for SaaS agreements is 12 months of fees."*

She reads the surrounding context, confirms the severity, and creates a task: **"Negotiate liability cap at renewal — propose 12× monthly fee ceiling."** The task is linked to the clause, assigned High priority, due 30 days before the renewal date. It is visible to her and to the Procurement manager responsible for the renewal negotiation.

She does not email anyone. She does not create a separate Jira ticket with no contract context. The insight and the action are in the same place, connected to the source.

Three weeks later, the General Counsel secures a commercial insurance policy that caps the company's liability exposure for this contract. Sarah returns to the Contracts tab — Risk Exposure view. She clicks the **Critical** badge next to Salesforce CRM Enterprise. A popover opens: she selects **Medium**, writes *"Excess liability insurance obtained — policy ref INS-2026-084. Renewal negotiation still in progress for contractual cap."*, and saves.

The badge updates immediately. The list re-sorts with Salesforce no longer at the top. Inside the contract detail, the Risk Status card now shows **Medium — Manually adjusted by Sarah Mitchell**, with a full audit trail beneath it: the new entry with her mitigation note, and the original AI assessment preserved below it as the baseline. Anyone who opens the contract — including Marcus in Procurement and Elena in Finance — sees the current effective risk and the evidence for why it changed.

The AI's assessment has not been deleted or overwritten. It is still there. The override is a human judgment layered on top of it, with a name, a timestamp, and a reason attached.

### Scenario B — Procurement Manager: Renewal pipeline to negotiation brief

Marcus opens the Contracts tab on the Renewals view — his default view, set to show pipeline sorted by urgency with leverage signals. The Workday HRIS Platform renews in 31 days. It has a 4% annual price escalator, no volume discount clause, and no open tasks.

He highlights the price escalator clause and creates two tasks: one to request competitive quotes from alternative vendors, one for Legal to review the escalator language before the notice window closes. He sets a reminder for himself 7 days before the cancellation window deadline.

He now has a working negotiation brief built from the contract itself — not assembled from memory and email.

### Scenario C — Executive (CFO): Portfolio risk in three minutes

Elena has a board meeting in two hours. She opens the Insights page. Her Executive view shows portfolio value, percentage at high or critical risk, and total uncapped financial exposure. The AI Risk Radar shows two critical contracts.

She clicks into each, sees the linked tasks (one has open remediation in progress, one does not), and escalates the unattended one to the General Counsel with a note. She now has a factual, sourced risk summary she can present — with evidence — without having read a single contract in full.

---

## 4. AI Architecture (Conceptual)

### What the system needs to do

**Clause extraction and classification**
Every clause in an uploaded contract is extracted, typed (liability, payment, termination, IP, confidentiality, auto-renewal, governing law, etc.), and stored as a structured object alongside its source text. This uses a combination of named-entity recognition and a language model fine-tuned on legal clause taxonomies (CUAD-style datasets as a starting point, fine-tuned on the specific clause types that matter to post-signature workflows).

**Risk scoring**
Each clause is scored using a multi-factor model: clause type weight × deviation from market standard × financial exposure magnitude. Risk scores are always accompanied by the specific clause text that drove them — the model's output is never presented without its evidence.

**Commitment and date extraction**
Financial commitments (payment amounts, price escalators, minimums, caps), renewal dates, notice windows, and termination triggers are extracted as structured fields. These feed the Renewals pipeline and financial exposure views. Date logic accounts for notice windows — a contract renewing in 90 days with a 60-day cancellation window has an *actual* deadline of 30 days.

**Natural language query**
The query bar accepts plain-language questions across the portfolio. Queries are decomposed into structured filters (contract type, clause type, date range, risk level, counterparty, financial threshold) and run against the structured clause store — not a pure embedding search. This keeps results deterministic and auditable, which matters in a legal context.

### Confidence, accuracy, and failure modes

Every AI output carries a confidence score and links to the source clause. The system does not present a risk flag without showing exactly what generated it.

Failure modes are handled explicitly:
- **Low confidence extractions** are marked "needs review" rather than classified and acted on
- **Ambiguous clauses** (liability caps buried in schedules, definitions spread across documents) are flagged with an explanation of why the system is uncertain
- **Missing data** is surfaced as "not detected" — the absence of a renewal date is itself information, not a null to ignore

The design principle: **confident assistant, not authority.** Human review of AI flags is built into the workflow, not bolted on.

---

## 5. What I'd Do With More Time

### Closing the action loop with external integrations

The most important gap in v1 is that actions created in Postsign live only in Postsign. In a real deployment, a task created from a contract clause should flow directly into the tools the team already uses: a Jira ticket, a procurement workflow, an invoice approval, a compliance checklist.

The integration roadmap in priority order:

1. **E-sign and document store sync** (DocuSign, Adobe Sign, Google Drive, SharePoint) — contracts enter the system automatically on execution, with no upload step
2. **Task system integrations** (Jira, Linear, Asana) — tasks created in Postsign sync bidirectionally with existing project management tools
3. **Finance system integrations** (NetSuite, SAP, Xero) — payment commitments extracted from contracts create draft purchase orders or invoice schedules automatically
4. **Compliance integrations** — flagged clauses trigger compliance tasks in GRC tools (Vanta, Drata)

### Negotiation memory

When a clause is flagged as high risk and a renegotiation task is created, the system should surface the organisation's own historical outcomes: *"We successfully negotiated a liability cap in 7 of 9 similar contracts. The clause language that worked was..."* Contract history becomes institutional knowledge, not institutional memory loss.

### The accountability signal

Over time, Postsign can surface a second layer of intelligence: not just what risks exist in contracts, but how the organisation is responding to them. Which risk flags have open tasks? Which have been escalated and resolved? Which have been acknowledged and ignored? This accountability signal is valuable to a GC or CFO who needs to demonstrate that the organisation manages its contract risk actively — not just that risks were identified.

### What I'd validate first

Before building any of this, one question per feature: **does this shorten the time between a risk being live in a contract and someone acting on it?** That is the core value loop. Features that don't close that gap get deprioritised.

---

*Prototype built with React, Vite, Tailwind CSS and Zustand using Replit Agent. All data is mocked. [Try the live prototype](https://contract-intelligence-hub-AkerkeBexultan.replit.app).*
