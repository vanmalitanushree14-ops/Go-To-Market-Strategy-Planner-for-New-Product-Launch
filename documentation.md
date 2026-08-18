# FlowPilot AI — Data Documentation & Analysis

## 1. Source
The analysis uses the supplied 100-row FlowPilot AI go-to-market dataset. Each row represents a product/market/campaign scenario with product positioning, competitor pricing, campaign investment, funnel expectations, revenue projections, market/readiness/channel/risk scores, GTM priority, launch phase, and status.

## 2. Data dictionary
- **Product ID:** Scenario identifier (P001–P100).
- **Customer Segment / Persona:** Target buyer classification.
- **Geography / Industry:** Market context.
- **Customer Pain Point / Value Proposition:** Problem and proposed solution.
- **Competitor Price / Proposed Product Price:** Pricing benchmark and proposed price.
- **Pricing Model:** Commercial model.
- **Marketing Channel / Campaign Type:** Acquisition approach.
- **Campaign Budget / Expected Reach / Leads / Conversions:** Funnel and investment assumptions.
- **Conversion Rate %:** Source-provided lead-to-conversion assumption.
- **Customer Acquisition Cost:** Source-provided CAC.
- **Expected Revenue / Revenue Forecast:** Shorter-period expected revenue and annualized/forecast revenue.
- **Market Demand / Product Readiness / Channel Effectiveness / Launch Risk:** 0–100 strategic scores.
- **GTM Priority / Launch Phase / Launch Status:** Recommended strategic posture.

## 3. Derived metrics
- Price Discount % = 1 − Proposed Price / Competitor Price
- Reach→Lead % = Expected Leads / Expected Reach
- Lead→Conversion % = Expected Conversions / Expected Leads
- Campaign ROI % = (Expected Revenue − Campaign Budget) / Campaign Budget
- Revenue per Conversion = Expected Revenue / Expected Conversions
- Revenue / Budget = Expected Revenue / Campaign Budget
- Efficiency Score = 30% Demand + 25% Readiness + 25% Channel Effectiveness + 20% (100 − Risk)

## 4. Data-quality note
The source contains a visible anomaly at P097: Expected Revenue is recorded as **574?**. Because the value is not a clean numeric amount, it is treated as missing in numeric calculations rather than silently corrected. All other source values are preserved.

## 5. Executive findings
- Records analyzed: 100
- Total campaign budget: ₹7,574,000
- Total expected revenue (excluding P097 anomaly): ₹16,692,199
- Total revenue forecast: ₹200,989,500
- Total expected reach: 4,930,000
- Total expected leads: 93,970
- Total expected conversions: 9,671
- Blended lead-to-conversion rate: 10.29%
- Budget / expected conversion: ₹783
- Portfolio campaign ROI: 120.4%
- Average market demand: 89.9/100
- Average product readiness: 92.6/100
- Average channel effectiveness: 89.6/100
- Average launch risk: 26.1/100

## 6. Strategic interpretation
The dataset strongly supports a launch-oriented strategy: most records are marked High GTM Priority and the majority are in Launch/Active status. Enterprise scenarios generally carry larger budgets and higher revenue potential, while SME scenarios provide broader reach and a lower-cost acquisition pattern. The best-performing scenarios should be prioritized where demand, readiness and channel effectiveness are high while launch risk remains controlled.

## 7. Recommended management actions
1. Prioritize High-GTM-Priority scenarios with high efficiency scores.
2. Scale channels with strong revenue-to-budget performance and low CAC.
3. Use enterprise direct-sales/ABM motions selectively because they require higher investment but can support larger revenue.
4. Preserve lower-cost SME acquisition motions for reach and pipeline generation.
5. Validate the P097 revenue field before using it in financial reporting.
