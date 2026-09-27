# Tradingview-S50
Data of SET50 index future for importing to Amibroker.

## Info
Price, time, volume of each series in 1 minute timeframe concatenated together. Data in last trading day of each series will be replaced with data from the next series. For example, at the date 2021-12-29 (which is the LTD of S50Z2021) will be replaced with data from S50H2022 instead.
  
## How to Use
Download `S50H16-S50Z25_1m.zip` from this repository. Extract it to retrieve the .csv file before importing it into Amibroker.

## Price Error
1. Certain row might have bar at time 12:30, but actually it must be counted in the previous bar at 12:29.
2. The data from intraday might have price error, too high or too low, or lack of some bar. So I tried to correct them manually as below, which might be inaccurate from reality.

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

**S50H2023**  
In 1 minute timeframe, the first bar should be _29 Dec 2022_, but I got _3 Jan 2023_ instead (2 days missed, 29th and 30th).  
Resolved by using data in 5 minutes timeframe on _29 - 30 Dec 2022_.

**S50H2024**  
In 1 minute timeframe, the first bar should be _27 Dec 2023_, but I got _2 Jan 2024_ instead (2 days missed, 27th and 28th).  
Resolved by using data in 5 minutes timeframe on _27 - 28 Dec 2023_.

**S50U2024**  
In 1 minute timeframe, the first bar should be _27 Jun 2024_, but I got _8 Jul 2024_ instead (7 days missed).  
Resolved by using data in 5 minutes timeframe on _27 Jun - 5 Jul 2024_.

**S50Z2024**  
In 1 minute timeframe, the first bar should be _27 Sep 2024_, but I got _30 Sep 2024_ instead (1 day missed, 27th).  
Resolved by using data in 5 minutes timeframe on _27 Sep 2024_.

**S50H2025**  
In 1 minute timeframe, the first bar should be _27 Dec 2024_, but I got _6 Jan 2025_ instead (4 days missed, 27th, 30th, 2nd and 3rd).  
Resolved by using data in 5 minutes timeframe on _27 Dec 2024 - 3 Jan 2025_.

**S50M2025**  
In 1 minute timeframe, the first bar should be _28 Mar 2025_, but I got _31 Mar 2025_ instead (1 day missed, 28th).  
Resolved by using data in 5 minutes timeframe on _28 Mar 2025_.  
Note: there is no data after 14:05 on 28 Mar 2025 because SET halted trading of SET, mai and TFEX in the afternoon session due to the earthquake.

**S50U2025**  
In 1 minute timeframe, the first bar should be _27 Jun 2025_, but I got _7 Jul 2025_ instead (6 days missed).  
Resolved by using data in 5 minutes timeframe on _27 Jun - 4 Jul 2025_.

**S50Z2025**  
In 1 minute timeframe, the first bar should be _29 Sep 2025_, but I got _6 Oct 2025_ instead (5 days missed).  
Resolved by using data in 5 minutes timeframe on _29 Sep - 3 Oct 2025_.

## Trading Hours
1. Until 22 Mar 2024, the afternoon session starts at 14:15 (325 bars per full day).
2. From 25 Mar 2024, the afternoon session starts at 13:45 (355 bars per full day).
3. A few minutes might have no bar when there was no trade in that minute, e.g. no 09:45 bar on 8 May 2025.

## Series Dates (from 2022)
Start date is the LTD of the previous series. End date is the day before the LTD of the series itself.

| Series | Start | End | LTD (not included) |
|---|---|---|---|
| S50M2022 | 2022-03-30 | 2022-06-28 | 2022-06-29 |
| S50U2022 | 2022-06-29 | 2022-09-28 | 2022-09-29 |
| S50Z2022 | 2022-09-29 | 2022-12-28 | 2022-12-29 |
| S50H2023 | 2022-12-29 | 2023-03-29 | 2023-03-30 |
| S50M2023 | 2023-03-30 | 2023-06-28 | 2023-06-29 |
| S50U2023 | 2023-06-29 | 2023-09-27 | 2023-09-28 |
| S50Z2023 | 2023-09-28 | 2023-12-26 | 2023-12-27 |
| S50H2024 | 2023-12-27 | 2024-03-27 | 2024-03-28 |
| S50M2024 | 2024-03-28 | 2024-06-26 | 2024-06-27 |
| S50U2024 | 2024-06-27 | 2024-09-26 | 2024-09-27 |
| S50Z2024 | 2024-09-27 | 2024-12-26 | 2024-12-27 |
| S50H2025 | 2024-12-27 | 2025-03-27 | 2025-03-28 |
| S50M2025 | 2025-03-28 | 2025-06-26 | 2025-06-27 |
| S50U2025 | 2025-06-27 | 2025-09-26 | 2025-09-29 |
| S50Z2025 | 2025-09-29 | 2025-12-26 | 2025-12-29 |
