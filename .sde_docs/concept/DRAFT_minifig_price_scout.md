# 💡 Concept: Minifig Scout — Valuation Tooling for a Solo BrickLink Dealer

## 📌 Status

`DRAFT` · **v6** (v5 verified the cost model; v6 answers directly whether any scaling path leads to serious income — verdict: **no**, not via this mechanism)

| Field | Value |
|---|---|
| Created | 2026-08-21 |
| Goal | **Commercial dealing** — minifigures only (BrickLink type `M`) |
| Capital | €2,000 at start → €20,000+ later (user, 2026-08-21) |
| Repository | Own repo; this concept stays in `ideas` |
| API access | Registration form renders and consumer keys can be created. **Not yet verified:** that key issuance completes, that a member-tier key returns 200 on `/items/minifig/{no}/price`, or that the account survives review |
| Adversarial review | v2 → `BLOCK` (resolved). v3 → **`BLOCK`** with 16 refutations, mostly internal contradictions; resolved here by deletion · reviewer: **`same-model-fallback`** — no `reviewer_model` configured, so the review shares a real part of the author's blind spots |
| Market reality | **17,883 stores · 6,294,965 minifigures listed.** Top-selling minifig = 1,388 transactions in 6 months ≈ **7.7/day globally**; rank 20 ≈ 2.3/day ([browse](https://www.bricklink.com/browse.asp), [sold stats](https://www.bricklink.com/catalogStatsSold.asp?itemType=M&v=0), pulled 2026-08-21) |
| Worked example | `sw0181` (Starkiller) — `.sde_docs/context/logo_minis_example.md`; its numbers are **AI-simulated and unverified** |

> `.sde_docs/config` is missing — running on defaults. `/sde-status` can create it to configure `adversarial_review` / `reviewer_model`.

---

## 🎯 Problem Statement

**Where can capital be deployed into minifigures at a return that survives fees, shipping, tax and time-to-sell — repeatedly, at a scale one person can operate?**

The governing constraint is **capital turnover, not appreciation**. A collector optimises price; a dealer optimises return per euro per week.

Critically: **no amount of price data answers this question.** The two unknowns are the all-in take rate and the *realised* holding period, and both are only observable by trading. That single observation is what reduced this concept from a data platform to a script and a spreadsheet.

---

## 🔢 The verified economics

### One domestic trade, every deduction sourced

German VAT-registered seller, bought €45, sold €75 gross to a German buyer, €4.99 shipping charged:

| Line | Amount | Source |
|---|---|---|
| Item price (incl. 19% USt) | €75.00 | — |
| less USt 19% | −€11.97 | statutory |
| Net item price | €63.03 | — |
| **BrickLink commission** — 3% of the **VAT-net item price**, shipping excluded | −€1.89 | [help #38](https://www.bricklink.com/help.asp?helpID=38) |
| **PayPal DE** 2.99% + €0.39 on €79.99 received | −€2.78 | [PayPal DE](https://www.paypal.com/de/webapps/mpp/merchant-fees) |
| Shipping charged / actual postage (DHL Kleinpaket, tracked) | +€4.99 / −€3.19 | postage figure is secondary-source, unverified |
| Cost of goods | −€45.00 | — |
| **Net, before packaging, labour and tooling** | **≈ +€16.16** | |

**Platform take rate is ~6.2% of gross** — and BrickLink is only 2.5pp of it; **PayPal is 3.7pp**. Commission is tiered *by order size*, dropping to 2% above $500 and 1% above $1,000, with no monthly or listing fees ([help #38](https://www.bricklink.com/help.asp?helpID=38)). The widely-quoted "5% BrickLink fee" is wrong — it comes from AI-generated SEO blogs.

**Two immediately actionable consequences:**

- **Use Stripe, not PayPal.** Stripe DE is 1.5% + €0.25 on EEA cards versus PayPal's 2.99% + €0.39 ([Stripe DE](https://stripe.com/de/pricing)). On this order that is €1.45 instead of €2.78 — **€1.33 saved, ~8% of the net margin**, for a one-time setup. Caveat: verify chargeback/protection differences before switching.
- **The Kleinunternehmer decision dwarfs everything the software could optimise.** Under §19 UStG the €11.97 VAT line disappears and the same trade nets **≈ €28.13** instead of €16.16 — but you lose input-tax deduction. That single choice is worth **~€12 on one €75 sale, more than every platform fee combined.** No amount of price optimisation comes close. This belongs with a Steuerberater before anything else happens.

### The US channel is closed — delete cross-region arbitrage

This was one of three signals in v4's script and it came from the example note's "Strategy A". It does not survive contact with 2025/26 shipping rules:

- Goods are **excluded from international letter mail**: "Im internationalen Briefversand sind Waren grundsätzlich – bis auf wenige Ausnahmen – ausgeschlossen" ([Deutsche Post](https://www.deutschepost.de/de/b/brief-national2027_Aenderungen.html)). The €1.80–3.30 "just send it as a Großbrief International" route small sellers use is not a sanctioned product for commercial goods.
- **Warenpost International requires a business contract at ≥200 shipments/year** ([Deutsche Post](https://www.deutschepost.de/de/w/warensendung.html)) — a starting dealer does not qualify.
- **US postal goods shipping resumed for business customers only**, via PDDP, since 23 Sep 2025 ([DHL](https://group.dhl.com/de/presse/pressemitteilungen/2025/dhl-paket-nimmt-postalischen-warenversand-aus-deutschland-in-die-usa-und-puerto-rico-fuer-geschaeftskunden-wieder-auf.html)); US de minimis ended 29 Aug 2025, so every shipment is dutiable ([WKO](https://www.wko.at/aussenwirtschaft/wegfall-de-minimis-regel-usa)).
- Without a contract, commercial US shipping means DHL Express/UPS/FedEx — reference **€22.49** for a Päckchen M when bookable at all ([paketda](https://www.paketda.de/ausland/usa.html)).

Platform + payment deductions on a US sale are **€8.62 on €75 (11.5%)**, roughly double domestic — and then the cheapest legal shipping **exceeds the entire €30 gross margin**. **Model domestic + EU only.**

### The bound on Phase A

| | |
|---|---|
| Capital deployed (€2,000 less ~20% float) | ~€1,600 |
| Buy price for a flip candidate | €10–15 |
| Lots held | ~110–160 |
| Realised turns per year | 1.3–3 (holding period 4–9 months, **unmeasured**) |
| **Optimistic net profit, year one** | **≈ €500–€1,500** |

Optimistic: no dead stock, no returns, your hours valued at zero. **This is the number that disqualifies any build with a multi-year payback** — which was exactly v3's design.

### Build vs. buy — the uncomfortable arithmetic

**[BL Metrics](https://www.blmetrics.com/) already sells this product**: "Sourcing — find the right sets, parts and minifigures to buy, with regional ROI and arbitrage opportunities" plus "smart pricing formulas that automatically adjust based on market data, cost, and sell-through rates". **$49 / $99 / $129 per month.** [Bricqer](https://www.bricqer.com/guides/pricing-formulas) sells automatic repricing at 3.5% of sold items, $50/month minimum.

Set that against Phase A profit of €500–1,500/year ≈ **€42–125/month**:

> **The commercial tool costs approximately one hundred percent of Phase A's profit.** At €2,000 of capital you can afford neither to buy this tooling nor to build it, once your hours count for anything. Software becomes justifiable only at a capital level where annual profit substantially exceeds ~€1,200/year of tooling cost — and at that point buying may well beat building.

That is the honest framing, and it is *why* the build below is 150 lines rather than a platform.

---

## 🚧 Constraints established by research

### Scraping is closed
- [`robots.txt`](https://www.bricklink.com/robots.txt) disallows **`/catalogPG.asp`** — the price guide page itself.
- [Web Robots / Spiders Policy](https://www.bricklink.com/help.asp?helpID=139): "any robot, spider, other automatic device, **or manual process** to monitor or copy our web pages".
- [API ToS](https://www.bricklink.com/v3/terms_of_use_api.page): forbids reverse-engineering internal feeds "**even if such data is not available in the BrickLink API**".
- **AWS WAF** on `bricklink.com`; `help.bricklink.com` returns Cloudflare 403 to non-browser agents.

### API eligibility — not settled
The [API ToS](https://www.bricklink.com/v3/terms_of_use_api.page) (rev. Feb 02, 2023) states: "**Registered sellers of the Website ("BrickLink Sellers") may register to the API.**" Newly added in that revision; corroborated by [BricklinkSharp](https://github.com/gebirgslok/BricklinkSharp) and [BrikBiz](https://www.brikbiz.com/faqs.html).

**v3 claimed this was resolved because the form renders. That was the same error v1 made with Playwright** — diagnosing that an unenforced control is not a licence, then treating a rendered page as one. A rendered form establishes that a page renders. The real resolution is the [seller upgrade](https://www.bricklink.com/help.asp?helpID=2440), which the dealer decision requires anyway.

### The data contract
`GET /items/minifig/{no}/price?guide_type=sold` returns, besides aggregates, a `price_detail[]` of individual dated sales (`unit_price`, `quantity`, `seller_country_code`, `date_ordered`). `guide_type=stock` returns current asks as `(unit_price, quantity, shipping_available)` — **no seller identity, no lot ID.** Quota is **5,000 calls/day**; new and used are separate calls.

The 6-month window is live and unarchived ([Help #31](https://www.bricklink.com/help.asp?helpID=31)), and no public historical minifigure series exists. That remains true — it is simply no longer this project's problem to solve (see *Deleted*).

---

## 💡 The build

Three steps. Total software: **one script.**

### Step 1 — The trade log (this week, before any code)

A spreadsheet. **Ten completed trades**, roughly €300 of capital, every deduction written down: buy price, BrickLink commission, payment fee, postage, packaging, days-to-sell, net.

This is the decisive experiment, and v3 did not schedule it at all. It answers the one risk that can invalidate the premise — *are the margins there?* — and it measures the two unknowns the Problem Statement names. Nothing in software brings that day closer, and four months of building before the first real datum was the worst error in v3's sequencing.

### Step 2 — The valuation script (~150 lines)

Python 3.12 + uv. `httpx` + `requests-oauthlib` for OAuth1 HMAC-SHA1, or ~80 lines hand-rolled. No scheduler, no database, no web app.

One function, `value(item_no, condition)` → 2–3 live calls returning:

| Output | Source |
|---|---|
| Sold median (robust to outliers) | median of `sold` → `price_detail[].unit_price`. ⚠️ Structurally biased **low** — see *Risks* |
| Sales per 182 days — **liquidity** | `sold` → `unit_quantity` |
| Lots below 70% of median — **depth** | count over `stock` → `price_detail[]` |
| **Days-to-sell distribution** — the differentiated signal | gaps between successive `date_ordered` values in `sold` → `price_detail[]` |
| Supply cap, on request | `/items/minifig/{no}/supersets` → count of sets |

**The days-to-sell derivation is the one thing here that is not already commoditised.** No public dataset maps a minifigure listing to days-on-shelf, and the commercial tools advertise only an aggregate "sell-through rate". But `price_detail[].date_ordered` gives dated individual transactions, so the *distribution* of intervals between sales is computable per figure from a single call. Since turnover — not margin — is the binding constraint (see *Risks*), this is the number that should drive every buy decision, and it is the strongest reason to write your own script rather than rent someone else's.

**CSV in, CSV out**, so it prices a supplied bulk-lot list in one run: 200 figures = 200 calls = 4% of the daily quota. That makes ~25 bulk-lot valuations per day possible with no stored data at all.

**Plus five lines: gzip every raw response to disk**, keyed by `(no, condition, fetch_date)`. This yields a growing archive of exactly the figures you actually touch, at zero marginal call cost and near-zero code — and it is the only surviving part of v1–v3's archive ambition.

### Step 3 — Gated on Step 1, deliberately unspecified

If the trade log shows real margins, build whatever it identifies as the bottleneck. If sourcing is the constraint, build sourcing; if pricing your own stock is, build the repricer. **Choosing now would be choosing without the information Step 1 exists to produce** — which is the rule v3 stated and then exempted its largest component from.

---

## 🔧 Corrections carried forward

These are real defects found in earlier versions; they apply to the script above.

- **`country_code` and `region` are mutually exclusive** in the API contract. Sending both means one is silently ignored. Both filter by *store location*, not by "ships to you", and the price guide **returns no shipping cost at all**. Use one per call: `region=eu` for statistical breadth on `sold`, `country_code=DE` for buyability on `stock`.
- **Currency is an archive hazard.** `currency_code=EUR` converts at the rate on the day of the call, so the same historical sale re-fetched later returns a different euro value. Never put price in a dedup key; always store the fetch date.
- **Truncation is unmeasured, and it bites hardest where a dealer cares most.** If `price_detail[]` is capped for high-volume figures, the data is worst exactly on the liquid, fast-turning stock the turnover doctrine says to trade. Compare entry count against `unit_quantity` on the first live call, and cross-check once against the website. Repeated fetching does not fix truncation — five identical truncated tails are one truncated tail.
- **The €25 collision.** v3 used €25 as both the minimum viable *sale* price and the average *purchase* price, which makes the margin zero by construction. They are different numbers: sale floor ≈ €25, buy price ≈ €10–15.
- **The 2-month holding period was invented.** v3's own text contradicted it twice (30% dead stock beyond a year; 20–60 transactions/year for a mid-tier figure). Defensible range is **4–9 months**, and the trade log will replace the estimate with a measurement.

---

## ⚖️ Deleted after review

Removal, not mitigation — each item is gone, with what breaks stated honestly.

| Deleted | Why | What breaks |
|---|---|---|
| **Full-catalog sweep** (37k calls/pass, enumeration, adaptive cadence, GB/year) | **The decisive finding.** All three features are *live-call* features — repricing, lot valuation and velocity ranking each need a call made now about an item in front of you. A 37-day-stale median is strictly worse than a fresh call. The sweep's only unique output is a multi-year series whose payoff the doc itself dated at 24–36 months, against a business bounded at ~€1,000/year that Step 1 exists to validate or kill within months | The longitudinal series. Deferring it 6 months costs 6 months of history *for figures you do not trade* — the loss is real but small against a 3-year payoff, and Step 2's logging habit preserves it for everything you touch |
| **Its justification** | v3 justified the sweep by "discovery requires the whole population" for purpose #2 — then demoted purpose #2 in the same document and handed it to BrickEconomy "from day one". The justification evaporated and nobody noticed. Coverage was 100–300 figures observed per figure actionable, and the marginal figure swept is by construction one that does not sell | — |
| **Repricing as the first feature** | Contradicted the same document's phasing ("manual is survivable at 50–100 lots", "automation unavoidable past ~300"). It is the **most capital-dependent** feature, hence last at €2,000 and first at €20,000 — the capital logic was inverted. There is no inventory, no seller account, automation may be prohibited, and the return is ~€220/year against building an authenticated write path | Nothing today. At ~100 lots, repricing by hand is under an hour a month |
| **18.5k one-off superset sweep** | Fetch supersets for the ~150 figures actually under consideration: 150 calls, on demand | Nothing |
| **SQLite + raw-response table** | Gzipped files are the same archive with less code at this volume | Nothing |
| **Stage 2 web app** (FastAPI/Jinja2/HTMX/Chart.js) | A CSV in a spreadsheet does it at ~100 lots | Nothing. This was your stated interface preference and it is deferred, not refused — it becomes reasonable somewhere past a few hundred lots |
| **The 40-figure daily ask watchlist + 60-day gate** | The basket would have to be chosen now, before you have inventory, a thesis, or one realised margin — 60 days of data about a basket selected with no information | The lot-survival experiment. Reinstate it after Step 1, when the basket can be chosen from figures you actually trade |
| **BrickEconomy as a first-class component** | Investor-horizon metrics for a business that thinks in weeks | Nothing; keep as a manual lookup when curious |
| **The €20,000 ranking-metric design** | Premature, and self-defeating — see *The €20,000 contradiction* below | Nothing; it resolves to a number in a config file when the time comes |

### The €20,000 contradiction — resolved: no scaling path leads to serious money

v5 left this as "your call." Asked directly — **is there a realistic, reasonable chance of scaling this to serious income?** — the honest answer, worked through below, is **no**, not through this mechanism. This is the single most decision-relevant conclusion in the document, so it is derived explicitly rather than left as a business decision with no verdict attached.

**Define "serious":** ~€24,000/year (€2,000/month) — a real income, not pocket money. What would it take?

**Same unit economics, more capital.** Phase A's own optimistic bound is 31–94% annual return on deployed capital (€500–1,500 net on €1,600 deployed — before valuing a single hour of labour). Holding that return constant, €24,000/year needs **€25,000–80,000 deployed** — already past the stated €20,000 ceiling, and that is before the return rate itself degrades.

**It does degrade, in one of two directions, and both are shown in the doc's own numbers:**

- **Stay at €10–15 buy prices, scale the capital.** At €25,000 deployed, 6-month turns, ~€12 average buy: **~350 purchases/month = ~350 sales/month ≈ 16–17 parcels/day.** At €80,000: ~50/day. That is not a solo, software-assisted side activity — it is a full-time packing operation, before sourcing, listing, grading, and disputes are even counted. This is the labour ceiling from *Scale* in v3, and it does not relax with more capital — it gets worse linearly.
- **Move to €100+ buy prices to keep parcel count sane.** At €25,000 deployed, ~250 units at 6-month turns is a manageable ~1.3 parcels/day. But per this concept's own supply-cap thesis, €100+ figures are exactly the capped-supply, long-retired, **thin-market** end. The market data already in this document is blunt about what "liquid" means at that end: the single best-selling minifigure on the *entire platform*, summed across all 17,883 competing stores, moves **7.7 times a day**; rank 20 manages 2.3/day. A store's own holding of a handful of units in a €100+ figure, one listing among dozens of competitors, realistically turns over in a horizon of many months to years — not six. The realised return on this path is not the optimistic 31–94%; it is unknown, probably much lower, and the activity is no longer dealing — it is speculative collecting with a dealer's paperwork.

**There is also a hard ceiling on the total opportunity, independent of your own capital.** [BL Metrics](https://www.blmetrics.com/) already sells sourcing arbitrage and automatic repricing against this exact data source, and **deliberately caps itself at 100 users**. That is not a marketing choice — a vendor capping their own revenue is a direct statement that the exploitable inefficiency in this dataset does not support more concurrent extractors than that. Scaling this concept's approach does not mean claiming a bigger share of a growing pie; it means competing harder for a slice of a pool a competitor has already sized and found small enough to ration.

**What a real path to €24,000+/year actually looks like:** running an established BrickLink store at genuine retail scale — thousands of listings, storage space, sourcing relationships (estate sales, wholesale, collection breakups), a multi-year feedback history, and, realistically, other people's labour for picking and packing. Real stores like this exist and do earn a living. But that is a **small retail business** — capital, reputation, labour and years are the determining factors, not price-signal software. The research found no credible dataset of realised minifigure-flipping margins at any scale, and the closest first-hand testimony available is consistent and blunt: it "only pays off if you don't count work hours." Every recommendation in this concept, from Step 1 onward, is sized for a script-and-spreadsheet operation precisely because that honest ceiling exists — building more software does not raise it.

**What this changes practically:** nothing about the near-term build. Step 1 (the trade log) and Step 2 (the valuation script) remain correct regardless of the answer, because they are also the cheapest way to find out whether even the small version clears its costs. What changes is the framing of "later": €20,000+ is not this concept scaled up — it is a different, harder business that this concept's software plays only a minor role in, and the decision to pursue it should be made as a retail-business decision, not as a continuation of this tool.

### Not built: the "market squeeze" calculator
The example note proposes buying out the cheapest lots to lift the floor and make collectors pay it. Not designed here: its purpose is to corner supply, and it does not work anyway — BrickLink is global, supply is replenished by collection breakups, and a 100-lot order book repairs itself in weeks while capital sits idle. The one good idea from that section, **order-book depth**, is kept in Step 2 for the opposite purpose: judging whether a cheap listing is real.

### Discarded sources
**Rebrickable:** "There is no Set/Part pricing data available" ([docs](https://rebrickable.com/api/v3/docs/)). **Brickset:** minifig operations are scoped to the user's own collection, and it carries LEGO *retail* prices. **BrickOwl:** has `catalog/price_history`, but access is request-gated, GBP-only, thin market. **eBay/multi-marketplace:** substantial project of its own; unverified, out of scope.

---

## ⚠️ Risks

1. **The edge is already being sold — and rationed.** BL Metrics ships sourcing arbitrage, regional ROI and automatic repricing today, and **deliberately caps itself at 100 users** ([blmetrics.com](https://www.blmetrics.com/)). A vendor capping their own revenue is an explicit admission that this alpha **decays with the number of people running it**. This is the strongest single argument against the premise, and it is not speculation — it is a competitor's stated business decision.
2. **Turnover is brutal below the top of the catalog.** The best-selling minifigure on the entire platform transacts ~7.7 times per day *globally*; rank 20 manages ~2.3/day; below roughly the top 50 a SKU moves a handful of times a *month* platform-wide — against 17,883 stores and 6.29M listed minifigures ([browse](https://www.bricklink.com/browse.asp), [sold stats](https://www.bricklink.com/catalogStatsSold.asp?itemType=M&v=0)). Any model assuming you buy underpriced and turn it quickly is fighting this distribution. It also confirms the review's point that the supply-cap thesis selects for *illiquid* stock.
3. **The price guide is structurally biased downward.** Sold prices are recorded in USD at the historical rate and re-converted at today's, and VAT is excluded — so the displayed "average" sits slightly below true market, and sellers pricing to it push it lower ([BrickStore #80](https://github.com/rgriebl/brickstore/issues/80)). **An algorithm that mechanically trusts the guide joins the race to the bottom rather than escaping it.** Any pricing rule must correct for this deliberately.
4. **Repricing has a hard throughput ceiling that engineering cannot beat.** There is **no bulk-update endpoint** — repricing is one `PUT /inventories/{id}` per lot, against the same 5,000 calls/day. Bricqer, a mature server-side product, states a full price refresh "may take several hours to several days" for this reason. There is no latency edge available to anyone.
5. **The German legal overlay is a documented, precedented cost.** BrickLink provides no native Impressum/AGB/Widerrufsbelehrung — sellers hand-build them into free-text splash pages. A 2018 Abmahnung wave closed **~90 of ~800** active German shops, with the assessment that a fully compliant German BrickLink shop is "nahezu unmöglich" ([promobricks](https://www.promobricks.de/bricklink-deutsche-haendler-derzeit-abgemahnt/)). A subscription market exists purely for these texts (**€5.90/month net**, [IT-Recht Kanzlei](https://www.it-recht-kanzlei.de/Service/agb-BrickLink.php)). Also mandatory: EU DSA self-certification ([help #2655](https://www.bricklink.com/help.asp?helpID=2655)), and a **€10,000/year** EU cross-border threshold that forces OSS registration ([help #2550](https://www.bricklink.com/help.asp?helpID=2550)).
6. **Tax treatment is structural, not a percentage.** **Differenzbesteuerung (§25a UStG)** decides whether VAT lands on the *spread* or the *full price*; the Kleinunternehmer choice alone swings ~€12 on a €75 sale. **PStTG/DAC7** platform reporting triggers early at any real sales rate. **Not researched, not advice** — Steuerberater before the first sale.
7. **Bulk-lot valuation is a labour arbitrage, not an information arbitrage.** A seller who can export an item list already has tools that price it against the same guide. The real edge is that bulk sellers discount heavily for a quick exit *because parting out is work*. Genuine, but its ceiling is your parcels-per-day. Experienced sellers are consistent on this: it "only pays off if you don't count work hours" ([Brickset forum](https://forum.brickset.com/discussion/28087/starting-out-selling-on-bricklink-advice-please)).
8. **Sum-of-medians overvalues a lot.** 200 figures at ~40 sales/month is five months of your entire capacity for one purchase — and listing them makes *you* the clustered cheap lots in exactly those figures. Lot valuation must be liquidity-weighted and self-impact-adjusted.
9. **It is a job.** Picking, grading, packing, shipping, disputes, feedback. No repricing tool touches any of it, and that is where the hours actually go.

**The one honest gap in this counter-case:** no first-hand report was found of anyone trying API-signal-driven minifigure flipping and losing money. The case above is structural and inferential — assembled from platform data, competitor behaviour and adjacent seller testimony — not from a matching failure report. That absence is **weak evidence either way** and should not be read as reassurance.

## 📋 Open Questions

1. **Kleinunternehmer or Regelbesteuerung?** Worth ~€12 on a €75 sale — more than every platform fee combined, and more than any pricing optimisation this software could ever deliver. Plus Differenzbesteuerung (§25a) and PStTG/DAC7. **Steuerberater, before the first sale.** *(Blocking, and it outranks everything technical.)*
2. **What do ten real trades show?** Take rate is now known a-priori (~6.2%); what is not known is the **realised holding period**, and Risk 2 suggests it may be far worse than 4–9 months. *(Blocking — but it is trading, not building.)*
3. **Seller upgrade — start now.** Requires a purchase earning positive feedback, then ID + business-address + inventory proof, then **up to two weeks or longer** of manual review ([help #2440](https://www.bricklink.com/help.asp?helpID=2440)). Pure calendar time — start it in parallel with everything else.
4. **Is `price_detail[]` truncated for high-volume figures?** One check on the first live call, per *Corrections*.
5. ~~**Is there a realistic path to €20,000+ scaling into serious income?**~~ ✅ **Resolved: no**, not via this mechanism — see *The €20,000 contradiction*. What is still yours to answer: whether you want to pursue the different, harder business (real retail scale) that question surfaces, independent of this concept.
6. **What does the trade log say the bottleneck is?** Determines Step 3. Deliberately unanswered.

7. **Stripe instead of PayPal?** Saves ~1.3pp of gross (~8% of net margin). Check chargeback and buyer-protection differences first.

**Resolved:** ~~does BrickLink permit automated repricing~~ → **yes**, the API ToS contains no clause against algorithmic pricing, and "reasonable commercial uses of the API are permitted" · ~~US cross-region arbitrage~~ → **deleted**, the channel is structurally closed · ~~hobbyist or dealer~~ → dealer · ~~how much capital~~ → €2,000 → €20,000+ · ~~which series to track~~ → moot, the sweep is deleted · ~~does the registration form render~~ → yes, but that settles less than v3 claimed
