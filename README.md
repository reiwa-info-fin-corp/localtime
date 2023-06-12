# LocalTime
# author:reiwa_info_fin_corp

When using the Date construct in Node.js to generate a date object, it is not possible to set an arbitrary time zone.
This means that the date and time will differ depending on the environment in which the date object is generated using the Date construct.

Therefore, we will create a LocalTime module that displays the local time in the arbitrarily set time zone, no matter what environment it is executed in.

The LocalTime module is named LocalTime.js.

The time zone is selected from 43 different city names.
As a mechanism, since UTC (Universal Coordinated Time) is the same no matter what environment is used, the local time of the set city name is obtained by calculating the time difference from the UTC value.

How to use
Import your own module LocalTime.js using require and store it in the constant localTime.
Execute the following methods from the localTime object.
SetLang method: If you want to use Japanese, set "JP". If not set, English is used.
SetTimeZone method: Set "3 alphabetic characters of the city name of the TimeZone". Example LON
GetAvailableCities method: Displays a list of cities that can be set.
GetUTCTimeString method: Displays "UTC time.
Example display [UTC] 2023-05-22(Mon) 06:17:54.152
GetLocalTimeString method: "Local time" is displayed.
Example display [LON] 2023-05-22(Mon) 06:17:54.152
TimeZone method: "Three alphabetic characters of the city name in the TimeZone" is retrieved. Example LON
SerialNumber method: Obtains the "city name number. Example No.01
TimeDifference method: Obtains the "difference between UTC and local time. Example UTC + 0
City method: Displays the "country / city name". Example: London, United Kingdom
FullYear method: retrieves the "year".
Month method: retrieves the "month.
Date method: retrieves the "day".
Day method: retrieves the "day of the week".
Hours method: gets the "hours.
Minutes method: retrieves the minute.
Seconds method: gets the number of seconds.
Milliseconds method: retrieves a "millisecond.


The test code LocalTime_sample.js is executed as follows.

C:\node\reiwa_info_fin_corp\LocalTime>node LocalTime_sample.js
[UTC] 2023-06-08(Thu) 06:40:18.322
[LON] 2023-06-08(Thu) 06:40:18.329
TimeZone:        LON
SerialNumber:    No.01
TimeDifference:  UTC + 0
City:            The United Kingdom / London
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           06
Minutes:         40
Seconds:         18
Milliseconds:    322
[UTC] 2023-06-08(Thu) 06:40:18.330
[MAD] 2023-06-08(Thu) 07:40:18.331
TimeZone:        MAD
SerialNumber:    No.02
TimeDifference:  UTC + 1
City:            Spain / Madrid
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           07
Minutes:         40
Seconds:         18
Milliseconds:    330
[UTC] 2023-06-08(Thu) 06:40:18.332
[PAR] 2023-06-08(Thu) 07:40:18.332
TimeZone:        PAR
SerialNumber:    No.03
TimeDifference:  UTC + 1
City:            France / Paris
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           07
Minutes:         40
Seconds:         18
Milliseconds:    332
[UTC] 2023-06-08(Thu) 06:40:18.334
[ROM] 2023-06-08(Thu) 07:40:18.334
TimeZone:        ROM
SerialNumber:    No.04
TimeDifference:  UTC + 1
City:            Italy / Rome
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           07
Minutes:         40
Seconds:         18
Milliseconds:    333
[UTC] 2023-06-08(Thu) 06:40:18.335
[BER] 2023-06-08(Thu) 07:40:18.335
TimeZone:        BER
SerialNumber:    No.05
TimeDifference:  UTC + 1
City:            Germany / Berlin
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           07
Minutes:         40
Seconds:         18
Milliseconds:    335
[UTC] 2023-06-08(Thu) 06:40:18.336
[CAI] 2023-06-08(Thu) 08:40:18.336
TimeZone:        CAI
SerialNumber:    No.06
TimeDifference:  UTC + 2
City:            Egypt / Cairo
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           08
Minutes:         40
Seconds:         18
Milliseconds:    336
[UTC] 2023-06-08(Thu) 06:40:18.337
[AHI] 2023-06-08(Thu) 08:40:18.337
TimeZone:        AHI
SerialNumber:    No.07
TimeDifference:  UTC + 2
City:            Greece / Athens
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           08
Minutes:         40
Seconds:         18
Milliseconds:    337
[UTC] 2023-06-08(Thu) 06:40:18.338
[JNB] 2023-06-08(Thu) 08:40:18.338
TimeZone:        JNB
SerialNumber:    No.08
TimeDifference:  UTC + 2
City:            South Africa / Johannesburg
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           08
Minutes:         40
Seconds:         18
Milliseconds:    338
[UTC] 2023-06-08(Thu) 06:40:18.339
[RUH] 2023-06-08(Thu) 09:40:18.339
TimeZone:        RUH
SerialNumber:    No.09
TimeDifference:  UTC + 3
City:            Saudi Arabia / Riyadh
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           09
Minutes:         40
Seconds:         18
Milliseconds:    339
[UTC] 2023-06-08(Thu) 06:40:18.343
[THR] 2023-06-08(Thu) 10:10:18.343
TimeZone:        THR
SerialNumber:    No.10
TimeDifference:  UTC + 3.5
City:            Iran / Tehran
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           10
Minutes:         10
Seconds:         18
Milliseconds:    343
[UTC] 2023-06-08(Thu) 06:40:18.344
[DXB] 2023-06-08(Thu) 10:40:18.344
TimeZone:        DXB
SerialNumber:    No.11
TimeDifference:  UTC + 4
City:            United Arab Emirates / Dubai
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           10
Minutes:         40
Seconds:         18
Milliseconds:    344
[UTC] 2023-06-08(Thu) 06:40:18.345
[KBL] 2023-06-08(Thu) 11:10:18.345
TimeZone:        KBL
SerialNumber:    No.12
TimeDifference:  UTC + 4.5
City:            Afghanistan / Kabul
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           11
Minutes:         10
Seconds:         18
Milliseconds:    345
[UTC] 2023-06-08(Thu) 06:40:18.346
[KHI] 2023-06-08(Thu) 11:40:18.346
TimeZone:        KHI
SerialNumber:    No.13
TimeDifference:  UTC + 5
City:            Pakistan / Karachi
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           11
Minutes:         40
Seconds:         18
Milliseconds:    346
[UTC] 2023-06-08(Thu) 06:40:18.347
[DEL] 2023-06-08(Thu) 12:10:18.348
TimeZone:        DEL
SerialNumber:    No.14
TimeDifference:  UTC + 5.5
City:            India/Delhi
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           12
Minutes:         10
Seconds:         18
Milliseconds:    347
[UTC] 2023-06-08(Thu) 06:40:18.348
[DAC] 2023-06-08(Thu) 12:40:18.349
TimeZone:        DAC
SerialNumber:    No.15
TimeDifference:  UTC + 6
City:            Bangladesh / Dhaka
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           12
Minutes:         40
Seconds:         18
Milliseconds:    348
[UTC] 2023-06-08(Thu) 06:40:18.349
[RGN] 2023-06-08(Thu) 13:10:18.349
TimeZone:        RGN
SerialNumber:    No.16
TimeDifference:  UTC + 6.5
City:            Myanmar / Yangon
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           13
Minutes:         10
Seconds:         18
Milliseconds:    349
[UTC] 2023-06-08(Thu) 06:40:18.350
[BKK] 2023-06-08(Thu) 13:40:18.350
TimeZone:        BKK
SerialNumber:    No.17
TimeDifference:  UTC + 7
City:            Bangkok, Thailand
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           13
Minutes:         40
Seconds:         18
Milliseconds:    350
[UTC] 2023-06-08(Thu) 06:40:18.351
[SIN] 2023-06-08(Thu) 14:40:18.351
TimeZone:        SIN
SerialNumber:    No.18
TimeDifference:  UTC + 8
City:            Singapore / Singapore
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           14
Minutes:         40
Seconds:         18
Milliseconds:    351
[UTC] 2023-06-08(Thu) 06:40:18.352
[HKG] 2023-06-08(Thu) 14:40:18.352
TimeZone:        HKG
SerialNumber:    No.19
TimeDifference:  UTC + 8
City:            Hong Kong / Hong Kong
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           14
Minutes:         40
Seconds:         18
Milliseconds:    352
[UTC] 2023-06-08(Thu) 06:40:18.353
[BJS] 2023-06-08(Thu) 14:40:18.354
TimeZone:        BJS
SerialNumber:    No.20
TimeDifference:  UTC + 8
City:            China / Beijing
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           14
Minutes:         40
Seconds:         18
Milliseconds:    353
[UTC] 2023-06-08(Thu) 06:40:18.354
[TPE] 2023-06-08(Thu) 14:40:18.355
TimeZone:        TPE
SerialNumber:    No.21
TimeDifference:  UTC + 8
City:            Taiwan / Taipei
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           14
Minutes:         40
Seconds:         18
Milliseconds:    354
[UTC] 2023-06-08(Thu) 06:40:18.358
[TYO] 2023-06-08(Thu) 15:40:18.358
TimeZone:        TYO
SerialNumber:    No.22
TimeDifference:  UTC + 9
City:            Japan / Tokyo
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           15
Minutes:         40
Seconds:         18
Milliseconds:    358
[UTC] 2023-06-08(Thu) 06:40:18.360
[SEL] 2023-06-08(Thu) 15:40:18.360
TimeZone:        SEL
SerialNumber:    No.23
TimeDifference:  UTC + 9
City:            South Korea / Seoul
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           15
Minutes:         40
Seconds:         18
Milliseconds:    360
[UTC] 2023-06-08(Thu) 06:40:18.361
[ADL] 2023-06-08(Thu) 16:10:18.361
TimeZone:        ADL
SerialNumber:    No.24
TimeDifference:  UTC + 9.5
City:            Australia / Adelaide
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           16
Minutes:         10
Seconds:         18
Milliseconds:    361
[UTC] 2023-06-08(Thu) 06:40:18.362
[SYD] 2023-06-08(Thu) 16:40:18.362
TimeZone:        SYD
SerialNumber:    No.25
TimeDifference:  UTC + 10
City:            Australia / Sydney
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           16
Minutes:         40
Seconds:         18
Milliseconds:    362
[UTC] 2023-06-08(Thu) 06:40:18.365
[NOU] 2023-06-08(Thu) 17:40:18.365
TimeZone:        NOU
SerialNumber:    No.26
TimeDifference:  UTC + 11
City:            New Caledonia / Noumea
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           17
Minutes:         40
Seconds:         18
Milliseconds:    364
[UTC] 2023-06-08(Thu) 06:40:18.366
[AKL] 2023-06-08(Thu) 18:40:18.366
TimeZone:        AKL
SerialNumber:    No.27
TimeDifference:  UTC + 12
City:            New Zealand / Auckland
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           18
Minutes:         40
Seconds:         18
Milliseconds:    366
[UTC] 2023-06-08(Thu) 06:40:18.367
[SUV] 2023-06-08(Thu) 18:40:18.367
TimeZone:        SUV
SerialNumber:    No.28
TimeDifference:  UTC + 12
City:            The Republic of Fiji / sSuva
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           18
Minutes:         40
Seconds:         18
Milliseconds:    367
[UTC] 2023-06-08(Thu) 06:40:18.369
[MDY] 2023-06-07(Wed) 19:40:18.369
TimeZone:        MDY
SerialNumber:    No.29
TimeDifference:  UTC - 11
City:            The United States of America / Midway Atoll
FullYear:        2023
Month:           06
Date:            07
Day:             Wed
Hours:           19
Minutes:         40
Seconds:         18
Milliseconds:    369
[UTC] 2023-06-08(Thu) 06:40:18.370
[HNL] 2023-06-07(Wed) 20:40:18.370
TimeZone:        HNL
SerialNumber:    No.30
TimeDifference:  UTC - 10
City:            The United States of America / Honolulu
FullYear:        2023
Month:           06
Date:            07
Day:             Wed
Hours:           20
Minutes:         40
Seconds:         18
Milliseconds:    370
[UTC] 2023-06-08(Thu) 06:40:18.374
[ANC] 2023-06-07(Wed) 21:40:18.375
TimeZone:        ANC
SerialNumber:    No.31
TimeDifference:  UTC - 9
City:            The United States of America / Anchorage
FullYear:        2023
Month:           06
Date:            07
Day:             Wed
Hours:           21
Minutes:         40
Seconds:         18
Milliseconds:    374
[UTC] 2023-06-08(Thu) 06:40:18.376
[YVR] 2023-06-07(Wed) 22:40:18.377
TimeZone:        YVR
SerialNumber:    No.32
TimeDifference:  UTC - 8
City:            Canada / Vancouver
FullYear:        2023
Month:           06
Date:            07
Day:             Wed
Hours:           22
Minutes:         40
Seconds:         18
Milliseconds:    376
[UTC] 2023-06-08(Thu) 06:40:18.378
[LAX] 2023-06-07(Wed) 22:40:18.378
TimeZone:        LAX
SerialNumber:    No.33
TimeDifference:  UTC - 8
City:            The United States of America / Los Angeles
FullYear:        2023
Month:           06
Date:            07
Day:             Wed
Hours:           22
Minutes:         40
Seconds:         18
Milliseconds:    377
[UTC] 2023-06-08(Thu) 06:40:18.379
[DEN] 2023-06-07(Wed) 23:40:18.379
TimeZone:        DEN
SerialNumber:    No.34
TimeDifference:  UTC - 7
City:            The United States of America / Denver
FullYear:        2023
Month:           06
Date:            07
Day:             Wed
Hours:           23
Minutes:         40
Seconds:         18
Milliseconds:    379
[UTC] 2023-06-08(Thu) 06:40:18.380
[MEX] 2023-06-08(Thu) 00:40:18.380
TimeZone:        MEX
SerialNumber:    No.35
TimeDifference:  UTC - 6
City:            Mexico / Mexico City
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           00
Minutes:         40
Seconds:         18
Milliseconds:    380
[UTC] 2023-06-08(Thu) 06:40:18.381
[CHI] 2023-06-08(Thu) 00:40:18.381
TimeZone:        CHI
SerialNumber:    No.36
TimeDifference:  UTC - 6
City:            The United States of America / Chicago
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           00
Minutes:         40
Seconds:         18
Milliseconds:    381
[UTC] 2023-06-08(Thu) 06:40:18.382
[NYC] 2023-06-08(Thu) 01:40:18.382
TimeZone:        NYC
SerialNumber:    No.37
TimeDifference:  UTC - 5
City:            The United States of America / New York
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           01
Minutes:         40
Seconds:         18
Milliseconds:    382
[UTC] 2023-06-08(Thu) 06:40:18.383
[YMQ] 2023-06-08(Thu) 01:40:18.383
TimeZone:        YMQ
SerialNumber:    No.38
TimeDifference:  UTC - 5
City:            Canada / Montreal
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           01
Minutes:         40
Seconds:         18
Milliseconds:    383
[UTC] 2023-06-08(Thu) 06:40:18.384
[MAO] 2023-06-08(Thu) 02:40:18.384
TimeZone:        MAO
SerialNumber:    No.39
TimeDifference:  UTC - 4
City:            Brazil / Manaus
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           02
Minutes:         40
Seconds:         18
Milliseconds:    384
[UTC] 2023-06-08(Thu) 06:40:18.385
[BUE] 2023-06-08(Thu) 03:40:18.385
TimeZone:        BUE
SerialNumber:    No.40
TimeDifference:  UTC - 3
City:            Argentina / Buenos Aires
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           03
Minutes:         40
Seconds:         18
Milliseconds:    385
[UTC] 2023-06-08(Thu) 06:40:18.386
[RIO] 2023-06-08(Thu) 03:40:18.386
TimeZone:        RIO
SerialNumber:    No.41
TimeDifference:  UTC - 3
City:            Brazil / Rio de Janeiro
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           03
Minutes:         40
Seconds:         18
Milliseconds:    386
[UTC] 2023-06-08(Thu) 06:40:18.387
[FEN] 2023-06-08(Thu) 04:40:18.387
TimeZone:        FEN
SerialNumber:    No.42
TimeDifference:  UTC - 2
City:            Brazil / Fernando de Noronha
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           04
Minutes:         40
Seconds:         18
Milliseconds:    387
[UTC] 2023-06-08(Thu) 06:40:18.389
[PDL] 2023-06-08(Thu) 05:40:18.389
TimeZone:        PDL
SerialNumber:    No.43
TimeDifference:  UTC - 1
City:            Portuguese / Azores
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           05
Minutes:         40
Seconds:         18
Milliseconds:    389
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
SUV (UTC + 12):  No.28 The Republic of Fiji / sSuva
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

C:\node\reiwa_info_fin_corp\LocalTime>

--Japanese begin--
Node.jsでDateコンストラクを使ってdateオブジェクトを生成するときに任意のタイムゾーンを設定できない。
つまり、Dateコンストラクを使ってdateオブジェクトを生成する環境によって日時が異なることを意味する。

そこで今回、どんな環境で実行しても任意で設定したタイムゾーンの現地時間を表示するLocalTimeモジュールを作る。

LocalTimeモジュールをLocalTime.jsとする。

タイムゾーンは、43種類の都市名から選択する。
仕組みとして、どんな環境で実行してもUTC(協定世界時)は同じ値になるため、UTCの値から時差を計算することによって設定した都市名の現地時間を求めている。

★使い方
自作モジュールLocalTime.jsをrequireを使ってインポートして、定数localTimeに格納する。
localTimeオブジェクトから次のメソッドを実行する。
SetLangメソッド:日本語にしたいときは「JP」を設定する。設定しない場合は英語になる。
SetTimeZoneメソッド:「TimeZoneの都市名アルファベット3文字」を設定する。 例 LON
GetAvailableCitiesメソッド:設定可能な都市名一覧を表示される。
GetUTCTimeStringメソッド:「UTC時間」を表示される。
表示例 [UTC] 2023-05-22(Mon) 06:17:54.152
GetLocalTimeStringメソッド:「現地時間」を表示される。
表示例 [LON] 2023-05-22(Mon) 06:17:54.152
TimeZoneメソッド:「TimeZoneの都市名アルファベット3文字」を取得する。 例 LON
SerialNumberメソッド:「都市名の番号」を取得する。例 No.01
TimeDifferenceメソッド:「UTCと現地時間の差」を取得する。例 UTC + 0
Cityメソッド:「国名 / 都市名」を表示する。例 イギリス / ロンドン
FullYearメソッド:「年」を取得する。
Monthメソッド:「月」を取得する。
Dateメソッド:「日」を取得する。
Dayメソッド:「曜日」を取得する。
Hoursメソッド:「時間」を取得する。
Minutesメソッド:「分」を取得する。
Secondsメソッド:「秒」を取得する。
Millisecondsメソッド:「ミリ秒」を取得する。

--Japanese end --

