# kyureki-json
Japanese Kyureki Info JSON(日本旧历/旧暦)

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

## TODO

1873-2099
- [ ] 1873 - 1890
- [ ] 1891 - 1900
- [ ] 1901 - 1910
- [ ] 1911 - 1920
- [ ] 1921 - 1930
- [ ] 1931 - 1940
- [x] 1941 - 1950
- [x] 1951 - 1960
- [x] 1961 - 1970
- [x] 1971 - 1980
- [x] 1981 - 1990
- [x] 1991 - 2000
- [x] 2001 - 2005
- [x] 2006 - 2010
- [x] 2011 - 2015
- [x] 2016 - 2020
- [x] 2021 - 2025
- [x] 2026 - 2030
- [x] 2031 - 2035
- [x] 2036 - 2040
- [x] 2041 - 2045
- [x] 2046 - 2050
- [x] 2051 - 2055
- [x] 2056 - 2060
- [x] 2061 - 2065
- [x] 2066 - 2070
- [x] 2071 - 2075
- [x] 2076 - 2080
- [x] 2081 - 2085
- [x] 2086 - 2090
- [x] 2091 - 2095
- [x] 2096 - 2099

## Why `kyureki-json`

I want to display Kyureki(旧暦) information and Rokuyo(六曜) calculated from Kyureki for the past few years and next several decades in my app.

After several days of research, I found that many Kyureki algorithms are based on qreki, a software implementation developed by Mr. Takano in the 1980s, and its derivative versions.

It worked well in the first two decades after its creation. However, according to the information on this webpage (https://wiki.suikawiki.org/n/qreki), I think that it may be more appropriate to use a lookup table to calculate the lunar calendar now (in 2023) and for the next few decades.

Hence, I need such a file.
