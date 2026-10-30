Introduction

I built a new dashboard from a used car dataset to answer a simple question: what really decides how much a car is worth, and where does a dealership’s money come from? Age drives value more than anything else, brands are priced by badge and engine and not by wear, and the models that fill the lot are not the ones that earn the most.

The dataset at a glance

49,988 cars listed (50,000 rows in the raw file, 12 duplicates removed)
11 columns after cleaning (7 original and 4 that I added)
5 manufacturers: Ford, VW, Toyota, BMW and Porsche
15 models, built between 1984 and 2022
3 fuel types: Petrol, Diesel and Hybrid
Total listed value: $691,500,855
Average price per car: $13,833.34
Top revenue model: Toyota RAV4, with $83,407,168 in listed value

Data Story
This dataset covers the used car market, with 49,988 cars listed at a total value of $691.5 million and an average price of $13,833. The cars come from 5 manufacturers and 15 models, and they split almost evenly into three eras: Old (1984 to 1998), Classic (1999 to 2009) and Modern (2010 to 2022). At the top end sits the BMW M5, with an average price of $39,911. At the bottom sits the Ford Fiesta at $7,198. For me, the story is about knowing what a car is worth today, and what drives that worth.

Data Tool and Source
Tool: Microsoft Excel (Tables, PivotTables, PivotCharts, slicers, KPI cards, dashboard)
Source: https://www.kaggle.com/datasets/youssefmahdyabosaleh/car-sales-data

Data Cleaning Process

Checked for blank cells and found none.
Checked for duplicate rows and found 12. I removed them, which took the data from 50,000 rows to 49,988.
Renamed the model “911” to “911 Sports Car” so it reads clearly on the charts (872 rows).
Checked the ranges: years 1984 to 2022, engine sizes 1.0L to 5.0L, prices from $76 to $168,081, and mileage from 630 to 453,537 miles. Nothing was impossible.
Converted the range to an Excel Table so every PivotTable reads from one source.
Added four columns to help the analysis:
Vehicle Age: 2026 minus the year of manufacture
Average Miles Per Year: mileage divided by vehicle age
Era: Old (1984 to 1998), Classic (1999 to 2009) or Modern (2010 to 2022)
Mileage Status: High (about 100,000 miles or more) or Low
7. Grouped vehicle age (in 5-year groups) and engine size (in 1-litre groups) so trends are easy to read.
8. Sorted the groups in the right order, because Excel sorts them alphabetically by default.

Columns Within the Data
Car: Manufacturer, Model, Engine Size, Fuel Type.
Age: Year of Manufacture, Vehicle Age, Era.
Usage: Mileage, Average Miles Per Year, Mileage Status.
Value: Price.

Pre-Analysis

Splitting the data
Dependent variables (what I measure): Price, Mileage, Average Miles Per Year.
Independent variables (what might cause change): Manufacturer, Model, Engine Size, Fuel Type, Year of Manufacture, Vehicle Age, Era, Mileage Status.
Industry type: this industry belongs to the Automotive Resale (Used Car Market) industry, which uses sales data to decide what to buy, how to price it and how fast to sell it.

Stakeholders: purchasing managers, sales directors, dealership owners and investors, finance and inventory teams, and the buyers themselves.

What success means to the industry: success in the used car market means buying cars at the right price, pricing them to sell, and keeping money from sitting in stock that loses value. It means knowing which cars hold their value, which models bring in the most money and which sell the most, so that the right cars are on the lot at the right price. It also means selling quickly, because every year a car sits it loses value, and keeping a healthy mix of high-volume everyday models and higher-value ones.

My 8 Potential questions
Which era has the highest average price?
How much does the average price fall as cars get older?
Do older cars get driven more or less each year?
Does a bigger engine mean a higher price?
Which manufacturer supplies the most Modern stock?
Do some brands wear their cars harder?
Which models bring in the most total sales value?
Which models are listed most often?

In-Analysis

This was done after the cleaned data was turned into PivotTables and charts, one for each of my pre-analysis questions. I looked at each chart on its own to see what it shows and what it means before putting them on the dashboard.

1. Average Resale Price by Era
   <img width="751" height="451" alt="image" src="https://github.com/user-attachments/assets/405e672e-0844-41fe-8d7a-33cb6decf5cb" />

Observation: Modern cars average $29,120, Classic $8,949 and Old $2,721. Each era holds about a third of the cars (34.1%, 33.8% and 32.1%).

Insight: Modern is 3.3 times the price of Classic and 10.7 times the price of Old. Since the numbers of cars are almost equal, the gap is about price per car, not volume. Modern cars are 34% of the stock but hold 71.8% of the total value. The same gap (about 3.2 times) appears in every manufacturer.

2. Average Price by Vehicle Age Group
   <img width="815" height="443" alt="image" src="https://github.com/user-attachments/assets/fac3303b-5a17-481f-929a-15cb8c4ac6ab" />

Observation: the average falls from $42,613 (4–8 years) to $27,458, $16,460, $9,504, $5,625, $3,230, $1,929 and $1,201 (39–43 years).

Insight: cars lose about 35% to 43% of their value every 5 years, roughly 10% to 12% a year. The drop is steady, with no single cliff. In dollars the loss is biggest early: about $5,700 a year at ages 4 to 8, falling to about $1,500 a year at ages 16 to 20.

3. Average Yearly Mileage by Vehicle Age
   <img width="750" height="450" alt="image" src="https://github.com/user-attachments/assets/7d060d5b-a48d-462b-a72e-abba6cac65f1" />


Observation: yearly mileage rises from 3,197 miles (4–8 years) to 4,311, 4,864, 5,120, 5,286, 5,418, 5,493 and 5,534 (39–43 years).

Insight: older cars are driven 73% more miles per year than the newest ones, but the rise slows and levels off at about 5,500 after roughly 20 years. Older cars aren’t parked up. They keep working. Together with chart 2, price falls about 40% every 5 years while yearly mileage rises.


4. Average Price by Engine Size
   <img width="626" height="355" alt="image" src="https://github.com/user-attachments/assets/93d8cc05-1197-444b-9dcd-5a483abd85e1" />

Observation: prices are $10,751 (1–2L, 33,918 cars), $16,514 (2–3L), $26,170 (3–4L, 1,775 cars) and $36,885 (4–5L, 2,176 cars).

Insight: the biggest engines cost 3.4 times the smallest. Engines of 3L and above exist only in BMW and Porsche, so brand and engine overlap. Even inside one brand, bigger engines cost more: Toyota +57% (1–2L to 2–3L), Ford +34%, VW +20%, and BMW rises from $16,062 (2–3L) to $39,911 (4–5L). Porsche is the exception. The average age is about the same across engine groups (21.5 to 21.9 years), so age doesn’t explain it.

5. Share of Modern Stock by Manufacturer
   <img width="750" height="397" alt="image" src="https://github.com/user-attachments/assets/bca9cbc5-d524-4a30-a333-0cfd6007f97c" />

Observation: among 17,060 Modern cars, Ford holds 29.82%, VW 29.06%, Toyota 25.77%, BMW 9.92% and Porsche 5.43%.

Insight: three volume brands make up 84.65% of the Modern stock. Premium brands add only 15%. Every brand is about a third Modern (33.3% to 35.5%), so no brand has noticeably newer stock.

6. Average Mileage by Manufacturer
   <img width="750" height="431" alt="image" src="https://github.com/user-attachments/assets/313147f9-817e-4261-8df1-96bd3b672d49" />

Observation: VW averages 113,511 miles, BMW 112,858, Ford 112,525, Porsche 111,628 and Toyota 111,369.

Insight: the gap from top to bottom is only 1.9%. Wear is the same across brands, so price differences between brands come from brand, engine size and age, not from how hard the cars were driven.


7. Top 5 Models by Sales Value
   <img width="750" height="450" alt="image" src="https://github.com/user-attachments/assets/afe2b753-51f5-4899-ab5e-5a5fae1bff7e" />

Observation: RAV4 $83.4M (12.1% of all listed value), M5 $65.7M, Mondeo $65.5M, Passat $62.8M and Focus $58.6M. Together they hold $336.0M, or 48.6% of the total.

Insight: value is price times volume. RAV4 earns the most even though it is only 7th by number of cars (4,292), because it averages $19,433. The M5 is 11th by count (1,645) yet 2nd by value, at an average of $39,911.


8. Top 6 Models by Cars Listed
   
   <img width="528" height="415" alt="image" src="https://github.com/user-attachments/assets/1c191e14-c7b5-4b46-9267-6e63ada387c8" />

Observation: Mondeo 5,057, Golf 5,049, Polo 4,988, Focus 4,975, Fiesta 4,924 and Passat 4,869. Only 188 cars separate first from sixth. Together they are 29,862 cars, or 59.7% of all listings.

Insight: the six most-listed models are three Ford and three VW, and they are listed in almost equal numbers. Volume doesn’t mean value: Polo and Fiesta are among the most listed but rank 8th and 10th by sales value.

Post-Analysis

After putting the charts together, I read the dashboard as one picture and checked the patterns again within each manufacturer. A few points come from extra checks on top of the charts (fuel type, mileage status and the within-brand comparisons).

1. The value sits in younger cars.

Observation: cars aged 4 to 13 years are only 24.7% of the stock but hold 59.5% of the total listed value. Modern cars are 34% of the cars and 71.8% of the value.

Insight: a dealership’s money is in young stock. Old cars (over 24 years) add almost nothing: 6.3% of value from the Old era.

2. Cars lose value steadily, not suddenly.

Observation: every 5-year step costs 35% to 43% of the price, and the pattern is the same in all five manufacturers (the first drop is 34% to 36% in each).

Insight: there is no single “sell by” year. What changes is the dollars lost: roughly $5,700 a year for a 4-to-8-year-old car, against about $1,500 for a 16-to-20-year-old. The cost of holding stock is highest when the car is youngest.

3. Price follows brand, engine and age, not wear.

Observation: brands drive almost the same mileage (1.9% gap) and show the same yearly-mileage curve at every age, yet average prices differ a lot: Porsche $29,185, BMW $24,432, Toyota $14,341, Ford $10,671, VW $10,362.

Insight: buyers pay for the badge, engine size and age, not for how much a brand’s cars have been used.

4. Premium brands punch above their weight.

Observation: BMW and Porsche are 15.1% of cars but 28.5% of listed value. Ford and VW are 59.7% of cars but 45.4% of value.

Insight: volume brands fill the lot, and premium brands lift the value. The business needs both.

5. Volume is not value.

Observation: only three models appear in both the top 5 by value and the top 6 by volume (Mondeo, Passat and Focus). RAV4 and the M5 earn the most with fewer cars, while Polo and Fiesta have many cars but low value.

Insight: counting cars hides where the money is. Models should be judged on both volume and value.

6. Cars are used more as they age, then it levels off.

Observation: yearly mileage climbs from 3,197 to about 5,500 and flattens after about 20 years, in every brand.

Insight: older cars are not low-use bargains. Part of why they cost less is that they are driven more each year.

7. Hybrids carry a small premium but are not growing in this data.

Observation: Petrol is 50.97% of the cars, Diesel 26.53% and Hybrid 22.49%. Hybrids average $14,949, against $13,699 for Petrol and $13,146 for Diesel, and they cost more in every era (about 7% to 10% over Petrol). The Hybrid share stays flat across eras (22.1% to 23.0%). There are no electric cars.

Insight: the data doesn’t show hybrids growing. It only shows a steady price premium.

8. Mileage status mostly tracks age.

Observation: High-mileage cars average $4,410 against $23,442 for Low-mileage cars, but 90% of Old cars are High-mileage compared with 3.6% of Modern cars.

Insight: the price gap here is mostly the age gap, so it can’t be used alone to price a car.

Overall Recommendation

Put most of the buying budget into cars aged 4 to 13 years (purchasing managers). They are a quarter of the stock but nearly 60% of the value.

Sell young stock quickly (sales directors). A 4-to-8-year-old car loses about $5,700 a year, far more than an older one. Review the age of stock regularly and discount early where needed.

Use an age-based price guide (sales and pricing teams). Expect roughly 10% to 12% depreciation a year, and about 40% every 5 years, in every brand.

Keep the high-value models stocked (purchasing managers): RAV4, M5, Mondeo, Passat and Focus brought in 48.6% of the listed value.

Keep the volume base (sales directors). Ford and VW fill 59.7% of listings and keep the lot moving. Don’t let the premium brands crowd them out.

Grow premium stock carefully (investors and owners). BMW and Porsche earn about double their share of cars, but they are only 15% of Modern stock, so test small increases before shifting the budget.

Price engine size inside each brand (pricing teams). Bigger engines add 20% to 57% within a brand, so don’t compare engines across brands.

Don’t price by brand mileage (pricing teams). Brand averages are almost the same, so use each car’s own age and mileage.

Price hybrids at a small premium (sales directors), about 7% to 10% over the Petrol version, but don’t plan a big shift into hybrids based on this data.


Conclusion

Going into this project, I expected a few things to be obvious: that big engines cost more, that old cars are cheap, and that the most common models earn the most. The data confirmed the first two, and then surprised me on the third. Age is the biggest driver of value, cars lose about 40% of their price every 5 years, and the models that fill the lot are not the ones that earn the most. Brands are priced by their badge and engine and not by how hard their cars have been driven. For a dealership, the message is clear: spend on younger stock, sell it while it is still worth the most, and judge models by both volume and value.





