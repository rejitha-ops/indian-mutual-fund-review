# Which mutual funds should we keep, watch, or drop?

I looked at 18 Indian mutual funds (9 funds, each with a Direct and a Regular plan) and asked: which ones grew well, and which ones were too risky?

**Tools:** Python (pandas) in Google Colab, and Power BI.

**Note:** The company in this project is made up, for practice.

![Dashboard](Mutual%20Fund%20Dashboard.png)

## The problem

Imagine a small company that helps people invest every month. Every three months, it checks its list of recommended funds. This time, it has to decide for each fund: keep it, watch it, or drop it. I helped answer that, using the last 13 years of price data.

## What I did

1. **Got the data.** I downloaded the daily prices of 18 funds from a free website (MFapi.in) using Python in Google Colab. That was about 68,000 rows.
2. **Checked and cleaned it.** I looked for empty cells and repeated rows (there were none). I started every fund on the same date, 28 May 2013, so the comparison is fair.
3. **Worked out three numbers for each fund.** These were how much it grew each year, how far it fell from its highest price, and how many days it took to get back to that price. I also compared Direct and Regular plans.
4. **Made a decision and a dashboard.** I used an index fund (UTI Nifty 50) as the yardstick. A fund that grew more without falling more was a Keep. I showed the results in a Power BI dashboard.

## What I found

1. **Higher growth came with bigger falls.** Nippon India Small Cap grew the most (25.1% a year) but also fell the most (48.6%). The bond fund grew the least (7.6%) but fell only 4%.
2. **Direct plans did better than Regular plans** for all 9 funds, by 0.12 to 1.41 points a year.
3. **Four funds did better than the index fund on both growth and falls:** Axis Midcap, Parag Parikh Flexi Cap, ICICI Pru US Bluechip, and Mirae Large Cap. I marked them Keep. Mirae's lead on risk was small.
4. **Kotak Global Emerging Market is a drop candidate.** It grew less than the index and took about 2.6 years to recover. I don't know why it was slow, so it needs a check before anyone drops it.

## What this project can't tell us

- I only looked at 18 funds that I picked myself, so this is not a view of all Indian funds.
- All 18 funds still exist today. Funds that closed are missing, which makes the results look better than they really were.
- I used one period, May 2013 to Oct 2026. A different period could change the ranking.
- The data has prices only. It has no fees, taxes, or client details, so I can't say whether clients should switch to Direct plans.
- The data shows what happened, not why. For example, I don't know why Kotak was slow to recover.

## Files

- `Mutual_Fund_Analysis.ipynb`: the Python notebook
- `fund_summary.csv`: growth, biggest fall, and days to recover for each fund
- `Mutual Fund Dashboard.pbix`: the Power BI file
- `Mutual Fund Dashboard.png`: a picture of the dashboard

Data source: MFapi.in (daily fund prices). The raw price file is not included. To rebuild it, run the notebook.
