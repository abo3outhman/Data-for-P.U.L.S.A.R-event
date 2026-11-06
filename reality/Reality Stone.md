# 💠 Reality Stone — Participant Guide

> _"Reality is often disappointing."_ Not here. Your job is to find what is **really** happening in the data.

---

## 1. The Mission

A company is losing employees. Management does not know why.

**Your mission:** analyze the HR data, find **why employees leave**, build a **dashboard** that lets management explore it, and write a **PDF report** that tells them what to do about it.

This is a **data analysis** challenge. No machine learning model is required or scored. You are judged on the quality of your **understanding** and your **decisions**, not on a prediction metric.

---

## 2. What You Receive

- One HR dataset (Excel/CSV), the same for every team.
- A data dictionary explaining each column.

**Warning:** real data is never clean. Expect missing values, duplicates, inconsistent labels and impossible values. Handling them well is part of the score.

---

## 3. What You Must Submit

|File|Format|Naming|
|---|---|---|
|Dashboard|Power BI (`.pbix`), Excel (`.xlsx`) or Tableau (`.twbx`)|`TeamName_Reality.<ext>`|
|Report|PDF|`TeamName_Reality.pdf`|

Both files are required. A missing file means the mission is **not complete**.

---

## 4. Rules

- **Tools:** use a visual BI tool (Power BI, Excel, Tableau). Python/SQL may be used for cleaning, but the final dashboard must be built in your BI tool.
- **AI:** allowed **only as a guide or for research** (explaining a concept, looking up a method). Do **not** connect any AI or MCP to Power BI or to the tool you build with, and do not let an AI build your dashboard or write your report for you.
- **Declaration:** you must declare in your report how you used AI and tools (see section 5, last item).
- **Be honest with the data:** do not hide problems, and do not claim more than the data supports.

---

## 5. The PDF Report — Required Structure

Keep it concise: **10 pages maximum**, appendix excluded. Sections must appear **in this order**.

### Cover

Team name, members with their department, BI tool used, names of the submitted files.

### 1. Executive Summary

The most important section. A manager who reads only this must understand your whole work.

- **Final answer:** the **top 3 reasons** employees leave, **ranked**, each backed by a number.
- Your **number-one recommendation** and its expected financial impact.
- One sentence on what you could **not** conclude.

> ⚠️ This "final answer" is **locked at submission**. On Welcome Day, it will be compared to **the reality** hidden in the data.

### 2. Business Question and Scope

Restate the problem in your own words. State your assumptions and define your indicators (for example: _attrition rate = employees who left ÷ total employees_).

### 3. Data and Cleaning Log

- Number of rows **before** and **after** cleaning.
- A table with, for each problem found: **what it is, how many cases, what you did, why**.
- It must cover: **duplicates, missing values, outliers/impossible values, inconsistent labels**.

### 4. Dashboard Overview

Screenshots of your dashboard and a short **reading guide**: what each view shows, what the filters do, and which question each view answers.

### 5. Findings

Between **3 and 5 findings**. Each finding follows this pattern:

1. **Claim:** one clear sentence.
2. **Evidence:** a chart. Its **title must be the conclusion**, not a description (write _"Attrition peaks in the first 2 years"_, not _"Attrition by tenure"_). Show the sample size `n` and label the axes.
3. **Why it matters:** the business meaning.
4. **Confidence:** High, Medium or Low, with a reason.

At least one finding must describe **who the employee who leaves looks like**.

### 6. Recommendations

A table with: **action, target group, estimated cost, expected benefit, priority, risk**. Every finding must lead to at least one recommendation. Use the cost information in the data to justify numbers.

### 7. Limitations

What the data cannot tell you, where correlation is not causation, and what you would investigate next.

### 8. Tools and AI Declaration

Which tools you used and for what. Where and how you used AI (guide/research only). A statement that no AI/MCP was connected to your BI tool. Signed by the team.

### Appendix (not counted in the limit)

Data dictionary, extra charts, calculation details.

---

## 6. Dashboard — Minimum Requirements

- Works without errors when opened, and is built on your **cleaned** data.
- At least **5 KPIs** clearly visible (for example attrition rate, number of leavers, cost of attrition).
- At least **3 interactive filters** (slicers).
- At least one view showing **change over time**, and one comparing **groups**.
- Readable by a non-technical manager: clear titles, consistent colors, no clutter.

---

## 7. Mission Complete Checklist

Your team's mission is **complete** only if all of these are true (verified by a supervisor at submission):

- [ ] PDF follows the structure above, in order, within the limit
- [ ] Dashboard opens and meets the minimum requirements
- [ ] Cleaning log covers the four problem types
- [ ] At least 3 findings, each with evidence and a recommendation
- [ ] Recommendation table is complete (cost and benefit included)
- [ ] Tools and AI declaration is signed
- [ ] Both files are named correctly and submitted before the deadline

---

## 8. Ranking

- Teams are evaluated on: data cleaning, depth and correctness of analysis, dashboard quality, recommendations, and report quality.
- At **[TIME]**, if a team has finished with **Mission Complete** after it, it takes **first place**.
- On Welcome Day, **the reality is revealed**: your locked final answer is compared with what is truly in the data.

Good luck. 💠