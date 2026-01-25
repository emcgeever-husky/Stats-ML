# **The Cost of Living Crisis: A Data-Driven Analysis**

## **The Problem: Why the “Average” CPI Fails Students**

Headline inflation statistics such as the Consumer Price Index (CPI) are designed to represent the *average urban consumer*. However, students face a fundamentally different cost structure—one heavily weighted toward tuition, rent, food away from home, and digital services. As a result, official CPI measures may significantly understate the inflation actually experienced by students.

This project investigates whether student living costs have diverged from official inflation measures since 2016, and whether regional inflation dynamics further exacerbate this gap.

---

## **Methodology: Python, APIs, and Index Theory**

I constructed a **custom Student-Specific Price Index (Student SPI)** using Python and public data from the Federal Reserve Economic Data (FRED) API.

### Key methodological steps:
- Collected CPI subcomponents relevant to students (tuition, rent, food, streaming services).
- Addressed **inconsistent CPI base years** by re-indexing all series so **January 2016 = 100**, enabling meaningful comparisons.
- Built a weighted index using a **Laspeyres-style framework**, reflecting a fixed student consumption basket.
- Integrated **regional CPI data** (Boston–Cambridge–Newton metro area) to examine geographic disparities.
- Visualized trends using `matplotlib`, including shaded inflation gaps.

This approach mirrors how official price indexes are constructed, while tailoring the basket to a specific population.

---

## **Key Findings**

### **1. Student costs have consistently outpaced official inflation**
My analysis reveals a **persistent divergence between the Student SPI and National CPI**, beginning shortly after 2016 and accelerating after 2021. By 2025, the Student SPI is approximately **8–10 percentage points higher** than the official CPI, indicating materially higher inflation for students.

> In short: students experience inflation that is systematically understated by headline CPI.

---

### **2. Tuition and digital services distort raw CPI comparisons**
Plotting *raw (non-normalized)* FRED CPI series highlights why normalization is essential. Tuition and streaming services use different base years, making level comparisons misleading. While raw indexes differ dramatically in magnitude, their growth trajectories only become interpretable after re-indexing.

This reinforces a key lesson in applied macroeconomics: **index levels are meaningless without a common base year**.

---

### **3. Regional inflation compounds student cost pressures**
Comparing **National CPI**, **Boston-area CPI**, and the **Student SPI** shows that:
- Boston inflation closely tracks, but often slightly exceeds, national CPI.
- Student costs rise faster than both national and regional CPI.

This suggests students in high-cost metro areas face a *double burden*: unfavorable consumption weights and elevated regional inflation.

---

## **Conclusion**

This project demonstrates that inflation is not a single number—it is **basket-dependent and location-dependent**. For students, official CPI significantly understates cost-of-living pressures, particularly in major metropolitan areas.

By combining economic theory, public APIs, and transparent index construction, this analysis highlights how data science can uncover meaningful disparities hidden behind aggregate statistics.

---

## **Tools & Skills Demonstrated**
- Python (pandas, matplotlib)
- FRED API (macroeconomic data retrieval)
- Index construction & normalization
- Laspeyres price index theory
- Data visualization & economic storytelling
