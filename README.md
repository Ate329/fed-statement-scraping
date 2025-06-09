# FOMC Meeting Statements & Minutes
> **Note**
> This is a fork of [vtasca/fed-statement-scraping](https://github.com/vtasca/fed-statement-scraping).

This repository automatically scrapes and aggregates the Federal Reserve FOMC meeting statements, minutes, and scheduled future meetings - creating a dataset that enables tracking US monetary policy changes through time.

It works by polling the website of the U.S. Federal Reserve on a periodic basis and scraping the new statements, minutes, and scheduled meetings as they become available. 
The scraper runs in a scheduled GitHub Actions workflow, which is [available here](https://github.com/vtasca/fed-statement-scraping/actions/workflows/main.yml).

The dataset in this repository begins in 2020, as older data is no longer available on the Federal Reserve's website. For historical data starting from 2000, please refer to the dataset in the [original repository](https://github.com/vtasca/fed-statement-scraping/blob/master/communications.csv).

## Usage
The updated dataset is located in this repository at [`communications.csv`](https://github.com/ate329/fed-statement-scraping/blob/master/communications.csv). If found, new data is added on a daily basis.

### Data description
- `Date` - Date of the FOMC meeting.
- `Release Date` - Release date of the statement/minutes. Note that minutes are usually released with a ~3 week lag from the meeting date.
- `Type` - Communication type, one of:
  - `Statement` - FOMC meeting statement
  - `Minute` - Detailed minutes of the meeting
  - `Scheduled Meeting` - Future scheduled meeting date
- `Text` - The text content of each communication release (empty for scheduled meetings).

### Meeting Types
The dataset includes three types of entries:
1. **Statements** - Released on the day of the meeting, containing the FOMC's decisions and economic outlook
2. **Minutes** - Detailed record of the meeting discussion, released approximately three weeks after the meeting
3. **Scheduled Meetings** - Future meeting dates announced by the Fed

Note: When a meeting date has an associated statement or minutes, the "Scheduled Meeting" entry is automatically removed to avoid duplication.

### Availability
This dataset is also available on [Kaggle](https://www.kaggle.com/datasets/vladtasca/fomc-meeting-statements-and-minutes), together with related Jupyter notebooks.

## Related research
Monetary policy decisions shown in the FOMC meeting statements have been analyzed at length in academic research and found to have immediate effects on the volatility and direction of equity index prices[^1] and interest rates[^2].
[^1]: Rosa, C. (2011). Words that shake traders: The stock market's reaction to central bank communication in real time. Journal of Empirical Finance, 18(5), 915-934.
[^2]: Gürkaynak, R. S., Sack, B., & Swanson, E. (2005). The sensitivity of long-term interest rates to economic news: Evidence and implications for macroeconomic models. American economic review, 95(1), 425-436.

## Background information
The [Federal Open Market Committee (FOMC)](https://www.federalreserve.gov/monetarypolicy/fomc.htm) meets eight times during the year to make decisions regarding the implementation of monetary policy, with the aim of achieving the Federal Reserve's dual mandate: promoting maximum employment and maintaining stable prices (controlling inflation).

The FOMC meeting statement document is one of the main formal communication documents used by the Fed, and contains information about key interest rate decisions, an assessment of the economic outlook, a view on inflation as well as forward guidance. This information helps businesses, investors and the general public take monetary policy into account and make more informed economic decisions.
