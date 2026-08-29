# 💡 Concept: The Optimal Business Strategy Behind the WEG Finding

## 📌 Status

`DRAFT` · **v2** — v1 proposed an outsourced bookkeeping back office. An independent refutation returned **`BLOCK`** and it held. v2 deletes that shape rather than guarding it, corrects a legal misreading v1 asserted at high confidence, and reports what the round actually produced: **a corrected search specification and one fork for the user.**

| Field | Value |
|---|---|
| Created | 2026-08-28 |
| Builds on | `DRAFT_belegverwaltung_produktvision.md` v3 · `DRAFT_erechnung_monetization.md` v3 |
| Team | 2–3 people, agentic-dev background, **no distribution, no domain trust** |
| Target | **€8k MRR ≈ €96k/year** (user, 2026-08-28) |
| Services constraint | Only as acquisition/onboarding, **permanently <20% of team time** (user, 2026-08-28) |
| Research | 6 delegated passes + 1 adversarial pass |
| Adversarial review | **`BLOCK`** — resolved by **deleting** the proposed solution. Reviewer independently verified Beisheim, Scalara, VDIV, the BMF letter and the address lists, and found a competitor category v1 never checked |
| **Decision** | **Branch B selected** (user, 2026-08-29) — leave German property administration and re-specify the search against the four filters. Branch A is closed, not deferred |
| Reviewer independence | **`same-model-fallback`** — fourth round without cross-model review. The reviewer flagged that v1's legal misreading is *exactly* the error class a same-model reviewer is least likely to catch, and caught it only by fetching the source. Treat all legal reasoning here as no more independent than v1's |

---

## ⚖️ Verdict

**No shape in German property administration survives the stated constraints.** That is a negative result, and after three concepts it is the useful one — because the reason is now specific and it is not about the ideas.

> **The binding constraint was never which idea to pick. It is that this team has no distribution and no domain trust — and every shape that clears the economics in this domain requires the second one more than the ideas that were rejected.**

Two things do come out of this round, and both are actionable:

1. **A fork with honest economics on both branches** (§ *The fork*), one of which is a real, existing, unglamorous business the user could enter — if they drop the <20% services constraint.
2. **Four filters** any next idea must pass, each derived from a documented failure rather than a principle (§ *The corrected specification*).

**The user has taken Branch B** (2026-08-29): the domain is left rather than the constraint relaxed. The four filters, not this document's shapes, are what carries into the next round.

**And one action that costs a week and has never been taken in three rounds:** twenty phone calls. Everything below is desk research. The project has zero minutes of primary customer contact.

---

## 🎯 Problem Statement

Given that (a) the e-invoicing category is closed and (b) distribution has been the binding constraint in every round — what is the best available business strategy for 2–3 developers with no distribution to reach €8k MRR in German property administration?

---

## ⛔ v3's WEG/GoBD niche — closed, but not for the reason v1 gave

**v1 claimed the legal premise was refuted, at "high confidence — primary sources". That was wrong, and it was the same failure mode v1 diagnosed in v3.**

The [BMF-Schreiben of 9.4.2026](https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Umsatzsteuer/Umsatzsteuer-Anwendungserlass/2026-04-09-unternehmereigenschaft.html) (III C 2 – S 7104/00030/006/041) implements the JStG 2022 amendment to § 2 Abs. 1 UStG: VAT entrepreneur status exists **independently of legal capacity**, so non-rechtsfähige Gemeinschaften *can* be Unternehmer. **That is a broadening letter — it removes an obstacle in v3's favour.** v1 read it as narrowing. And v3's structural argument stands unanswered: **§ 4 Nr. 13 UStG** exempts a WEG's supplies to members, which only makes sense if those supplies are otherwise steuerbare unternehmerische Leistungen — an exemption presupposes entrepreneurship rather than negating it.

**What is correct:** GoBD does not bind a WEG *as such* — no statutory retention regime exists for ordinary WEG records ([Greiner, ZMR 2018](https://www.greiner.one/images/publications/Aufsaetze/2018_02_Aufbewahrung_WEGUnterlagen_ZMR_2018_131.pdf)) — and no case of a WEG fined under § 26a UStG was found in three rounds.

**The shape closes anyway, on commercial grounds that need no legal argument:**

| | |
|---|---|
| **Price** | `selbstverwalten.com/preise` **verified first-hand 2026-08-28**: €8,16 / €12,74 / €20,07 per unit/month *incl. VAT*, billed annually, −20% from 11 units, −35% from 26, −50% from 51. |
| **Corrected ARPU** | Self-managed WEGs are communities of "bis zu zehn Eigentümer" (Wohnen im Eigentum e.V.), not the 22-unit average v3 priced against → **€41–107 net**, so **75–195 WEGs** for €8k, not 63–98. |
| **No list** | No WEG register exists. § 26a WEG registers certified *individuals*, not communities. |
| **Occupied** | **Matera** (DE since 2021, 10.000+ units, six cities, ~€55M raised) · **dotega** (€1,3M pre-seed HTGF; holds the Wohnen im Eigentum partnership — and WiE has ~16.000 members, so that channel is small *and* taken) · **objego** (an ista + Aareal Bank JV). |
| **No demand signal** | **Zero of eight vendors market GoBD-compliant or revisionssichere archiving.** In a market this competitive that is a demand signal, not an opening. |

⚠️ **Unresolved and flagged, not smoothed:** WEG population figures conflict by 3,5× — ~427.000 (BT-Drs. 20/9890, an explicit *Grundannahme*, Stand 2020) vs >1,5 Mio. from trade sources. Zensus 2024 counts 9.277.939 Wohnungseigentumseinheiten, which constrains neither. The "43.000 self-managed WEGs" of v3 is not a source; it is 427.000 × 10%, both inputs assumptions from the same 2020 document.

---

## ⛔ The inversion — selling to the Verwalter — is closed too

Tested before recommending anything, and it fails on three independent fronts:

- **Every system-of-record vendor shipped AI invoice capture and automatic Kontierung during 2025**: [casavi AI Assist](https://casavi.com/de/software/casavi-ai-assist/), Aareon AAVA, [DOMUS novio](https://www.domus-software.de/stetige-optimierung-und-technische-aufruestung/) (GA 01.04.2025), [Immoware24](https://support.immoware24.de/hc/de/articles/24670590424349-Aktivierung-und-Nutzung-der-KI-Features), [etg24](https://etg24.de/funktionen/e-rechnung-hausverwaltung/), iX-Haus, Facilioo, Scalara.
- **A full ERP including that AI costs from €0,39 per unit/month** ([Immoware24](https://www.hausverwaltungschecker.de/immoware24/), plus a €15/month base). Any bolt-on would be priced above the system it bolts onto. *(Scalara's often-quoted €199–599 could not be confirmed — `scalara.de/preise` publishes no prices, only a quote form. Do not reuse that figure.)*
- **[Buena](https://tech.eu/2025/07/23/gv-and-20vc-back-buenas-vision-to-reinvent-property-management-through-ai-powered-rollups-with-58m-investment/) raised $58M** (GV, 20VC) to acquire small Hausverwaltungen — 60.000 units, 20 firms — targeting exactly the ~30.000 small firms a cold-outreach plan would call. Each acquisition removes a prospect.

---

## 🗑️ What v1 proposed, and why it was deleted

v1 recommended an **automation-first bookkeeping back office for small Hausverwaltungen**, priced €3–5 per unit/month against Beisheim's €5,90, entered via *"give us the five objects you were about to drop."* The refutation killed it on four grounds that cannot be mitigated, only removed. Recorded because each is a reusable trap:

**1. The category was never checked.** v1 treated [Beisheim](https://beisheim.immo/) as a price benchmark and never as a competitor. An established German *Objektbuchhaltung auslagern* category sells the identical outcome to the identical buyer with the identical Fachkräftemangel pitch: [AZIW](https://aziw.de/kunden/) (segmented by customer maturity — a mature go-to-market, not an entrant), [HausEasy](https://www.hauseasy.de/) (per-unit monthly rate, works *inside* the client's existing software), [LINSTAD](https://www.linstad.de/objektbuchhaltung-auslagern), [Dash](https://www.dash-abrechnung.de/ueber-uns/) (GoBD-certified), [Akkurat](https://www.akkurat-abrechnung.de/). v1 ran a pass thorough enough to check eight ERP vendors for GoBD marketing and did not check who else sells what it recommended selling.

**2. The "undercut" compared unlike quantities.** Beisheim's €5,90 includes **Zahlungsverkehr via EBICS, GoBD archiving, Forderungsmanagement and Mahnwesen**. v1 explicitly excluded payment execution. A narrower scope at 51–85% of the price, from an unknown vendor, against an incumbent offering free onboarding — that is *more* expensive per unit of delivered outcome, and it hands back the two most calendar-driven tasks the customer needed relieved.

**3. The denominator was wrong in the direction that flattered the design.** Revenue is per unit; **cost is per object and per booking.** A 5-unit and a 50-unit WEG have roughly the same invoice count, one Teilungserklärung, one bank account, one Wirtschaftsplan, one § 28 settlement. v1 derived minutes-per-unit from a **32-unit** object and applied it to a wedge made of **5–10-unit** objects — a 3–6× per-unit penalty it never noticed. The gate and the wedge were measured on incompatible samples.

**4. The <20% cap failed, and the arithmetic hid it.** The 67 h/month figure counted production minutes only — excluding cold-call selling, onboarding and migration, the per-customer configuration v1 called its *moat*, Rückfragen, review-and-signoff, support and the Eigentümerversammlung season. All are team time on customer work. Worse, the industry's own claimed ceiling breaches the cap: [mitarbyte](https://mitarbyte.com/blog/weg-abrechnung-ki-automatisieren-mitarbyte/) puts realistic automation at **60–80% less manual work**, human final approval mandatory, and states plainly that *"eine vollautomatische, rechtssichere WEG-Abrechnung auf Knopfdruck gibt es 2026 nicht."* At 60% the cap is breached; it holds only above ~71%, before adding back any excluded work. **The shape is structurally a BPO, which acceptance criterion 2 forbids.**

**And the wedge was mechanically inverted.** A shed mandate is shed *entirely* — the Verwaltervertrag ends, so there is no residual bookkeeping to hand over. The real pitch was *"keep a mandate you already judged unprofitable, and pay me on top."* VDIV's own framing is 57% shedding objects that miss **Wirtschaftlichkeitsanforderungen** and 63% shedding **besonders zeitintensive** ones — and what makes them time-intensive is owner conflict, Beschlussanfechtung, Sanierungsstau and per-object overhead a 6-unit object cannot amortise, not bookkeeping. The market's own revealed answer is in the same dataset: **12% fee increases planned, up to 17% for small objects.** They raise the price; they do not outsource.

---

## 🧩 What actually survives

**The demand is real and verified.** VDIV Branchenbarometer 2025 (n=1.072 firms, up to 446 valid per question), independently re-checked by the reviewer: **73% name Fachkräftemangel as their biggest challenge, 70% report Überlastung, 57% shed mandates missing profitability, 63% shed time-intensive objects, ~14% accept no new mandates** (>1 in 5 among Kleinstverwaltungen). Firm count fell from ~24.000 to under 22.000.

**A buyer list exists — and is worth less than v1 claimed.** Verified across six providers: [vertriebslisten.de](https://vertriebslisten.de/products/hausverwaltungen) 11.300 · [datenhalle.de](https://www.datenhalle.de/produkt/Haus-und-Grundst%C3%BCcksverwaltungen-in-Deutschland/) 12.484 · [firmenliste.net](https://www.firmenliste.net/product.php?idListe=311&katId=9&firmenliste=Hausverwaltungsunternehmen) 16.220 · [hausverwaltungen-adressen-kaufen.de](https://hausverwaltungen-adressen-kaufen.de/produkt/hausverwaltungen-adressen-deutschland/) 18.108 **at €0,02/address** · [adressen.kaufen](https://adressen.kaufen/branchen/immobilien/hausverwaltungen/) 33.459 · [adressbar.de](https://adressbar.de/branchendetail/Hausverwaltungsunternehmen-376) 7.849. The 4,3× spread and a top figure exceeding the count of firms in existence mean heavy duplication. **A list anyone can buy for €0,02 is not distribution.** It converts "no distribution" into "cold email at cold-email rates" — and contactability was never the binding constraint. **Trust was**, and it still is: a stranger does not get handed client-money records.

**v1's "price against labour, not software" rule is retracted as a law and kept only as an observation.** It proves too much — it equally endorses cleaning and callcentres — and it contains no term referencing this team's assets, so applied honestly it selects *against* a team whose advantage is software. It is also partly a **search artifact**: software prices sit on public pages and were findable; service prices sit behind quote forms (AZIW, HausEasy, LINSTAD and Dash all decline to publish), and Beisheim was findable *because* it is the outlier that publishes. And v1's own sentence concedes the comparison is invalid — *"the only variable is how much human judgement and liability the seller absorbs."* If judgement and liability differ, it is not the same work. The 15–25× gap **is** the work, plus insurance, plus a balance sheet.

---

## 🔀 The fork

Both branches were real when written. **The user chose Branch B on 2026-08-29**; Branch A is recorded below because the reasoning that made it the better *services* shape stays reusable, not because it remains open.

### Branch A — Enter the Objektbuchhaltung category, and drop the <20% services constraint · **CLOSED (user, 2026-08-29)**

The smallest honest version, which the refutation itself proposed: **sell only the § 28 Jahresabrechnung + Wirtschaftsplan, as a fixed fee per object per year (~€500–900).**

| | |
|---|---|
| **Why it is better than v1's shape** | Object-denominated pricing **matches the actual cost driver**, so the small-object inversion disappears. No continuous access to client-money records — the largest trust barrier is removed, not mitigated. The deliverable is discrete, inspectable and refusable, so a two-person unknown can be trusted with it *once*, which is the only trust that must be won. |
| **The arithmetic** | €96k/year ≈ **130–190 objects**. Not MRR — seasonal annual revenue. |
| **What it costs** | Delivery concentrates in Q1–Q2 and is brutal. It is a services business, entrant N in a quote-priced category against AZIW, Akkurat, HausEasy, LINSTAD, Dash. **Criterion 2 must be abandoned, not finessed.** |
| **Honest odds** | It is a real business with real customers and no fantasy in it. It is not a software company, and the team's dev speed is not the scarce input — trained Immobilienbuchhalter, WEG judgement and indemnity cover are. |

### Branch B — Accept the domain is wrong for this team, and re-specify the search · **SELECTED**

Three rounds have eliminated: generic e-invoicing, five vertical wedges, Peppol, multi-jurisdiction, Vereine, Kleinstbetriebe, WEG/GoBD, the Verwalter bolt-on, and the back office. **The elimination rate is the finding.** A strategy that is the last option standing after three rounds of elimination was chosen by exhaustion, not by fit.

---

## 📐 The corrected specification

Four filters, each derived from a documented failure rather than a principle. Any next idea must pass all four:

1. **The buyer can say yes on the product alone** — without handing over money, records, or liability first. *(Kills: every property-administration shape. Trust, not contactability, is this team's binding constraint.)*
2. **The price is set by something not collapsing** — not a function every incumbent must ship as a checkbox because regulation forces it. *(Kills: e-invoicing, the AI bolt-on.)*
3. **The team's actual advantage is the scarce input.** If the scarce input is a licence, a certified professional, or an indemnity history, dev speed is irrelevant. *(Kills: Branch A on its own terms, and the Verwalter route.)*
4. **The cost driver and the price metric share a denominator.** *(The per-object-vs-per-unit trap; general, and it was invisible until measured.)*

---

## ✅ Recommendation

**The branch is chosen. What survives of the recommendation is the habit, not the call list.**

The twenty calls below were designed to price Branch A. With Branch A closed they are no longer the next action — *but the discipline they encode is the one thing this project has never done, and it must carry into the next domain unchanged:*

> ~~Call 20 Hausverwaltungen from a €0,02/address list.~~ *(Superseded by the Branch B decision.)* Two questions:
> *"Which mandates did you drop in the last 12 months, and why?"* — and — *"Who does your Objektbuchhaltung, and what would make you change that?"*
>
> Cost: one week, ~€400 of addresses. It prices Branch A, tests filter 1 directly, and converts three rounds of desk research into the project's first primary data.

**Carry this forward as a rule, not an artefact:** in the next domain, the twenty conversations happen *before* the concept document, not after it. Filter 1 — *can the buyer say yes on the product alone?* — is answerable only by asking, and it is the filter that eliminated everything here.

**The order-of-operations lesson is now the main finding.** Three concept documents, ~330 tool calls, nine research passes, zero customer conversations. Every round has recommended the cheap falsification step and none has run it. For a team whose advantage is that building is cheap, the binding constraint is **talking before designing** — and the cost of not doing so is now measurable: this document is the third one.

---

## ⚖️ Discarded

| Approach | Why |
|---|---|
| WEG GoBD archiving SaaS (v3) | Commercially closed — no list, corrected ARPU, Matera/dotega/objego, zero demand signal. *Not* legally refuted; v1's legal argument was wrong. |
| AI bolt-on for Verwalter software | Every ERP shipped it in 2025; a full ERP costs from €0,39/unit; Buena is consolidating the buyers. |
| Outsourced bookkeeping back office (v1) | Deleted — see above. Occupied category, inverted wedge, wrong denominator, structurally a BPO. |
| Outcome-priced software, no service | The comfortable option and the worst. The 15–25× gap exists *because* the seller absorbs judgement and liability; refuse that and you are back at €0,39. |
| § 60b GEG compliance tracking | Genuinely unserved (no tracking product found), hard statute (≥6 units, pre-Oct-2009 systems due **30.09.2027**, €5.000 under [§ 108 GEG](https://www.gesetze-im-internet.de/geg/__108.html)) — but the money goes to the SHK trade (€100–300/inspection), it is a two-sided marketplace with a cold start on both sides, and the deadline is a decaying one-time wave. |
| Trinkwasser / Legionellen (€25.000 + IfSG) | Techem/ista already bundle it. Fails the "not supplied by the incumbent" test. |
| Verwalterwechsel handover platform | Real friction, unproven monetisation — all existing handover guidance is free marketing content, and the Vermittlungsportale own the moment via lead fees. |
| Become a certified Verwalter | § 34c GewO + § 26a certification, head-on against Matera (~€55M) and Buena ($58M). |

---

## 📋 Open Questions

1. ~~**Which branch?**~~ **Answered (user, 2026-08-29): Branch B.** The <20% services constraint holds and the domain is abandoned instead. Three rounds inside German compliance software produced no viable shape, and that is accepted as the result rather than negotiated around.
2. **Will customer conversations precede the next concept document?** Recommended three times, run zero times. Branch B makes this the first test of the new specification, not a footnote to it.
3. **What is the next domain?** Deliberately left open here — choosing it is a `/sde-concept` run of its own, and filter 3 (*the team's advantage is the scarce input*) should drive it rather than market size.
4. **What is the actual WEG population?** 427.000 vs >1,5 Mio. unresolved. Affects no recommendation here, and with Branch B it is now moot.
5. **Set `reviewer_model`** in `.sde_docs/config` — fourth round on `same-model-fallback`, and this round proves the cost: v1's central legal claim was wrong and only a source fetch caught it.

---

> **Bounded negatives.**
> - **Verified first-hand by the author:** `selbstverwalten.com/preise` only. **Verified independently by the reviewer:** Beisheim's €5,90 and its scope, the six address-list providers, the VDIV figures, the BMF letter, and that Scalara publishes no prices.
> - **Retracted from v1:** the €1,50–2,50/unit in-house cost floor was the author's own assumption and is probably too low — at a typical 800–1.200-unit Objektbuchhalter load it is €4–6/unit, which inverts the argument v1 built on it. The "€3–5 is more expensive than an employee" framing is withdrawn entirely.
> - **Retracted from v1:** Scalara at €199–599. Unverifiable; the vendor publishes no prices.
> - **Absence of evidence, not evidence of absence:** no WEG fined under § 26a UStG, § 108 GEG or TrinkwV; no § 60b tracking product; no third-party bolt-on vendor known to have succeeded *or* failed. Each weakens; none proves.
> - **§ 60b's survival of the July 2026 GEG reform is inferred** from the statute page's amendment date, not from commentary confirming the text is unchanged.
> - **The reviewer ran on the author's own model.** Its legal reasoning carries the same blind spots as the document's, and it says so itself.
> - `.sde_docs/config` is missing — running on defaults; `/sde-status` can create it to configure `adversarial_review` / `reviewer_model`.
