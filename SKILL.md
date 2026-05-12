---
name: fundamental-stock-selection
description: A股产业主题基本面选股流程。Use this skill when the assistant needs to analyze an A-share listed company, create an observation-pool rating, distinguish real industry beneficiaries from concept speculation, score fundamentals, or perform pre-trading fundamental screening for sectors such as commercial aerospace/satellite internet, humanoid robots/embodied AI, semiconductor equipment, AI compute infrastructure, high-end equipment, low-altitude economy, military informatization, innovative drugs, new-energy export chains, or brain-computer interface. Do not use this skill to give direct buy/sell points; use it before any technical trading analysis.
---

# Fundamental Stock Selection

## Core Rule

Use this skill to decide whether an A-share company has enough verifiable fundamental support to enter an observation pool. Do not recommend a stock, give buy/sell points, or treat a theme as an investment conclusion.

Unless the user explicitly requests another language, output the analysis in Chinese. Treat this skill as a fundamental-screening gate before any later technical-analysis or position-management discussion.

Always separate:

- Confirmed facts
- Reasonable inference from public information
- Market expectations
- Concept speculation
- Unverified information

Avoid these phrases and equivalent claims: 必涨, 确定性机会, 稳赚, 闭眼买, 低风险高收益, 无脑持有.

## Required Sources

Prefer sources in this order:

1. Annual reports, interim reports, quarterly reports, exchange filings, and CNINFO announcements
2. SSE, SZSE, BSE inquiry letters and replies
3. Investor-relations activity records and earnings previews
4. Ministry, regulator, industry-association, and authoritative research data
5. Public broker summaries only as supporting comparison
6. Market-data sites such as Eastmoney, iFinD, Wind, Choice only as auxiliary data
7. Social media, forums, rumors, and short videos are not core evidence

If current financials, announcements, market price, or valuation data are needed, browse or use current data sources first. State the data date explicitly.

## Missing Data Rule

If some data are unavailable, do not fabricate them. Mark them as "未披露 / 未取得 / 需进一步核查". 
Do not give full score to any module with missing critical evidence.
If key data such as recurring net profit, operating cash flow, related-business revenue share, order verification, or valuation data are missing, the rating cannot exceed B unless strong official evidence supports the conclusion.

## Mandatory Analytical Modules

These five modules must run on every analysis. They are not optional sections — they enforce evidence discipline and prevent theme speculation from inflating scores.

### M1 — Evidence Strength Rating

Every core conclusion must carry an inline evidence grade in brackets:

- `[A]` = directly stated in annual report, interim report, quarterly report, or exchange filing
- `[B]` = derived from financial statement data (calculated, not directly stated)
- `[C]` = broker summary, investor-relations activity record, or media report
- `[D]` = unverified rumor, social media, or short video

Do not mix grades within a single claim. If a section's evidence is entirely `[C]` or `[D]`, it cannot drive a rating above B.

### M2 — Revenue Penetration Table

For any industry theme, complete this table before assigning industry relevance or competitiveness scores:

| Item | Required answer |
|---|---|
| Is there related revenue? | Yes / No |
| Related revenue amount (latest year) | Figure or 未披露 |
| Related revenue share | % or 未披露 |
| Related business gross margin | % or 未披露 |
| Verifiable customers | Names or 未披露 |
| Order or contract disclosure | Yes / No / Insufficient |
| Mass-production stage | Sample / Pilot batch / Mass / None |
| Evidence grade | A / B / C / D |

If related revenue is not disclosed and no order or customer verification exists, the theme cannot add more than 3 points to Company Competitiveness.

### M3 — Order Conversion Analysis

Required for: auto parts, semiconductor equipment, aerospace, defense, industrial equipment.

Must answer:
- Lifecycle order → estimated annual contribution (lifecycle total ÷ expected years)
- Order-to-revenue timing: design-in → SOP → ramp → stable supply
- Order profit quality: gross margin of that product line, annual price-down risk, capex requirement, customer bargaining power
- Organic growth rate: reported growth minus M&A and disposal contribution

Include this table:

| Segment | Reported growth | M&A / disposal effect | Organic growth | Judgment |
|---|---:|---:|---:|---|
| Segment A | | | | |
| Segment B | | | | |
| Total revenue | | | | |

If organic growth cannot be isolated, state "未能拆分，表观增速含并购因素". If order profit quality cannot be verified, state "订单验证强，但利润弹性未验证" and cap order-related scoring accordingly.

### M4 — Valuation Three-Way Split

The valuation section must cover all three dimensions:

1. **Historical percentile**: where does current PE / PB / PS sit relative to the company's own 3-year or 5-year range?
2. **Peer comparison**: use a consistent peer set matched to the company's primary business. Do not mix growth-stock peers with value-stock peers for the same company.
3. **Earnings sensitivity**: what happens to implied valuation if net profit changes ±20%? State whether the stock becomes clearly cheap or clearly expensive under each scenario.

Valuation module score cannot exceed 10/15 if any of the three dimensions is missing.

### M5 — Observation Pool Execution Table

Required for every B-rated stock. Must specify quantified, verifiable thresholds — not vague phrases like "业绩不及预期":

| Trigger type | Quantified condition | Action |
|---|---|---|
| Continue tracking | No negative signal fired | Keep in pool, review at next report |
| Upgrade to A | [specific threshold] | Move to core pool |
| Downgrade to C | [specific threshold] | Move out of priority |
| Remove (D) | [specific threshold] | Exit pool, avoid |

Example of acceptable threshold: "revenue YoY < −5% for two consecutive quarters".
Example of unacceptable threshold: "revenue declines".

---

## Inputs To Collect

For each company, collect or ask for:

- Stock code and company name
- Target industry direction and industry-chain position
- Current market value and price, when valuation is discussed
- Revenue mix, gross-profit mix, main customers, and comparable companies
- Latest three annual reports and latest four quarterly reports when available
- Earnings preview/flash, major contracts, refinancing, M&A, restructuring, inquiry letters, pledge/reduction/unlock announcements, litigation, penalties, and risk warnings

## Workflow

Run the process in this exact order.

### 1. Industry Relevance

Answer first: does the company genuinely belong to the target industry chain?

Check whether the company has disclosed the related business in official filings, whether the business has actual revenue, whether revenue share is identifiable, whether customers/orders/products/certifications are verifiable, and whether the relationship is only an interactive-platform answer, press release, equity investment, joint venture, or marginal component supply.

Classify relevance as:

- High: core or growth business with verifiable revenue and orders
- Medium: real business exists but revenue share is low or still in customer introduction
- Low: small business, investment exposure, cooperation, or R&D reserve
- Concept: no revenue, no order, no customer evidence

If the result is Concept, normally rate C or D regardless of theme heat.

### 2. Financial Quality

Evaluate whether growth is real, profit is sustainable, and cash flow matches accounting profit.

Cover:

- Revenue scale, three-year CAGR, quarterly year-on-year and quarter-on-quarter changes
- Whether growth comes from core business, consolidation, accounting changes, or one-off projects
- Gross margin, net margin, period expense ratio, R&D expense ratio, impairment, government subsidies, investment income
- Parent net profit and recurring net profit; recurring profit has priority
- Operating cash flow, operating cash flow/net profit, free cash flow, cash received from sales/revenue
- Accounts receivable, inventory, contract liabilities, capital expenditure, cash, and short-term debt pressure
- Debt ratio, interest-bearing debt, goodwill, equity pledge, shareholder reduction, frequent refinancing

Treat these as warning signs: revenue growth with receivables expanding faster, profit growth without recurring profit growth, operating cash flow persistently below profit, margin deterioration, unclear order support for inventory expansion, high debt plus weak cash flow.

### 3. Industry Position

Determine whether the company is a real industry leader, core supplier, second-tier beneficiary, marginal supplier, or concept mapping.

Answer:

- Which industry-chain link is the company in?
- Is this link a bottleneck or high-value link?
- Is there import-substitution or national-security logic?
- What are the technical barriers, customer barriers, certifications, scale advantages, or cost advantages?
- Are orders, batch supply, or core-customer supply-chain entries verifiable?
- Can the industry trend transmit into revenue and profit?

### 4. Sector-Specific Checks

For detailed sector indicators, load [sector-indicators.md](references/sector-indicators.md).

Use the relevant section only:

- Commercial aerospace / satellite internet
- Humanoid robot / embodied AI
- Semiconductor equipment
- AI compute infrastructure

For other sectors, adapt the same structure: industry-chain position, customer/order verification, commercial stage, margin/cash-flow quality, and policy/valuation risk.

### 5. Valuation

Do not look at PE alone. Match valuation with growth quality, industry stage, profit sustainability, and cash flow.

Use:

- PE for profitable and stable companies
- PB for heavy-asset or cyclical companies
- PS or EV/Sales for high-growth companies with low or unstable profits
- PEG only when profit growth is reasonably stable
- EV/EBITDA for companies with heavy depreciation and amortization
- Market value/order or market value/revenue only as auxiliary measures for order-driven companies

For loss-making companies, explain why PE is not usable. Use PS, EV/Sales, cash burn, cash reserve, verified customers/orders, revenue growth, gross-margin improvement, and path to breakeven. If there is no revenue growth, order verification, or cash-flow improvement, do not raise the rating because of theme space.

### 6. Scoring And Rating

Load [scoring.md](references/scoring.md) and apply the 100-point framework.

Before finalizing the rating, apply hard exclusions and mandatory downgrades from [scoring.md](references/scoring.md).

Rating meanings:

- A: strong tracking, core observation pool, not a buy signal
- B: cautious tracking, normal observation pool
- C: not considered for now, wait for fundamental improvement
- D: high-risk avoidance

### 7. Output

Use the standard template in [output-template.md](references/output-template.md). The template is mandatory: do not omit any numbered section, including core business breakdown, peer comparison, and valuation. If data are missing, keep the section and mark fields as "未披露 / 未取得 / 需进一步核查" instead of skipping it. Keep the conclusion clear and include:

- Direct conclusion
- Core evidence
- Analysis process
- Risk warning
- Counterargument
- Next actions

End by stating that fundamental screening does not replace position management, stop-loss discipline, or later technical analysis.

After completing the analysis, save the full report as a Markdown file using the Write tool. File name format: `公司名-YYYYMMDD.md` (e.g., `均胜电子-20260511.md`). Save to the current working directory unless the user specifies otherwise. The file must contain all sections from the output template including the five mandatory modules.

## Risk Discipline

This skill improves research discipline but cannot remove investment risk.

Remember:

- Financial reports are lagging indicators.
- Theme sectors often price expectations before earnings.
- Some announcements are incomplete or non-quantitative, so use revenue, contract liabilities, receivables, inventory, and cash flow for cross-checking.
- Small accounts should avoid over-diversification and concentrated exposure to one theme.
- A-rated output means "worth tracking", not "suitable to buy now".
