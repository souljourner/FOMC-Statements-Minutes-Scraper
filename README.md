# FOMC-Statements-Minutes-Scraper
A convenient Python 3.5 class for scraping all the existing FOMC meeting statements.

This class by default uses 10 threads to speed up the scraping time.

Output by default is a Pandas Dataframe.  Also has the option to write to disk a pickled Pandas Dataframe.


### Author: souljourner (John Zhu)


## EXAMPLE USAGE

### From bash:

```bash
$ python fomc.py
```
This creates a pickled Pandas Dataframe of the meeting minutes with the dates as the index.



### From Python:

```python
from FOMC import FOMC
fomc = FOMC()

# get the meeting statements back as a Pandas Dataframe
df = fomc.get_statements()

# write the dataframe as a pickle file
fomc.pickle("./df_minutes.pickle")
```

### Parameters:
Parameters are passed into FOMC() init:

All parameters are optional

```python
fomc = FOMC(base_url='https://www.federalreserve.gov', 
            calendar_url='https://www.federalreserve.gov/monetarypolicy/fomccalendars.htm',
            historical_date = 2011,
            verbose = True,
            max_threads = 10)

```

**base_url**: FOMC website base URL

**calendar_url**: URL of where the current meetings are listed

**historical_date**: year (int) where it is considered historical.  At this time of writing, 2011 was in the historical archive rather than in the current list.

**verbose**: if set to False, will not print any output during scraping

**max_threads**: the number of threads to use for web scraping

