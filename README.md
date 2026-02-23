# iTunes Dataset Cleaning, Validation & Preparation Report
## Project: iTunes Music Dataset Analysis

Prepared By: @vaibhavdevangan
Date: 23/02/2026

### 1. Introduction

This report documents the complete data cleaning, structural validation, and preparation process performed on the iTunes dataset.

The objective was to:

Clean and standardize the raw dataset

Validate structural consistency (album vs track logic)

Prepare a finalized analytics-ready dataset

Enable dashboarding and visualization

The final dataset is ready for EDA, dashboard creation, and advanced modeling.

### 2. Dataset Overview

Original Rows: 4,915
Original Columns: 15

After cleaning and filtering:

Final Rows: 4,538
Final Columns Used for Analytics: 9

Columns Retained

track_id

track_name

artist_name

collection_name

genre

track_price

collection_price

release_date

track_time_millis

### 3. Data Cleaning & Preprocessing Steps
3.1 Dropped Columns

Removed irrelevant or non-informative fields:

album_artist

currency

preview_url

artwork_url

country

rating

3.2 Invalid Value Handling

Replaced invalid price values (-1) in:

track_price

collection_price

Converted them to NaN

3.3 Missing Value Handling

Removed rows where both track_price and collection_price were missing

Remaining minor missing values were retained due to low proportion

Final missing summary (after cleaning):

artist_name → 2

release_date → 48

These were retained as they do not materially affect pricing or structural analysis.

3.4 Data Type Conversions
Column	Final Data Type
track_id	object
track_price	float64
collection_price	float64
release_date	datetime64[ns, UTC]
track_time_millis	int64
### 4. Structural Validation Checks

Before visualization, key structural tests were performed:

4.1 Album Price Consistency

24 albums were found to have multiple collection prices

Indicates minor structural inconsistency in album-level pricing

4.2 Album Size Distribution

Mean tracks per album ≈ 1.69

Albums with 1 track: 2,133

Albums with 100+ tracks: 0

Interpretation:
The dataset is primarily track-centric, not album-centric.

4.3 Extreme Pricing Validation

Maximum collection price: $119.99

Corresponding track count: 1

This confirms that pricing is not strictly tied to album size.

### 5. Feature Engineering for Analytics

Additional derived columns were created:

track_duration_min → track_time_millis converted to minutes

price_tier → categorized pricing (Budget / Standard / Premium)

These were added to support dashboard visualization.

### 6. Key Analytical Findings from Visualization
6.1 Pricing Model

Pricing is concentrated in fixed tiers

No strong relationship between duration and track price

Indicates a standardized pricing model

6.2 Duration Pattern

Most tracks range between 3–4 minutes

Duration is relatively standardized across genres

6.3 Genre Concentration

Bollywood and Pop dominate track volume

Sharp drop after top 2 genres

Long-tail genres have limited representation

Conclusion:
The platform operates as a standardized, tier-based single-track digital marketplace with strong mainstream genre concentration.

### 7. Output

Final Exported Dataset:
itunes_cleaned_analytics.csv

Export configuration:

index=False used to prevent row index inclusion

This dataset is dashboard-ready.

### 8. Next Steps

Build Power BI / Tableau dashboard

Perform statistical hypothesis testing

Time-series analysis on release trends

Advanced pricing or genre modeling

 ### Final Status

The dataset has been:

Cleaned

Structurally validated

Feature engineered

Visualized

Exported for analytics

It is fully prepared for dashboarding and advanced analytical workflows.
