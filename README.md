# Religion and Educational Attainment Across U.S. Counties

Do counties with higher religious adherence have lower rates of college degree completion? This project gathers, cleans, and joins two public datasets to find out.

## Data
- **2020 U.S. Religion Census** (Association of Religion Data Archives): manual download, 838 columns
- **U.S. Census Bureau ACS 5-Year Estimates (2020)**: pulled through the Census API with `requests`

## Data wrangling
- Dropped denomination columns more than 50% empty (838 → 78), then kept the 8 columns needed
- Converted Census API values from strings to integers
- Built a 5-digit FIPS key from separate state and county codes (zero-padded) so the datasets could be joined
- Joined into one tidy dataset: **3,143 counties**, saved alongside the raw files

## Findings
- Counties with higher religious adherence tend to have lower shares of bachelor's degree holders (a negative trend, with a lot of variation)
- The 10 states with the highest average adherence generally have lower bachelor's attainment than the 10 least religious states
- This is a correlation only. Income, rural vs. urban, and demographics are likely confounders

## Next steps
Break the relationship down by religious tradition, control for income and rural/urban status, and compare with 2010 data.

## Tools
Python · pandas · Matplotlib · requests · Jupyter
