# 💡 Concept: Verified Correctness — and the Constraint Set That Killed It

## 📌 Status

`DRAFT` · **v2** — v1 recommended a Shopify accessibility-remediation app. An independent refutation returned **`BLOCK`** on primary sources and it held completely. v2 **deletes** that shape, records why, and reports the finding that outlives it: **the constraint set is over-determined, and that is now the decision in front of the user.**

| Field | Value |
|---|---|
| Created | 2026-08-29 |
| Follows | `APPROVED_weg_business_strategy.md` (Branch B) |
| Team | 2–3 people, AI/agentic engineering · **no industry access, no audience, no capital** |
| Target | €8k MRR ≈ $9k · services <20% of team time |
| **Decision** | **Fork C selected** (user, 2026-08-29) — €8k MRR is a **milestone, not a floor**. First target **€2–3k MRR** |
| Research | 6 domain/occupancy passes + 1 adversarial pass |
| Adversarial review | **`BLOCK`** — resolved by **deletion**. Reviewer retrieved three direct competitors and Shopify's own API-scope policy from primary sources the author never opened |
| Reviewer independence | **`same-model-fallback`** — sixth round. The reviewer notes the specific cost this time: *"the author's blind spot was not looking at the app store listing page"*, and a same-model reviewer *"shares the author's disposition to trust delegated research summaries over primary retrieval"* |

---

## ⚖️ Verdict

**No shape survives. But this round did not fail the way the previous three did — it failed identically, which is itself the result.**

> **Four rounds, roughly fifteen shapes, one repeating mechanism: the automatable part of the work is already free, and the valuable part needs a human. Every shape therefore resolves to a services business, and a services business violates the <20% constraint.**

That is not bad luck across four unrelated domains. It is what the constraint set produces. **€8k MRR + services under 20% + no audience + no access + no capital** is very likely over-determined, and the honest next move is not a fifth domain — it is to decide which constraint to change.

**§ The fork** sets out the three available relaxations. **The user selected Fork C** (2026-08-29): €8k is a staged milestone with a first target of €2–3k MRR. Its real effect is not arithmetic — see § *What Fork C actually changes*.

---

## 🎯 Problem Statement

For 2–3 AI engineers with no industry access, no audience and no capital: which domain allows a monetizable product where the buyer needs no trust, the price is not collapsing, and reliability engineering is the scarce input?

---

## ✅ What this round established, and what stands

These findings survived the refutation and are reusable regardless of domain.

**1. The scarce input is reliability engineering — Filter 3 is answered.** 57% of organisations run agents in production; **89% have observability but only 52% have evaluations**, and "quality" is the top deployment barrier at 32% (LangChain, *State of Agent Engineering 2026*). **95% of enterprise GenAI pilots produce no P&L impact, and vendor-built systems succeed twice as often as internal builds** (MIT NANDA: 52 exec interviews, 153 leaders, 300 deployments). AI skills are the hardest category to hire — ~1,6M open roles against ~518k qualified people, at a 56% wage premium, up from 25% (ManpowerGroup 2026, 39.063 employers; PwC, ~1B job ads). Model access is an API and prompting is not scarce; the gap between 89% and 52% is.

**2. The AI kill pattern.** No proprietary data, no workflow lock-in, and **price set by the margin between API cost and markup**. Casualties: the wrapper cohort, "ChatGPT for PDFs" (native file upload, Nov 2023), AI budgeting apps (May 2026), RAG middleware (Assistants API). Measured: **Jasper fell from ~$120M to $55–88M** after ChatGPT undercut its $29/mo floor. Survivors hold something else — Abridge ($5,3B, $100M ARR, 250+ health systems) on clinical-record integration; Granola by becoming the data layer other tools query after being publicly sherlocked.

**3. Verification is genuinely sold apart from generation** — Stanford found legal tools marketed as *"hallucination-free"* by LexisNexis and Thomson Reuters **hallucinate 17–33% of the time**, and a market of pure checkers followed. The template is real. **What v1 got wrong was not the template but where to apply it.**

**4. Both accepted buyer types are worse than they look.**
- **Developers:** no verified case exists of a 2–3 person team with zero audience reaching $8–10k MRR self-serve in under ~12 months. Every fast case had a pre-built audience (ShipFast: 95k Twitter + 20k newsletter). The audience-free winners — Plausible, Honeybadger — took **18–24+ months**. Churn is 6,5%/month below $300k ARR (ChartMogul).
- **Prosumer:** high willingness to pay only where the tool is tied to income or regulation (SimplePractice $49–99/mo; Clio $49–149/user, $500M ARR). But **only ~10% of monthly payers reach year 2, 56–72% of annual subscribers cancel within the first year**, and 8–12% of charges fail per cycle below $20k MRR (RevenueCat, 75–115k apps).

**5. Distribution has exactly one rentable answer, and it is expensive in a different currency.** The **Shopify App Store** is the only ecosystem with repeated evidence of small teams at $5–50k MRR, 0% revenue share to $1M lifetime, and discovery that works without an audience. But: **median paying app under $1k MRR, only ~0,18% of developers exceed $1M/year, and $5–50k MRR is the top decile of a category.** New apps need **10+ reviews within 30 days** to surface at all; ~60% of installs come from in-store search; Shopify sells ads above the organic layer. Everything else failed — Chrome Web Store (~70% earn ~$0), App Store (>90% of revenue to the top 1%), Steam (median 2026 launch ~$350 lifetime), **ChatGPT and Claude directories (no payment path in 2026)**. And SEO is no longer a cold-start channel: **−58% CTR on the #1 organic result where AI Overviews appear** (Ahrefs, 300k keywords), against −34,5% a year earlier.

---

## 🗑️ What was proposed and deleted

v1 recommended a **Shopify app performing theme-level accessibility remediation, positioned against the overlay category the FTC had just sanctioned** ($1M order against accessiBe, April 2025, permanently barring unsubstantiated automated-compliance claims). Five findings killed it, each from a primary source the author never opened.

**1. The category is occupied by the exact positioning.** Shopify's Accessibility category holds **129 apps**, including three direct non-overlay competitors:

| App | Launched | Price | Their own words |
|---|---|---|---|
| **Patrol** | Dec 2024 | Free / **$200/mo** | *"is not an overlay widget. Our product resolves ADA violations in a merchant's theme files or directly in Github"* |
| **TestParty** | Jun 2025 | Free / **$599/mo** | *"Fix ADA & WCAG violations in two weeks. Source code fixes, no overlays"* |
| **EnableAll** | Nov 2025 | Free / $49 / $149 / **$399** · Built for Shopify | *"Go beyond traditional accessibility overlays with automated Code-Fix technology"* |

Plus ~10 audit/scanner apps and ~25 alt-text apps — **most of them free**, led by AltKing (167 reviews, free, Built for Shopify). Alt text is the largest automatable defect class; contrast, the second, is a theme setting. Subtract both and the automatable-and-unoccupied remainder is thin.

**2. The mechanism is gated by the platform, and the permitted path is the anti-goal.** Shopify's own docs: Asset `PUT`/`DEL` requires the `write_themes` scope, and an App-Store app *"needs to be **granted an exemption by Shopify**."* Accessibility is **not** in the eligible list — while *"Editing a CSS class or adding attributes to an existing theme element"* appears explicitly as **not eligible**, with the recommended alternative being theme app embeds that *"load scripts to target specific elements of the page."* **Shopify's sanctioned path for the product's core operation is runtime DOM patching — structurally what an overlay does.** Tellingly, EnableAll's listing discloses only *read* access to themes while marketing code fixes at the source: the differentiator is already being claimed by a vendor that cannot technically perform it, and no buyer can tell.

**3. "The buyer verifies without trusting the vendor" — the concept's whole reason for existing — is false.** **An overlay passes the same axe/Lighthouse check**; that is why overlays exist. The free tool cannot distinguish the product from the sanctioned category, so the one claim that matters is exactly the one it cannot adjudicate. Empirically merchants are not verifying: on Shopify, UserWay sits at **2,6★ (10 reviews)** and accessiBe at 3,9★ (16), while **free widgets lead the category** (Avada, 293 reviews at 5,0). If verification governed purchase, that ranking would be inverted.

**4. The <20% cap is refuted by revealed behaviour, not merely unproven.** All three competitors converged independently on retainer-plus-human: Patrol customers describe *"monthly meetings"* and paying *"their developers"* for what AI cannot do; TestParty sells *"monthly manual audits (screen reader, keyboard, zoom)"*; EnableAll's $149 and $399 tiers are explicitly **manual** testing and fixes. Three vendors, three price points, one answer.

**5. The "decisive unknown" resolves against the concept, and was answerable before recommending.** Shopify's **Theme Store requirements** are an admission gate every listed theme must clear: Lighthouse accessibility ≥90 across home/product/collection on desktop and mobile, full keyboard operability, visible focus, `alt` via `image.alt`, label/input matching, 4.5:1 and 3:1 contrast, **focus order matching DOM order**, and **24×24 px touch targets — WCAG 2.2 AA SC 2.5.8**. That is close to an enumeration of the machine-detectable defects the product proposed to sell, pre-cleared at theme approval. The residual gap to full WCAG 2.2 AA consists precisely of the judgement-dependent criteria that cannot be automated — which is why all three incumbents sell a monthly human.

> **And the process failure must be stated plainly, because it recurred.** The previous round was blocked for recommending a category without checking who sold it. v1 here performed that check for the *rejected* candidate, skipped it for the *recommended* one, and asserted in the document that the lesson had been applied. It then cited **testparty.ai** — a $599/month direct competitor on the same channel — as a neutral source for market statistics, flagged only as "vendor-adjacent". Twice in a row, the same class of error, the second time under a claim of having avoided it.

---

## 🧩 The finding that outlives the shape

The refutation's scope analysis produced something general, and it is the most useful output of this round:

> **Every cut that fixes the services cap deletes the property the Problem Statement requires; every part that satisfies the Problem Statement breaks the cap.**

Strip the accessibility product back to read-only audit and monitoring and the services load vanishes — but so does the product: that is the competitors' *free* tier, and reliability engineering stops being the scarce input. Keep the remediation and the human returns. **The two requirements are mutually exclusive in this domain, and the same exclusion killed the last three rounds.** Hence a fifth filter, earned rather than assumed:

> ### Filter 5
> **In any domain where correctness depends on human judgement, the automatable fraction is the commoditised fraction.** Detection is free because it is mechanical; the residue is valuable *because* it needs judgement — and judgement is a person, which is a services business. Do not look for a product in the residue.

Four rounds now say the same thing from four directions. **A product for a team that cannot sell services, cannot reach anyone, and has no capital must be one where the machine-checkable part is itself the whole value — not the cheap half of it.**

---

## 🔀 The fork — this is the decision

The constraint set is over-determined. Three relaxations are available; they are not equivalent.

### A · Relax "<20% services" · *not chosen*
Opens the Objektbuchhaltung branch from the previous round, and this round's accessibility category as vendor #4 against Patrol, TestParty and EnableAll. **Honest reading:** the second is worse than the first. If services are acceptable, the earlier § 28 Jahresabrechnung shape at €500–900 per object per year was the stronger one and is still there.

### B · Acquire the missing asset rather than relax a constraint · *not chosen — but not foreclosed, see below*
Every fast winner in the research had one thing the team lacks, and it is the *only* missing input that can be manufactured rather than bought: **an audience.** ShipFast reached $250k in five months on 95k Twitter followers and a 20k newsletter built beforehand; Photo AI's $132k MRR ran on Pieter Levels' existing following — the researcher flagged it explicitly as *not* a zero-audience proof point. The audience-free winners, Plausible and Honeybadger, substituted **18–24 months** of compounding instead.

So the real choice is not which idea, but **which of the two currencies to spend: 12–18 months of compounding, or 6–12 months of deliberate audience-building before the product exists.** Both are time. Neither needs capital, access or trust. This is the first path in four rounds that attacks the constraint that has actually been binding.

*Its honest cost:* it is not engineering, it is publishing, and it pays nothing while it runs.

### C · Treat €8k as a milestone, not a floor · **SELECTED**
A €2–3k MRR first milestone opens micro-niches that €8k closes by arithmetic alone. The user has framed it as staged rather than reduced, which is the reading under which it is not merely a deferral.

---

## 🎚️ What Fork C actually changes

The obvious reading — a lower target needs fewer customers — is true and is the least interesting part.

| Target | at $29/mo | at $49/mo | at $99/mo |
|---|---|---|---|
| €2–3k MRR (≈$2,2–3,3k) | 76–114 | 45–67 | **22–33** |
| €8k MRR (≈$9k) | 310 | 184 | 91 |

**The real effect is that it changes which competitors turn up.**

- **On Shopify, $2–3k MRR is roughly top-quartile rather than top-decile.** The 90th-percentile requirement that made round 4's arithmetic punishing was a function of the target, not of the platform.
- **A niche worth €30k/year is invisible to a funded competitor.** Every entrenched player that closed a shape in four rounds — Buena ($58M), Matera (~€55M), dotega, TestParty, Patrol, EnableAll — needs a market an order of magnitude larger to be worth entering. **Round 4's competitor set was drawn by the size of the target as much as by the choice of domain.** This is the first structural advantage the team has been handed rather than having to build.
- **Filter 5 still binds and C does not repeal it.** What C makes viable is a niche where the *whole* machine-checkable job is the value — not the cheap half of a judgement-dependent one. **Small and complete beats large and residual.** That is now the search specification.
- **Distribution is unchanged.** C lowers the bar; it does not supply an audience. Fork B remains available and is not mutually exclusive with C — a smaller target simply makes a smaller audience sufficient.

---

## ✅ Recommendation

1. **The fork is decided: C.** The next concept run searches under a €2–3k first target, and its specification is Filter 5 read positively — **find a job that is entirely machine-checkable, small enough that no funded competitor wants it, and priced by what an error costs.** Not the residue of a judgement-dependent job.
2. **Do not repeat the round-4 search under a smaller number.** Accessibility, feeds and the property domain are closed on occupancy and on mechanism, not on target size.
3. **First action is primary retrieval, not delegated research.** Two consecutive blocks came from trusting summaries instead of opening the page. This round's deciding facts sat on a public app-store listing and in Shopify's own API documentation — both free, both minutes away, neither opened. **In the next round, the occupancy check for the *recommended* shape is done by hand, first, before the shape is written down.**
4. **Fork B stays on the table.** A €2–3k target makes a modest audience sufficient, so C and B compose rather than compete.

---

## 📋 Open Questions

1. ~~**Which fork?**~~ **Answered (user, 2026-08-29): C.** €8k is a staged milestone; the first target is €2–3k MRR.
2. ~~**Is €8k a floor or a milestone?**~~ **Answered: a milestone.** It had been treated as a floor throughout rounds 1–4, which silently inflated every competitor set.
3. **What is the next niche, under Filter 5 read positively?** Open, and the subject of the next `/sde-concept` run.
4. **Does the team also want Fork B in parallel?** A €2–3k target makes a small audience sufficient; the two compose. Not decided.
4. **Set `reviewer_model`** in `.sde_docs/config`. Six rounds on `same-model-fallback`, and this round names the specific cost: a same-model reviewer shares the author's disposition to trust delegated summaries over primary sources — the exact failure being reviewed.

---

> **Bounded negatives.**
> - **The author verified nothing first-hand this round.** Every deletion above rests on the reviewer's primary retrieval — Shopify listings and Shopify's own API documentation — which is stronger evidence than the document it overturned.
> - **The ADA litigation counts (3.117 suits in 2025, +27%, 22,64% on overlay sites) remain unverified**, and one of the two sources cited for them is a direct competitor. The reviewer could not reach a neutral source (Seyfarth, UsableNet) before exhausting its budget. **Do not reuse these numbers.**
> - **Corrected from earlier in this round:** Shopify's 0% band is a one-time $1M lifetime allowance, not an annual reset; "~$93k average developer revenue" is a winner-skewed mean against a median under $1k MRR.
> - **The German BFSG angle is the weaker one, not the stronger one** — 14 months past the 28 June 2025 deadline, with fines to €100.000 available under § 37, **no fine, penalty or takedown could be found**, and the "authorities begin scanning in Q3 2026" claims trace to vendor marketing blogs. The microenterprise exemption (<10 employees **and** ≤€2M, services only) removes the small end.
> - **The "~30–40% of WCAG issues are automatically detectable" figure is industry consensus, not a measured study** — and the refutation showed it caps the product rather than justifying it.
> - `.sde_docs/config` is missing — running on defaults.
