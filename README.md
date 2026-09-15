# cyclistic-bikeshare-analysis
Bike-share usage analysis comparing annual members vs casual riders — Google Data Analytics Certificate Case Study
## Business Task

Analyze 12 months of Cyclistic trip data (September 2025 – August 2026) to identify how annual members and casual riders use Cyclistic bikes differently. These insights will support the marketing team in designing a strategy to convert casual riders into annual members.

## Data Sources

- Public Divvy trip data, covering September 2025 to August 2026 (12 monthly files)
- Raw dataset: 4,702,361 rows, 13 columns
- Data provided by Motivate International Inc. under license (no personally identifiable information; individual riders cannot be tracked across purchases)

## Data Cleaning

- **Datetime conversion**: Converted `started_at` / `ended_at` to datetime format; derived `ride_length` (minutes) and `day_of_week` / `day_name`
- **Outlier removal**: Removed 29 rides with negative duration and 3,146 rides exceeding 24 hours (0.07% of total data), likely due to system testing or bikes not properly docked
- **Missing value validation**: Missing station names (~19% of records) were confirmed to correspond 100% to `electric_bike` rides — a structural difference in the data (electric bikes can be parked outside docking stations), not a data quality issue. No further cleaning required.

## Key Findings

### 1. Ride Length

Casual riders take significantly longer rides on average — 18 minutes vs. 12 minutes for members (a 51% difference).

![Ride Length Comparison](ride_length_comparison.png)

### 2. Weekly Usage Pattern

Members' usage is concentrated on weekdays, consistent with commuting behavior. Casual riders peak on weekends, consistent with leisure/recreational use.

![Rides by Day of Week](rides_by_day.png)

### 3. Bike Type Preference

Casual riders show a stronger preference for electric bikes (71.2%) compared to members (66.0%).

![Bike Type Preference](bike_type_preference.png)

### 4. Seasonal Trend

Both rider types show a clear seasonal pattern, peaking in summer (Jun–Aug) and declining sharply in winter (Dec–Jan). However, casual riders show far greater seasonal sensitivity — ride volume increases roughly 9x from winter low to summer peak, compared to only ~3x for members. This suggests members maintain consistent usage year-round (likely driven by commuting needs), while casual ridership is heavily weather-dependent and recreational in nature.

*Note: Months are ordered by calendar month (Jan–Dec) to highlight seasonal patterns, as the 12-month dataset spans September 2025 to August 2026.*

![Monthly Trend](monthly_trend.png)
## Recommendations

Based on the analysis of ride length, weekly patterns, bike type preference, and seasonal trends, here are three recommendations to help convert casual riders into annual members:

**1. Launch a "Weekend-to-Weekday" membership trial**
Casual riders are heavily weekend-concentrated and show no weekday commuting pattern. Rather than marketing annual membership as a "commuter" product, offer a limited-time trial (e.g., discounted membership for the first month) that lets casual riders experience weekday convenience and pricing benefits — nudging them to build a weekday riding habit before committing.

**2. Target the summer peak with a seasonal membership push**
Casual ridership grows ~9x from winter to summer, while member ridership stays comparatively stable year-round. This means casual riders are most active — and most likely to be considering bike-share as a genuine transportation option — during Jun–Aug. Concentrate membership conversion campaigns (e.g., station signage, in-app prompts after a ride) during this window, when casual riders are already engaged and price-sensitive to single-ride costs adding up.

**3. Promote membership value through the electric bike experience**
Casual riders show a stronger preference for electric bikes (71.2%) than members (66.0%), and take notably longer rides overall. A membership pricing structure that includes reduced or capped electric bike surcharges could directly appeal to casual riders' existing usage pattern, framing membership as a cost-saving upgrade to a bike type they already prefer.

## Tools Used

Python (pandas, matplotlib, seaborn) in Jupyter Notebook
