# Step 1: diagnosis
Dataset: teaching_prices_messy.csv

**Issue 1**: missing value in price, there is one missing figure in price
code that revealed it: raw.isna().sum()
action: investigate, as could be an error, if there is an individual date available and a proper individual entry there should logically be some value for price
**Issue 2**: duplicate value, there is a duplicated entry with same date item city and prices at 2 places in the dataset.
code: raw[raw.duplicated(keep=False)]
Action:  exclude, it is simple an error made, it is not an observation that has happened twice as data is in order of dates, it is simply observation accidentally recorded twice.
**Issue 3**: Outlier value, a value in the price column of a row contains a value 1250, likely because of missing or misentered decimal, code caught it as it included a comma in it
code: number=pd.to_numeric(raw["price"],errors="coerce")
raw[number.isna()][["date","item","city","price"]]
action:flag, it should not be excluded rather be flagged to make aware of it being an outlier value or that it has been entered incorrectly for eg.comma instead of decimal.
