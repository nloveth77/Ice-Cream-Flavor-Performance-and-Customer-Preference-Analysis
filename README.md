
# Ice-Cream-Flavor-Performance-and-Customer-Preference-Analysis

Introduction

This analysis examines customer preference data for various ice cream product offerings across key qualitative attributes (flavor profile, base ingredients, consumer preference) and quantitative evaluation metrics (Flavor Rating, Texture Rating, Overall Rating, Total Rating).  Additionally, temporal rating shifts across consecutive days are tracked to understand rating consistency and variance over time.




Objective

Evaluate flavor and texture performance across different base flavor categories (Vanilla vs. Chocolate).
Quantify customer sentiment (“Liked” status: Yes/No) and identify high-performing versus underperforming flavor variants.
Examine multi-attribute aggregate performance metrics (mean, max, sum, count) for texture and flavor ratings.
Monitor daily trend changes in ratings from 1/1/2022 to 1/7/2022 to detect stability and variance patterns.






<img width="1815" height="867" alt="ChatGPT Image Sep 29, 2026, 03_20_08 AM" src="https://github.com/user-attachments/assets/43a83c4e-f608-4899-b720-3e5088f30d33" />






Data Structure

The notebook processes two primary datasets:

Dataset 1: Product Flavors Performance (Flavors (1).csv)

Size / Grain: 9 unique ice cream flavor records.

Fields & Types:

Flavor (String / Categorical): Name of specific ice cream (e.g., Mint Chocolate Chip, Vanilla, Pistachio, Chocolate).

Base Flavor (String / Categorical): Underlying category (Vanilla or Chocolate).

Liked (String / Binary Categorical): Customer preference indicator (Yes / No).

Flavor Rating (Continuous Numeric, 0.0–10.0 scale): Customer taste score.

Texture Rating (Continuous Numeric, 0.0–10.0 scale): Customer mouthfeel/texture score.

Total Rating (Continuous Numeric): Calculated score (Flavor Rating + Texture Rating).


Dataset 2: Time-Series Ice Cream Ratings (Ice Cream Ratings (1).csv)

Size / Grain: 7 daily snapshot entries indexed by date (1/1/2022 to 1/7/2022).

Fields & Types:

Date (Date / Index): Daily observations.

Flavor Rating (Float): Normalized score.

Texture Rating (Float): Normalized score.

Overall Rating (Float): Normalized composite score.







<img width="1671" height="941" alt="ChatGPT Image Sep 28, 2026, 05_16_24 AM" src="https://github.com/user-attachments/assets/78a54d02-b411-4a70-9592-e28a9b2259af" />








Dependent and Independent Variables

Dataset 1: Product Flavor Analysis

Independent Variables:

Base Flavor (Vanilla, Chocolate)

Flavor (Individual product name)


Dependent Variables:

Flavor Rating

Texture Rating

Total Rating

Liked (Yes / No classification outcome)


Dataset 2: Temporal Rating Dynamics

Independent Variable: Date

Dependent Variables: Flavor Rating, Texture Rating, Overall Rating




Pre-Analysis Board

Before running aggregated groupings or visualizations, initial raw observations reveal:

Data Completeness: 9 complete rows in dataset 1, with zero missing values observed across columns.

Base Flavor Distribution: Imbalanced split — 6 Vanilla-based flavors versus 3 Chocolate-based flavors.

Rating Ranges:

Flavor Rating: Ranges from 2.3 (Pistachio) to 10.0 (Mint Chocolate Chip).

Texture Rating: Ranges from 3.4 (Pistachio) to 8.0 (Mint Chocolate Chip).

Baseline Acceptance Rate: 6 out of 9 flavors are marked as Liked = Yes (~66.7% approval).





In-Analysis Board

Aggregate Aggregation Matrix (Grouped by Base Flavor)

Write on Medium
Metric / Attribute

Chocolate Base (N=3)

Vanilla Base (N=6)

Product Count

3

6

Mean Flavor Rating

8.40

5.70

Max Flavor Rating

8.8 (Chocolate)

10.0 (Mint Chocolate Chip)

Min Flavor Rating

8.2 (Rocky Road / Chocolte Fudge Brownie)

2.3 (Pistachio)

Mean Texture Rating

7.23

5.65

Max Texture Rating

7.6

8.0

Min Texture Rating

7.0

3.4 (Pistachio)

Total Sum Ratings

47.1 Total Rating Points

68.1 Total Rating Points

Customer Liked Rate

100% Yes (3/3)

50% Yes (3/6)



Time-Series Trends (1/1/2022–1/7/2022)

Peak Flavor Rating: 1/6/2022 (Score: ~0.878)

Peak Texture Rating: 1/2/2022 (Score: ~0.938)

Peak Overall Rating: 1/5/2022 (Score: ~0.988)




Post-Analysis Observations and Recommendations

Observations

Chocolate Base Dominance: Chocolate-based products maintain higher average performance consistency with an average Flavor Rating of 8.40 and Texture Rating of 7.23, yielding a 100% customer approval rate (Liked = Yes).

Vanilla Base High Variance: While Vanilla holds the single highest-rated flavor (Mint Chocolate Chip with Flavor: 10.0, Texture: 8.0, Total: 18.0), it also holds all three rejected products (Vanilla [Total: 9.7], Pistachio [Total: 5.7], and Neapolitan [Total: 8.8]).

Threshold for Acceptance: Any product with a Total Rating below 10.0 resulted in Liked = No. The threshold for product acceptance requires a minimal average rating of ~5.0+ per attribute.

Time Series Dynamics: Flavor, texture, and overall daily ratings show inverse fluctuation cycles, indicating daily batch quality inconsistencies.




Recommendations

Reformulate / Discontinue Low Performers: Immediately revise or remove Pistachio (Flavor 2.3 / Texture 3.4), Neapolitan (3.8 / 5.0), and core Vanilla (4.7 / 5.0).

Expand Chocolate Sub-Flavors: Given the 100% approval rate of Chocolate bases, reallocate R&D resources toward expanding chocolate line variants.

Standardize Quality Control: Implement strict batch production controls to mitigate the daily rating swings observed in the temporal tracking.




Conclusions

Base Category Stability: Chocolate provides a higher guaranteed baseline satisfaction score. Vanilla offers high potential top-performers (Mint Chocolate Chip) but suffers from extreme lower-tail risk.

Key Driver: Flavor Rating exhibits a stronger correlation with customer acceptance (Liked) than Texture Rating alone.

Strategic Pivot: Focus on standardizing texture scores above 6.0 and flavor scores above 6.5 across all catalog offerings to ensure positive consumer sentiment.




Reference

kaggle.com
