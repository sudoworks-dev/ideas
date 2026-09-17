# Concept: A shared space to clarify an invoice

## Status

**DRAFT · v2 · 2026-09-17**

**Commercial recommendation: invest up to ten developer-days in a self-service invoice-clarification experiment, initially for small German architectural/construction-supervision offices handling recurring contractor queries. Test €39 net per initiating office per month after initial free use.** A small software business is plausible; demand for this standalone conversation layer and willingness to pay remain unvalidated. This is enough evidence for a capped experiment, not for several months of product development. The user has supplied the core interaction: upload an invoice, challenge individual positions, state a proposed amount, ask for a correction, and let the issuer reply and attach evidence to those same positions through a simple link.

Version 2 addresses demand, competitive space and monetisation explicitly. It narrows the acquisition cohort and replaces the earlier €19 starting-price hypothesis with €39; the simple general-purpose interaction remains. A €2–3k MRR result would validate a small revenue stream, not sustain salaries for the entire 2–3-person team.

This concept takes priority for the current discussion over the separately retained [invoice bridge proposal](DRAFT_erechnung_monetization.md). It does not approve implementation or claim validated demand. The earlier rejection of construction invoice checking does not establish that this particular interaction and onboarding model is commercially unviable.

| Basis | Decision |
|---|---|
| Team and ambition | Existing context: 2–3 developers, initially €2–3k MRR, no established distribution |
| User's product direction | Immediate self-service access, very little registration, external discussion per invoice position, evidence uploads, usage validation before committing to a business model |
| Services constraint | Retain the prior <20% ongoing team-time constraint; users make commercial decisions themselves |
| Local baseline | `master`, `ba0669aa90c4b10ef2ce2019231414a89d559b95`; pre-existing edits to two garden concepts remain out of scope. No remote refresh needed for concept work |
| Evidence | Current primary product pages, HOAI task definition and BAK survey, accessed 2026-09-17; no customer interviews, measured search volume, paid conversions or hands-on competitor trials |
| Review | Author self-critique; reuse the user's explicit decision against an additional agent review |

## Problem Statement

When an invoice recipient questions a position, the discussion can spread across an annotated PDF, emails, phone calls and separate supporting documents. Both parties then have to reconstruct which amount is disputed, why, what evidence answers it and whether the question is settled. This is the workflow hypothesis to verify; its frequency and cost have not been measured.

The intended outcome is a shared, position-specific clarification record that makes the next action obvious to both parties. A recipient can start independently. The issuer gets the question, the relevant position and a place to respond without buying software or joining a company workspace.

The first acquisition cohort should be owner-led German architecture/construction-supervision offices with roughly 1–10 people, active construction projects, and at least four position-specific clarification cases in a typical active month. These size/frequency filters are recruitment hypotheses, not measured market averages. The prospective buyer is the office owner; the recurring user is the person checking contractor invoices. Recruit only offices already able to judge the invoice themselves and currently exchanging questions and evidence through PDF/email. Offices without construction supervision or already satisfied with their existing workflow are outside this initial cohort. Private individuals can use the same interaction; occasional private disputes are a weaker starting hypothesis for subscriptions.

In this cohort, the initiator often acts for a building owner rather than being the invoice debtor. The interface must distinguish reviewer and payer: a review recommendation is not a payment commitment or the owner's agreement. Keep the first interaction between reviewer and contractor, with a summary exported to the owner through the existing process. If a live three-party approval chain is necessary in most cases, this cohort does not fit the proposed minimum product; do not quietly grow a construction-management platform.

Acceptance criteria for the concept:

- Preserve all central user actions: upload, manual checking, proposed reduction, correction request, external response, supporting document per position, visible resolution.
- First useful action precedes account setup; neither party needs a sales demo, paid seat or password-based registration to participate.
- An invoice can be discussed without importing a complete accounting workflow or deploying software at the issuer.
- Product status clearly distinguishes one party's proposal, the other party's response, an agreement, and payment.
- Specify how usage, bilateral participation, repeat use and eventual payment will be tested separately.

## Commercial assessment

### Demand: established work, unproven standalone purchasing demand

[HOAI Annex 10, LPH 8(g–i)](https://www.gesetze-im-internet.de/hoai_2013/anlage_10.html) explicitly includes invoice/measurement checking, comparison with order sums and variations, and cost control. This independently establishes a recurring professional task in the chosen field. It does not establish how many invoices require a discussion, that every architect performs this task, or that a separate website is wanted.

Paid offers in the adjacent workflow provide price anchors, not verified sales: CT Site sells invoice checking; Phase0 sells a broader AVA workflow; RechnungsWächter sells discrepancy and supplier-complaint handling (see comparison below). No source reviewed measures willingness to pay for precisely our guest conversation layer. Generic invoice volume, e-invoice mandates and late-payment statistics are therefore not used as demand estimates.

The inferred buying trigger is a concrete case with several unresolved positions, scattered supporting documents and repeated follow-up. The likely value is less time reconstructing the discussion and a usable record for the client. It is not the amount deducted: a legitimate invoice may be confirmed in full. A hypothetical office saving 15 minutes on each of four monthly cases saves one hour; at an assumed internal time value of €60/hour, that is €60 against a €39 subscription. Four cases at five minutes saved produce only €20 of value. Both figures are assumptions to measure, not advertised savings. The product needs either more frequent use or substantially useful coordination, not merely convenient PDF markup.

Counterevidence: the [BAK's 2026 economic survey summary](https://bak.de/kammer-und-beruf/daten-fakten/umfragen-kammermitglieder/gemeinsame-mitgliederbefragung-von-bak-bingk-aho-und-vbi-zur-wirtschaftlichen-situation-der-deutschen-architektur-und-ingenieurbueros-2025/) reports strained conditions and architectural-office backlogs falling from 11.5 to 10.0 months. That can constrain software budgets and case frequency; it is not automatically a reason to assume stronger demand for efficiency tools. Its 4,859 participating architecture/engineering offices are a survey sample, not the addressable customer count.

### Why this first niche

| Candidate | Commercial attraction | Main objection | Decision |
|---|---|---|---|
| Small offices performing construction supervision | Defined professional checking task; evidence often belongs to a particular position; office can reuse across clients/projects | Existing AVA tools, project seasonality, reviewer differs from payer | First cohort, restricted to already-manual external clarification |
| General small businesses | Straightforward buyer/payer relationship | Too broad; recurring position-level problems not established | Keep product usable, avoid diffuse acquisition |
| Hospitality/material purchasing | Supplier discrepancies have directly measurable monetary effects | RechnungsWächter already combines detection, complaints and credit follow-up; manual clarification alone may be weaker | Secondary alternative, not simultaneous launch market |
| Private consumers | Immediate need during a disputed bill | Infrequent events; often want expert judgement rather than a communication tool | Possible case purchases later, not subscription foundation |

This is a task-based niche inside a competitive market, not a claim to an empty industry. Its proposed opening is **external clarification after the professional has identified a question**, without migrating project accounting or making the contractor sign up. Marketing can address this specific job while the product stays simple and broadly usable. Do not add GAEB, measurement engines or cumulative payment accounting merely because the first users work in construction.

### Is the reachable opportunity large enough?

At €39/month, the initial target needs 52–77 retained paying offices. The research does not establish that this many offices meet the frequency filter and can be acquired economically. No top-down TAM is asserted. For illustration, if 20% of activated, qualified offices become paying customers, acquiring 77 customers needs about 385 such activations before churn; at 5%, it needs 1,540. These are sensitivity calculations, not forecasts or website-visitor conversion rates.

The first acquisition hypothesis is a useful public example and issue-summary template for construction-invoice clarification, shared through relevant contacts and communities where promotion is permitted. Search-led discovery is a second hypothesis; neither demand volume nor ranking feasibility was measured. No existing channel or partnership is assumed. A free export may attract users without converting them; count starts, shares, return visits and payments separately. Early personal onboarding can produce learning, but cannot be the permanent acquisition method at this price.

## Proposed Solution

### The smallest complete interaction

1. **Upload and mark.** The recipient drops a PDF onto the page, immediately sees it and marks a position or region. Add a reason, optional proposed reduction, or simply a question. No account wall before this action. A sample invoice provides a zero-data demonstration.
2. **Review the request.** The page gathers the open points and, when relevant, shows the invoice total, proposed deductions and proposed payment. The user checks the figures and enters the issuer's email address. An uploaded invoice is not reliable evidence of the original email sender: the recipient must confirm the contact.
3. **Share.** At the first persistent share, the initiator confirms their own email through a passwordless link. Send a neutral request with the key questions in the email and a link to the case. The initiator sees and confirms recipient, message and shared documents before sending.
4. **Respond at the position.** The issuer opens the case and can explain a position, attach a PDF/photo or propose a different amount. Participation is free and requires no conventional account. Use a private, case-scoped invitation; distinguish possession of a link from verified identity. Stronger email verification can be reserved for actions that record agreement.
5. **Record the result.** Each question can be answered, remain contested or be marked agreed by the relevant parties. Attach a corrected invoice as a new document/version if supplied by the issuer. Export a readable summary of the positions, explanations, attachments and current outcome.

The issuer must also benefit: a precise question and a quick opportunity to substantiate the original charge. Avoid accusatory framing such as an automatic verdict that the invoice is wrong. A neutral request can say that a position needs clarification and identify which evidence would help.

### Example and meaning of amounts

Illustrative case: an invoice totals €1,190 gross. The recipient disputes €119 for a position and proposes €1,071. The issuer attaches a signed work record to that position. The recipient accepts the explanation, withdraws the proposed deduction and the discussion ends at €1,190.

At every stage, the original invoice remains €1,190. A proposed amount is not an edited original, a confirmed agreement, a determination of legal entitlement or evidence of an actual payment. Closing a thread does not mean the invoice was paid. A correction request and a notice explaining an intended payment amount are distinct user-selected messages.

For the first prototype, users confirm the invoice total and the monetary effect of each disputed point on a consistent gross basis. Each issue has one current deduction so counterproposals are not added together. Show the arithmetic and allow questions with no amount. Do not infer a complete payable balance from only the annotated positions; taxes, credits, prepayments or other adjustments may require manual reconciliation. Defer complex monetary cases rather than displaying false precision.

The [BMF FAQ, sections 7b and 13](https://www.bundesfinanzministerium.de/Content/DE/FAQ/e-rechnung.html) addresses invoice correction and preservation of original structured data. This supports keeping the discussion separate from an issued invoice. It does not determine whether a user's deduction is contractually justified, and the tool does not offer that judgement.

### Scope and necessary implementation boundaries

**First prototype:** PDF display and position annotations; issue threads; explicit amount proposals; per-issue attachments; case-scoped guest sharing and email notification; simple issue/case status; downloadable summary. Support one initiator and one invited counterparty, with attribution of replies.

Manual position marking is sufficient to test the core collaboration loop. It accommodates an invoice PDF or a scan inside a PDF without first solving reliable full line-item extraction. XML-only e-invoices need a readable view; add a mature renderer if pilot inputs require them. This format extension is separate from the value hypothesis and must not turn into a proprietary validator project. No automatic commercial audit is assumed.

Cut from the first experiment: ERP/DATEV/banking integrations, automated invoice extraction, contract/measurement matching, payment initiation, formal debt collection, full archive services, mobile apps, multi-stage internal approval, organisation hierarchies and automatic reading of email replies. Notification emails include enough context for the recipient to understand the request; off-platform answers can be recorded by the initiator and labelled as transcribed, not authenticated supplier contributions.

Low registration friction still requires private access. The prototype should keep pre-share drafts local where feasible, persist cases only deliberately, restrict access per case, allow revoking invitations, and use sensible file limits and safe upload handling. State retention/deletion terms before sharing real documents and let users export them. Email verification and send limits address anonymous spam without requiring a company-onboarding process. These are implementation boundaries, not additional customer workflow screens or a reason to postpone a bounded prototype indefinitely.

### Competitive evidence and positioning

| Alternative | Current source observation | Implication |
|---|---|---|
| Email plus marked-up PDF | Working baseline to observe in pilots; no measured disadvantage is asserted | The product has to reduce reconstruction and follow-up effort enough that both parties tolerate a link |
| Generic document review | [Filestage documentation](https://help.filestage.io/en/articles/9112521-how-to-share-content-with-reviewers-and-control-their-permissions) supports review links and feedback without an account, with name/email for attribution | Guest review is a credible established interaction, not novel by itself. Invoice-specific proposals, position status and outcome summaries must provide additional convenience |
| Invoice workflow software | [Flowwer](https://www.flowwer.de/) advertises direct access creation and a €25/month offer | The statement that all alternatives require a demo is incorrect. Its page alone does not establish equivalent bilateral position discussion; this was not tested |
| Construction invoice checking | [reebuild](https://www.reebuild.com/bauunternehmen) advertises line-level checks, correction sheets and demo booking | Close feature adjacency and a possible substitute. Published capability does not establish that its complete onboarding and external collaboration experience matches this proposal |
| Direct self-service construction checking | [CT Site](https://ct-site.com/) offers PDF upload, position extraction/checking and correction-sheet export; free tier with one project/five invoices monthly, Standard €59 net/month for five projects/50 invoices | Strong contrary evidence to “only complex demo software exists.” Upload, checking and a cheap entry are already available. Public page does not establish equivalent external position threads; absence from the page is not proof of absence |
| Broader self-service AVA | [Phase0](https://www.phase0.com/kostenverfolgung) advertises invoice/LV checking and cost tracking inside AVA at €80/month annually or €100 monthly, with a 14-day no-card trial | More functionality for a higher price; a separate €39 tool must justify incremental value to existing users, not simply undercut the bundle |
| Supplier complaint management | [RechnungsWächter](https://www.rechnungswaechter.de/reklamation/) advertises position-linked supplier complaints, evidence and credit tracking from €78.40/site/month annually (€98 monthly), with assisted onboarding | Close commercial substitute, especially for recurring goods discrepancies. Shows the workflow is already monetised as an offer, not that customer numbers or our standalone demand are proven |

**Working positioning:** “Klär Rückfragen zu Rechnungen direkt an der betreffenden Position – gemeinsam mit dem Rechnungssteller.”

For the first cohort: “Rückfragen zu Handwerkerrechnungen klären: Position markieren, Nachweis anfordern, Antwort zuordnen – ohne neues Konto für den Handwerker.” Sell a completed clarification record, not an automatic verdict on correctness. Compare a representative case with email/PDF and the closest available self-service alternative during the pilot. If an existing product already delivers the same low-friction external loop well, convenience alone is insufficient differentiation. This desk review did not establish a unique feature or an incumbent's inability to copy it.

Ease of access is a real part of the offering: first result, setup effort, counterpart onboarding and required commitment matter alongside functionality. It is also easy to imitate. An early product can still be worth building if it consistently wins the particular task; no claim to an exclusive market or a durable moat is required for the experiment.

## Trade-offs & Alternatives

**Start with email/PDF only:** cheapest, familiar, often sufficient. A prototype can create a useful issue summary even when the issuer never visits. However, if most replies stay in email and users see no shared-context benefit, that invalidates the collaborative-product thesis. Do not count generated PDFs alone as bilateral success.

**Use a generic review tool:** an excellent demonstration control. It can validate whether people will discuss an invoice through a link. It may not test the intended immediate upload experience, invoice arithmetic and commercial status semantics. If it already satisfies the recruited users, an invoice-specific product needs a stronger reason to exist.

**Make both parties register:** easier account management but directly undermines the user's main hypothesis. Rejected for the first version. Lightweight proof of email access is compatible with no password or purchased seat.

**Let anyone send anonymously:** minimal apparent friction but poor sender accountability and an abuse problem. Rejected; require initiator email confirmation at first share rather than before the first useful action.

**Add automatic checking and extraction immediately:** could speed preparation, but increases scope and hides whether users value the conversation itself. Deferred. Human judgement about a position remains with the parties.

**Charge both sides or sell to large finance departments first:** may increase nominal revenue, but adds two purchase decisions or institutional onboarding. Rejected for this test. The recurring initiator is the initial prospective payer; invited participants stay free.

**Strongest objection:** an invoice dispute is adversarial enough that the issuer may ignore an unfamiliar link, respond by email or reject the platform's framing. That matters more than whether the page can be built. Neutral language, an informative email and no account requirement reduce friction; only observed recipient behaviour can resolve the uncertainty.

## Validation and business model

The user's usage-first approach is adopted. A final pricing system, market-size model and advance paid commitments are not prerequisites for a small prototype. Still identify the potential payer now and put a limit on free experimentation so usage is not indefinitely mistaken for a business.

**Recommended prototype cap:** ten developer-days for the complete narrow interaction, subject to implementation scoping; this is a proposed investment limit, not an implementation estimate or current build authorisation. If scope does not fit, cut integrations and automatic extraction, not the issuer's reply/upload capability that makes this experiment distinctive.

**First cohort:** aim for ten unrelated qualifying offices and twenty real clarification cases over approximately four to six weeks. Recruit users who already have an unclear contractor invoice; record their recent monthly case frequency and existing tools. Show the planned €39/month price when they enter the free pilot. Voluntary recruitment through relevant business contacts and permitted community participation is a channel hypothesis, not an established distribution asset. Record recruitment time as well as product behaviour. No outreach was performed in this turn.

Proposed decision thresholds, chosen to make the trial informative rather than statistically representative:

| Question | Observe | Initial continuation signal |
|---|---|---|
| Can users start unaided? | Upload to first useful issue and to share; setup failures | Most observed new users create an issue in about three minutes and prepare a share in about five, without a founder operating the tool |
| Is the problem real enough to involve the issuer? | Of twenty started real cases, how many are actually shared? | At least twelve shared cases |
| Does the second party participate? | Among shared cases, replies or supporting uploads in the product; email-only responses recorded separately | At least eight cases receive an in-product counterparty contribution |
| Does the conversation help? | Resolved questions, unnecessary follow-ups, time to understand the current status; compare recent email cases | At least six cases with a documented useful outcome confirmed by the initiator; ask counterparties about their effort too |
| Is there recurrence? | New cases by the same business when a new relevant invoice issue occurs | At least three initiators return for another real case without founder prompting |

Always report actual denominators and reasons for non-use. Do not count page views, sample invoices, team-created examples, multiple reminders to the same person or mechanically closed threads as successful clarification. If participants have no second relevant event during the observation period, recurrence is unknown rather than zero.

After two useful cases per office, or at the end of its four-week trial, offer **€39 net/month per initiating office**, monthly cancellable, with an initial allowance of twenty new cases per month and free counterpart participation. This price and allowance are test hypotheses; the business owner is the buyer, not each invited contractor or building owner. Do not bill without explicit acceptance. Retain immediate sample/upload use and a small introductory allowance after the pilot, but do not offer unlimited recurring initiation for free. Preserve access/export for existing records under the stated retention terms. Charge for continuing organisation and initiation, not for an issuer's ability to defend a position or for accessing an existing discussion.

**Payment continuation gate:** seek at least three unrelated offices paying the full test price, with at least two renewing into a second paid month and using another genuine case without founder mediation. Report how many received the offer and why the others declined. Extend observation to roughly 8–12 weeks where necessary for renewal; the initial 4–6 weeks cannot prove retention. These small counts justify only the next bounded iteration. Discounted commitments, hypothetical willingness and free use do not satisfy the gate. If useful cases are too infrequent, test the previously considered **€9 per case** separately; do not interpret case revenue as recurring subscription demand. The earlier €19/month option is retained as an alternative, not the starting offer: lowering the price doubles the required customer base and cannot repair absent recurrence.

At €19/month, €2–3k MRR needs **106–158 paying organisations**. At €39, it needs **52–77**, but that higher willingness to pay is unproven. €9 purchases need **223–334 paid cases every month** for €2–3k monthly revenue, which is not subscription MRR. Small file/email costs do not establish attractive economics: support, retention, acquisition and file retention also cost money.

A few paid subscriptions or case purchases justify a further bounded test, not a sustainable-business claim. Track founder service work against the existing <20% constraint. There must be no recurring founder mediation or invoice adjudication behind the website.

### Operating economics and acquisition constraint

Illustrative planning model, all net and explicitly unmeasured: €39 revenue minus €4 variable hosting/storage/email/payment costs leaves €35 before support. Ten support minutes per office/month valued at €60/hour leave €25 contribution before fixed costs, development, acquisition and taxes. At 52–77 offices that is €1,300–1,925/month, not team profit. Thirty support minutes leave only €5/customer; low infrastructure costs would not rescue that model.

A three-month acquisition-payback target would therefore allow about **€75 fully loaded CAC** at €25 contribution. Include time spent recruiting non-buyers, demos and onboarding. Two founder hours at €60 already exceed that budget before advertising. At 5% monthly customer churn, 77 customers require roughly four new customers per month just to maintain the base. Churn is a scenario, not measured. Track it by paid cohort once enough time passes; do not manufacture an LTV from two renewals.

For perspective, €8k MRR requires 206 offices at €39, and €25k requires 642, before discounts/churn. This can become a modest software business if low-touch acquisition and retention work; the initial €2–3k target alone does not establish a full-time business for 2–3 people. Avoid success fees on “saved” invoice amounts: they reward disputed deductions, require attribution/adjudication and conflict with a neutral conversation service.

**Distribution possibility:** each useful invitation exposes a second business to the product. That is an opportunity for discovery, not an automatic viral loop. Measure how many invited issuers later start their own cases; use a discreet optional invitation after completion and never gate their reply behind marketing consent.

**Decision:** build the capped prototype; expand only if bilateral participation, eligible repeat use and then the payment/renewal gate hold. Improve only an observed bottleneck if initiation is easy but sharing or replies fail. Stop expanding if users consistently prefer email or an existing tool, no repeat-event cohort emerges, offices refuse payment despite recurring value, or acquisition/support effort defeats the economics. Lack of qualified pilot recruitment within the recruitment window is a distribution warning, not proof of no demand; do not respond by adding more features. A useful occasional-use utility may justify a separate case-price experiment, but is not automatically a viable business.

## Open Questions

1. Can enough small offices meeting the stated frequency filter be reached economically, and do they need a separate clarification tool alongside existing AVA/email? The first cohort is selected; its size and demand remain unverified.
2. Will issuers open and answer a neutral invitation from an unfamiliar service, and which minimal identification step is acceptable?
3. Does manual position marking stay fast enough on real invoices? Extraction can be added if this measured step is the bottleneck.
4. Are proposed payment amounts central to usage, or are explanations and evidence sufficient in most cases? Keep both in the prototype but measure their use.
5. Which payment cadence fits actual frequency, and can the initiating user buy without a separate organisational approval process?
6. What retention period and file sizes fit the first users and the operating budget? Decide these before live sharing; do not make an implicit indefinite-archive promise.
7. Does the reviewer/contractor conversation work with an exported owner summary, or does the actual buying requirement force three-party approval or integrated construction accounting?

## Review

Configuration remains absent; the default review mode is `ask`. The missing-config notice was already given earlier in this task. The user's explicit refusal of an extra agent review is reused. **Actual mode: author self-critique only. No independent review or PASS is claimed.**

**SCOPE:** the minimum design is one invoice, position-linked questions and amount proposals, one external counterparty, replies and evidence uploads, status and export. Removing external participation would break the user's distinguishing workflow; it remains. Automatic extraction, integrations, payments, domain-specific adjudication and internal organisation workflows are cut because they are unnecessary to test it. Passwordless identification at sharing is retained to enable persistence and attributed communication with limited friction.

| Finding | Resolution |
|---|---|
| Prior analysis conflated invoice checking, internal approval and bilateral clarification | Treat this interaction as a separate experiment; preserve earlier evidence without importing its blanket NO |
| Registration friction was dismissed as cosmetic | Make time-to-first-value and counterparty friction explicit acceptance criteria |
| “Competitors all require demos” is too broad | Correct with Flowwer's direct signup and Filestage's guest review. No competitive uniqueness asserted |
| Usage-first could postpone monetisation indefinitely | Permit free product validation, then test a real price within the bounded cohort; separate use from revenue evidence |
| Short-paying could be presented as objectively correct | Keep original invoice, proposals, replies, agreement and payment distinct; no automated entitlement judgement |
| The issuer bears effort and may decline | Preserve recipient value, free guest participation and useful email context; measure in-product replies separately |
| Shared links could be mistaken for verified company identity | Case-scoped invitations and clear attribution; stronger verification for agreement actions without a conventional registration funnel |
| Ten-day scope could turn into a full invoice platform | Keep a manual PDF-first path and one complete bilateral loop; technical scoping still required |
| A professional checking task was being mistaken for paid demand for this tool | Separate task evidence, advertised adjacent prices and missing conversion evidence; add payment and renewal gates |
| Niche recommendation could ignore cheap self-service rivals | Add CT Site, Phase0 and RechnungsWächter; remove any premise of a vacant market or universally demo-gated alternatives |
| Construction reviewers are often not the debtor | Identify reviewer role and export to owner; no implied authority to agree payment; reject scope growth if a three-party system is essential |
| Small MRR target could be mistaken for supporting a whole team | Show contribution, support, CAC, churn and later customer-count requirements; retain assumptions explicitly |

**Author conclusion:** a capped experiment is commercially justified by an established task, plausible repeated coordination value and adjacent paid offers. The strongest contrary case is that email plus an existing checking tool already solves enough of the task, leaving too little incremental value for €39/month and an extra supplier link. The proposed gap is narrower than a new invoice-checking market and easy for adjacent vendors to copy. Confidence is medium that this is a sensible first cohort to test, low that standalone payment and economic acquisition will hold. No customer demand, retained MRR or unique competitive advantage is claimed as validated.

The concept remains DRAFT pending explicit approval of the developed design. This document does not authorise implementation, external messages or publication.
