# Tradingview-S50
Data of SET50 index future for importing to Amibroker.

### Info
Price, time, volume of each series in 1 minute timeframe concatenated together. Data in last trading day of each series will be replaced with data from the next series. For example, at the date 2021-12-29 (which is the LTD of S50Z2021) will be replaced with data from S50H2022 instead.

### How to Use
Just download the .zip file from the release. Extract it to retrieve the .csv file before importing it into Amibroker.

### Price Error
1. Certain row might have bar at time 12:30, but actually it must be counted in the previous bar at 12:29.
2. The data from intraday might have price error, too high or too low, or lack of some bar. So I tried to correct it manually as below which migh be inaccurate from reality.

**S50U2017**  
2017-09-25T11:49:00+07:00  High 1160 -> 1064.1  
2017-09-25T11:54:00+07:00  High 1160 -> 1064.4  

**S50Z2018**  
2018-11-08T15:40:00+07:00  Low 1101.9944 -> 1115.7  
2018-11-08T15:41:00+07:00  Low 1101.9944 -> 1115.6  
2018-11-08T15:44:00+07:00  Low 1101.9944 -> 1114.9  
2018-11-08T15:52:00+07:00  Low 1101.9944 -> 1116.2  
2018-11-08T15:54:00+07:00  Low 1101.9944 -> 1116.5  
2018-11-08T15:55:00+07:00  Low 1101.9944 -> 1116.4  

**S50M2019**  
2019-06-25T12:01:00+07:00  Low 1139.5 -> 1146.9  
2019-06-25T12:05:00+07:00  Low 1139.5 -> 1147.7  
2019-06-25T12:14:00+07:00  Low 1147 -> 1148.5  

**S50U2019**  
In 1 minute timeframe, the first bar should be _27 Jun 2019_, but I got _1 July 2019_ instead (2 days missed, 27th and 28th).  
Resolved by using data in 5 minutes timeframe on _27 - 28 Jun 2019_.

**S50H2020**  
In 1 minute timeframe, the first bar should be _27 Dec 2019_, but I got _30 Dec 2019_ instead (1 day missed, 27th).  
Resolved by using data in 5 minutes timeframe on _27 Dec 2019_.
  
