## COVID19 Pandemia Stats
### LAST UPDATED: 11 November 2020 
Example:
```
$ cd data
$ curl https://github.com/CSSEGISandData/COVID-19/blob/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv -o time_series_19-covid-Confirmed.csv
$ for i in `seq 1 11`; do curl https://github.com/CSSEGISandData/COVID-19/blob/master/csse_covid_19_data/csse_covid_19_daily_reports/11-$i-2020.csv -o covid-11-$i-2020.csv;done
```
### Data Source
[John Hopkins](https://github.com/CSSEGISandData/COVID-19)
