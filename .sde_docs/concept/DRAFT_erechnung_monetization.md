# 💡 Concept: E-Rechnung as a Business — Viability Assessment

## 📌 Status

`DRAFT` · **v3** (v1 proved a narrow "no" and asserted a wide one; v2 tested the wide claim against the cross-border/network layer and it survived; v3 re-runs everything against the real revenue target — **a livelihood for three, not €4k** — and checks whether the larger target *reopens* any shape rather than assuming it hardens all of them)

| Field | Value |
|---|---|
| Created | 2026-08-21 |
| Source idea | `.sde_docs/context/ebill_idea.md` — MVP spec for an inbound e-invoice web app |
| Question asked | *"Lohnt es sich, Richtung E-Rechnung etwas zu bauen mit dem Ziel der Monetarisierung?"* |
| Constraints | Team 2–3 · **no distribution**, cold start (user, 2026-08-21) |
| Revenue target | **A real livelihood for three people** — "kein Spielerei"; not required from day one, but the *perspective* must exist (user, 2026-08-21). Modelled as **€21–29k MRR within 36–48 months**; the initially stated €3.000–5.000 MRR is treated as a waypoint, not the goal |
| Research | 4 delegated passes, ~270 tool calls: regulatory/market · competitive/pricing · vertical wedges · Peppol & cross-border |
| Adversarial review | v1 → **`REVISE`**, 7 refutations. All resolved below, three by deletion. Reviewer ran on **Opus 5 and could not confirm it differed from the author's model — treat as `same-model-fallback`**: this review shares a real part of the author's blind spots and is not the independent check a cross-model review would give |
| **Verdict** | **NO** — do not build the spec; do not enter e-invoicing as a software business |

---

## 🎯 Problem Statement

**Is there a defensible way for a 2–3 person team with no distribution to build a business in German e-invoicing that can plausibly pay three real salaries, as the market exists in August 2026?**

The market is not the issue. It is enormous and legally compelled: **3,131,417 VAT-filing businesses** ([Destatis Umsatzsteuerstatistik 2024, table 73311-01](https://www.destatis.de/DE/Themen/Staat/Steuern/Umsatzsteuer/Publikationen/Downloads-Umsatzsteuern/statistischer-bericht-umsatzsteuer-2140810247005.xlsx?__blob=publicationFile)), all obliged to receive e-invoices since 2025-01-01. The question is whether any of that demand is **reachable** and **chargeable**. Those are separate filters and this category fails both.

---

## 🔢 The denominator

The target must carry a time horizon, a churn assumption and a budget, or it silently decides the answer. **v1's table had none of the three** — and omitted churn, which would have *strengthened* its own argument, a sign the table was assembled to illustrate a conclusion rather than locate one.

v3 corrects something larger. The goal is **a livelihood for three people, with the perspective present even if not the starting point.** Three developer salaries plus employer contributions and overhead is roughly **€250–350k annual revenue ≈ €21–29k MRR**. The working denominator:

> **€25k MRR within 36–48 months, net of ~4%/month churn, on ≤€10.000 total acquisition spend — with a credible path, not a starting position.**

| Price/month | Customers for **€4k** (old waypoint) | Customers for **€25k** (the actual goal) | Gross adds/month at 4% churn to hold €25k |
|---|---|---|---|
| €9 (observed floor) | 445 | **2.778** | ~111/month, forever |
| €199 | 21 | **126** | ~5/month |
| €400 | 10 | **63** | ~2,5/month |
| €1.500 (ISV licence) | 3 | **17** | ~0,7/month |

The €9 row is now not merely a treadmill but arithmetically out of reach: 2.778 paying SMBs with no channel, against four vendors discounting 35–60%. **The low-ACV half of the market is closed by the target alone**, before any competitive argument is applied.

## ⛔ Finding 1 — The spec already exists, twice, at €9–10 *(load-bearing)*

Not "a crowded market" in the abstract. The product described in `ebill_idea.md` is **already shipping**.

| Spec requirement | Already shipped by |
|---|---|
| Dedicated inbound address | **zeit.io** (`rechnungseingang@firma.zeit.io`), **aipi.email** |
| ZUGFeRD/XRechnung parsing + validation | both (~200 rules at aipi) |
| XML → readable visualization | both — plus **free** at ELSTER, Quba, Handwerksafe, sevdesk, RechneX |
| Approval workflow, GoBD archiving, DATEV export | both |
| **EPC/GiroCode payment QR** | **Handwerksafe — free, in-browser, no registration** |

[zeit.io](https://zeit.io/de/blog/rechnungen-empfangen-mit-dem-e-rechnungs-postfach) €9/mo · [aipi.email](https://aipi.email/e-rechnungseingang.html) €10/mo, which solves payment via **SEPA-XML export to the bank** — better than a QR for anyone paying more than one invoice at a time · [Handwerksafe SEPA-QR](https://www.handwerksafe.de/tools/sepa-qr/), free, same Handwerker buyer.

**The QR code is not a differentiator.** It is free, it exists, and the EPC payload is a documented 12-line string — a two-week build for any competitor.

---

## ⛔ Finding 2 — In Germany, the compliance minimum has no price

Precise scope: this anchor is on **receipt**, i.e. transport and inbox. It does not by itself price the spec's approval workflow or search — Finding 1 does that. v1 inflated a receipt anchor into a whole-workflow ceiling; the corrected claim is narrower and still decisive.

- **The BMF says an inbox suffices.** *"Für den Empfang einer elektronischen Rechnung genügt bereits ein E-Mail-Postfach."* ([BMF FAQ](https://www.bundesfinanzministerium.de/Content/DE/FAQ/e-rechnung.html), updated March 2026)
- **The state ships a free viewer** — [ELSTER](https://www.elster.de/eportal/e-rechnung), since Feb 2025, lobbied for by the ZDH precisely so Handwerker need buy nothing.
- **DATEV made receipt permanently free** — no setup fee, no base fee, any transport channel, and **registration is not gated on being a DATEV customer**. Sending from third-party systems €0.50/invoice; DATEV E-Rechnungsschreibung **€5.00 per year** ([pricing](https://www.datev.de/web/de/nachrichten/datev/datev-e-rechnungsplattform-kostenfrei-bis-mitte-2026-neue-preise-fuer-danach/)). **1.01M customers; 51M e-invoices in H1 2026** alone vs ~64M in all of 2025 ([DATEV H1 2026](https://www.datev.de/web/de/berufsgruppenuebergreifend/presse/presseinformationen/meldungen-2026/datev-steigert-umsatz-und-kundenbasis)).
- **Four credible €0 tiers**: easybill Free (50 docs/mo), Papierkram Free (GoBD-certified), Accountable Free (unlimited), Qonto Starter.
- **The paid floor is a full suite, not a point tool**: [Lexware Office S €7.90](https://www.lexware.de/preise/) and [WISO MeinBüro €7.09](https://www.meinbuero.de/preise/) both include inbound receipt *plus* an auto-import mailbox.
- **Acquisition is the binding constraint, and the pricing pages prove it.** Four independent vendors discount simultaneously: sevdesk 60% off (€25.90 → €9.95), Lexware 50% for three months, WISO 35–50%, Accountable and FastBill ~20% annual. Persistent deep discounting across four independent competitors is the signature of a market where **list prices do not clear**. A team with no channel and no ad budget enters underneath that.

---

## ⛔ Finding 3 — Pain and willingness-to-pay run in opposite directions

Timeline confirmed and **not slipped**: § 27 Abs. 38 UStG ([statute](https://www.gesetze-im-internet.de/ustg_1980/__27.html)) — receiving obligation for all since 2025-01-01; paper/PDF sending allowed to 2026-12-31, extended to 2027-12-31 only if prior-year turnover ≤ €800.000; **universal sending from 2028-01-01**. The [JStG 2026 draft](https://wts.com/de-de/publishing-article/20260817-regierungsentwurf-jahressteuergesetz~publishing-article) (Kabinett, 2026-08-12) leaves §§ 14/14a and § 27 Abs. 38 untouched. Roughly **600k** businesses are in the 2027 wave, **~2.5M** in 2028 (below €1M = 2,648,947, i.e. 84.6% of filers).

The 2027 wave forces mid-size firms to *send*, which mechanically floods ~2.5M small firms with inbound e-invoices. **ZDH, n=1.926 Handwerksbetriebe, fielded 2026-01-12 to 2026-02-27** ([ZDH](https://www.zdh.de/ueber-uns/fachbereich-steuern-und-finanzen/umsatzsteuer/umfrageergebnisse-e-rechnung/), [analysis](https://www.handwerksblatt.de/themen-specials/die-e-rechnung-wird-pflicht-tipps-fuer-handwerksbetriebe/zdh-umfrage-im-handwerk-noch-mehr-aufwand-mit-der-e-rechnung)) already measures the pain: ~50% of inbound invoices arrive as e-invoices · **47,4% say processing them is *more* work than PDFs** · one-third cannot read the data · **33% have no GoBD-compliant archiving** · 56% are below €800k.

**But the pain sits in the cohort that will not pay.** Their sending duty starts 2028; **Kleinunternehmer are permanently exempt from ever issuing** (§ 34a UStDV); invoices ≤ €250 are exempt (§ 33 UStDV); and receipt is satisfied for €0 by a BMF-blessed inbox. The people with the pain have a free government-endorsed alternative; the people with budget are already inside DATEV or an ERP. **No product decision fixes that inversion.**

---

## ⛔ Finding 4 — Five candidate shapes, verified against primary sources, all closed

### A · Hausverwaltung / WEG — **CLOSED**
The premise was that structured line-item data would finally automate the § 35a EStG labour-share split. **Corrected from v1, which overstated this:** EN 16931 *does* provide a structured carrier — **BG-32 / BT-160 (Item attribute name) + BT-161 (value), cardinality 0..n**, rule [BR-54](https://docs.peppol.eu/poacc/billing/3.0/rules/ubl-tc434/BR-54/), mapping to `cac:AdditionalItemProperty` (UBL) and `ram:ApplicableProductCharacteristic` (CII). So "the standard cannot supply the data" is **false as stated**.

It is nonetheless **true in practice**: no German body — FeRD, KoSIT, ZDH, or any Handwerk association — has defined a convention for it. No code list, no attribute string, no mapping guidance. The two implementations checked emit **human-readable text, not structured XML**: [xrechnungs.de](https://www.xrechnungs.de/de/lohnkostenausweis-rechnung) describes only a UI field, and [Sage HWP](https://onlinehilfe.sage.de/onlinehilfe/hwp/53/hwhelp/doku_paragraph_35a.htm) emits print-template placeholders with no documented XML export. This is an **adoption gap, not a standard gap** — and adoption gaps close in one release cycle.

Independently, the wedge is occupied: **Aareon/Haufe shipped an XRechnung/ZUGFeRD viewer across all PowerHaus archives in Q1 2025** ([PowerHaus](https://powerhaus.aareon.de/e-rechnung-powerhaus)); [etg24](https://etg24.de/funktionen/e-rechnung-hausverwaltung/) does AI e-invoice inbound *plus* an owner Belegprüfung portal at €90–400/mo; VDIV's own Handlungsempfehlung never raises Belegeinsicht-vs-XML as a problem.

### B · Arztpraxen / Heilberufe — **CLOSED** (v1 closed this on the wrong lever)
v1 claimed there is "no financial penalty for doing nothing." **That was false.** § 26a Abs. 2 Nr. 2 UStG penalises breach of the § 14b eight-year retention duty — which reaches *received* invoices — with a Bußgeld up to **€5.000** (§ 26a Abs. 3, [statute](https://www.gesetze-im-internet.de/ustg_1980/__26a.html)).

The wedge still closes, on weaker but sufficient grounds: the Bußgeld is a **maximum**, requires *vorsätzlich oder leichtfertig* conduct, and **no evidence of enforcement against small businesses for archiving failures could be found** — practitioners treat it as ancillary to audit findings, not a standalone instrument. As a purchase driver it is a paper tiger. Meanwhile § 14 UStG expressly exempts § 4 Nr. 8–29 turnover from the issuing duty, the BMF says an inbox suffices, and **CGM already ships it** (PRAXISARCHIV for Z1/Z1.PRO, an eRECHNUNG module in MEDISTAR). *Correction to v1's over-generalisation:* Apotheken (~17k, fully taxable, full Vorsteuerabzug, high inbound volume) and mixed-turnover practices sit inside this segment and outside the exemption argument — they are not closed by the reasoning above, only by Findings 1–3.

### C · B2D / e-invoicing API for other ISVs — **CLOSED**
Closed at both ends. **Top: DATEV gives the API away free** — send *and* receive, ZUGFeRD 2.x / XRechnung / Peppol BIS 3.x, auto-visualization, **free of charge for solution providers** ([DATEV FAQ für Softwarehersteller](https://www.datev.de/web/de/berufsgruppenuebergreifend/ueber-datev/portfolio/oekosystem/partnering/datev-marktplatz/faq-zur-datev-e-rechnungsplattform-fuer-softwarehersteller)). *(These are distinct things and v1 blurred them: using the platform API is open to anyone; being **listed** on DATEV Marktplatz requires 25 live customers and 3 references. The free API closes this wedge; the listing gate closes the Steuerberater channel. Two gates, two paths.)*

**Bottom: free, excellent, current open source.** Verified via GitHub API 2026-08-21 — [Mustangproject](https://github.com/ZUGFeRD/mustangproject) (Apache-2.0) released **core-2.25.0 on 2026-08-05** adding ZUGFeRD 2.5.2 / Factur-X 1.09.2, covering inbound parsing, validation, visualization, CLI and REST. The [KoSIT validator](https://github.com/itplr-kosit/validator) shipped v1.6.3 on **2026-08-20**. **Middle already occupied at €10–20/mo**: [B2Brouter](https://www.b2brouter.net/global/api-e-invoicing/) from €15, [Factora](https://factora.software/api/) from €19.90, [rechnungsapi.de](https://www.rechnungsapi.de/pricing) €9.99 — all white-label.

### D · Peppol Access Point / network infrastructure — **CLOSED, and this is the interesting one**
This was the strongest surviving candidate: a **certification-gated moat** is exactly what "defensible" means. It fails on the network's own design.

Operating an AP is genuinely hard — OpenPeppol fees **€1.050 sign-up + €1.850/yr + €1.500 certification** for a 1–50-person AP ([fee schedule](https://peppol.org/join/fees/)); **ISO/IEC 27001 mandatory for all Service Providers from 2027-07-01** ([AgID](https://peppol.agid.gov.it/en/news/ISO-IEC-27001-Certification-Mandatory-for-Peppol-Service-Providers-from-1-July-2027/)); **99,5% availability 24/7**, unavailable after 60 continuous seconds; liability capped at €500k per event / €1m annually. No documented case of a 1–5 person team operating a certified AP was found.

**But you never have to.** The Peppol Service Provider Agreement defines any party transacting *through* another provider's AP as an **"End User"** — no certification, no membership, no ISO 27001, no SLA — and **§ 15.1 expressly permits subcontracting** ([SP Agreement](https://peppol.agid.gov.it/attachments/PeppolServiceProviderAgreement_V_1_1_giu2023.pdf)). Storecove, B2Brouter and Tickstar sell white-label AP-as-a-service commercially.

> **The moat is real, expensive, and on the wrong side of you.** It protects ~800 incumbent Service Providers — including Telekom MMS, SAP, SEEBURGER and Siemens — *from* you, while protecting you from nobody, because every competitor reaches the same network through the same reseller APIs.

What remains is resale margin on a commodity whose observable price is **€0,07/document** ([COMPLAVIS](https://www.complavis.de/peppol-dienst/)), **€0,18/invoice** ([e-invoice.be](https://e-invoice.be/peppol-ap)), and **free at the SME tier from Qvalia, itself a certified AP** ([Qvalia](https://qvalia.com/pricing/)) — the €0 force arriving via Sweden, driven by APs treating transport as an upsell loss-leader, not by any tax authority. At €0,05–0,10 retained per document, **€4.000 MRR needs 40.000–80.000 documents/month**, i.e. hundreds of active business customers, acquired with no distribution.

### E · Multi-jurisdiction compliance layer — **CLOSED**
The €0 force is indeed German-political. Crossing the border does not escape it — **Poland's KSeF is state-run and free including a free public API and free taxpayer app; Italy's SdI is free including free 15-year archiving; Belgium publishes an official free/low-cost software list.** Three of four markets replicate the German problem verbatim.

France is the one market that removed the free path — and **licensed scarcity there is dead**: the DGFiP dataset on the French government's own open-data portal lists **137 Plateformes Agréées as of 2026-06-25**, 146–166 by August, register uncapped and growing, incumbents already including **Pennylane, Qonto, Sage, Cegid, Tiime, Indy and Sellsy** — i.e. the accounting vendors who own the distribution this team lacks. You would be entrant ~150.

Demand-side: **no German buyer evidence at all** — no Mittelstand case study, no Branchensoftware vendor procuring an independent multi-country layer. The nearest example bought from its own ERP vendor. Supply-side is occupied by EDICOM, Pagero, ecosio and SEEBURGER selling that exact product today.

---

## 🔁 Does the larger target reopen anything? — tested, no

A bigger revenue goal is not uniformly worse news: it makes **high-ACV shapes relatively more attractive**, so a shape closed at €4k could in principle reopen at €25k. Each closed shape was re-checked against the new target rather than assumed to harden.

| Shape | Direction at €25k | Why |
|---|---|---|
| Copy-and-undercut | **Worse** | 2.778 customers at €9. Arithmetically out of reach. |
| Vertical SaaS | **Worse** | 126 customers at €199 *inside one vertical*, against Aareon/etg24/CGM incumbents. |
| B2D API | **Worse** | 50–100 ISVs at €250–500 against a **free** DATEV API. |
| Peppol AP / reseller | **Much worse** | €4k needed 40–80k documents/month; €25k needs **250.000–500.000/month** at €0,05–0,10 retained. |
| Multi-jurisdiction | **Worse** | Scaling toward €25k moves you into the enterprise band — i.e. directly into EDICOM, Pagero, ecosio, SEEBURGER. |
| Implementation consulting | **Neutral-to-worse** | See below. |

**Nothing reopens.** The one shape that deserved a genuine hearing is the pricing dead zone, so it gets one.

### The strongest surviving pro-case — and why it still fails

Research found **nothing credible between GetMyInvoices (€99–179) and Candis (€389)**. A gap that wide in a large market is worth taking seriously: ~126 customers at €199, or ~63 at €400, would clear the target. The buyer is real and identifiable — 100–500 invoices/month, roughly €2–20M turnover, **in the 2027 wave and therefore under a deadline four months out**, too small for Candis/Finway, too big for Lexware. ZDH's 8–15 minutes of manual handling per invoice is genuine money at that volume.

Three reasons it still closes:

1. **The gap is empty for a structural reason, not by oversight.** €200–380/month is the classic SaaS dead zone: too expensive to convert self-serve, too cheap to fund a salesperson. Entering it means paying enterprise-style sales costs on mid-market revenue — and the missing input here is precisely a channel.
2. **The value being bought is AP automation, not e-invoicing.** Approval routing, coding, ERP posting — e-invoicing is the wedge, not the product. That is a well-funded competitive category, and it lands squarely on rule 2 below: the buyer already owns an ERP whose vendor ships e-invoicing because it must.
3. **The arithmetic is tight even if you win.** 126 customers on a 6–12 month mid-market sales cycle, with three people who are also building and supporting the product, is roughly 3–4 closes/month sustained for three years, from a standing start with no references.

It is the best case available and it is not good enough. Recording it because it is the argument a reader should expect to see answered, not skipped.

## 🧩 The rule behind all of it

v1 proposed *"e-invoicing is a compliance checkbox, nobody pays for a checkbox."* **That over-generalised from four German data points and is refuted by v1's own best datum** — Handwerksbetriebe pay ~€3.000 setup for a checkbox they were legally compelled to tick. Two narrower rules survive, and the second is the real finding:

1. **Where the state and the dominant accounting incumbent both supply the compliance minimum for free, the compliance minimum has no price.** True in Germany, Poland and Italy; not a law of the category — France licenses private operators instead of replacing them.
2. **E-invoicing transport is a network utility, and utilities are won by whoever already owns the customer relationship.** This holds across every jurisdiction, and it is why the wide "no" stands. Peppol's open-participation design guarantees your competitors reach the network as cheaply as you do; the only durable asset is an installed base to switch onto your rails. **That is precisely the missing input.**

Corollary worth carrying into any next idea: **look for problems where the buyer's spend rises when you solve them better** — not problems where a checkbox suffices, and not layers that ship inside something the customer already bought.

---

## ⚖️ Discarded approaches

| Approach | Why discarded |
|---|---|
| Copy zeit.io/aipi and undercut | Floor €9; receipt is €0 forever; 445 customers, no channel. Undercutting €0 is arithmetic, not strategy. |
| Compete on UX | Compliance tools are bought on trust and on already-being-there. The free tiers are credible, not crippled. |
| Vertical SaaS (any vertical) | Two verified closed; the failure mode repeats — every vertical's Branchensoftware incumbent ships e-invoicing as a checkbox because it must, and gives it away because it cannot charge. |
| B2D infrastructure API | DATEV free on top, Apache-2.0 Mustangproject underneath, €10–20/mo in the middle. |
| Peppol AP / reseller | Moat protects the ~800 incumbents, not you; transport at €0,07–0,18 and free at SME tier. |
| Multi-country compliance layer | PL/IT/BE state-free or curated-free; France has 137+ licensed operators; no buyer evidence; EDICOM/Pagero/ecosio/SEEBURGER incumbent. |
| Sell to the 2027 sending wave (~600k firms) | They have ERP/DATEV. DATEV charges €0.50/invoice third-party, €5/year for its own Schreibung. |
| Data-exhaust / spend analytics | Chicken-and-egg — needs volume, volume needs the free tool nobody adopts. DATEV holds 51M invoices/half-year. GDPR and competition-law exposure on aggregating third-party invoice data. |
| Steuerberater white-label | DATEV owns it. Marktplatz listing needs **25 live customers + 3 references first** — a gate, not a route. |
| § 35a labour-share extraction | **Struck in v2.** v1 recommended it as the one surviving lead. It is already shipping: [selbstverwalten.com](https://selbstverwalten.com/blog/hausgeldabrechnung-steuern-absetzen) states verbatim that it *"erkennt beim Rechnungsupload per KI den Arbeitskostenanteil und die § 35a-Kategorie jeder Rechnung"*, with the per-owner certificate *"in der Jahresabrechnung … automatisch erstellt."* v1 ran hard incumbent searches against every idea it meant to kill and none against the one it meant to keep. |
| Implementation consulting | Clears the bar on verified numbers (see below) but is an agency, not a build. |

---

## 💰 The one place money verifiably changes hands

ZDH measures **~€3.000 one-off setup and ~€800/year ongoing** per Handwerksbetrieb. That is spent on **implementation, not SaaS**. At €3.000/project, ~16 projects/year clears the old €4.000/month waypoint — but **the real target needs ~83 projects/year**, i.e. each of three people closing and delivering roughly one every two weeks, continuously, with no product leverage and no channel. That is a treadmill at the edge of what three people can sustain, and it is a job rather than an asset: revenue stops the month the work stops.

**v1 dismissed this as "decaying after 2028." That was wrong and self-contradictory** — v1's own research established the ViDA calendar: **mandatory intra-EU DRR from 2030-07-01 and full harmonization of domestic reporting systems by 2035-01-01** ([EU Commission](https://taxation-customs.ec.europa.eu/taxation/vat/vat-digital-age-vida_en)). German businesses hit a domestic plateau in 2028 and a second, larger EU-wide wave in 2030. The honest objections are narrower: it is an agency, revenue stops when the team stops, and it needs local presence — not that demand decays.

It is recorded, not recommended. But it is the only verified money in this research, and it has one property nothing else here has: **it manufactures the missing input.** Eighty implementation projects is eighty customer relationships plus first-hand knowledge of what those buyers already pay to have done by hand — which is distribution and product discovery, funded rather than bought.

That is the honest shape of a "services now, product later" path, and its failure mode is equally honest and very common: consulting revenue is a local optimum that consumes all capacity, most agencies never escape it, and the product you would eventually build serves buyers whose price expectation was set by €0 tools. It is the only route in this document with a ceiling above €250k, and it is a bet on escaping a trap that most teams do not escape.

---

## ✅ Recommendation

**Do not build `ebill_idea.md`.** It exists twice at €9–10, its named differentiator is free, and receipt is €0 by decree of both the BMF and DATEV. *(High confidence — survived every attack in the adversarial pass.)*

**Do not enter e-invoicing as a software business.** Not primarily because the BMF made it free — that reason is jurisdiction-bound and v1 leaned on it too hard — but because **transport and compliance are network utilities won by whoever already owns the customer relationship**, and that is exactly the missing input. Established across six shapes and five jurisdictions.

**The livelihood target makes this a harder no, not a softer one.** Every shape was re-tested at €25k MRR and none reopened; the low-ACV half of the market is now closed by arithmetic before any competitive argument applies. The pricing dead zone at €200–380 is the strongest surviving pro-case and it fails on structure, not on effort.

**If the ambition is a real business for three people, the binding problem is not the product — it is that you have no distribution and this category will not sell you one.** Every path examined either requires a channel you lack, or hands the customer to someone who already has one. Only the services route manufactures a channel, and it does so at the cost of becoming an agency.

**Before any further idea in this space, falsify it cheaply**: 15–20 interviews asking what the buyer *currently pays someone to do by hand*, then deliver it manually for three paying customers. ~4–6 weeks of one person, ~€200. If three will not pay for a concierge version, software will not change that.

## 📋 Open Questions

1. ~~Is €3.000–5.000 MRR a floor or a ceiling?~~ **Answered (user, 2026-08-21):** a real livelihood for three, perspective required though not from day one. Folded in throughout — see the denominator and the reopen test.
2. **Open — is the attachment to *e-invoicing*, or to "a monetizable B2B SaaS in German compliance"?** Left open by the user. It matters because the two rules below are the transferable output of this research, and if the answer is the latter, the next concept run should start from a rule rather than from a technology.
3. **Open — would the services route be acceptable?** Left open by the user. It is the only path here with a ceiling above €250k and the only one that manufactures distribution, at the cost of being an agency first.

> **Bounded negatives.** Three findings rest on absence of evidence and should not be read as proof: no small team operating a certified Peppol AP; no enforcement of § 26a against small businesses; no German convention for § 35a via BT-160/161. The German/French Service-Provider counts are the reviewer's own row counts, not published figures. `.sde_docs/config` is missing — running on defaults; `/sde-status` can create it to configure `adversarial_review` / `reviewer_model`.
