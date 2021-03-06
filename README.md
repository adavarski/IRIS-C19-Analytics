# IRIS Covid-19 Analytics

## Introduction (How it works)
The dashboards are running on InterSystems IRIS 2019.4 Community Edition.
It uses IRIS Analytics module and DSW as a representation layer

[AnalyzeThis](https://openexchange.intersystems.com/package/AnalyzeThis) module has been used to generate the class and the cube.
Pivots and Dashboards were built manually using [InterSystems IRIS Analytics](https://docs.intersystems.com/irislatest/csp/docbook/Doc.View.cls?KEY=D2GS)
[DSW](https://openexchange.intersystems.com/package/DeepSeeWeb) is used to design representation layer
[ISC-DEV](https://openexchange.intersystems.com/package/ISC-DEV) module was used to export pivot and dashboard.

To export Pivot and Dashboard changes do:
```
IRISAPP> do ##class(dev.code).export("*.DFI")
```
This will export pivots and dashboards into /src/dfi folder of the repo.

## Installation 

Open terminal and clone/git pull the repo into any local directory

```
$ git clone https://github.com/adavarski/IRIS-C19-Analytics
```
### Data Source
The data is taken from [Johns Hopkins repo](https://github.com/CSSEGISandData/COVID-19)
```
Example: 11 November 2020
$ cd data
$ curl https://github.com/CSSEGISandData/COVID-19/blob/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv -o time_series_19-covid-Confirmed.csv
$ for i in `seq 1 11`; do curl https://github.com/CSSEGISandData/COVID-19/blob/master/csse_covid_19_data/csse_covid_19_daily_reports/11-$i-2020.csv -o covid-11-$i-2020.csv;done
```

### Build & Run

```
$ docker-compose build
$ docker-compose up -d

Example: 
$ docker-compose up -d
Creating network "iris-c19-analytics_default" with the default driver
Creating iris-c19-analytics_iris_1 ... done

```

## Analytics: 

http://localhost:32916/dsw/index.html#/IRISAPP/Covid19/Countries.dashboard
http://localhost:32916/dsw/index.html#/IRISAPP/Covid19/Worldmap.dashboard
http://localhost:32916/dsw/index.html#/IRISAPP/Covid19/bubble%20chart.dashboard

Screenshots:

<img src="https://github.com/adavarski/IRIS-C19-Analytics/blob/main/screenshots/Countries-C-19.png?raw=true" width="650">
<img src="https://github.com/adavarski/IRIS-C19-Analytics/blob/main/screenshots/Worldmap-C-19.png?raw=true" width="650">
<img src="https://github.com/adavarski/IRIS-C19-Analytics/blob/main/screenshots/Top10-C19.png?raw=true" width="650">


