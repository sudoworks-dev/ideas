# 💡 Concept: "Einfache Belegverwaltung für die E-Rechnungspflicht" — Viability Assessment

## 📌 Status

`DRAFT` · **v3** — result-focused rewrite of v2. Substance unchanged; the refutation-process narrative was removed because it served the author, not the reader.

| Field | Value |
|---|---|
| Created | 2026-08-28 |
| Assesses | `.sde_docs/context/ebill_produktvision_2026-08.md` — founder vision, August 2026 |
| Question | *"Lässt sich diese Idee monetarisieren und lohnt sich somit das Bauen?"* — beyond a hobby project |
| Team | 2–3 people, strong software / agentic-dev background, **no distribution** |
| Targets | **(A) €4–8k MRR** — side income / one salary · **(B) €25k MRR** — livelihood for three |
| Research | 4 delegated passes, ~273 tool calls · adversarial review: `REVISE`, resolved in v2 |
| Reviewer independence | **`same-model-fallback`** — same model as the author. Real reduction in independence; `/sde-status` can set `reviewer_model` |

---

## ⚖️ Verdict

**Do not build the vision as written.** Three of its factual premises fail against primary sources, and each was checkable in under an hour.

**But the category is not closed.** Transport and receipt of e-invoices are permanently €0 and unmonetizable. **GoBD archiving is not** — and one shape built on that distinction survives: *archiving for self-managed WEGs, priced per unit.* At the €8k target it is the most defensible number in this document. It is a hypothesis to test, not a business to start.

**Kill the three-segment hedge.** Vereine and Kleinstbetriebe are closed on price. Only WEGs survive.

---

## 🎯 Problem Statement

Can a 2–3 person team with no distribution monetize a simple e-invoice/Beleg management SaaS for Vereine, self-managed WEGs and Kleinstbetriebe, beyond hobby scale, in the German market of August 2026?

The vision is strategically well-reasoned — it sees that the generic product is crowded, narrows to ignored segments, and names a concrete differentiator. Its premises are the problem.

---

## ⛔ The three premises that fail

### 1. Vereine are not compelled

The Ausgangslage rests on *"Dies zwingt Millionen von Betrieben, Vereinen und Eigentümergemeinschaften…"*. The BMF says the opposite:

> *"Betreffen Leistungen den nichtunternehmerischen Bereich des Vereins, muss der Verein weder E-Rechnungen empfangen können noch selbst E-Rechnungen ausstellen."*
> — [BMF-FAQ E-Rechnung](https://www.bundesfinanzministerium.de/Content/DE/FAQ/e-rechnung.html)

§ 14 UStG binds **Unternehmer**. Where the duty does apply, *"genügt bereits ein E-Mail-Postfach"* (same source). And the 2027/2028 deadline never arrives: § 34a Satz 4 UStDV makes the Kleinunternehmer exemption from issuing **permanent**.

Two qualifications that soften this: the share of Vereine that *are* unternehmerisch was **not found** in any source — so "most" cannot be asserted. And belief-driven demand is real: vendors and Landessportbünde actively claim the opposite, and German compliance software has repeatedly sustained paid vendors on perceived obligation (TSE/KassenSichV, DSGVO tooling).

**What actually closes Vereine is not the law — it is price.** €11–13 ARPU for the median Verein (60,9% have ≤100 members) against a maximum viable CAC of €92, plus 70+ competing products and a permanently free tier (ClubDesk to 50 members).

*In the team's favour:* **WEGs are genuinely compelled.** A WEG **is** Unternehmer under § 2 UStG; § 4 Nr. 13 exempts supplies *to members* without removing that status, and the § 4 Nr. 8–29 carve-out attaches to the invoiced transaction — so a Handwerker's taxable service to a WEG is fully in scope. § 14b retention applies, with a Bußgeld to €5.000 under § 26a.

### 2. The differentiator ships at €9/month

> *"Kern-Differenzierungsmerkmal … Das System überwacht das bestehende Postfach des Kunden via IMAP oder OAuth."*

[Rechnungsradar](https://rechnungs-radar.de/) sells exactly this — *"Gmail und Microsoft per OAuth, alle übrigen Anbieter über verschlüsseltes IMAP"*, retroactive inbox scan, free Kanzlei seat, EU servers — for **€9/month**. *(Verified first-hand, 2026-08-27.)* Also shipping mailbox monitoring: GetMyInvoices, Tailride, Pleo, Dext. And free in open source: paperless-ngx + [Mustangproject](https://github.com/ZUGFeRD/mustangproject).

Scoped precisely: Rechnungsradar is a **feeder into accounting software** — no GoBD archive, no approval workflow, no outbound XRechnung, no § 28 WEG Jahresabrechnung. It refutes the *differentiator claim*, not the whole product.

Two things worth carrying forward:
- **"Keine Verhaltensänderung" is inverted for this buyer.** Microsoft `Mail.Read` needs **tenant-admin** consent. Asking a volunteer to grant a two-person startup read access to a mailbox holding member and donor correspondence is a *harder* ask than a forwarding address — and creates an Art. 28 AVV obligation for a customer with no DPO.
- **Google's CASA audit ($675–1.800/yr, 100-user cap until verified) is a scope decision, not a fixed cost.** It applies only if you support Gmail. Plain IMAP still works for GMX/Web.de/T-Online/IONOS. Ship those plus a forwarding address and it costs €0.

### 3. Both named "besondere Hebel" already ship

**SEPA-Lastschrift für Mitgliedsbeiträge** — claimed as *"von keiner Standardlösung sauber bedient"*. Refuted four times: WISO MeinVerein ships it in **every** tier, SPG-Verein calls it a core function, ClubDesk includes it from €10, easyVerein markets it as a headline strength.

**WEG-Jahresabrechnungs-Export** — [selbstverwalten.com](https://selbstverwalten.com/) targets self-managed WEGs of 6–20 units and already ships AI invoice-field extraction, banking **and** *"Jahresabrechnung nach § 28 WEG"*. etg24 ships XRechnung/ZUGFeRD ingestion with approval workflow; objego's base module is permanently free.

And the pitched Verein product exists cheaper: **netxp-Verein, €7,50/month flat** below 250 members, with automatic e-invoice parsing and archiving.

---

## 🔢 The numbers

The buying entity is the **organisation**, and the segments are priced very differently — WEG software is billed **per unit**.

| Segment | Anchor | ARPU per organisation |
|---|---|---|
| selbstverw. WEG, 10 units | selbstverwalten.com €8,16 / €12,74 / €20,07 **per unit/month** | **€82 / €127 / €201** |
| Verein, ≤100 members (the median) | WISO MeinVerein XS | **€11–13** |
| Kleinstbetrieb | lexoffice €6,90 · sevdesk €8,90 · Rechnungsradar €9 | **€7–9** |

| ARPU/org | €4k | €8k | €25k | €25k as % of ~43.000 WEGs |
|---|---|---|---|---|
| €30 | 133 | 267 | 833 | 1,9% |
| €82 | 49 | 98 | 305 | 0,7% |
| €127 | 31 | 63 | 197 | **0,5%** |

| ARPU | Churn | LTV | Max CAC at 3:1 | Payback at CAC €500 |
|---|---|---|---|---|
| €13 (median Verein) | 4% | €276 | **€92** | 45 months |
| €82 (10-unit WEG) | 4% | €1.742 | **€581** | 7,2 months |
| €127 (10-unit WEG) | 4% | €2.699 | **€900** | 4,6 months |

> **The one number that decides everything: at 4%/month churn, ARPU must exceed ~€71 per organisation for a €500 CAC to clear 3:1.**
> Vereine (€13) and Kleinstbetriebe (€7–9) sit far below it. A per-unit-priced WEG sits comfortably above it.

*Caveat:* €127 at selbstverwalten.com buys the **whole § 28 apparatus** — Wirtschaftsplan, Hausgeld, Beschlüsse, banking — not a Belegpostfach. A pure archiving product cannot assume that price. But even €30/organisation (≈€3/unit × 10) yields LTV €638 and a €212 max CAC — still 3× the median Verein.

---

## 🟡 What survives: GoBD archiving for the § 28 WEG cycle

Four conditions meet here and nowhere else in this vision:

- **Real obligation** — WEG is Unternehmer, § 14b applies, § 26a threatens up to €5.000.
- **Nobody gives this function away.** DATEV's free E-Rechnungspostfach and the BMF's *"ein E-Mail-Postfach genügt"* cover **receipt only**. GoBD-compliant storage requires DATEV Unternehmen online at €11,56/month; the ELSTER viewer *"löst nur das Leseproblem – nicht die Anforderungen an eine GoBD-konformen digitale Archivierung."*
- **A buyer with personal exposure** — a Verwaltungsbeirat handling other owners' money under § 28 WEG, answerable to an annual Eigentümerversammlung, on a hard deadline. Textbook compliance willingness-to-pay.
- **A budget line** — the Hausgeld, from which a professional Verwalter's €25–35/unit/month would otherwise be paid. €127/month for 10 units is ~15% of one month of professional management.

The population is also growing, for a reason worth reading correctly: VDIV's Branchenbarometer 2025 reports self-management grows **because professional managers are rejecting mandates**. That is a supply-side vacuum — organisations with a statutory duty, an annual deliverable and a budget, and nobody serving them.

**Why this is still not a "yes":** selbstverwalten.com is already there with a fuller product; ~43.000 organisations is a small, register-less universe with no list to buy; 197 customers is a real sales problem for three people who are also building; per-unit pricing for a *pure archiving* product is unproven; and invoice volume per WEG was **not found** in any source. Distribution remains the binding constraint.

---

## 🎯 The two targets

| Target | Verdict |
|---|---|
| **€4k** | Reachable in the WEG shape (31–49 organisations at €82–127). Not reachable in Vereine or Kleinstbetriebe. |
| **€8k** | **63–98 WEGs ≈ €96k/year — one funded salary plus overhead for a two-person team.** Matches your own target A, and is the most defensible number here. |
| **€25k** | 197–306 WEGs = 0,5–0,7% share. A hard sales problem, *not* arithmetic impossibility. What closes it is channel, not maths. |

---

## 🧩 The transferable rule

> **Compliance is a durable moat only where the compliance minimum is not supplied free by the state or the dominant incumbent — and that test must be applied per *function*, not per category.**

This is the answer to your question about agentic-dev commoditization. Construction is commoditizing and was never the moat: in the Designli Moat Report (2026-08-04, n=100), **not one founder rated technical defensibility 5/5**. But compliance genuinely resists it — a scan of vibe-coded apps found 2.038 critical vulnerabilities, 400+ leaked secrets and 175 cases of exposed PII; Veracode found OWASP Top-10 flaws in 45% of AI-generated samples. **Revisionssichere Archivierung is an assurance claim, not a feature claim, and assurance is what a weekend build cannot produce.** Small German vendors clear this bar — Papierkram names PKF publicly as its GoBD auditor.

Applied here: **transport is €0 and always will be; archiving is not.** Generalising the first into the second is what nearly buried the only live shape.

---

## ✅ Recommendation

1. **Do not build the vision as written.** *(High confidence.)*
2. **Drop Vereine and Kleinstbetriebe.** Closed on price and on DATEV respectively.
3. **Test the WEG archiving shape before writing anything further.**

> **The €200 test:** 15–20 interviews with Verwaltungsbeiräte of self-managed WEGs (6–20 units), via Haus & Grund groups and Eigentümerforen. Ask what they pay for today and what they currently do about § 14b. Then hand-deliver GoBD archiving for three paying WEGs at €40–80/month for four weeks. **Price per unit, not per organisation.** ~4–6 weeks of one person, ~€200.

If three WEGs will not pay for a concierge version, software will not change that. If they will, you have priced the surviving shape for €200 instead of a build.

**The order of operations is the real lesson.** All three false premises were checkable against a primary source in under an hour, and the vision was written before that hour was spent. For a team whose advantage is that building is cheap, the binding constraint is **falsifying before designing**.

---

## 📋 Open Questions

1. **Is the attachment to *e-invoicing*, or to "a monetizable B2B SaaS in German compliance"?** Two rounds have now been spent inside one category.
2. **Would a services-first route be acceptable?** ZDH (n=1.926, Jan–Feb 2026) measures **~€3.000 one-off** per Handwerksbetrieb — the only verified money across both rounds, and the only path that *manufactures* the missing distribution, at the cost of being an agency first.
3. **Will the falsification step run before the design step this time?** Recommended twice, not yet run, while two full vision documents were produced.
4. **Set `reviewer_model`** in `.sde_docs/config` — two rounds have used `same-model-fallback`.

---

> **Bounded negatives — read before relying on any number.**
> - **Verified first-hand:** Rechnungsradar and DATEV pricing only. **Everything else is subagent-sourced with URLs and not re-checked** — including all selbstverwalten.com, netxp-Verein, WISO MeinVerein, objego and vermieter1 figures. **The per-unit WEG pricing that drives this document's conclusion is in that unverified group. Check `selbstverwalten.com/preise` first if you act on it.**
> - **Not found, and load-bearing:** the share of Vereine that are *unternehmerisch tätig*; invoice volume per self-managed WEG; any verified count of self-managed WEGs (only the Bundesregierung's 10% assumption, Stand 2020, BT-Drs. 20/9890).
> - **The 85% gross margin is a placeholder.** At €9 ARPU, EU card fees alone are 4–6% of revenue; and GoBD imposes an **8–10 year retention cost that persists after churn** — a liability LTV cannot represent. Treat every LTV figure as indicative.
> - **The DACH CAC benchmark (€500–2.000) comes from a population with 10–50× this ARPU**, and CAC scales with ACV. It is used here only to locate the ~€71 threshold, never to close a case.
> - **Unresolved:** UStG treats a WEG as Unternehmer; VDIV asserts it is a *Verbraucher* under § 13 BGB and escalated to the BMF. No published answer found.
> - **Do not assert** that GoBD binds a WEG *as such* (no statute found — the clean hook is § 14b UStG), nor that a DPIA is mandatory for mailbox scanning (the DSK Muss-Liste is non-exhaustive; no regulator has ruled on this fact pattern).
> - **An earlier draft anchored all three segments at €9 per organisation**, misapplying WEG per-unit pricing. That error made the verdict look far more certain than the evidence supported. Corrected here; noted so the €9 anchor is not reintroduced.
> - `.sde_docs/config` is missing — running on defaults.
