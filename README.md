# 💳 Revolut Spending Analysis

## 📌 Project Overview  
This project analyzes **Revolut card spending patterns** between **Jan 2020 – Jun 2023**.  
Using transaction-level data across **age groups, spending categories, and online usage**, I explored how spending evolved over time and applied **forecasting model (Holt-Winters)** to predict future trends.  

The goal: **to understand customer behavior, seasonal spending patterns, and future growth trends**.

---

## 📂 Dataset Description  

The dataset consists of **three sheets** (daily data):  

1. **Spending by age**  
   - Columns: `Date`, `Total`, `18-34`, `35-54`, `55+`  
   - Shows daily total spend and breakdown by age group.  

2. **In-store v Online**  
   - Columns: `Date`, `Online`, `Instore` (percentages)  
   - Shows how much spending was online vs physical stores.  

3. **Spending by sector**  
   - Columns: `Date`, `Total`, `Automotive Fuel`, `Entertainment`, `Food & Drink`,  
     `Pubs,restaurants and fast food`, `Retail`, `Travel and accommodation`  
   - Shows daily spend across major categories.  

---

## 🔧 Data Preprocessing  

- ✅ **Checked for duplicates & null values** → none found (ensures clean dataset).  
- ✅ **Parsed dates into `datetime` format** → makes it easy to group by month/year/weekday.  
- ✅ **Set `Date` as index** → simplifies time-series analysis.  
- ✅ **Merged sheets** into one **master dataset** → easier for cross-analysis.  
- ✅ **Extracted Month & Weekday from Date** → enables monthly and weekly trend analysis.  
- ✅ **Grouped data by Month-Year** → calculated **average spending per calendar month** for clear visualization.  

---

## 📊 Analysis & Visualizations  

### 1️⃣ Monthly Spending Trends  
- Spending dipped sharply in **Apr–May 2020** (COVID impact).  
- Strong recovery and **steady growth from mid-2020 to 2023**.  
- Seasonal spikes around **end-of-year holidays**.  
- Overall, **spending increased significantly year-over-year**.  

📈 *Graph: Monthly Spending Line Chart*  

---

### 📊 Daily Spending Across Sectors  

This visualization explores how daily spending evolved across categories such as **Automotive Fuel, Entertainment, Food & Drink, Pubs/Restaurants/Fast Food, Retail, and Travel & Accommodation**. Each sector reveals a unique pattern shaped by seasonality, consumer behavior, and external shocks like COVID-19.  

#### ⛽ Automotive Fuel Spending  
- **Mid-year spikes:** A consistent rise in spending is observed between **July and August** each year, showing a seasonal peak in fuel usage.  
- **Late-year decline:** After August, spending typically **drops steadily until December**.  
- **December rebound:** In December, there is often a **slight increase** again, possibly due to holiday travel.  
- **Overall trend:** Automotive Fuel shows a **gradual upward trend across the years**, reflecting recovery post-pandemic and increased mobility.  

#### 🎭 Entertainment Spending  
- **Early decline:** Spending dropped sharply at the **start of 2020**, likely due to COVID-19 restrictions on entertainment activities.  
- **Volatile pattern:** After the dip, spending shows **frequent ups and downs**, reflecting the discretionary and event-driven nature of entertainment.  
- **Gradual recovery:** Despite fluctuations, there is a **slow upward trend across the years**, but no strong long-term trend.  
- **Key insight:** Entertainment spending is less stable, highly sensitive to external factors like restrictions and holidays.  

#### 🍽️ Food and Drink Spending  
- **Stable and resilient:** Food and Drink remained **strong during early 2020**, topping all sectors in spending.  
- **Consistency:** Spending stayed relatively **constant with only small ups and downs**, highlighting its essential nature.  
- **Slight upward trend:** Shows a **gradual increase year-over-year**, indicating rising food-related expenditure.  
- **Seasonal peaks:** Clear **spikes in December** each year, tied to the holiday season.  
- **Key insight:** Food and Drink is the **most stable sector**, with consistent demand even during uncertainty.  

#### 🍔 Pubs, Restaurants, and Fast Food Spending  
- **Initial decline:** A **sharp drop in early 2020**, due to COVID restrictions on dining and social activities.  
- **Seasonal spikes:** Spending often **peaks around August–September**, reflecting holidays and dining out.  
- **Year-end decline:** Drops significantly towards year-end, showing a consistent seasonal pattern.  
- **Overall trend:** Despite fluctuations, the **general trend is steady**, without strong long-term growth.  
- **Key insight:** Highly **seasonal and event-driven**, strongly influenced by holidays and restrictions.  

#### 🛍️ Retail Spending  
- **Early decline:** Retail spending fell during **early 2020 lockdowns**.  
- **Strong rebound:** Quickly became the **top spending category** after restrictions eased.  
- **Seasonal spikes:**  
  - **Heavy peaks in August–September** (back-to-school, seasonal sales).  
  - **Smaller spike in December** (holiday shopping).  
- **Overall trend:** Retail shows a **clear upward trajectory**, cementing its dominance.  
- **Key insight:** Retail is a **major driver of overall growth**, resilient and tied to consumer shopping cycles.  

#### ✈️ Travel & Accommodation Spending  
- **Severe initial drop:** Spending almost disappeared during **early 2020** due to global travel bans.  
- **Temporary mid-year spike:** A short-lived increase in **Aug–Sep 2020** during partial reopening.  
- **Gradual recovery:** From **mid-2021 (May)** spending began to rise steadily.  
- **Sudden spike:** A strong surge in **October 2021**, but not sustained.  
- **Stabilization:** After 2021, spending remained **relatively stable with minor ups and downs**.  
- **Key insight:** The most **volatile sector**, directly tied to global events and restrictions.  

➡️ Together, these trends show how different spending categories **react differently to global shocks, seasonal cycles, and consumer behavior** — with **Retail and Food & Drink driving stability**, while **Travel and Entertainment remain the most sensitive sectors**.


---

### 📆 Average Monthly Spending Trends Across Categories  

This graph tracks **average monthly spending** across different categories from **January 2020 to June 2023**, giving a clearer view of long-term seasonality and category growth.  

#### ⛽ Automotive Fuel  
- Experienced a **sharp dip in early 2020** due to COVID-19 mobility restrictions.  
- Clear **summer spikes (July–August)** each year, showing seasonal travel patterns.  
- Overall, fuel spending has a **strong upward trajectory**, peaking in mid-2022 before stabilizing slightly higher than pre-pandemic levels.  

#### 🎭 Entertainment  
- Dropped significantly in early 2020 as lockdowns limited entertainment options.  
- Shows **small peaks and troughs**, reflecting its discretionary nature.  
- Over time, entertainment spending **gradually increased**, but remains lower compared to other categories, suggesting slower recovery.  

#### 🍽️ Food and Drink  
- The most **stable category** across the timeline, even during COVID-19.  
- Maintains a **steady baseline demand** as food is an essential expense.  
- Displays **seasonal spikes in December**, likely due to holiday gatherings and celebrations.  
- Slightly increasing over time, but with less volatility compared to other sectors.  

#### 🍔 Pubs, Restaurants, and Fast Food  
- Severely impacted in early 2020, dropping to its lowest point.  
- Gradual recovery followed by **consistent mid-year spikes (August/September)**.  
- Still shows significant **fluctuations year to year**, but the overall trend is **upward**.  

#### 🛍️ Retail  
- After the initial dip in 2020, retail became a **leading sector in spending growth**.  
- Clear **peaks in August–September** (likely due to seasonal/back-to-school shopping).  
- Smaller but visible **spikes in December** due to holiday shopping.  
- Overall, retail shows the **most consistent upward trend** across the years.  

#### ✈️ Travel & Accommodation  
- Suffered the **steepest drop in early 2020** as global travel shut down.  
- Gradual recovery starting in **mid-2021**, reflecting reopening and travel resumption.  
- Shows seasonal spikes, particularly in summer months, but overall spending **remains lower than pre-COVID peaks**.  

---

➡️ **Key Insight:**  
Across categories, **Retail and Automotive Fuel** show the strongest recovery and growth, while **Food & Drink** remains steady as an essential expense. **Travel & Accommodation** and **Entertainment** were most disrupted by COVID-19, but are slowly stabilizing. Seasonal spending patterns — especially in **summer (Aug/Sept)** and **December holidays** — remain consistent drivers across all categories.  
 

---

### 👥 Average Monthly Spending Trends by Age Category  

This graph shows how Revolut spending trends differ across three age groups — **18–34**, **35–54**, and **55+** — from **January 2020 to June 2023**.  

#### 🔵 Age 18–34  
- After an initial dip in early 2020 (COVID-19 period), this group shows the **strongest and most consistent upward trend**.  
- Spending steadily rises month by month, with a few seasonal fluctuations.  
- By 2023, this age group becomes the **largest contributor to overall spending**, indicating their growing dominance in Revolut’s customer base.  

#### 🟠 Age 35–54  
- Similar to the 18–34 group, spending dropped significantly in early 2020.  
- Shows **moderate growth** with several peaks (notably mid-2021 and mid-2022).  
- Spending levels remain high but consistently **below the 18–34 group**.  

#### 🟢 Age 55+  
- This group experienced the **steepest decline during COVID-19** and recovered more slowly.  
- Spending has been relatively **stable with small growth**, but it lags behind the younger age groups.  
- Indicates that older users are **less active spenders** on Revolut compared to younger groups.  

---

➡️ **Key Insight:**  
Younger users (18–34) are driving Revolut’s growth with steadily rising monthly spending, while middle-aged users (35–54) also contribute strongly but at a lower level. Older users (55+) spend significantly less, highlighting a potential growth opportunity if Revolut can increase adoption in this segment.  


---

### 📊 Average Monthly Spending  

This chart shows the **average spending per month** across all users and categories.  

- **Lowest Spending:** June records the lowest average spend (~93.7), showing a seasonal dip in mid-year.  
- **Steady Growth:** From July onwards, spending gradually increases.  
- **Peak Spending:** August and December stand out with the **highest spending levels (~115.7)**.  
  - **August** may reflect summer holidays and increased leisure activities.  
  - **December** aligns with festive shopping and holiday season spending.  

➡️ **Key Insight:**  
Spending patterns show clear seasonality, with **holiday months (August & December)** driving the highest expenses, while **mid-year months (April–June)** tend to be lower. This seasonal behavior can help in forecasting peak transaction volumes and resource planning for Revolut.  
 

---

### 👥 Average Monthly Spending by Age Category  

This chart compares **monthly spending patterns across age groups (18–34, 35–54, 55+)**.  

- **18–34 age group**:  
  - Consistently the **highest spenders** across all months.  
  - Shows sharp increases in **August, November, and December**, likely tied to holidays and seasonal activities.  
  - Peaks in **December**, reflecting strong year-end spending.  

- **35–54 age group**:  
  - Moderate spending compared to younger users.  
  - Exhibits seasonal spikes, especially in **August and December**, though at lower levels than the 18–34 group.  

- **55+ age group**:  
  - Lowest spending overall.  
  - More stable month-to-month with fewer spikes, suggesting **steady but conservative spending habits**.  

➡️ **Key Insight:**  
Younger Revolut users (18–34) drive the **largest share of monthly spending**, while older groups (55+) maintain steadier, lower spending patterns. Seasonal peaks (summer and year-end) are consistent across all age groups, but the magnitude of spending is much stronger among younger users.  
  

---

### 📊 Average Monthly Spending by Sector  

This chart shows how average monthly spending is distributed across different sectors:  

- **Automotive Fuel** 🚗:  
  - Strong seasonal variation, peaking sharply in **August**.  
  - Reflects higher travel and fuel demand during summer months.  

- **Retail** 🛍️:  
  - Consistently the **highest spending sector** throughout the year.  
  - Peaks in **December**, driven by year-end shopping and holiday sales.  

- **Food and Drink** 🍔🥤:  
  - Steady spending across the year with small fluctuations.  
  - Noticeable rise during **August and December**, possibly tied to holidays and social events.  

- **Pubs, Restaurants, and Fast Food** 🍻🍕:  
  - Moderate spending with a **strong peak in August**, likely due to vacations and outings.  
  - Declines afterward but remains consistent month to month.  

- **Entertainment** 🎬🎮:  
  - Lowest category overall.  
  - Shows some seasonal variation, but remains relatively flat compared to other sectors.  

- **Travel and Accommodation** ✈️🏨:  
  - Seasonal spikes, especially in **August**, aligning with vacation periods.  
  - Drops back in non-travel months but remains steady otherwise.  

➡️ **Key Insight:**  
Spending patterns are strongly seasonal. **Retail and Automotive Fuel dominate overall spending**, while **Travel and Food-related sectors spike during holidays and summer months**, highlighting the influence of **vacations and festive seasons** on consumer behavior.  
  

---

### 🛒 Instore vs Online Spending  

The pie chart shows the **average spending split** between Instore and Online purchases:  

- **Instore Spending**: 57.3%  
- **Online Spending**: 42.7%  

➡️ **Key Insight:**  
Consumers spend **more in physical stores than online**, with instore spending making up the **majority share**.  
However, the **online spending share (42.7%) is significant**, reflecting the growing adoption of digital transactions and e-commerce alongside traditional shopping.  
 

---

### 👥 Total Spending by Age Category  

This bar chart shows the **cumulative spending across different age groups**:  

- **18–34 years**: 148,341.1  
- **35–54 years**: 121,591.3  
- **55+ years**: 93,150.1  

➡️ **Key Insight:**  
- The **18–34 age group** spends the most overall, highlighting their strong contribution to Revolut’s transaction volumes.  
- The **35–54 group** follows as the second highest spenders, likely driven by stable income and family-related expenses.  
- The **55+ age group** spends the least in total, suggesting a more conservative spending pattern compared to younger users.  

This breakdown helps identify **which demographics drive Revolut’s revenue**, with younger users leading the way.   
 

---

### 🛍️ Total Spends in different Categories  

This bar chart highlights the **cumulative spending across different sectors**:  

- **Retail**: 168,122.9  
- **Automotive Fuel**: 153,822.9  
- **Food & Drink**: 146,025.5  
- **Travel & Accommodation**: 105,560.7  
- **Pubs, Restaurants & Fast Food**: 96,477.5  
- **Entertainment**: 72,616.8  

➡️ **Key Insights:**  
- **Retail dominates** as the largest category, showing that day-to-day shopping and consumer goods make up the bulk of Revolut card spending.  
- **Automotive Fuel** and **Food & Drink** are also significant contributors, reflecting essential daily needs.  
- **Entertainment** accounts for the smallest share, suggesting that discretionary spending in this category is relatively low compared to essentials.  

This breakdown provides a **clear picture of consumer priorities**: essential needs (retail, food, transport) take the top spots, while leisure categories rank lower.  
 
 
---

### 📅 Last Month’s Spending Breakdown (May 2023)

This chart shows the **distribution of spending across categories for the final month of available data (01 May 2023 – 31 May 2023):**

- **Retail**: 189.23  
- **Automotive Fuel**: 162.72  
- **Food & Drink**: 150.38  
- **Travel & Accommodation**: 137.26  
- **Pubs, Restaurants & Fast Food**: 120.78  
- **Entertainment**: 93.27  

➡️ **Key Insights:**  
- **Retail spending dominated** the last month, continuing its position as the top category.  
- **Automotive Fuel and Food & Drink** remained strong contributors, showing consistent demand for essentials.  
- **Entertainment once again ranked lowest**, highlighting that leisure spending was comparatively subdued.  
- Compared to earlier months, this snapshot reflects a **stable spending pattern**, with essential categories consistently leading.    
 
---

## Holt-Winters Forecast (Additive)

The Holt-Winters Exponential Smoothing model was applied to forecast future Revolut spending patterns.

- The **blue line** shows the actual monthly spending data from January 2020 to June 2023.  
- The **red line** represents the Holt-Winters forecast for the upcoming months.  

### Findings
- The model successfully captures the **steady upward trend** in Revolut spending.  
- Seasonal behaviors such as **holiday spikes and mid-year increases** are reflected in the forecast.  
- Future spending is expected to remain strong, fluctuating around **170–180 units on average**, highlighting both **trend continuation** and **seasonal stability**.


---

### 📊 Hypothesis Testing: Yearly Spending Trend

- **H₀ (Null Hypothesis):** There is no relationship between year and total spending (slope = 0).  
- **H₁ (Alternative Hypothesis):** There is a significant positive relationship between year and total spending (slope > 0).  

**Regression Results:**  
- Coefficient (Year): **22.7** → Spending increases by ~22.7 units each year.  
- p-value = **0.011** (< 0.05) → Statistically significant.  
- 95% Confidence Interval: **[12.5, 33.0]**  
- R² = **0.979** → 97.9% of the variation in spending is explained by the year.  

✅ **Conclusion:** Since p < 0.05, we reject H₀. This means Revolut spending is significantly increasing every year. The growth is consistent and highly predictable, not due to random variation.

 

