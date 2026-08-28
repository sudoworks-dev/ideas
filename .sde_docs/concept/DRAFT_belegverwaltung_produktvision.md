# 💡 Concept: "Einfache Belegverwaltung für die E-Rechnungspflicht" — Viability Assessment

## 📌 Status

`DRAFT` · **v2** — v1 was refuted on five quantitative points by the adversarial review and is rewritten here, not patched. v1's wide verdict is **withdrawn**.

| Field | Value |
|---|---|
| Created | 2026-08-28 |
| Source | `.sde_docs/context/ebill_produktvision_2026-08.md` — founder vision, *"Interne Diskussionsgrundlage, Stand August 2026"* |
| Related | `DRAFT_erechnung_monetization.md` v3 assessed a **different, earlier** spec (`ebill_idea.md`) and returned NO. Treated here as a prior to re-derive, **not** as evidence |
| Question | *"Lässt sich diese Idee monetarisieren und lohnt sich somit das Bauen?"* — explicitly beyond a hobby project |
| Team | 2–3 people, strong software + agentic-dev background, **no distribution** |
| Targets tested | **(A) €4–8k MRR** — meaningful side income / **one salary** · **(B) €25k MRR** — livelihood for three |
| Research | 4 delegated passes, ~273 tool calls. Rechnungsradar + DATEV pricing **verified first-hand**; rest subagent-sourced with URLs |
| Adversarial review | **`REVISE`** — 12 refutations, 5 changing the verdict. All resolved below, four **by deletion**. Reviewer: **`same-model-fallback`** (Claude Opus 5, same as author) |
| **Verdict** | **NO to the vision as written** (high confidence) · **Wide "do not enter e-invoicing" claim withdrawn** — one shape survives and was never tested |

> ⚠️ **Read this before the findings.** The reviewer ran on the **same model as me** because `.sde_docs/config` is absent and no `reviewer_model` is set. This is the *second consecutive* round without a genuinely independent reviewer. It caught five real errors anyway — but it shares a real part of my blind spots, and you should weight this document accordingly. `/sde-status` can create the config to fix this.

---

## 🎯 Problem Statement

**Can a 2–3 person team with no distribution monetize a simple e-invoice/Beleg management SaaS aimed at Vereine, self-managed WEGs and Kleinstbetriebe, beyond hobby scale, in the German market of August 2026?**

The vision is strategically well-reasoned: it correctly sees that the generic product is crowded, narrows to segments incumbents ignore, and names a concrete differentiator. **Three of its factual premises are nonetheless false, and each was checkable in under an hour.**

---

## 🔁 What the adversarial review changed — stated plainly

I am recording this because the corrections run *against* my own v1 conclusion, and a reader who only sees v2 would not know how close v1 came to being confidently wrong.

| v1 claimed | Corrected |
|---|---|
| "€9 is the price this market clears at" | **Wrong.** v1 quoted selbstverwalten.com's *"€8,16–€20,07 **per unit** per month"* in one section and then used €9 as a **per-organisation** ARPU in the arithmetic. A 10-unit WEG pays **€82–€201/month**. Off by up to 14×, always in the verdict's favour |
| "€25k is closed by arithmetic" | **Withdrawn.** At corrected pricing, €25k ≈ **197–306 WEGs out of ~43.000** = 0,5–0,7% share. That is a hard sales problem, not arithmetic impossibility |
| "The category has a price ceiling of zero" | **Wrong.** DATEV's €0 and the BMF's *"ein E-Mail-Postfach genügt"* cover **receipt/transport only**. Neither supplies **GoBD archiving** — the vision's fourth MVP function and the one nobody gives away |
| Verein churn multiplier ~4,2%/mo | **Deleted.** Unsourced, my own construction, never used in any table, and causally wrong — the contracting party is the *Verein*, not the Kassenwart |
| vermieter1's €449 lifetime deal "should end the discussion" | **Read backwards.** The same vendor sells €9,90/month alongside it. €449 ÷ €9,90 = **45 months** — evidence of *higher* willingness-to-pay, not lower |
| "Second independent assessment" | **Withdrawn.** Same author, same model, same evidence corpus, v3's rule imported as the filter. Serial correlation, not independence — warranting *lower* confidence, not higher |
| Verband channel closed | **Reopened.** LSB Thüringen picked a single vendor (IntelliVerein) for member clubs; WLSB runs standing *Rahmenverträge*. And `lsb-vergleichsportal.de` is a **free, self-listed, high-intent directory** — for a team whose deficit is distribution, that is an asset I filed as a barrier |

**Four of v1's six errors ran in the same direction: they made the verdict look more certain than the evidence supported.** That is the same failure mode the predecessor draft's v1→v3 history shows. It is the most useful thing in this document.

---

## 🔢 The denominator — corrected

The buying entity is the **organisation**, and the segments are priced differently. v1's single €9 anchor was the error that produced its conclusion.

**Observed incumbent pricing, per organisation:**

| Segment | Incumbent anchor | Org-level ARPU |
|---|---|---|
| selbstverw. WEG, 10 units | selbstverwalten.com €8,16 / €12,74 / €20,07 **per unit/month** | **€82 / €127 / €201** |
| Verein, ≤100 members (the median: 60,9% are this size) | WISO MeinVerein XS | **€11–13** |
| Verein, larger bands | WISO MeinVerein up to L | €22–€72 |
| Kleinstbetrieb | lexoffice S €6,90 · sevdesk €8,90 · Rechnungsradar €9 | **€7–9** |

**Customers required, and the share of the universe that implies:**

| ARPU/org | €4k | €8k | €25k | €25k as % of ~43.000 WEGs |
|---|---|---|---|---|
| €9 (v1's wrong anchor) | 444 | 889 | 2.778 | 6,5% |
| €30 | 133 | 267 | 833 | 1,9% |
| €82 | 49 | 98 | 305 | **0,7%** |
| €127 | 31 | 63 | 197 | **0,5%** |

**Unit economics at 85% gross margin** *(a placeholder, not an assumption — see Bounded negatives)*:

| ARPU | Churn | LTV | Max CAC at 3:1 | Payback at CAC €500 |
|---|---|---|---|---|
| €13 (median Verein) | 4% | €276 | **€92** | 45 months |
| €22 | 4% | €468 | €156 | 27 months |
| €82 (10-unit WEG, Basis) | 4% | €1.742 | **€581** | 7,2 months |
| €127 (10-unit WEG, Komfort) | 4% | €2.699 | **€900** | 4,6 months |
| €127 | 7% | €1.542 | €514 | 4,6 months |

> **The threshold: at 4%/month churn, ARPU must exceed ~€71/organisation for a €500 CAC to clear 3:1.** Vereine and Kleinstbetriebe sit far below it. A per-unit-priced WEG sits comfortably above it. **That single line separates the dead segments from the live one**, and v1 missed it by anchoring all three to €9.

*Caveat the reviewer's arithmetic understates:* €127/month at selbstverwalten.com buys the **whole § 28 WEG apparatus** — Wirtschaftsplan, Hausgeld, Beschlüsse, banking, Jahresabrechnung — not a Belegpostfach. A pure archiving/Beleg product cannot assume that price. But even €30/organisation (≈€3/unit on 10 units) yields LTV €638 and a €212 max CAC — still 3× above the median Verein.

---

## ⛔ Finding 1 — For Vereine, the compulsion the vision is built on largely does not exist

The Ausgangslage rests on: *"Dies zwingt Millionen von Betrieben, Vereinen und Eigentümergemeinschaften…"* The BMF says the opposite:

> *"**Betreffen Leistungen den nichtunternehmerischen Bereich des Vereins, muss der Verein weder E-Rechnungen empfangen können noch selbst E-Rechnungen ausstellen.**"* — [BMF FAQ E-Rechnung](https://www.bundesfinanzministerium.de/Content/DE/FAQ/e-rechnung.html)

§ 14 UStG binds **Unternehmer**. A Verein in its ideeller Bereich is not one. Where the duty *does* apply, *"Für den Empfang einer elektronischen Rechnung genügt bereits ein E-Mail-Postfach"* (BMF; confirmed by the Bundesregierung, [hib 1017282](https://www.bundestag.de/presse/hib/kurzmeldungen-1017282)). And the 2027/2028 deadline never arrives: § 34a Satz 4 UStDV makes the Kleinunternehmer exemption from *issuing* **permanent** — *"kann … immer als sonstige Rechnung … übermittelt werden"* ([statute](https://www.gesetze-im-internet.de/ustdv_1980/__34a.html)).

**Two honest qualifications, both weakening this finding:**

1. **I cannot say "most".** v1 did, and it was unsupported: the number of Vereine that are *unternehmerisch tätig* was **not found** in any source. Sportvereine with Bandenwerbung, Sponsoring, Vereinsgaststätte or Zweckbetrieb are unternehmerisch, and that may be a large share. The universe can only be bounded from above.
2. **Belief-driven demand is real and I under-weighted it.** ClubDesk writes *"praktisch alle Vereine … müssen E-Rechnungen empfangen können"*; several Landessportbünde headline the same. German compliance software has repeatedly sustained paid vendors on *perceived* obligation — TSE/KassenSichV, DSGVO tooling, Hinweisgeberschutz. Demand follows fear of an audit, not statutory reading.

**The finding therefore narrows to:** compulsion is a weak and legally contestable basis for the Verein segment. What actually closes Vereine is not this finding — it is the €11–13 median ARPU against a €92 maximum viable CAC, plus 70+ competing products and a permanently free tier (ClubDesk to 50 members).

*Correction in the team's favour:* **WEGs are genuinely compelled.** A WEG **is** Unternehmer under § 2 UStG; § 4 Nr. 13 exempts supplies *to members* without removing Unternehmereigenschaft, and the § 4 Nr. 8–29 carve-out attaches to the **invoiced transaction**, so a Handwerker's taxable service to a WEG is fully in scope. § 14b UStG retention applies, with a Bußgeld to €5.000 under § 26a.

---

## ⛔ Finding 2 — The named differentiator ships in Germany at €9/month *(verified first-hand)*

> *"Kern-Differenzierungsmerkmal … Das System überwacht das bestehende Postfach des Kunden via IMAP oder OAuth."*

[Rechnungsradar](https://rechnungs-radar.de/), fetched 2026-08-27: *"Gmail und Microsoft per OAuth, alle übrigen Anbieter über verschlüsseltes IMAP"* · *"durchsucht dein Postfach auch rückwirkend"* · *"100 % Genauigkeit bei E-Rechnungen"* · *"Dein Kanzleikonto kostet nichts"* · EU servers · **€9/month**. Also shipping mailbox monitoring: GetMyInvoices, Tailride (free tier), Pleo Fetch, Dext. **And free in open source**: paperless-ngx (IMAP rules + documented Gmail/Outlook OAuth) + [Mustangproject](https://github.com/ZUGFeRD/mustangproject) (Apache-2.0, v2.25.0, 2026-08-05).

**Scoped precisely — v1 overstated this.** Rechnungsradar is a **feeder into accounting software**, not the vision's product: no GoBD long-term archive, no Prüfung/Freigabe workflow, no outbound XRechnung creation, no § 28 WEG Jahresabrechnung. Direct integrations on Starter are Lexoffice and Buchhaltungsbutler; DATEV/ADDISON/sevdesk/Agenda are reached by mail forwarding. So the finding refutes **the differentiator claim**, not the whole product.

**Two further corrections to v1:**

- **"Keine Verhaltensänderung" is still false, and inverted for this buyer.** Microsoft `Mail.Read` is high-impact: end-user consent is blocked, a **tenant admin must approve**. Asking a volunteer to grant a two-person startup read access to a mailbox holding member and donor correspondence is a *harder* ask than a forwarding address — and it manufactures an Art. 28 AVV obligation for a customer with no DPO.
- **But CASA is a scope decision, not a permanent tax.** v1 wrote "four-figure annual audit, forever". Google's Restricted-scope regime ([Google](https://developers.google.com/identity/protocols/oauth2/production-readiness/restricted-scope-verification), self-scan [deprecated](https://appdefensealliance.dev/casa/tier-2/tier2-overview), $675–1.800/yr, 100-user cap until verified) applies **only if you support Gmail**. Plain IMAP still works for GMX/Web.de/T-Online/IONOS/self-hosted. Ship those plus a forwarding address for Gmail/O365 and the CASA cost is **€0**.

And the AI extraction it enables is a depreciating asset: ~**$0.0013/page** on Claude vision ([Anthropic](https://platform.claude.com/docs/en/build-with-claude/vision)), while a genuine ZUGFeRD needs no OCR at all — and from **2027-01-01** all domestic B2B invoices must be structured EN 16931.

---

## ⛔ Finding 3 — Both named "besondere Hebel" already ship

**"SEPA-Lastschrift … von keiner Standardlösung sauber bedient"** — refuted four times. WISO MeinVerein ships *"Rechnungen & Lastschriften"* in **every** tier; SPG-Verein calls it core (*"Erstellen Sie mühelos SEPA-Lastschriften"*); ClubDesk includes it from €10; easyVerein markets it as a headline strength. Commodity table stakes.

**"Ein einfacher Export für die WEG-Jahresabrechnung würde die Lösung unverzichtbar machen"** — [selbstverwalten.com](https://selbstverwalten.com/) targets self-managed WEGs of **6–20 units** and already ships AI invoice-field extraction (*"alle Felder automatisch erkennen: Betrag, Fälligkeit, Kategorie, IBAN"*), banking **and** *"Jahresabrechnung nach § 28 WEG"*. etg24 ships XRechnung/ZUGFeRD ingestion with approval workflow; objego's base module *"kostet nichts und bleibt auch kostenlos"*.

**And the pitched Verein product already exists cheaper:** netxp-Verein at **€7,50/month flat** below 250 members — *"E-Rechnungen werden automatisch ausgelesen, digitale Belege archiviert und für den Zahlungsverkehr … vorbereitet"*.

*(Subagent-sourced with URLs; not re-verified first-hand — WebFetch quota exhausted.)*

---

## ⛔ Finding 4 — Channel and focus

**The Steuerberater multiplier is structurally hostile.** DATEV is a **Genossenschaft owned by 40.176 Steuerberater** with ~80% of a profession of 89.549 — the proposed channel partner co-owns the incumbent, which carries ~1,7M companies on DATEV Unternehmen online and moved 51M e-invoices in H1 2026. sevdesk and Lexware Office already give Kanzleien free access, so a third entrant has nothing to trade. The vision's *"50+ Mandanten"* premise is contradicted by the only observable program: BuchhaltungsButler's **top** partner tier requires *"mindestens 10 Mandanten"*. *(One data point; the case against is structural inference, not evidence.)*

**Three "PRIMÄR" segments is a hedge.** Each needs a different product (Mitgliederverwaltung / § 28 WEG Jahresabrechnung / DATEV-Export-Buchhaltung), a different channel, and a different killer feature. This is the one problem fixable by decision alone, and the recommendation below fixes it.

**The Verband channel is reopened, against v1.** v1 closed it because four Landessportbünde run a neutral comparison portal. That was a misreading twice over: **LSB Thüringen picked a single vendor** (IntelliVerein, free to member clubs into 2026) and the WLSB maintains standing *Rahmenverträge* — Verbände visibly do enter single-vendor arrangements. And [lsb-vergleichsportal.de](https://www.lsb-vergleichsportal.de/) is a **free, non-commercial, vendor-self-listed directory** with a dedicated Finanzbuchhaltung comparison, reaching exactly the buyer v1 called unreachable. For a team whose stated deficit is distribution, that is the most useful fact in this research.

---

## 🤖 Finding 5 — Agentic dev, commoditization, and the moat that is actually there

The team asked this directly. The answer has two halves and v1 got the second one wrong.

**Construction is commoditizing, and it was never the moat.** A non-developer can now deploy auth + database + Stripe conversationally; Codex passed 5M weekly users with non-developers growing 3× faster; Claude Cowork (2026-01-12) puts an agent on a non-technical person's filesystem. In the Designli Moat Report (2026-08-04, n=100), **not one founder rated technical defensibility 5/5**.

**But compliance genuinely resists it, and this is the strongest thing in the team's favour anywhere in this research.** The best-argued 2026 analysis puts the vibe-coding kill zone at mid-tier, single-function, bounded-workflow SaaS and **explicitly excludes products embedded in audit trails and compliance regimes**. The evidence is concrete: a scan of vibe-coded apps found 2.038 highly critical vulnerabilities, 400+ leaked secrets and 175 instances of exposed PII including bank data; Veracode found 45% of AI-generated samples carried OWASP Top-10 flaws. **Revisionssichere Archivierung is an assurance claim, not a feature claim — and assurance is what a weekend build cannot produce.** Small German vendors clear this bar: Papierkram publicly names PKF as its GoBD auditor; ISO 27001 at small scope runs €8k–€40k.

**v1 then dismissed this on a premise that is false.** It wrote that the state and DATEV supply the compliance minimum free. They supply **receipt** free. Neither supplies **GoBD archiving** — DATEV's free E-Rechnungspostfach does not archive; GoBD-compliant storage requires DATEV Unternehmen online at €11,56/month, and the ELSTER viewer *"löst nur das Leseproblem – nicht die Anforderungen an eine GoBD-konforme digitale Archivierung."*

> **Corrected rule — the transferable output of this round:**
> **Compliance is a durable moat only where the compliance minimum is not supplied free by the state or the dominant incumbent — and that test must be applied per *function*, not per category.**
> In German e-invoicing: **transport is €0 and always will be. Archiving is not.** v1 generalised the first into the second and nearly buried the one live shape in the process.

*(Free private tiers claiming archiving do exist — Accountable, Zervant, sevDesk, WISO MeinBüro, objego. Whether any carries an actual GoBD attestation is unverified. The observable price for attested archiving is ~€10–12, not €0.)*

---

## 🟡 Shape 4 — the case v1 never generated, given a genuine hearing

The review's strongest move was not a refutation but a construction: **GoBD assurance for the § 28 WEG cycle, priced per unit, sold to a personally exposed volunteer.** It survives Findings 1–4 and was never tested. Stated as an advocate would:

- **The obligation is real here** (unlike Vereine): WEG is Unternehmer, § 14b retention applies, § 26a carries a Bußgeld to €5.000.
- **Nobody gives the archiving job away** — that is the corrected Finding 5.
- **The segment already pays per unit**: €82–€201/month for a 10-unit WEG, which clears the ~€71 ARPU threshold with room. vermieter1's €449 lifetime deal independently prices WTP at **45 subscription-months**.
- **The buyer profile is textbook compliance-WTP**: a Verwaltungsbeirat handling other owners' money under § 28 WEG, answerable to an annual Eigentümerversammlung, with personal exposure and a hard annual deadline.
- **There is a budget line** — Hausgeld, from which a professional Verwalter's €25–35/unit/month would otherwise be paid. €127/month for a 10-unit WEG is ~15% of one month of professional management.
- **The population is growing** — and v1 filed the reason as a negative when it is the opposite. VDIV's Branchenbarometer 2025 says self-management grows because professional managers are **rejecting mandates**: a supply-side vacuum of organisations with a statutory duty, an annual deliverable, a budget, and nobody to serve them.

**Why it is still not a "yes":** selbstverwalten.com already occupies it with a fuller product and knows the segment; ~43.000 organisations is a small, register-less universe with no list to buy; 197 customers at €127 is a real sales problem for three people who are also building; per-unit pricing on a *pure archiving* product is unproven — €127 buys the whole § 28 apparatus, not a Belegpostfach; and the invoice volume per WEG is **not found** in any source. Distribution remains the binding constraint.

**But it is a hypothesis to test, not a shape to dismiss** — and that distinction is the difference between v1 and v2.

---

## ⚖️ The two targets, answered separately

**€4k — reachable in the WEG shape, not in the others.** 31–49 organisations at €82–127, or 133 at €30. LTV €638–€2.699 supports a €212–900 CAC. In Vereine (€13 ARPU, €92 max CAC) or Kleinstbetriebe (€7–9 against DATEV at €0), it is not reachable.

**€8k — the target v1 never evaluated, and the most interesting one.** 63–98 WEGs at €82–127. ≈ **€96k/year: one funded salary plus overhead for a two-person team.** That is unambiguously past hobby scale, it matches the user's own stated target A (*"one salary"*), and on corrected pricing it is the most defensible number in this document.

**€25k — a hard sales problem, not arithmetic impossibility.** 197–306 WEGs = 0,5–0,7% of the universe. v1's "closed by arithmetic" is **withdrawn**. What closes it is channel: 197 relationship-led sales into a register-less segment, by three people who are also building and supporting, against an incumbent already there.

**And v1's "€4k is a hobby project" is withdrawn as an illegitimate bar.** It divided €4k across three people to reach "€1.333/person" — importing v3's three-salary framing into a target the user had defined as *"meaningful side income / one salary"*. One salary means one salary.

---

## ✅ Recommendation

**1. Do not build the vision as written.** *(High confidence — Findings 1–3 survived the review intact.)* Its premise is refuted by the BMF for the primary segment, its differentiator sells for €9/month in Germany today, and both segment levers already ship from vendors aimed at exactly those segments.

**2. Kill the three-segment hedge.** Vereine are closed on price (€11–13 ARPU vs. €92 max CAC, 70+ products, free tier, no compulsion). Kleinstbetriebe are closed on DATEV (€0 receipt, 1,7M companies already on DUO, free Kanzlei seats at sevdesk and Lexware). **Only self-managed WEGs survive, and only for the archiving job.**

**3. Do not accept a category-wide "no".** v1 issued one and it was wrong. The correct scope is: *transport and receipt are permanently €0 and unmonetizable; GoBD archiving for a legally compelled, per-unit-priced, personally exposed buyer is not.*

**4. Run the €200 test before writing another vision document.** This has now been recommended twice across two rounds and not run, while two full vision documents were produced. Concretely, and this is the actionable output of this analysis:

> **15–20 interviews with Verwaltungsbeiräte of self-managed WEGs (6–20 units), sourced from Haus & Grund groups and Eigentümerforen. Ask what they currently pay for, and what they do about § 14b retention today. Then hand-deliver GoBD archiving manually for three paying WEGs at €40–80/month.** ~4–6 weeks of one person, ~€200. Test the price per unit, not per organisation.

If three self-managed WEGs will not pay for a concierge version, no software changes that. If they will, you have priced the one shape that survived — and you will have learned it for €200 instead of a build.

**5. The order of operations is the real lesson.** All three false premises, and four of v1's own six errors, were checkable against a primary source in under an hour. For a team whose stated advantage is that building is cheap, the binding constraint is not construction — it is **falsifying before designing**. Building cheaply is worth little if it is spent building the wrong thing quickly.

---

## 📋 Open Questions

1. **Is the attachment to *e-invoicing*, or to "a monetizable B2B SaaS in German compliance"?** Carried from v3, still unanswered, now urgent — two rounds spent inside one category.
2. **Would a services-first route be acceptable?** ZDH (n=1.926, fielded Jan–Feb 2026) measures **~€3.000 one-off** per Handwerksbetrieb — the only verified money across both rounds, and the only path that *manufactures* the missing distribution, at the cost of being an agency first.
3. **Will the falsification step be run before the design step this time?** The one variable fully under the team's control, and the difference between the next round costing an afternoon and costing a month.
4. **New — set `reviewer_model`.** Two consecutive rounds have used `same-model-fallback`. Given that this round's same-model reviewer still found five verdict-changing errors, a genuinely independent one is likely to find more.

---

> **Bounded negatives — read before relying on any number.**
> - **Verified first-hand (2026-08-27/28):** Rechnungsradar pricing/mechanism; DATEV E-Rechnungsplattform pricing. **Everything else is subagent- or reviewer-sourced with URLs and not re-checked by me** (WebFetch quota exhausted) — including all selbstverwalten.com, netxp-Verein, WISO MeinVerein, objego, vermieter1 and LSB Thüringen figures. **The corrected per-unit pricing that drives v2's changed conclusion is in this unverified group. Verify it first if you act on this.**
> - **Not found, load-bearing:** the share of German Vereine that are *unternehmerisch tätig*; the invoice volume per self-managed WEG per year; any verified count of self-managed WEGs (only the Bundesregierung's 10% assumption, Stand 2020, BT-Drs. 20/9890).
> - **The 85% gross margin is a placeholder, not an assumption.** It is wrong in both directions: at €9 ARPU, EU card processing alone is 4–6% of revenue; and GoBD imposes an **8–10 year retention cost that persists after the customer churns** — a liability the LTV formula cannot represent at all. Treat every LTV figure as indicative.
> - **The DACH CAC benchmark (€500–2.000) is drawn from a population with 10–50× this ARPU**, and CAC scales with ACV. It is used here only to locate a *threshold* (~€71 ARPU), not to close a case. v1 used it to close a case; that was a category error.
> - **Unresolved contradiction:** UStG treats a WEG as Unternehmer; VDIV asserts it is a *Verbraucher* under § 13 BGB and escalated to the BMF. No published answer found.
> - **Do not assert:** that GoBD binds a WEG *as such* — no statute found; the clean hook is § 14b UStG. Nor that a DPIA is mandatory for mailbox scanning — the DSK Muss-Liste is non-exhaustive and no regulator has ruled on this fact pattern.
> - **Deleted from v1 as unsound, recorded so it is not reintroduced:** the Verein churn multiplier; the vermieter1 "lifetime deal ends the discussion" reading; the App-Store revenue-concentration block (consumer mobile does not transfer to German B2B compliance SaaS); the "second independent assessment" confidence claim.
> - **Correction to the predecessor draft:** the DATEV pricing URL cited in `DRAFT_erechnung_monetization.md` now returns HTTP 404; repoint to `https://e-rechnungsplattform.datev.de/`.
> - `.sde_docs/config` is missing — running on defaults.
