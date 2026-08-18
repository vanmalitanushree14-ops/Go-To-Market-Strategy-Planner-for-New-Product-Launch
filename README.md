# Go-To-Market-Strategy-Planner-for-New-Product-Launch

An end-to-end Go-To-Market and Product Analytics project for **FlowPilot AI**, an AI Productivity SaaS tool.  
This repo contains 100 simulated customer segments across SMEs and Enterprise to analyze pricing, campaigns, revenue forecast, and launch readiness.

## 🎯 Project Objective
Help Product + Marketing teams decide:
1.  **Which customer segments to target first** based on GTM Priority
2.  **Optimal pricing and channels** by Market + Persona  
3.  **Revenue Forecast and CAC** to plan budget
4.  **Launch Readiness** using Product + Channel + Risk scores

## 📁 Dataset Overview
**File**: `flowpilot_gtm_dataset.csv`  
**Rows**: 100 customer segments/personas  
**Columns**: 31

### Key Columns
| Category | Columns |
| --- | --- |
| **Product** | Product ID, Product Name, Product Category |
| **Targeting** | Target Market, Customer Segment, Customer Persona, Geography, Industry |
| **Pain & Value** | Customer Pain Point, Value Proposition, Competitor Name, Competitor Price |
| **Pricing** | Proposed Product Price, Pricing Model |
| **GTM & Marketing** | Marketing Channel, Campaign Type, Campaign Budget, Expected Reach, Expected Leads, Expected Conversions |
| **Performance** | Conversion Rate %, Customer Acquisition Cost, Expected Revenue, Revenue Forecast |
| **Scoring** | Market Demand Score, Product Readiness Score, Channel Effectiveness Score, Launch Risk Score |
| **Decision** | GTM Priority, Launch Phase, Launch Status |

## 📊 Key Insights from Data
1.  **Highest Revenue Segments**: Enterprise Clients in Banking/FinTech with `Proposed Price = 3999` and `Revenue Forecast > 30L`
2.  **Best CAC**: Freelancers and Budget Buyers via Instagram/YouTube have CAC < 300
3.  **Launch Ready**: 65% of segments are in `Launch/Active` phase with `GTM Priority = High`
4.  **Top Channels**: LinkedIn for Enterprise, Instagram + Google Ads for SMEs
5.  **Risk**: Enterprise segments have higher `Launch Risk Score` due to compliance

## 🛠️ How to Use This Repo

### 1. Analysis Files
Open `flowpilot_gtm_dataset.csv` in Excel / Google Sheets / Python

### 2. Recommended Dashboards
Build these 4 charts:
- **Revenue vs CAC Scatter**: X=CAC, Y=Revenue Forecast, Color=Customer Segment
- **GTM Priority Funnel**: Count of High/Medium/Low by Launch Phase
- **Channel Effectiveness Bar**: Avg `Channel Effectiveness Score` by `Marketing Channel`
- **Top 10 Segments Table**: Sort by `Revenue Forecast` descending

### 3. Python Quickstart
```python
import pandas as pd
import plotly.express as px

df = pd.read_csv('flowpilot_gtm_dataset.csv')

# Top 10 segments by revenue
top10 = df.nlargest(10, 'Revenue Forecast')
print(top10[['Customer Persona', 'Industry', 'Revenue Forecast']])

# CAC vs Revenue
fig = px.scatter(df, x='Customer Acquisition Cost', y='Revenue Forecast', 
                 color='Customer Segment', size='Expected Conversions')
fig.show()
