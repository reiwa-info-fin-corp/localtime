# LocalTime
When using the Date construct in Node.js to generate a date object, it is not possible to set an arbitrary time zone.
This means that the date and time will differ depending on the environment in which the date object is generated using the Date construct.
Therefore, we will create a LocalTime module that displays the local time in an arbitrarily set time zone, no matter what environment it is executed in.
The time zone is selected from 43 different city names.
The way it works is that UTC(Coordinated Universal Time) will have the same value no matter what environment it is run in, so the UTC value and the city's time difference value are used to find the local time for the set city name.

(Node.jsでDateコンストラクを使ってdateオブジェクトを生成するときに任意のタイムゾーンを設定できない。
つまり、Dateコンストラクを使ってdateオブジェクトを生成する環境によって日時が異なることを意味する。
そこで今回、どんな環境で実行しても任意で設定したタイムゾーンの現地時間を表示するLocalTimeモジュールを作る。
タイムゾーンは、43種類の都市名から選択する。
仕組みとして、どんな環境で実行してもUTC(協定世界時)は同じ値になるため、UTCの値と都市の時差の値を使用して、設定した都市名の現地時間を求める。)

## Install it via npm
```shell
npm i @reiwa_info_fin_corp/localtime
```

## Require the Module
```shell
const localTime = require("@reiwa_info_fin_corp/localtime");
```

## To use

Whenever the SetTimeZone, GetUTCTimeString, or GetLocalTimeString method is executed, a process is performed in the LocalTime module to obtain the UTC time and the local time of the set city.  
On the other hand, when the Get method is executed, no processing is performed in the LocalTime module to obtain UTC time and the local time of the city.
When the Get method is executed, the year, month, day, weekday, hour, minute, second, and millisecond of the local time can be obtained.
This local time is exactly the same local time obtained when executing the SetTimeZone method or the GetUTCTimeString method or the GetLocalTimeString method before executing the Get method.

(SetTimeZoneメソッド、GetUTCTimeStringメソッド、GetLocalTimeStringメソッドを実行する際は、必ずLocalTimeモジュール内でUTC時間と設定した都市の現地時間を求める処理が実行される。  
一方、Getメソッドを実行する際は、LocalTimeモジュール内でUTC時間と都市の現地時間を求める処理は一切行われない。Getメソッドを実行すると、現地時刻の年、月、日、曜日、時、分、秒、ミリ秒を取得することができる。この現地時刻は、Getメソッド実行前に、SetTimeZoneメソッドまたはGetUTCTimeStringメソッドまたはGetLocalTimeStringメソッドを実行時に求めた現地時刻と全く同じ現地時刻である。)

```shell
//Set the city.
//(都市を設定する。)
localTime.SetTimeZone("TYO");
//Default language is English.If you want to set Japanese, set "JP".
//(デフォルト言語は英語。もし、日本語を設定するなら"JP"を設定する。)
localTime.SetLang("JP");
//Get UTC time.
//(UTC時間を取得する。)
localTime.GetUTCTimeString();
//Get the local time of the city.
//(都市の現地時間を取得する。)
localTime.GetLocalTimeString();
//Bring up a list of possible city names to be set.
//(設定可能な都市名の一覧を出す。)
localTime.GetAvailableCities();
//Get TimeZone
localTime.Get("TimeZone");
//Get SerialNumber
localTime.Get("SerialNumber");
//Get TimeDifference
localTime.Get("TimeDifference");
//Get City
localTime.Get("City");
//Get FullYear
localTime.Get("FullYear");
//Get Month
localTime.Get("Month");
//Get Date
localTime.Get("Date");
//Get Day
localTime.Get("Day");
//Get Hours
localTime.Get("Hours");
//Get Minutes
localTime.Get("Minutes");
//Get Seconds
localTime.Get("Seconds");
//Get Milliseconds
localTime.Get("Milliseconds");
```

## Parameters 
The SetTimeZone method can be set to the following cities.
You can choose only one of 43 cities.

(SetTimeZoneメソッドで設定できる都市は、以下の通りである。43都市のうち、1都市のみ選択可能である。)
```
LON
MAD
PAR
ROM
BER
CAI
AHI
JNB
RUH
THR
DXB
KBL
KHI
DEL
DAC
RGN
BKK
SIN
HKG
BJS
TPE
TYO
SEL
ADL
SYD
NOU
AKL
SUV
MDY
HNL
ANC
YVR
LAX
DEN
MEX
CHI
NYC
YMQ
MAO
BUE
RIO
FEN
PDL
```

## Sample Code
You can run the Sample Code.

(あなたはサンプルコードを実行できる。)

```shell
〇〇\node_modules\@reiwa_info_fin_corp\localtime>npm test

> @reiwa_info_fin_corp/localtime@1.0.6 test
> node LocalTime_sample.js

[UTC] 2023-06-25(Sun) 07:34:36.188
[LON] 2023-06-25(Sun) 07:34:36.193
TimeZone:        LON
SerialNumber:    No.01
TimeDifference:  UTC + 0
City:            The United Kingdom / London
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           07
Minutes:         34
Seconds:         36
Milliseconds:    188
[UTC] 2023-06-25(Sun) 07:34:36.196
[MAD] 2023-06-25(Sun) 08:34:36.196
TimeZone:        MAD
SerialNumber:    No.02
TimeDifference:  UTC + 1
City:            Spain / Madrid
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           08
Minutes:         34
Seconds:         36
Milliseconds:    195
[UTC] 2023-06-25(Sun) 07:34:36.203
[PAR] 2023-06-25(Sun) 08:34:36.203
TimeZone:        PAR
SerialNumber:    No.03
TimeDifference:  UTC + 1
City:            France / Paris
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           08
Minutes:         34
Seconds:         36
Milliseconds:    203
[UTC] 2023-06-25(Sun) 07:34:36.209
[ROM] 2023-06-25(Sun) 08:34:36.209
TimeZone:        ROM
SerialNumber:    No.04
TimeDifference:  UTC + 1
City:            Italy / Rome
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           08
Minutes:         34
Seconds:         36
Milliseconds:    208
[UTC] 2023-06-25(Sun) 07:34:36.217
[BER] 2023-06-25(Sun) 08:34:36.217
TimeZone:        BER
SerialNumber:    No.05
TimeDifference:  UTC + 1
City:            Germany / Berlin
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           08
Minutes:         34
Seconds:         36
Milliseconds:    217
[UTC] 2023-06-25(Sun) 07:34:36.223
[CAI] 2023-06-25(Sun) 09:34:36.224
TimeZone:        CAI
SerialNumber:    No.06
TimeDifference:  UTC + 2
City:            Egypt / Cairo
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           09
Minutes:         34
Seconds:         36
Milliseconds:    223
[UTC] 2023-06-25(Sun) 07:34:36.232
[AHI] 2023-06-25(Sun) 09:34:36.232
TimeZone:        AHI
SerialNumber:    No.07
TimeDifference:  UTC + 2
City:            Greece / Athens
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           09
Minutes:         34
Seconds:         36
Milliseconds:    232
[UTC] 2023-06-25(Sun) 07:34:36.238
[JNB] 2023-06-25(Sun) 09:34:36.238
TimeZone:        JNB
SerialNumber:    No.08
TimeDifference:  UTC + 2
City:            South Africa / Johannesburg
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           09
Minutes:         34
Seconds:         36
Milliseconds:    238
[UTC] 2023-06-25(Sun) 07:34:36.244
[RUH] 2023-06-25(Sun) 10:34:36.244
TimeZone:        RUH
SerialNumber:    No.09
TimeDifference:  UTC + 3
City:            Saudi Arabia / Riyadh
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           10
Minutes:         34
Seconds:         36
Milliseconds:    244
[UTC] 2023-06-25(Sun) 07:34:36.253
[THR] 2023-06-25(Sun) 11:04:36.253
TimeZone:        THR
SerialNumber:    No.10
TimeDifference:  UTC + 3.5
City:            Iran / Tehran
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           11
Minutes:         04
Seconds:         36
Milliseconds:    253
[UTC] 2023-06-25(Sun) 07:34:36.259
[DXB] 2023-06-25(Sun) 11:34:36.259
TimeZone:        DXB
SerialNumber:    No.11
TimeDifference:  UTC + 4
City:            United Arab Emirates / Dubai
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           11
Minutes:         34
Seconds:         36
Milliseconds:    258
[UTC] 2023-06-25(Sun) 07:34:36.266
[KBL] 2023-06-25(Sun) 12:04:36.267
TimeZone:        KBL
SerialNumber:    No.12
TimeDifference:  UTC + 4.5
City:            Afghanistan / Kabul
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           12
Minutes:         04
Seconds:         36
Milliseconds:    266
[UTC] 2023-06-25(Sun) 07:34:36.272
[KHI] 2023-06-25(Sun) 12:34:36.273
TimeZone:        KHI
SerialNumber:    No.13
TimeDifference:  UTC + 5
City:            Pakistan / Karachi
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           12
Minutes:         34
Seconds:         36
Milliseconds:    272
[UTC] 2023-06-25(Sun) 07:34:36.280
[DEL] 2023-06-25(Sun) 13:04:36.280
TimeZone:        DEL
SerialNumber:    No.14
TimeDifference:  UTC + 5.5
City:            India/Delhi
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           13
Minutes:         04
Seconds:         36
Milliseconds:    280
[UTC] 2023-06-25(Sun) 07:34:36.286
[DAC] 2023-06-25(Sun) 13:34:36.287
TimeZone:        DAC
SerialNumber:    No.15
TimeDifference:  UTC + 6
City:            Bangladesh / Dhaka
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           13
Minutes:         34
Seconds:         36
Milliseconds:    286
[UTC] 2023-06-25(Sun) 07:34:36.292
[RGN] 2023-06-25(Sun) 14:04:36.292
TimeZone:        RGN
SerialNumber:    No.16
TimeDifference:  UTC + 6.5
City:            Myanmar / Yangon
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           14
Minutes:         04
Seconds:         36
Milliseconds:    292
[UTC] 2023-06-25(Sun) 07:34:36.300
[BKK] 2023-06-25(Sun) 14:34:36.300
TimeZone:        BKK
SerialNumber:    No.17
TimeDifference:  UTC + 7
City:            Bangkok, Thailand
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           14
Minutes:         34
Seconds:         36
Milliseconds:    300
[UTC] 2023-06-25(Sun) 07:34:36.306
[SIN] 2023-06-25(Sun) 15:34:36.306
TimeZone:        SIN
SerialNumber:    No.18
TimeDifference:  UTC + 8
City:            Singapore / Singapore
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           15
Minutes:         34
Seconds:         36
Milliseconds:    306
[UTC] 2023-06-25(Sun) 07:34:36.314
[HKG] 2023-06-25(Sun) 15:34:36.314
TimeZone:        HKG
SerialNumber:    No.19
TimeDifference:  UTC + 8
City:            Hong Kong / Hong Kong
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           15
Minutes:         34
Seconds:         36
Milliseconds:    314
[UTC] 2023-06-25(Sun) 07:34:36.320
[BJS] 2023-06-25(Sun) 15:34:36.320
TimeZone:        BJS
SerialNumber:    No.20
TimeDifference:  UTC + 8
City:            China / Beijing
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           15
Minutes:         34
Seconds:         36
Milliseconds:    320
[UTC] 2023-06-25(Sun) 07:34:36.327
[TPE] 2023-06-25(Sun) 15:34:36.328
TimeZone:        TPE
SerialNumber:    No.21
TimeDifference:  UTC + 8
City:            Taiwan / Taipei
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           15
Minutes:         34
Seconds:         36
Milliseconds:    327
[UTC] 2023-06-25(Sun) 07:34:36.333
[TYO] 2023-06-25(Sun) 16:34:36.334
TimeZone:        TYO
SerialNumber:    No.22
TimeDifference:  UTC + 9
City:            Japan / Tokyo
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           16
Minutes:         34
Seconds:         36
Milliseconds:    333
[UTC] 2023-06-25(Sun) 07:34:36.337
[SEL] 2023-06-25(Sun) 16:34:36.337
TimeZone:        SEL
SerialNumber:    No.23
TimeDifference:  UTC + 9
City:            South Korea / Seoul
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           16
Minutes:         34
Seconds:         36
Milliseconds:    337
[UTC] 2023-06-25(Sun) 07:34:36.338
[ADL] 2023-06-25(Sun) 17:04:36.338
TimeZone:        ADL
SerialNumber:    No.24
TimeDifference:  UTC + 9.5
City:            Australia / Adelaide
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           17
Minutes:         04
Seconds:         36
Milliseconds:    338
[UTC] 2023-06-25(Sun) 07:34:36.339
[SYD] 2023-06-25(Sun) 17:34:36.339
TimeZone:        SYD
SerialNumber:    No.25
TimeDifference:  UTC + 10
City:            Australia / Sydney
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           17
Minutes:         34
Seconds:         36
Milliseconds:    339
[UTC] 2023-06-25(Sun) 07:34:36.343
[NOU] 2023-06-25(Sun) 18:34:36.343
TimeZone:        NOU
SerialNumber:    No.26
TimeDifference:  UTC + 11
City:            New Caledonia / Noumea
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           18
Minutes:         34
Seconds:         36
Milliseconds:    343
[UTC] 2023-06-25(Sun) 07:34:36.344
[AKL] 2023-06-25(Sun) 19:34:36.344
TimeZone:        AKL
SerialNumber:    No.27
TimeDifference:  UTC + 12
City:            New Zealand / Auckland
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           19
Minutes:         34
Seconds:         36
Milliseconds:    344
[UTC] 2023-06-25(Sun) 07:34:36.345
[SUV] 2023-06-25(Sun) 19:34:36.345
TimeZone:        SUV
SerialNumber:    No.28
TimeDifference:  UTC + 12
City:            The Republic of Fiji / Suva
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           19
Minutes:         34
Seconds:         36
Milliseconds:    345
[UTC] 2023-06-25(Sun) 07:34:36.346
[MDY] 2023-06-24(Sat) 20:34:36.346
TimeZone:        MDY
SerialNumber:    No.29
TimeDifference:  UTC - 11
City:            The United States of America / Midway Atoll
FullYear:        2023
Month:           06
Date:            24
Day:             Sat
Hours:           20
Minutes:         34
Seconds:         36
Milliseconds:    346
[UTC] 2023-06-25(Sun) 07:34:36.347
[HNL] 2023-06-24(Sat) 21:34:36.347
TimeZone:        HNL
SerialNumber:    No.30
TimeDifference:  UTC - 10
City:            The United States of America / Honolulu
FullYear:        2023
Month:           06
Date:            24
Day:             Sat
Hours:           21
Minutes:         34
Seconds:         36
Milliseconds:    347
[UTC] 2023-06-25(Sun) 07:34:36.348
[ANC] 2023-06-24(Sat) 22:34:36.348
TimeZone:        ANC
SerialNumber:    No.31
TimeDifference:  UTC - 9
City:            The United States of America / Anchorage
FullYear:        2023
Month:           06
Date:            24
Day:             Sat
Hours:           22
Minutes:         34
Seconds:         36
Milliseconds:    348
[UTC] 2023-06-25(Sun) 07:34:36.349
[YVR] 2023-06-24(Sat) 23:34:36.349
TimeZone:        YVR
SerialNumber:    No.32
TimeDifference:  UTC - 8
City:            Canada / Vancouver
FullYear:        2023
Month:           06
Date:            24
Day:             Sat
Hours:           23
Minutes:         34
Seconds:         36
Milliseconds:    349
[UTC] 2023-06-25(Sun) 07:34:36.350
[LAX] 2023-06-24(Sat) 23:34:36.350
TimeZone:        LAX
SerialNumber:    No.33
TimeDifference:  UTC - 8
City:            The United States of America / Los Angeles
FullYear:        2023
Month:           06
Date:            24
Day:             Sat
Hours:           23
Minutes:         34
Seconds:         36
Milliseconds:    350
[UTC] 2023-06-25(Sun) 07:34:36.351
[DEN] 2023-06-25(Sun) 00:34:36.351
TimeZone:        DEN
SerialNumber:    No.34
TimeDifference:  UTC - 7
City:            The United States of America / Denver
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           00
Minutes:         34
Seconds:         36
Milliseconds:    351
[UTC] 2023-06-25(Sun) 07:34:36.352
[MEX] 2023-06-25(Sun) 01:34:36.352
TimeZone:        MEX
SerialNumber:    No.35
TimeDifference:  UTC - 6
City:            Mexico / Mexico City
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           01
Minutes:         34
Seconds:         36
Milliseconds:    352
[UTC] 2023-06-25(Sun) 07:34:36.353
[CHI] 2023-06-25(Sun) 01:34:36.353
TimeZone:        CHI
SerialNumber:    No.36
TimeDifference:  UTC - 6
City:            The United States of America / Chicago
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           01
Minutes:         34
Seconds:         36
Milliseconds:    353
[UTC] 2023-06-25(Sun) 07:34:36.354
[NYC] 2023-06-25(Sun) 02:34:36.354
TimeZone:        NYC
SerialNumber:    No.37
TimeDifference:  UTC - 5
City:            The United States of America / New York
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           02
Minutes:         34
Seconds:         36
Milliseconds:    354
[UTC] 2023-06-25(Sun) 07:34:36.355
[YMQ] 2023-06-25(Sun) 02:34:36.355
TimeZone:        YMQ
SerialNumber:    No.38
TimeDifference:  UTC - 5
City:            Canada / Montreal
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           02
Minutes:         34
Seconds:         36
Milliseconds:    355
[UTC] 2023-06-25(Sun) 07:34:36.356
[MAO] 2023-06-25(Sun) 03:34:36.356
TimeZone:        MAO
SerialNumber:    No.39
TimeDifference:  UTC - 4
City:            Brazil / Manaus
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           03
Minutes:         34
Seconds:         36
Milliseconds:    356
[UTC] 2023-06-25(Sun) 07:34:36.359
[BUE] 2023-06-25(Sun) 04:34:36.359
TimeZone:        BUE
SerialNumber:    No.40
TimeDifference:  UTC - 3
City:            Argentina / Buenos Aires
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           04
Minutes:         34
Seconds:         36
Milliseconds:    359
[UTC] 2023-06-25(Sun) 07:34:36.360
[RIO] 2023-06-25(Sun) 04:34:36.360
TimeZone:        RIO
SerialNumber:    No.41
TimeDifference:  UTC - 3
City:            Brazil / Rio de Janeiro
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           04
Minutes:         34
Seconds:         36
Milliseconds:    360
[UTC] 2023-06-25(Sun) 07:34:36.361
[FEN] 2023-06-25(Sun) 05:34:36.361
TimeZone:        FEN
SerialNumber:    No.42
TimeDifference:  UTC - 2
City:            Brazil / Fernando de Noronha
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           05
Minutes:         34
Seconds:         36
Milliseconds:    361
[UTC] 2023-06-25(Sun) 07:34:36.362
[PDL] 2023-06-25(Sun) 06:34:36.362
TimeZone:        PDL
SerialNumber:    No.43
TimeDifference:  UTC - 1
City:            Portuguese / Azores
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           06
Minutes:         34
Seconds:         36
Milliseconds:    362
--AvailableCities(43) begin--
LON (UTC + 0):   No.01 The United Kingdom / London
MAD (UTC + 1):   No.02 Spain / Madrid
PAR (UTC + 1):   No.03 France / Paris
ROM (UTC + 1):   No.04 Italy / Rome
BER (UTC + 1):   No.05 Germany / Berlin
CAI (UTC + 2):   No.06 Egypt / Cairo
AHI (UTC + 2):   No.07 Greece / Athens
JNB (UTC + 2):   No.08 South Africa / Johannesburg
RUH (UTC + 3):   No.09 Saudi Arabia / Riyadh
THR (UTC + 3.5): No.10 Iran / Tehran
DXB (UTC + 4):   No.11 United Arab Emirates / Dubai
KBL (UTC + 4.5): No.12 Afghanistan / Kabul
KHI (UTC + 5):   No.13 Pakistan / Karachi
DEL (UTC + 5.5): No.14 India/Delhi
DAC (UTC + 6):   No.15 Bangladesh / Dhaka
RGN (UTC + 6.5): No.16 Myanmar / Yangon
BKK (UTC + 7):   No.17 Bangkok, Thailand
SIN (UTC + 8):   No.18 Singapore / Singapore
HKG (UTC + 8):   No.19 Hong Kong / Hong Kong
BJS (UTC + 8):   No.20 China / Beijing
TPE (UTC + 8):   No.21 Taiwan / Taipei
TYO (UTC + 9):   No.22 Japan / Tokyo
SEL (UTC + 9):   No.23 South Korea / Seoul
ADL (UTC + 9.5): No.24 Australia / Adelaide
SYD (UTC + 10):  No.25 Australia / Sydney
NOU (UTC + 11):  No.26 New Caledonia / Noumea
AKL (UTC + 12):  No.27 New Zealand / Auckland
SUV (UTC + 12):  No.28 The Republic of Fiji / Suva
MDY (UTC - 11):  No.29 The United States of America / Midway Atoll
HNL (UTC - 10):  No.30 The United States of America / Honolulu
ANC (UTC - 9):   No.31 The United States of America / Anchorage
YVR (UTC - 8):   No.32 Canada / Vancouver
LAX (UTC - 8):   No.33 The United States of America / Los Angeles
DEN (UTC - 7):   No.34 The United States of America / Denver
MEX (UTC - 6):   No.35 Mexico / Mexico City
CHI (UTC - 6):   No.36 The United States of America / Chicago
NYC (UTC - 5):   No.37 The United States of America / New York
YMQ (UTC - 5):   No.38 Canada / Montreal
MAO (UTC - 4):   No.39 Brazil / Manaus
BUE (UTC - 3):   No.40 Argentina / Buenos Aires
RIO (UTC - 3):   No.41 Brazil / Rio de Janeiro
FEN (UTC - 2):   No.42 Brazil / Fernando de Noronha
PDL (UTC - 1):   No.43 Portuguese / Azores
--AvailableCities(43) end--

〇〇\node_modules\@reiwa_info_fin_corp\localtime>
```

## License
The MIT License (MIT)

Copyright (c)2023 reiwa_info_fin_corp

