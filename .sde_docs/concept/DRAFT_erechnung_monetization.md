# Concept: A recipient-specific invoice bridge for small retail suppliers

## Status

**DRAFT · v6 · 2026-09-17**

**Recommendation: test a small paid software product that makes existing outgoing invoices usable by a specific retail customer, starting with Lexware Office suppliers invoicing through Markant.** Invest at most five developer-days in the first technical prototype, after reproducing the problem on two current customer examples. This is a positive recommendation for a bounded experiment, not evidence of an already validated business.

Working name: **Rechnungsbrücke**. The offer is: keep your invoicing system, select the recipient, add the missing business identifiers once, and export a checked invoice with a transparent change report. Start with one source format and one documented recipient route. Proposed price: **€79 net/month**. At that price, 26–38 active customers produce €2,054–3,002 MRR.

| Item | Governing basis |
|---|---|
| User request | Identify the most worthwhile invoice-related niche/product to prototype and validate; do not merely reject another supplied idea |
| Team | 2–3 people, software/agentic-development background; no existing distribution |
| Initial target | €2–3k MRR, explicitly resolved in v5; €8k is a later milestone |
| Services | Preserve the <20% ongoing team-time constraint recorded in the approved WEG strategy; no recurring manual invoice repair business |
| Scope of this turn | Research and concept only; no implementation, outreach, purchases, or publication |
| Local baseline | `master` at `7a8e80a309ab6fb1de303f6f5dc4205937461e75`; pre-existing changes in the two garden concepts, untouched; remote freshness not checked and unnecessary for this work |
| Review | Author self-critique. Additional agent review explicitly declined by the user in this turn |
| Confidence | Medium that this is worth the bounded test; low on paid demand, attainable customer count, and durability until tested |

### History and decision precedence

The complete previous document, including v1–v5 findings, sources, open questions and reviews, is preserved without content changes in [the v5 historical record](history/erechnung_monetization_v5_2026-09-17.md). This v6 replaces its current recommendation, not its historical evidence. Existing German/PDF editions describe earlier versions and are not v6 translations.

The generic inbox, viewer, archive and approval-suite proposals remain unattractive starting points. However, **the blanket conclusion that invoice software cannot be a worthwhile business is withdrawn as insufficiently supported**. Competitor existence, funding and theoretical copying ability establish competitive pressure, not market foreclosure. An unknown vendor's trust hurdle is a cost to test, not proof that buying is impossible. Nor are €200–380 subscriptions universally unsellable without enterprise sales. Historical assumptions about churn and sales cycles were not measured for this team.

The [approved WEG strategy](APPROVED_weg_business_strategy.md) remains unchanged. The present user request explicitly reopens invoice-related exploration. Its filters remain useful challenges, but v6 does **not** claim to have passed all of them: native-software catch-up and repeatable distribution remain material risks. Approving v6 would accept a limited experiment despite those risks; it would not approve a WEG revival or a relaxation of the services constraint.

## Problem Statement

Small manufacturers and brands supplying retail customers can have an otherwise usable invoicing system whose export does not satisfy a buyer's operational requirements. The seller then faces rejection, repeated manual entry, or a system migration. The commercial problem is getting the invoice into the customer's processing flow; a generic standards-validation badge alone does not accomplish that.

**Selected initial buyer:** the owner or office manager of a small German supplier that uses Lexware Office, repeatedly invoices retail locations via Markant, and can demonstrate a current export/recipient mismatch. Food and nonfood suppliers are prospect pools, not independently proven segments. Employee count and turnover are not qualification criteria.

A qualified prospect must have all of the following:

- A recent rejection or documented onboarding failure and access to the applicable recipient requirements.
- Recurring affected invoices, provisionally at least 20/month, or measured recurring effort sufficient to justify €79. This is a screening hypothesis, not a market statistic.
- Authoritative GLNs, item identifiers and references already available in its business records.
- A supported XML export and an existing route on which that recipient accepts the resulting XML format; no new EDI transport project.
- A reason to retain its source system, and a problem that cannot be removed by a simple setting or currently available update.

**Intended outcome:** identify whether a reusable adapter can remove repeated invoice preparation work and recipient rejection for this cohort at a commercially useful price.

Acceptance of the concept requires a named buyer, evidence of the problem, direct substitutes, a narrowly specified prototype, acquisition and economic assumptions, and falsifiable continuation/stop decisions. Business validation additionally requires actual payment, recipient acceptance and repeat use; none has occurred in this turn.

## Evidence: what is established and what is not

All linked public pages below were inspected on 2026-09-17. Publication dates are distinguished from access dates. Public documentation establishes advertised functionality, not hands-on performance or vendor revenue.

| Evidence | What it supports | Limitation / contrary implication |
|---|---|---|
| [Joint letter of eight business associations, 13 May 2026, p. 2](https://www.bauverbaende.nrw/fileadmin/user_upload/8er_eRechnung_Validierung_VoSt-Abzug_13-05-2026.pdf) reports Markant figures: 48% of electronic invoices rejected between 1 Jan 2025 and 31 Mar 2026; 18% of suppliers sending e-invoices | Processing failures are a reported operational issue, beyond a hypothetical inconvenience | Underlying Markant dataset unavailable; advocacy document, not independent audit. Invoice denominator, retries and error mix are unspecified. **Not** a claim that 48% of suppliers need our product, or that GLNs cause all these errors |
| [VeR trade initiative, 14 July 2026](https://www.verband-e-rechnung.org/handel-und-ver-pushen-qualitaet-bei-e-rechnungen/) identifies missing identifiers and inconsistent fields; REWE, hagebau, Markant and Müller participate | Standards-conformant documents can still create process problems in retail | Also powerful evidence against durability: the industry is actively standardising the missing conventions |
| [GS1 implementation recommendation, Dec 2025, §§5.4.1 and 5.4.6](https://www.gs1-germany.de/fileadmin/gs1/fachpublikationen/GS1-AE-EN16931_Teil1-V2.0_final12-2025.pdf) specifies GLNs for party roles and GTIN representation | The initial mapping can be explicit and deterministic, using identified source data | GS1 guidance is not the complete rule set for a particular Markant account. Applicable versions and buyer instructions still have to be obtained |
| [Lexware Office's current XRechnung help](https://help.lexware.de/de-form/articles/548465-eine-xrechnung-erstellen) documents export limitations, including some PDF text fields absent from XML | Source-system export limitations are real | The page does **not** specifically prove that BT-71 is still unavailable today. We did not test a live account. That exact deficiency must be reproduced before development |
| [Sage user discussion, Mar–Sep 2025](https://www.sage-forum.de/threads/erechnung-zugferd-f%C3%BCr-markant.5270/) reports missing party GLNs and a code change that passed Markant-specific validation | A concrete historical example of the mechanism and a small technical remedy | Anecdotal, different source system, old. The same thread advertises an integration service and anticipates native support. It strongly undermines any claim to a technical moat |

A January 2026 [Lexware user report](https://www.reddit.com/r/selbststaendig/comments/1qq3hil/erechnungsfail_bei_lexoffice_trag_es_doch_in_den/) supplied the initial Lexware/Markant hypothesis; it is an unverified anecdote, not a current feature test. The [April 2026 imker discussion](https://www.imkerforum.de/forum/thread/85187-e-rechnung-mit-gln-nummern-und-steuersatz-der-durchschnittssatzbesteuerung/) also describes GLN trouble, but its claim that easybill cannot populate those fields is contradicted by current easybill documentation. We do not carry that outdated claim forward or add agricultural tax cases to the MVP.

**Inference:** an installed-base compatibility gap is a more promising starting hypothesis for this team than another generic invoice-management app. **Unknown:** how many still-affected suppliers are reachable and will buy rather than switch, configure, or wait. No interviews, customer files, recipient tests or purchase commitments have been obtained.

## Proposed Solution

### The job and the purchase reason

Illustrative example, not an observed customer result: a supplier already prepares 60 monthly invoices in its accounting software. Several go to different retail locations. Its source export omits the structured delivery-location identifier. An employee currently re-enters or repairs that information for every invoice. Rechnungsbrücke associates each known location with its confirmed identifier and reuses that mapping for subsequent batches, showing every change before export.

The prospective purchase reason is **repeatedly avoiding a manual second invoicing workflow while keeping the existing system**. At 60 invoices × 3 minutes avoided, the hypothetical saving is 3 hours/month; at a buyer-assigned €40/hour, €120. These are explicit sensitivity inputs, not evidence of ROI. At 20 invoices × 1 minute, the benefit is only €13.33 on the same basis: this buyer should not pay €79.

The face value of a delayed invoice is not product value. Reduced delay may have value, but no invoice principal is counted as newly earned money, and technical acceptance is not a payment guarantee.

### Smallest useful prototype

A local file-processing application on the operating system shared by the first pilot customers. Use established parsing/validation components such as [KoSIT Validator](https://github.com/itplr-kosit/validator) and [Mustangproject](https://github.com/ZUGFeRD/mustangproject), selecting exact versions after inspecting samples. Their existence supports feasibility, not a claim that they already implement the recipient's rules.

1. Import a batch of XML invoices from **one verified Lexware export format/version**. Show unsupported inputs explicitly.
2. Load a small customer-approved mapping table: seller/buyer/location identifiers and, only if required in the same initial cases, SKU-to-GTIN mappings. Never infer identity from a vague name match. Unknown locations/items become unresolved cases.
3. Display required additions or conflicts. Populate only an allowlist of confirmed identifiers/references; keep monetary values, tax treatment, invoice identity and business parties unchanged. Wrong parties or conflicting existing identifiers require correction in the source process.
4. Validate the output against the relevant standard bundle and the **documented subset** of recipient rules. Distinguish these results from actual recipient acceptance; never label a generic validator pass “Markant accepted”.
5. Export a separate result with a readable before/after report and a manifest relating input hash, output hash, profile version and user confirmation. Keep original files untouched. The customer submits using its established route and retains the issued output in its existing records system.

Processing locally reduces the initial need to give an unknown vendor invoice content or mailbox credentials. It does not eliminate software trust, installation friction, or retention obligations. The prototype must have no invoice-content telemetry, external model calls or silent network validation. Diagnostic exports are deliberate and redacted.

Start with **new, not-yet-submitted invoices and controlled test copies**. Previously issued/rejected invoices may need a formal correction process; arbitrary XML mutation and resubmission under the same identity is not assumed permissible. The issuer must settle the authoritative output, retention and correction workflow before a live pilot. The [BMF FAQ §§7b, 8, 12–13](https://www.bundesfinanzministerium.de/Content/DE/FAQ/e-rechnung.html) separately addresses correction, agreed transmission routes, structured-data precedence and retention. This concept does not certify a legal workflow.

**Cuts:** no OCR or plain-PDF extraction; no ZUGFeRD PDF rewriting in the first prototype; no EDI/Peppol transport; no API/OAuth/mailbox access; no bookkeeping, payment, archive service, rejection-email agent, general XML editor, universal rule builder or second source connector. These cuts exclude many potential customers and are intentional. If qualified buyers require these capabilities before any value can be delivered, the current experiment fails rather than expanding by default.

**Why the remaining complexity exists:** saved mappings remove repeated entry; a batch workflow makes recurring use measurable; source/output traceability reduces operational ambiguity; two-layer validation prevents a misleading standards-only success message. A one-off XML script could prove technical repair but could not test recurring usability and maintenance value.

### Competition and the actual wedge

| Substitute | Verified offer | Consequence for our selection |
|---|---|---|
| Native configuration/update | [easybill](https://support.easybill.de/hc/de/articles/360017769980-BT-Felder-bei-ZUGFeRD-und-XRechnung-Quellen-und-Unterschiede), updated 16 Sep 2026, exposes seller, buyer and delivery-location identifiers | Native remediation is the first option checked. Do not target customers already satisfied by this. Migrating or using easybill for these invoices is a real alternative |
| Source-specific addon | [HPHock's JTL addon](https://hphock.de/jtl-wawi-e-rechnungen-globalids-markant-konformitaet-in-version-1-7-2/) explicitly addresses Markant identifiers | Confirms that packaged adapters exist and threatens expansion. No JTL connector in the first product; no claim that this is a new category |
| Retail-specific automation | [ATN's Markant offer](https://atnservices.de/handelspartner/markant): €199/month net, no setup fee, invoice generation from buyers' sales data and EDI delivery | Direct competitive benchmark. Our narrower hypothesis preserves the existing invoice-creation workflow and uses files locally. ATN may still be better; its ability to accommodate the same input was not tested. Price alone is insufficient differentiation |
| Recipient's own service | [Markant m.eInvoicing](https://lp.markant.com/einvoicing) offers integration and data enrichment | A credible, trusted substitute. No pricing or willingness to serve these small accounts verified; **do not assume** it is expensive or inaccessible |
| General converter | [Invoice-Converter](https://www.invoice-converter.com/de/pricing) advertises browser conversion at €10/month billed annually (€15 monthly) and other tiers | A low price anchor. We cannot charge €79 for conversion alone. Exact recipient-profile depth not tested; include it in the pilot comparison |
| EDI integrators / converters | [softma](https://softma.de/) names Markant and multiple source systems; [TransdatiX](https://www.transdatix.com/Applications/Convert/ZEV-Markant/Invoice/Schema) documents a Markant converter | Integration is an established competitive business. No claim of an empty market or exclusive access |

**The wedge is a hypothesis, not an observed product gap:** a reusable, local, file-based bridge for one installed source system and one buyer route, with less workflow change than migration or a new invoicing service. Its repeatable operational fit must win a live comparison. If a cheap existing tool handles the same recurring job conveniently, do not build merely to undercut it.

### Why someone would keep paying

Invoices continue to need the source-to-recipient mapping, location/item mappings evolve, and the supported export/profile versions need maintenance. Those are possible reasons for recurring payment. A customer whose problem is permanently solved by a static patch has little reason to subscribe; that is the central retention risk, not a minor objection.

There is no strong initial moat. Reusable regression cases, documented acceptance history and relevant customer acquisition could become assets, but none exists yet. Do not assume the gap lasts through 2028, that expansion is automatic, or that a native fix can always be offset by finding another missing field. Stop selling affected adapters when native support makes them redundant.

## Trade-offs & Alternatives

| Candidate | Strongest case | Why it is not the first experiment |
|---|---|---|
| Generic inbox/approval/Steuerberater handover | Proven recurring administrative job | Prior work documents close, inexpensive substitutes; broad integration surface for a weak initial buying trigger. Historical conclusions remain bounded by their evidence |
| Small construction invoice review | Potentially substantial recurring labour savings and error prevention | Requires reliable matching of contracts, invoices and often measurements. Prior v5 left the sub-10-person gap untested; that remains an open alternative, not a proven impossibility. More document diversity and domain judgement than the selected prototype |
| Supplier credit/return follow-up | Recoverable amounts and tangible completion state | [RechnungsWächter](https://www.rechnungswaechter.de/reklamation/) already advertises matching complaints to credits; [its handwork page](https://www.rechnungswaechter.de/handwerk/) advertises price/quantity checks and €78.40/month annually (€98 monthly). No customer-specific reason to prefer our version established; it also needs more source documents |
| Parcel invoice audit | Structured data and a monetary outcome | [VersandGutschrift](https://www.versandgutschrift.de/) advertises no-retainer success pricing, including small shippers. Tariff interpretation, claim preparation and recovery create a greater services risk for this team's constraint. Not impossible, but not the leanest first bet |
| Invoice rejection dashboard for buyers | One buyer potentially brings many suppliers | Multi-party adoption and buyer-side integration before the supplier obtains value; cut from this concept |
| Manual XML repair / consulting | Could earn setup money quickly | Does not satisfy recurring software economics and the ongoing services limit |
| Configure existing software or do nothing | Cheapest and safest when existing configuration solves the job | Mandatory control alternative for every pilot; often the correct answer for an individual prospect |

This is a relative selection among researched shapes, not an exhaustive proof that it is the best possible niche in all invoicing.

## Economics and distribution

All prices below are proposed net prices and all operating inputs are planning assumptions. Neither market size nor conversion rate is known.

| Subscription | Customers for ≥€2k MRR | Customers for ≥€3k MRR |
|---|---:|---:|
| €49 | 41 | 62 |
| **€79 selected test** | **26** | **38** |
| €99 | 21 | 31 |

At €79, €8k needs 102 customers and €25k needs 317. The initial goal is not three salaries. At 38 customers, 2% monthly churn requires 0.76 replacement customers/month on average; 5% requires 1.9. These are scenarios, not estimates.

Illustrative unit economics: €79 less €5 delivery/licensing/payment cost, 15 minutes support at €60/hour (€15), and €10 allocated maintenance leaves **€49/customer/month before acquisition, fixed costs and taxes**. At 38 customers, that is €1,862, not €3,002 profit. If support averages an hour, the same model leaves €4. This would be commercially unacceptable at the selected price.

Target acquisition envelope: at most €100 cash plus four founder-hours at €60 per acquired customer = €340 economic CAC, approximately seven months' payback at €49 contribution. This is a test ceiling, not a predicted cost. Three initial customers cannot establish a reliable CAC or churn rate.

A prospect list is not distribution. At a hypothetical 10% qualified-prospect-to-paid rate, 38 customers need 380 qualified prospects before churn; at 5%, 760. Public evidence does not establish that many still-affected Lexware/Markant users. **This denominator is the biggest commercial evidence gap.** An association or platform partnership is not assumed.

Initial acquisition should follow the symptom: search terms such as “Markant Rechnung abgelehnt”, “BR-MARKANT-05”, “BR-MARKANT-06” and “Lexware GLN”; permitted participation in relevant supplier/software communities; and opt-in introductions by independent software coaches. Public supplier/brand websites provide a candidate pool only. Do not send unsolicited messages as part of this concept task.

The first offer should be a concrete demonstration on one current rejected test document and a short explanation of the supported export. No generic “E-Rechnungspflicht” campaign. We must measure how many buyers can be reached through an initial channel and whether later customers can be acquired through it again without founder personal connections.

## Bounded prototype and market test

**Recommended resource cap:** seven total person-days across qualification, prototype and initial selling, of which at most five are development; up to €500 external experiment spend. These are proposed limits, not spending authorisation. At an illustrative opportunity cost of €500/person-day, the experiment costs up to €4,000 including cash; it is not “free because AI can build it”. Calendar observation may run 6–8 weeks to see subsequent billing cycles. Development stops at the cap.

### Step 1 — Establish that the exact opening still exists

Within the first two person-days of research/selling effort, identify a pool of 30 plausible suppliers or opt-in referrals and seek ten problem conversations. These are funnel targets, not promised results. Examine the last actual rejection, the current export, the recipient's instructions and the workaround. Ask what happens next month, not whether they like an app.

Proceed to code only with **two unrelated businesses** showing the same current, reproducible source/recipient mismatch and providing permitted test samples or an equivalent observed reproduction. Confirm their route accepts the selected output format. First try native configuration, current updates and a relevant existing alternative. A review of a forum post is not a substitute for this step.

A rejected standard invoice does not establish a recipient-mapping problem: separate source invalidity, missing business data, incorrect routing and true profile differences. Only the last category, with available authoritative data, is initially served.

If samples, route requirements or the current gap cannot be obtained within the cap, stop this build decision as **unvalidated**. Do not label the whole market impossible and do not substitute a wider connector platform.

### Step 2 — Build the narrow demonstrator

Spend at most five developer-days on the five-step prototype above. Build from real patterns, use anonymised regression fixtures, and keep first live credentials and transmission outside the tool.

Acceptance before a paid operational pilot:

- Original inputs remain byte-identical and exports show their provenance.
- Only allowlisted approved fields change; monetary/tax/party conflicts block export.
- Malformed XML, unknown mappings, conflicting references and unsupported profiles fail visibly; XML external-entity/network resolution is disabled.
- Known good cases remain good; the reproduced failures are removed under the pinned rules without changing financial substance.
- At least one new/test invoice from **each of the two businesses** receives documented acceptance through its actual recipient test/onboarding route. A local green validation result alone fails this criterion.
- Issuer retention and correction responsibilities have an agreed operational path. No claim of general legal certification.

These are proposed future checks. No prototype or tests were run in this concept-only turn.

### Step 3 — Test a subscription, not politeness

Offer **€79 net for the first month, monthly cancellable**, with the supported scope stated. No setup fee during the experiment. Target three unrelated paying suppliers from the first ten qualified problem conversations, with a maximum of one hour onboarding per customer. Refunded payments, free trials and compliments do not count.

Record for every candidate: source version, invoice frequency, failure class, existing substitute tried, acquisition time/cost, willingness to pay, onboarding time, manual interventions, actual recipient results and reason for declining. Founders must not silently repair every invoice behind the scenes.

**Continue toward an MVP only when:** three pay; at least two process subsequent batches without founder invoice editing, have demonstrated useful recurring benefit, and renew for a second paid month; onboarding is ≤1 hour/customer; ongoing support is trending ≤15 minutes/customer/month; and total customer-specific service work stays below 20% of actual available team time. At least two customers must be acquired through a channel the team can repeat beyond personal contacts.

Measure the next ten paying customers before substantial expansion. Three pilots justify the next bounded step, not a scale-up or a claim that 38 are reachable.

**Stop or change the commercial model when:** native configuration fixes the cases; the buyer prefers an existing tool; only one-off repair sells; requirements differ so much that each customer needs custom code; EDI transport/OCR is necessary for the first users; current samples do not reveal enough recurring value; or paid renewals fail. A one-off utility may still be sellable but would not validate the MRR thesis.

## Open Questions

1. Does the current Lexware export still have the specific blocking deficiency for enough buyers? Public documentation is insufficient; this is the first empirical gate.
2. Which exact output format, profile version and transmission route does each initial recipient accept? Markant's public service description is not a complete recipient contract or test specification.
3. Does an existing native setting, converter or ATN already solve the same job with less total effort? No comparative hands-on test has occurred.
4. Will the same businesses pay again after onboarding, especially if their mapping is static or the source vendor fixes it?
5. Can 26–38 customers be reached economically before the gap shrinks? No addressable-market estimate or sustainable acquisition channel has been established.
6. What operating system, team availability and source/output retention workflow do the first pilots share? Do not build cross-platform support before this is known.
7. Can profile upkeep remain a shared software cost rather than per-customer consulting? The seven-day test cannot establish long-term support burden.

## Review

**Mode:** author self-critique using `sde-concept` and `sde-research`. `.sde_docs/config` is absent; default `ask` applied. The user explicitly answered “Nein, eigene Gegenprüfung genügt”. No subagent was dispatched and no independent or cross-model PASS is claimed.

**SCOPE:** the smallest informative experiment is one current source export, one recipient route, saved mappings, batch export and traceable validation. General conversion, OCR, hybrid-PDF rewriting, transport and integrations were removed. Those cuts prevent testing customers who need them, which is acceptable because the problem statement concerns a narrow compatible cohort. Saved mappings and a batch loop remain because a one-document repair cannot test recurring product value.

| Self-refutation | Disposition |
|---|---|
| “You selected another feature that the incumbent will ship.” | Accepted as the largest durability risk. Current easybill/JTL evidence is included; no moat claim. Reproduction and second-month renewal are required, but neither proves long-term defensibility |
| “A €199 competitor already does the retail job.” | ATN included prominently. Its advertised upstream sales-data workflow differs, but the exact competitive boundary is untested. Require customer comparison rather than asserting an underserved niche |
| “A €10 converter destroys the €79 price.” | Conversion removed as the value proposition. If the existing converter performs the same recurring job conveniently, stop; do not assume recipient rules justify a premium |
| “The 48% statistic invents a huge market.” | No TAM extrapolation. Its unknown denominator/error mix and second-hand nature are explicit. Required customer counts are derived from price; reachable counts remain unknown |
| “This is really an integration agency.” | Single source/profile and shared mappings only; bespoke customer code and routine founder invoice editing fail the test. Services measured against actual team availability |
| “A repaired XML may create inconsistent issued records.” | Originals, output manifest and issuer retention workflow retained; first technical trials use new/test invoices. Formal corrections are not automated. This adds necessary operational work and remains a pilot gate |
| “You still have no distribution.” | Correct. Named acquisition hypotheses and time/cash ceilings replace assumed partnerships. Failure to reach qualified buyers stops this investment |
| “The positive recommendation is only what the user wanted to hear.” | Narrowed to a capped prototype experiment with explicit negative controls. Paid demand, recurrence and defensibility remain unproven; evidence does not justify a full product commitment |

**Author disposition: suitable as a DRAFT for a bounded-test decision, with explicit empirical limits.** The strongest counterargument survives: this may be a short-lived compatibility patch whose customers should instead configure or upgrade existing software. The modest investment is justified by a specific reported pain, reusable technical mechanics and a test that can distinguish that patch from recurring demand quickly. It is not justified by novelty, a forecast market share, or confidence in development speed alone.

Approval has not been requested as a prerequisite to this research and has not been granted for the materially new concept. The document remains DRAFT. Explicit user approval is required to mark it APPROVED; implementation or executable plan extraction requires its own authorised scope. A possible next handoff, after approval, is `/sde-concept-transfer`.
