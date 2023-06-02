# kyureki-json
Japanese Kyureki Info JSON(日本旧历/旧暦)

Based on 21世紀暦(ISBN: 9784816916304)

## Format specification:

- `sexagenaryCycleInfo` represents the index of the year in the sexagenary cycle(干支), start from `0` to `59`.

  For example:
  - `0` is `甲子`
  - `59` is `癸亥`

- `leapMonth` represents the Leap Month(閏月) in a year.
  - `-1`: There is no Leap Month in this year.
  - `0`: 閏一月
  - `1`: 閏二月
  - `2`: 閏三月
  - ...

- `sizeInfo` represents the 30-day month and 29-day month. 
  
  The string consists of multiple binary digits, where each digit represents the number of days in the corresponding month. A value of 0 indicates that the month is a small month with 29 days, while a value of 1 indicates that the month is a big month with 30 days.

  For example:
  - `011010101010`, the first month of the year has 29 days, the second month has 30 days, the third month has 30 days, the fourth month has 29 days, and so on until the last month has 29 days

- `start` represents the first day(Gregorian Calendar) of the year.

## Why `kyureki-json`

I want to display Kyureki(旧暦) information and Rokuyo(六曜) calculated from Kyureki for the past few years and next several decades in my app.

After several days of research, I found that many Kyureki algorithms are based on qreki, a software implementation developed by Mr. Takano in the 1980s, and its derivative versions.

It worked well in the first two decades after its creation. However, according to the information on this webpage (https://wiki.suikawiki.org/n/qreki), I think that it may be more appropriate to use a lookup table to calculate the lunar calendar now (in 2023) and for the next few decades.

Hence, I need such a file.
