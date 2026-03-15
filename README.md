# Product Performance Analysis Report (MVP)
![Product Performance Analysis Landing](images/01-campaigns-overview.png)

> 🚧 **MVP (Under Development):** This dashboard is a working first version and is still evolving.  
> Expect ongoing improvements to the data model, measures, drilldowns, and UI polish.

---

## 🚀 Introduction
The **Product Performance Analysis Report** evaluates how the **Campaigns** product is performing across core business metrics, including **revenue**, **entries**, **clients**, and **campaigns**.

The report is designed for quick executive visibility (overview KPIs) and deeper operational insights (participation performance + demographics) for product, marketing, operations, and management.

---

## 🧰 Tools Used
- **Google Sheets** — lightweight staging, validation checks, and quick QA during development
- **Power BI** — data transformation, modeling, measures, and interactive reporting
- **Figma** — UI/UX wireframing and layout design (report look & feel)

---

## 📌 Table of Contents
- [Problem Statement](#problem-statement)
- [Data Source](#data-source)
- [Workflow Overview](#workflow-overview)
- [Report Pages](#report-pages)
- [Live Power BI Report](#live-power-bi-report)
- [Analysis & Insights](#analysis--insights)
- [Recommendations](#recommendations)
- [Contact](#Contact)

---

## Problem Statement
This dashboard answers questions like:
- 💰 How much revenue is the Campaigns product generating overall and by campaign type?
- 🧾 How many entries are received, and what portion is valid?
- 🏆 What is the win rate, and how many unique winners are participating?
- 🎁 How much reward value is allocated, and what is disbursed vs pending?
- ⏰ What time-of-day shows peak participant activity?
- 🗺️ Where are participants coming from (regional distribution)?
- 👥 What do demographics (e.g., gender) look like, and what was/wasn’t captured by campaign?

---

## Data Source
- **Source:** Internal company database (web-based connection)
- **Format:** Web (confidential/internal)
- **Privacy Note:** Due to confidentiality, the dataset and direct source link cannot be shared publicly.

---

## Workflow Overview
1. **Data extraction** from internal company systems (web connection).
2. **Staging + QA in Google Sheets** (spot checks, reconciliation, and early sanity tests).
3. **Power Query transformations** (type enforcement, cleaning, and shaping for reporting).
4. **Measures/KPIs in Power BI** for:
   - Revenue, Entries, Valid Entries, Wins
   - Rewards (total/disbursed/pending)
   - Rates (Validity Rate, Win Rate)
   - Participation breakdowns (time, campaign, demographics)
5. **UI/UX design in Figma**, then implemented in Power BI for a clean, app-like layout.

---

## Report Pages

### 1) Campaigns Performance Overview
**Purpose:** Executive snapshot of Campaigns product performance (high-level KPIs + trends).
- Total Revenue, Total Entries, Total Clients, Total Campaigns
- Revenue split by **Campaign Type**
- Monthly revenue trend (Month/Quarter toggle)

![Campaigns Performance Overview](images/01-campaigns-overview.png)

---

### 2) Entry & Participation Analytics — Performance
**Purpose:** Participation funnel + reward operations + activity patterns.
- Rewards overview (Total / Disbursed / Pending)
- Entries overview (Max Daily / Avg Daily)
- Validity + win performance (Validity Rate, Win Rate, Unique Winners)
- Reward amount distribution
- Valid entries & rewards by campaign
- Peak traffic analysis (entries by hour)

![Entry & Participation Analytics — Performance](images/02-entry-performance.png)

---

### 3) Entry & Participation Analytics — Demographics
**Purpose:** Who/where participants are (and what fields were captured).
- Regional entries distribution (Ghana shapemap)
- Super participant leaderboard (high-activity participants)
- Entries per gender (including “No Gender Data” where gender wasn’t collected)

![Entry & Participation Analytics — Demographics](images/03-demographics.png)

---

## Live Power BI Report
**Open the interactive report here:**  
[Demo Report](https://app.powerbi.com/view?r=eyJrIjoiNDBjYThkZmQtMDBjMC00MDQ4LWFkNjktYTM3ZjEzNDA2N2ViIiwidCI6Ijk0NDVhOTgzLTgyMjMtNDg3My1iYjhkLWM3NzRhODBkNTYxNSJ9)

> Note: GitHub README pages typically do **not** render iframes.

---

## Analysis & Insights
> The metrics below reflect the snapshot shown in the attached report images and may vary depending on refresh timing.

### ✅ Executive Snapshot
- **Total Revenue:** **GH¢470K**
- **Total Entries:** **133K**
- **Total Clients:** **2**
- **Total Campaigns:** **2**

| KPI | Value |
| --- | ---: |
| Total Entries | 133K |
| Valid Entries | 105K (**~79%** validity) |
| Invalid Entries | 28K (**~21%**) |
| Wins | 93K |
| Win Rate (Wins / Valid Entries) | **~88.6%** |
| Unique Winners | 38K |
| Avg Wins per Winner | **~2.45** |

---

### 🧾 Entry Validity (Why Entries Become Invalid)
Invalid entries are mainly driven by **two major causes**:
1. **Wrong code submission** — customers enter an incorrect/invalid code.
2. **Agent discretion** — a client’s agent can mark an entry as invalid based on internal rules or review outcomes.

**Insight:** Reducing wrong-code submissions is a product/UX opportunity, while agent-driven invalidation needs clear governance and auditability.

---

### 💰 Revenue Mix (Campaign Type)
| Campaign Type | Revenue | Share |
| --- | ---: | ---: |
| Sure Win (Single) | GH¢300K | **~63.8%** |
| Basic Random Win | GH¢170K | ~36.2% |

**Insight:** Revenue is currently weighted toward **Sure Win (Single)**, contributing nearly **two-thirds** of total revenue.

---

### 🎁 Rewards & Payout Operations
- **Total Rewards:** **GH¢70.52K**
  - **Disbursed:** GH¢60.12K (**~85%**)
  - **Pending:** GH¢10.40K (**~15%**)

**What “Pending” means:** Some rewards remain pending because **clients did not load/fund their payout accounts**, so payouts could not be completed to winners at the time.

**Insight:** Pending rewards are not just an ops backlog—this is also a dependency risk tied to client funding readiness.

---

### 📣 Campaign Contribution (Engagement vs Rewards)
From the “Valid Entries and Rewards per Campaign” visual:
- **Vivo Always-On 2025:** **74K** valid entries (**~70%** of valid entries)
- **Indomie Hero Pack Promo 2025:** **31K** valid entries (**~30%** of valid entries) and **~GH¢71K** total rewards (rounded on the chart)

**Insight:** One campaign drives most **engagement**, while another carries most of the **reward value**—useful for comparing campaign mechanics and ROI.

---

### ⏰ Peak Traffic (Entries by Hour)
**Observed pattern (from the peak traffic chart):**
- Very low activity overnight (roughly **00:00–04:00**)
- Strong ramp-up from early morning
- Sustained activity through the day
- Highest activity appears in the **late afternoon / early evening**, then declines after **~20:00**

**Insight:** Schedule push messages and operational monitoring around peak engagement hours.

---

### 🗺️ Demographics & Coverage
#### Regional Entries Distribution (Ghana shapemap)
Below is the regional distribution dataset used for the map visual (regional totals may not always match overall entries depending on coverage/time window and availability of region fields).

| Region     |   Total Entries |   Share % | Popular Location      |   Number of Locations |
|:-----------|----------------:|----------:|:----------------------|----------------------:|
| Accra      |           38840 |     45.63 | Accra                 |                   119 |
| Ashanti    |           21628 |     25.41 | Adum                  |                    71 |
| Central    |            8009 |      9.41 | Kasoa                 |                    37 |
| Western    |            7104 |      8.35 | Sekondi-Takoradi      |                    36 |
| Eastern    |            3207 |      3.77 | Koforidua Town Center |                    41 |
| Volta      |            2085 |      2.45 | Ho                    |                    19 |
| Bono       |            1771 |      2.08 | Sunyani               |                    13 |
| Ahafo      |             724 |      0.85 | Goaso                 |                     6 |
| Northern   |             704 |      0.83 | Tamale                |                    20 |
| Bono East  |             429 |      0.50 | Kintampo              |                     7 |
| Savannah   |             152 |      0.18 | Kpandu                |                     6 |
| Upper East |             150 |      0.18 | Bolgatanga            |                    10 |
| North East |             140 |      0.16 | Walewale              |                     5 |
| Oti        |              99 |      0.12 | Nkwanta               |                     8 |
| Upper West |              69 |      0.08 | Wa                    |                     4 |

**Insights:**
- **Accra (45.63%)** and **Ashanti (25.41%)** together account for **~71%** of captured regional entries.
- The top 4 regions (**Accra, Ashanti, Central, Western**) contribute **~88.8%** of captured regional entries.
- This indicates strong regional concentration—useful for targeted marketing and operational planning.

#### Entries Per Gender
| Gender | Entries | Share |
| --- | ---: | ---: |
| No Gender Data | 74K | **70.41%** |
| Female | 20K | 18.82% |
| Male | 11K | 10.76% |

**What “No Gender Data” means:** Not all campaigns collect gender, so “No Gender Data” often reflects **gender not captured by campaign design**, not necessarily a data quality issue.

**Insight:** Where gender is collected, it can support segmentation; where it isn’t, reporting should treat it as “Not Collected” rather than “Missing”.

---

## Recommendations
1. **Reduce wrong-code invalid entries (Product + Marketing)**
   - Improve code entry UX (format hints, validation feedback, clearer error states)
   - Where possible, implement code structure validation (length/pattern checks) before submission

2. **Govern agent-driven invalidations (Ops + Management + CTO)**
   - Document the invalidation policy and standardize reasons
   - Add audit-friendly logging (reason codes, agent ID, timestamp) to support transparency and dispute resolution

3. **De-risk pending payouts with client funding readiness (Ops + Management)**
   - Set a client funding/prefund SLA before campaign launch
   - Implement alerts when payout accounts are not loaded (to reduce pending accumulation)
   - Track “Pending Rewards Aging” as an operational KPI

4. **Improve demographic strategy without forcing it (Product + Marketing)**
   - Treat “No Gender Data” as “Not Collected” when campaigns don’t request it
   - If demographic segmentation is a goal, align campaign setup to include gender capture consistently (where appropriate)

5. **Use regional concentration for targeted execution (Marketing + Ops)**
   - Prioritize engagement initiatives in **Accra and Ashanti** where participation is most concentrated
   - Use high-entry regions for A/B testing campaign mechanics and messaging

6. **Monitor fairness/fraud signals (Ops + CTO)**
   - Review super participant patterns for abnormal behavior (high frequency, unusual win rates)
   - Add rules/thresholds for automated flagging (MVP → v2 improvement)

---

## Contact
- **Phone:** +233 54 583 2352  
- **LinkedIn:** [Click here](https://www.linkedin.com/in/douglasboateng/)  
- **Email:** [Click here](mailto:dougieboat@gmail.com)

---

*© 2025 Douglas Boateng | [GitHub](https://github.com/dougieboat)*
