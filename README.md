# FOMC-Statements-Minutes-Scraper
A convenient class for scraping all the existing FOMC meeting statements

### Author: John Zhu


## EXAMPLE USAGE
```python
from FOMC import FOMC
fomc = FOMC()

# get the meeting statements back as a Pandas Dataframe
df = fomc.get_statements()

# write the dataframe as a pickle file
fomc.pickle("./df_minutes.pickle")
```
