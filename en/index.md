[Versión en Español](MicheleQuere.github.io/)

## ABOUT ME
Project Manager with a Data Analyst certification in progress.
My approach is not limited to managing tasks; it is about orchestrating workflows where data dictates the strategy and technology empowers the experience.

[quere.michele@gmail.com](mailto:quere.michele@gmail.com) | +52 55 5072 8230 | 
[www.linkedin.com/in/michelequere](http://www.linkedin.com/in/michelequere) | Mexico, CDMX

### Technical Skills

- Data Analysis and Management using:
Google Sheets | SQL | Python
- Data Visualization using:
Matplotlib | Seaborn | Tableau | PowerBI

### Soft Skills

Data analysis | Problem solving | Effective communication | Results orientation | Attention to detail

---

## Projects

## Operational Performance Analysis in the Lsstcorp Data Management Project

We took the **tawos_test_clean.csv** dataset downloadable here: [https://www.kaggle.com/datasets/rachetkhanal/tawos-csv-clean?resource=download](https://www.kaggle.com/datasets/rachetkhanal/tawos-csv-clean?resource=download) to choose one of the documented projects and perform a performance analysis on the selected project: Lsstcorp Data Management from 2014 to 2020. The final table contains Jira records from that project.

### Tools

Python | Pandas | Tableau

### Key Questions

- Was the delivery of the Lsstcorp Data Management project successful?
- What management improvements were implemented to keep the project on schedule?
- Did the main obstacles in this project lie in the team's capacity and execution, or in planning and governance deficiencies?

### Methodology

- Data was explored and the project was chosen based on the number of non-null entries, meaning the project with the highest number of complete records.
- Dates were standardized and it was decided to fill missing Story Points data with the median of the Story Points.
- SPI and CPI were calculated using cumulative work and estimation dates to calculate EV and PV. 16.8% of Estimation Dates were not recorded and 22.1% of actual effort time was also unrecorded.
- Overview and Detail Dashboards were created in Tableau to present conclusions.

### Conclusions and Recommendations

**Findings:**

- **The Great Battle for the Schedule (SPI):** The project started with a heavy delay in 2014 (SPI of ~0.4), suggesting that the initial linear planning was too aggressive for the startup phase or that the team took time to get up to speed. Project scope creep could have also expanded the work. However, the project did not stagnate: it shows a **constant and sustained annual recovery over 7 years**, managing to accelerate its pace year after year until closing exactly on time in 2020 with a perfect SPI of 1.0.
- **The Cost-Efficiency Paradox (CPI):** Contrary to the previous analysis, the project was **highly cost-efficient during most of its lifecycle (2015-2018)**, maintaining a CPI healthily above 1.0 (with peaks up to 1.15) when the team tripled. This demonstrates that the intermediate technical execution was extremely clean. The loss of efficiency (CPI < 1.0) occurred strictly in the final stretch (2019-2020), when team member numbers dropped again, dragging the historic cumulative figure to an acceptable 0.95 at closing.
- **The Real Impact of Scaling:** Tripling the team size (from 36 members in 2014 to 110 in 2019) **did work to rescue the schedule**. The headcount increase directly coincides with the SPI acceleration. However, towards the last two years, the classic effect of diminishing returns is observed: coordination costs and team complexity penalized the CPI, causing it to fall below 1.0 at the end.

**Recommendations:**

- It is suggested to define formal milestones from the beginning of the project, even if these vary throughout the project lifecycle, rather than waiting until year 5. Milestones force governance decisions, create natural checkpoints to review CPI and SPI deviations, and give leadership structured moments to intervene before low performance becomes chronic. A project that lasts 7 years without milestones lacks an early warning system. Perhaps the error is merely a matter of rigor in Jira documentation.
- Implicit tolerance for chronic deviations. Maintaining performance indices (CPI/SPI) just below 1.0 in a sustained manner hides planning inefficiencies and generates severe cumulative financial losses, even when technical execution is solid. Implement an automatic escalation protocol for stable linear variations. An early diagnosis focused on the calibration of estimations and the review of scope governance is suggested, avoiding the assumption that indicator stability exempts the project from a root cause review.
- More rigor in Jira documentation (or other project management software) is highly useful to analyze processes and see where the project gets out of control.

### Visualizations

Line chart to visualize the evolution of SPI and CPI over the duration of the project

![CPISPI.png](assets/CPISPI.png)

Burndown to review the number of story points completed per year (with dynamic granularity to filter by year)

![Burndown.png](assets/Burndown.png)

Pareto and Bar charts to visualize the total effort in hours by ticket type and team growth per year

![paretoTeam.png](assets/paretoTeam.png)

View on Tableau Public:

[Tableau repository lsstcorp DM](https://public.tableau.com/views/DashboardLsst/Overview?:language=es-ES&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

View the full repository on GitHub:

[full repository lsstcorp DM](https://github.com/MicheleQGF/lsstcorp_DM-TAWOS_test)

---

## RappiPlus Project

The objective of this project is to evaluate the performance of the **RappiPlus** service to support **data-driven business decisions**.

We work with multiple business datasets:

- **rappiplus_orders_raw.csv:** information on orders, prices, discounts, and revenue
- **rappiplus_catalog.csv:** product costs, categories, and vendors
- **rappiplus_marketing_spend.csv:** marketing investment by channel and country
- **events / users / user_activity (SQL):** user behavior within the platform
- **experiment_checkout_ui.csv:** results of an A/B experiment in the checkout

#### Tools

Python | Pandas | SQL | Tableau

### Key Questions

- Do users actually buy more?
- Is the model generating profits?
- Are opportunities being lost in the purchasing process?

### Methodology

- Data was cleaned and standardized, removing inconsistencies and verifying the absence of duplicates and missing values.
- A business profitability analysis was conducted: Total revenue, total cost, Marketing investment, and margin over costs and marketing were calculated. The average ticket per order, average number of products per order, and marketing spend per channel were also calculated, and the best-selling product was identified.
- A conversion funnel was built and a conversion analysis between each step was performed to find at which stage most users are lost. Subsequently, a cohort retention evaluation was carried out.
- A Chi-square test was used to analyze whether or not there was a difference between the two product variants.

### Conclusions and Recommendations

#### Findings:

- **Argentina is the engine of profitability:** Although it sells nearly the same as Mexico ($20.7M vs $19.7M), **Argentina delivers 76% of the total business profit** ($4.5M) with a spectacular margin of **21.73%**.
- **Tactical inefficiency in Mexico:** Mexico is the country where the most money is spent on Marketing ($988K), but it is the least profitable in the region, contributing just a **3.27% margin** ($645K in profit). We are burning the acquisition budget in the market that generates the lowest returns.
- **Extreme dependency on a low-margin product:** The *Laptop-Gaming-16GB* is a giant that sustains **83.7% of the total revenue** of the operation ($43.4M out of the $51.8M total). The problem is that its margin is highly penalized (**6.81%**). If the laptop supplier fails or changes prices, the entire business enters a loss.
- **Hidden gems without volume:** Phones, vacuums, and tablets (*Phone-Pro, Vacuum-Pro, Tablet-Standard*) record brutal profit margins **between 90% and 96%**, but their sales volumes are insignificant compared to the laptop.
- **The Checkout Wall:** The navigation flow is impeccable: more than 90% of users who interact add products and advance with a very high purchase intent. However, **the biggest bottleneck is the 13% abandonment at `add_payment_info`**. Users want the product, but they back out when the platform requests payment details.
- **Ironclad retention with a glass ceiling:** A retention rate that flattens out between 40% and 43% from week 1 to week 4 demonstrates that the product has a very solid *Product-Market Fit* among its recurring users. However, it is stagnant. New cohorts are not increasing their engagement over time, showing a flat onboarding.
- **A/B Testing, an irrelevant change:** With a p-value > 0.05, the Treatment variant (16.3% conversion) did not demonstrate real statistical superiority over the Control (15.7%). The sample of ~10,000 combined users confirms that the evaluated redesign or change does not move the needle for the business.

#### Recommendations:

- Immediately reduce marketing spend in Mexico (halt inefficient acquisition) and reallocate those funds to **Argentina** to boost the high-margin market (21.73%), and to **Colombia** to incentivize volume growth.
- We recommend pushing products like the Phone-Pro-128GB (96% margin) and the Vacuum-Pro-Black (94% margin). They currently have a healthy order volume but a minimal impact on total revenue due to their low price or lower turnover compared to laptops.
- Prioritize efforts to resolve the 13% drop-off on the payment screen. Bank rejection rates for debit/credit cards should be audited, form fields simplified, and alternative local payment methods enabled.
- Refocus the budget from generic retargeting campaigns to a system of **dynamic rewards and incentives**. Since retention flattens from week 1, it is suggested to grant increasing benefits/discounts conditioned on consecutive use.
- Rolling out the treatment variant is not recommended.

### Visualizations

Visualization designed to audit capital productivity. The chart demonstrates the disproportionate spend in Mexico (focused on *Social* and *Paid Search*) compared to a billing return that does not justify such proportionality relative to Argentina. It serves as irreversible analytical evidence to comply with the optimization directive: contract the inefficient budget and inject liquidity into the highest-yielding location.

![Treemap.png](assets/Treemap.png)

Analytical module designed to evaluate the health of the product mix. The data demonstrates that the current billing volume is fragile: 87% of revenue is concentrated in the Electronics category, which is severely impacted by the low operating margin of its main product, the *Laptop-Gaming* (6.8%). This section serves as irreversible analytical evidence to support a commercial shift: it is a priority to decelerate dependency on the leading line and design positioning campaigns for Home and Fashion products that offer returns exceeding 90% over cost.

![Barras.png](assets/Barras.png)

![Tabla.png](assets/Tabla.png)

Link to Tableau Public:

[Tableau Rappiplus Repository](https://public.tableau.com/views/Sprint12_ProyectoFinal/DashboardOverview?:language=es-ES&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

View full repository:

[full Rappiplus repository](https://github.com/MicheleQGF/ProyectoRappiPlus)

---

## Commercial Strategy for Andes Capital Real Estate

The company manages the sale of different types of properties through various sales channels and customer segments. The information exists at a transactional level, but the client seeks a clear analytical view of the business. An interactive dashboard in Power BI is created to achieve this using the following datasets:
**hecho_ventas_propiedades.csv**: fact table with sales information
**dim_clientes.csv**: table with customer segmentation information
**dim_propiedades.csv**: table with information on property type, category, size, and number of rooms

### Tools

Power BI

### Methodology

- With the help of Power Query, we checked for duplicates and null values. Data types were standardized.
- A dim_date table was created to enable time intelligence measures.
- The 3 tables were connected using property_id and client_id.
- Measures with filter context and measures for cohort analysis were created.
- Overview, Commercial Analysis, Sales Channel Detail, Property Type Detail, Buyer Segment Detail, Size and Number of Rooms, Sale Month Cohort, and Retention Cohort Dashboards were developed.

### Key Questions:

- What is the **total revenue** generated by property sales?
- What **type of property generates the most revenue**?
- Which **customer segments buy the most**?
- How do **sales evolve over time**?
- Is the business **growing year-over-year**?
- Do customers **buy again after their first purchase**?

### Key Findings

- Total revenue for the 2023-2024 period was 6,012.5 Million, generated by 8,500 sales.
- The type of property generating the highest revenue is houses, at 1,147 Million in 2024.
- Mexico City is the main revenue engine, at 1,704 Million in 2024.
- The Brokers channel sustains the commercial structure with 72.8% of billing.
- The Star Product for sales volume consists of 100.40 m² units with 2 and 3 bedrooms, which are the standard for highest turnover and liquidity in the current inventory.
- There is a stable 3% margin on commissions.

**Main Metrics**

- Total Revenue: 6,012.5 Million during 2023 and 2024
- Sales Volume: 8,500 sales during 2023 and 2024
- Average Ticket: 707,350 during 2023 and 2024
- Total Commission: 200,630 during 2023 and 2024

**Actionable Insights**

- There is a critical dependency on the "First-time" buyer, representing 62.9% of revenue but showing higher recurrence only in Commercial properties and Houses.
- There is a marked seasonality: Sales are dangerously concentrated in Autumn and Spring, suffering drops of up to 36% during winter and summer. This coincides with the closing of fiscal cycles and the payment of annual bonuses or profit-sharing in both regions for the first period; as a hypothesis, the massive transaction volume of apartments in Autumn (835 sales) suggests that families seek to secure their housing before the December festivities.
- The first-time buyer segment concentrates most of the revenue, but Investors and High Net Worth clients are more recurring.
- Customers acquired in the 2023 cohorts during the months of February, March, and April show higher recurrence.
- Sales show an 11.1% YoY growth. Although this growth is slowing down since the MoM trend line is downward.
- Customer retention appears more in the Direct Channel. Retention also exists among investor clients who buy houses and commercial properties. That is, customer retention is seen in High-value properties.

### Strategic Recommendations

- It is suggested to **Maintain Scale in the Broker channel:** It is the high-turnover engine. It is used to quickly clear standard inventory and maintain constant cash flow; this would mean continuing with the acquisition of apartments under 100 m² with 2 and 3 bedrooms for first-time buyers. Likewise, it is necessary to **Boost Profitability in the direct channel:** It is the exclusive channel for the "Premium Program." By not paying external commissions, it protects the 3% margin and captures higher tickets free from massive competition.
- The second interesting scenario involves units over 200 m²; they are free from competition from the massive "First-time" buyer, being an exclusive territory for Investors, which grew by $128 million and carries a higher average ticket, especially for Commercial types. A dynamic portfolio diversification is needed to capture these types of properties and increase the portfolio of this type of buyer.
- Implement a Premium Loyalty Program, meaning a benefit scheme for "Frequent Investors" based on the behavior observed in cohorts buying properties under 100 m², incentivizing the purchase of a second and third unit. This plan would also seek to incentivize more recent cohorts (2024) to return to buy.
- This Premium Loyalty program could be offered more aggressively during summer and winter with a view to stabilizing seasonal decline during these times of the year.

### Visualizations

Below is a demonstration video of the interactive dashboard created in PowerBI:
<video src="assets/Andescapvideo.mp4" controls width="100%" poster="assets/2026-05-27 10_39_55-Proyecto10_MicheleQuere.png"></video>
