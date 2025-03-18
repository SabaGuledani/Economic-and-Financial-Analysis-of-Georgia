# Analysis of different Economic and Financial fields of Georgia
I analyzed different statistics which were available on [geostat](https://www.geostat.ge/en). I **cleaned** the data, **normalized** it in some cases and engineered interested features. I tried to answer some questions which may be interesting for analysis. In particular, these questions were associated with GDP, exchange rates, inflation, CPI, unemployment and wages.
Using knowledge I gained from the book "Practical Statistics for Data Scientists" I plotted the results and got some insights on the available data.

## GDP 
We get few insights from this data:
- The overall GDP (both at market and basic prices) has been growing steadily from 2010 to 2024, indicating **economic expansion**.
- The sharp increase after 2020 suggests **accelerated growth**, which could be linked to *post-pandemic recovery*.

**GDP** Growth Across All Measures is also a good sign and can indicate few interesting points:
- **Market Price GDP Growth**: This component (*red* section) has expanded in recent years, suggesting stronger consumer activity and investment confidence.
- **Basic Price GDP Growth**: The core economic value (*blue* section) has shown stable increases, meaning the **underlying economy is strengthening**.
- **Per Capita GDP Growth**: The *purple* section is also rising, which means **individual economic well-being is improving**, not just total GDP.

![image](https://github.com/user-attachments/assets/fe3315f2-e17a-475e-88ad-5303b6d447f4)


Actual growth also showed that growth *Per capita* and *market* growth are on par and are almost the same every year. which suggests that
- Economic gains are **broadly distributed**
- Risk of **bubbles** is reduced
- **productivity and business expansion** are aligned with individual income growth, which supports **sustainable economic development**.
![image](https://github.com/user-attachments/assets/b59f3b27-4851-46bb-9c2d-07dd1bc77293)


Next question is, Which industries are the main contributors to Georgia's GDP?
as we see from the chart, wholesale and retail trades and auto repair industry's median is the highest in terms of contributions to GDP, next comes *real estate* and *manufacturing*.
![image](https://github.com/user-attachments/assets/39c2e0d5-fa6c-45b6-801d-ea2107c1bafd)

## Insights from Exchange Rate Analysis (USD/GEL)

![image](https://github.com/user-attachments/assets/23fc38bd-b995-4931-afcd-ea49deeceb5c)


Significant Depreciation of GEL is observed after 2014 - From 2010 to 2023, the Georgian Lari (GEL) has *depreciated* against the USD, rising from **~1.7 GEL/USD** in 2010 to **~2.6-3.3 GEL/USD** in recent years. this indicates potential economic and political factors which led to deprecation. 
2019-2022 period is stands out with **highes volatility rates**  which might be caused by *Covid-19 pandemic*, but The partial recovery in **2023** suggests **improving economic conditions or policy interventions**.

## Consumer Price Index

Georgia has **Dramatic** overall inflation trend. The *Consumer Price Index* in Georgia has **increased by approximately 175%** from 2004 to 2025, rising from around 100 to 285.
**Fastest** inflation rate(2020-2025) is observed after **plateau period**(2012-2016), which is also indication that covid pandemic was pretty harsh for Georgian citizens. The increase is **more than 25%**.

![image](https://github.com/user-attachments/assets/ef27c386-bcb2-42cd-93e1-bf17115c980b)

### Insights by Category

Here are insights by **Category** and change between 2004 and 2025.
![image](https://github.com/user-attachments/assets/c35bb56a-7d3f-427e-81b1-6d87300b760c)

![image](https://github.com/user-attachments/assets/c799e89b-5446-4d22-83ab-32f69e3a4211)

CPI analysis over categories shows that:
- *Alcoholic beverages and tobacco* experienced the most extreme price increases, nearly **quadrupling** in price over the period.
- *Food and non-alcoholic beverages* show the second-highest inflation rate, with prices **tripling** since 2004. 
- *Restaurants and hotels* demonstrate substantial price growth, reflecting increased costs in the service sector.
- *Clothing and footwear* with *communication* are the only categories showing **deflation**, with prices actually decreasing over the period. which likely reflects technological improvements and market competition. 
- **Basic necessities** (food, housing, health) have all seen significant price increases, creating potential hardship for lower-income households.

With CPI I also calculated monthly inflation rates and applied rolling mean of last **12 months**(1 year) which revealed that the monthly inflation rate shows **significant volatility**, frequently swinging between **+3%** and **-4%** month-to-month, but despite these sharp monthly fluctuations, the **12-month rolling average** (purple dashed line) reveals a more **moderate** underlying trend, typically ranging between **0%** and **1%**.
![image](https://github.com/user-attachments/assets/065d10d4-c304-4133-94f8-47cf0dc79563)

### Salaries and employment

particularly interesting topic is employment and question: do wages keep up with inflation rates?
Trying to find how was the situation in Georgia with employment I started from observing **unemployment rates** in Georgia by **region**. I got access to unemployment rates by regions and years and extracted 2023 data to csv file. I had to fill the data with Abkhazia's "N/A" value and used **GADM41** map as container for my data. here's the **unemployment rates in Georgia in 2023 by region**: 
![image](https://github.com/user-attachments/assets/982c6005-17b3-4cad-88e0-46ba2281f968)

The map reveals **significant unemployment disparities** across Georgia's regions, with rates ranging from approximately 8% to over 20%. There appears to be a **concentration of higher unemployment** in the central regions of Georgia. The **northwestern regions** (excluding Abkhazia, which shows no data) demonstrate lower unemployment rates. Capital, Tbilisi shows surprisingly high rates of unemployment. There may be many reasons to why is there such disparities in unemployment rates among the country, but still the map highlights the need for **regionally targeted economic development strategies**. 

#### Salaries

Back to the question: do wages keep up with inflation rates?
In a search for the answer, I found a data of the average nominal salaries ranging from 70s to present, but, in my opinion, *mean* is not quite right reflection of situation with salaries.
For this the best metric is *median*, which was sadly only available for 2018-2023 and showed that median is **significantly lower** than mean, which is the result of enormous gap between social groups in terms of salaries. I tried predicting median salaries for the years 2004-2018 using the data I had for 2018-2023. **scatterplot** showed that there could be some strong correlation between the median and the mean:

![image](https://github.com/user-attachments/assets/7c1d0793-a786-4340-a99a-24f6ee28973b)

I calculated and correlation is 0.99 which allowed me to construct *linear regression* model for predicting values before 2018. Predicted data looks like this:
![image](https://github.com/user-attachments/assets/f4cac34e-56f7-4d82-b5ed-b131846913e7)


which reveals that predicted median salaries were still very low over the years.
After that I calculated the adjusted real wages and inflation over years, then calculated growth rates for both and plotted the results: 
![image](https://github.com/user-attachments/assets/d42c5042-9322-4eec-9ca4-984e9f394876)

![image](https://github.com/user-attachments/assets/b0c76c06-6f4d-408b-9d07-3010d5765a16)

We can tell a lot about the situation in Georgia with these two charts, the main question that if wages keep up with inflation is **yes**, *but* there is much more to learn from the data:
##### wage patterns

- Georgia experienced **highly volatile wage growth** between 2005-2023, with dramatic fluctuations ranging from approximately -3% to +37%.
- The **most dramatic wage growth peak occurred in 2008** (approximately 37%), followed by a severe collapse to negative growth in 2009-2010, likely reflecting the impact of the global financial crisis.
- After 2010, wage growth became **more moderate but remained unstable**, showing several periods of negative growth (2010, 2017, 2020, 2021).
##### Real Wage Gains and Losses
- The second chart clearly illustrates **when wages outpaced inflation (green bars)** versus when inflation exceeded wage growth (red bars).
- **Substantial real wage gains** occurred in 2005-2008 and 2012-2013, with the largest positive gap in 2008 (over 30%).
- **Significant real wage losses** occurred in 2010, 2017, 2019, and 2021, with the worst periods being 2010 and 2021 (approximately -13% to -16%).

#### **Correlation with Other Economic Indicators**

- When viewed alongside the previous unemployment and CPI data, a more complete picture emerges:
    - Periods of *high* regional unemployment often correspond with *weaker* wage growth
    - The dramatic CPI increases seen in the *2021-2023* period align with the high inflation shown in these graphs
    - The recent stabilization in monthly inflation rates corresponds with the improving wage-inflation gap in 2023.

# Conclusion
It was very interesting project to work on, the data required significant engineering and I challenged myself to do everything with **python**, even though if I used excel for extracting data, it would be much easier to do everything. in the process I learned how to work with tables that are structured in a way to not be easily readable by **pandas**. how to **plot** the data I am interested in, using **Matplotlib** and how to analyze plots to see bigger picture
