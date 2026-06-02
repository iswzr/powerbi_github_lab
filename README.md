# Power BI Custom UI: Bento-Box KPI Card (DAX + SVG)

Most Power BI dashboards answer "What is the number?" Great dashboards answer "What does this number mean to me?" 

This repository demonstrates how to build a high-performance, bento-box style KPI card using a **single DAX measure**. By leveraging dynamic SVGs rendered natively in Power BI, we eliminate the need to stack multiple text boxes, shapes, and native visuals over each other.

![KPI Card Preview](./Screenshot%202026-05-12%20152200.jfif) 
![KPI Card Preview](./LineChart.jfif) 

## 🧠 The Design Philosophy
Standard KPI cards often present raw numbers with equal weighting, leading to high cognitive load. This custom component uses established UI/UX principles to reduce time-to-insight:
* **Visual Hierarchy:** The primary metric (COGS % of Sales) dominates via size and position, while contextual numbers (Spent vs. Limit, Retained Profit) are subordinated.
* **Pre-attentive Processing:** An integrated SVG progress bar and status icon (Checkmark/Cross) instantly communicate whether performance is on track before a single number is read.
* **Human-Centric Copy:** Replaces rigid dataset labels with natural language ("retained as profit") to answer business questions directly.

## 🛠️ Technical Implementation
This project is saved using Power BI's **Developer Mode (`.pbip`)** to expose the underlying semantic model and report definitions. 

The core of the visual is powered by a single DAX measure (`SVG_AllInOne_KPI_Final`) that dynamically renders an XML string based on the standard Financial sample dataset. 

**Key Features of the DAX SVG:**
- Dynamic `viewBox` coordinates for pixel-perfect text alignment.
- Conditional formatting: Progress bar and icons switch between `#449E74` (Green/On-track) and `#D9534F` (Red/Off-track) based on a 70% threshold.
- Embedded typography directly within the SVG `<text>` tags.

## 🚀 How to Use This Repo
1. Clone this repository to your local machine.
2. Open the `Sales_Analytics.pbip` file in Power BI Desktop (requires Power BI Developer Mode to be enabled in Preview Features).
3. Review the `SVG_LinearProgressBar` measure in the data pane.
4. Add a native **Image Visual** to the canvas and bind the measure to it. 

---
*Developed by Iswzr*
