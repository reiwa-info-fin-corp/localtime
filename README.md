# LocalTime
When using the Date construct in Node.js to generate a date object, it is not possible to set an arbitrary time zone.
This means that the date and time will differ depending on the environment in which the date object is generated using the Date construct.
Therefore, we will create a LocalTime module that displays the local time in an arbitrarily set time zone, no matter what environment it is executed in.
The time zone is selected from 43 different city names.
The mechanism is that UTC (Coordinated Universal Time) will be the same regardless of the environment in which it is run, so the local time of the set city name is obtained by calculating the time difference from the UTC value.

(Node.jsでDateコンストラクを使ってdateオブジェクトを生成するときに任意のタイムゾーンを設定できない。
つまり、Dateコンストラクを使ってdateオブジェクトを生成する環境によって日時が異なることを意味する。
そこで今回、どんな環境で実行しても任意で設定したタイムゾーンの現地時間を表示するLocalTimeモジュールを作る。
タイムゾーンは、43種類の都市名から選択する。
仕組みとして、どんな環境で実行してもUTC(協定世界時)は同じ値になるため、UTCの値から時差を計算することによって設定した都市名の現地時間を求めている。)

## Install it via npm
```shell
npm i @reiwa_info_fin_corp/localtime
```

## Require the Module
```shell
const localTime = require("@reiwa_info_fin_corp/localtime");
```

## To use
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
(SetTimeZoneメソッドで設定できる都市は、以下の通りです。43都市のうち、1都市のみ選択可能です。)
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
You can run the sample code.
(あなたはサンプルコードを実行できる。)
```shell
〇〇\node_modules\@reiwa_info_fin_corp\localtime>node LocalTime_sample.js
[UTC] 2023-06-08(Thu) 10:52:56.579
[LON] 2023-06-08(Thu) 10:52:56.584
TimeZone:        LON
SerialNumber:    No.01
TimeDifference:  UTC + 0
City:            The United Kingdom / London
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           10
Minutes:         52
Seconds:         56
Milliseconds:    578
[UTC] 2023-06-08(Thu) 10:52:56.587
[MAD] 2023-06-08(Thu) 11:52:56.587
TimeZone:        MAD
SerialNumber:    No.02
TimeDifference:  UTC + 1
City:            Spain / Madrid
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           11
Minutes:         52
Seconds:         56
Milliseconds:    586
[UTC] 2023-06-08(Thu) 10:52:56.589
[PAR] 2023-06-08(Thu) 11:52:56.589
TimeZone:        PAR
SerialNumber:    No.03
TimeDifference:  UTC + 1
City:            France / Paris
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           11
Minutes:         52
Seconds:         56
Milliseconds:    589
[UTC] 2023-06-08(Thu) 10:52:56.591
[ROM] 2023-06-08(Thu) 11:52:56.591
TimeZone:        ROM
SerialNumber:    No.04
TimeDifference:  UTC + 1
City:            Italy / Rome
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           11
Minutes:         52
Seconds:         56
Milliseconds:    591
[UTC] 2023-06-08(Thu) 10:52:56.592
[BER] 2023-06-08(Thu) 11:52:56.592
TimeZone:        BER
SerialNumber:    No.05
TimeDifference:  UTC + 1
City:            Germany / Berlin
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           11
Minutes:         52
Seconds:         56
Milliseconds:    592
[UTC] 2023-06-08(Thu) 10:52:56.593
[CAI] 2023-06-08(Thu) 12:52:56.593
TimeZone:        CAI
SerialNumber:    No.06
TimeDifference:  UTC + 2
City:            Egypt / Cairo
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           12
Minutes:         52
Seconds:         56
Milliseconds:    593
[UTC] 2023-06-08(Thu) 10:52:56.594
[AHI] 2023-06-08(Thu) 12:52:56.594
TimeZone:        AHI
SerialNumber:    No.07
TimeDifference:  UTC + 2
City:            Greece / Athens
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           12
Minutes:         52
Seconds:         56
Milliseconds:    594
[UTC] 2023-06-08(Thu) 10:52:56.595
[JNB] 2023-06-08(Thu) 12:52:56.596
TimeZone:        JNB
SerialNumber:    No.08
TimeDifference:  UTC + 2
City:            South Africa / Johannesburg
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           12
Minutes:         52
Seconds:         56
Milliseconds:    595
[UTC] 2023-06-08(Thu) 10:52:56.596
[RUH] 2023-06-08(Thu) 13:52:56.597
TimeZone:        RUH
SerialNumber:    No.09
TimeDifference:  UTC + 3
City:            Saudi Arabia / Riyadh
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           13
Minutes:         52
Seconds:         56
Milliseconds:    596
[UTC] 2023-06-08(Thu) 10:52:56.598
[THR] 2023-06-08(Thu) 14:22:56.598
TimeZone:        THR
SerialNumber:    No.10
TimeDifference:  UTC + 3.5
City:            Iran / Tehran
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           14
Minutes:         22
Seconds:         56
Milliseconds:    598
[UTC] 2023-06-08(Thu) 10:52:56.599
[DXB] 2023-06-08(Thu) 14:52:56.600
TimeZone:        DXB
SerialNumber:    No.11
TimeDifference:  UTC + 4
City:            United Arab Emirates / Dubai
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           14
Minutes:         52
Seconds:         56
Milliseconds:    599
[UTC] 2023-06-08(Thu) 10:52:56.600
[KBL] 2023-06-08(Thu) 15:22:56.601
TimeZone:        KBL
SerialNumber:    No.12
TimeDifference:  UTC + 4.5
City:            Afghanistan / Kabul
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           15
Minutes:         22
Seconds:         56
Milliseconds:    600
[UTC] 2023-06-08(Thu) 10:52:56.601
[KHI] 2023-06-08(Thu) 15:52:56.602
TimeZone:        KHI
SerialNumber:    No.13
TimeDifference:  UTC + 5
City:            Pakistan / Karachi
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           15
Minutes:         52
Seconds:         56
Milliseconds:    601
[UTC] 2023-06-08(Thu) 10:52:56.605
[DEL] 2023-06-08(Thu) 16:22:56.605
TimeZone:        DEL
SerialNumber:    No.14
TimeDifference:  UTC + 5.5
City:            India/Delhi
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           16
Minutes:         22
Seconds:         56
Milliseconds:    605
[UTC] 2023-06-08(Thu) 10:52:56.606
[DAC] 2023-06-08(Thu) 16:52:56.606
TimeZone:        DAC
SerialNumber:    No.15
TimeDifference:  UTC + 6
City:            Bangladesh / Dhaka
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           16
Minutes:         52
Seconds:         56
Milliseconds:    606
[UTC] 2023-06-08(Thu) 10:52:56.607
[RGN] 2023-06-08(Thu) 17:22:56.607
TimeZone:        RGN
SerialNumber:    No.16
TimeDifference:  UTC + 6.5
City:            Myanmar / Yangon
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           17
Minutes:         22
Seconds:         56
Milliseconds:    607
[UTC] 2023-06-08(Thu) 10:52:56.608
[BKK] 2023-06-08(Thu) 17:52:56.608
TimeZone:        BKK
SerialNumber:    No.17
TimeDifference:  UTC + 7
City:            Bangkok, Thailand
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           17
Minutes:         52
Seconds:         56
Milliseconds:    608
[UTC] 2023-06-08(Thu) 10:52:56.609
[SIN] 2023-06-08(Thu) 18:52:56.609
TimeZone:        SIN
SerialNumber:    No.18
TimeDifference:  UTC + 8
City:            Singapore / Singapore
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           18
Minutes:         52
Seconds:         56
Milliseconds:    609
[UTC] 2023-06-08(Thu) 10:52:56.610
[HKG] 2023-06-08(Thu) 18:52:56.610
TimeZone:        HKG
SerialNumber:    No.19
TimeDifference:  UTC + 8
City:            Hong Kong / Hong Kong
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           18
Minutes:         52
Seconds:         56
Milliseconds:    610
[UTC] 2023-06-08(Thu) 10:52:56.611
[BJS] 2023-06-08(Thu) 18:52:56.611
TimeZone:        BJS
SerialNumber:    No.20
TimeDifference:  UTC + 8
City:            China / Beijing
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           18
Minutes:         52
Seconds:         56
Milliseconds:    611
[UTC] 2023-06-08(Thu) 10:52:56.612
[TPE] 2023-06-08(Thu) 18:52:56.612
TimeZone:        TPE
SerialNumber:    No.21
TimeDifference:  UTC + 8
City:            Taiwan / Taipei
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           18
Minutes:         52
Seconds:         56
Milliseconds:    612
[UTC] 2023-06-08(Thu) 10:52:56.613
[TYO] 2023-06-08(Thu) 19:52:56.613
TimeZone:        TYO
SerialNumber:    No.22
TimeDifference:  UTC + 9
City:            Japan / Tokyo
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           19
Minutes:         52
Seconds:         56
Milliseconds:    613
[UTC] 2023-06-08(Thu) 10:52:56.614
[SEL] 2023-06-08(Thu) 19:52:56.614
TimeZone:        SEL
SerialNumber:    No.23
TimeDifference:  UTC + 9
City:            South Korea / Seoul
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           19
Minutes:         52
Seconds:         56
Milliseconds:    614
[UTC] 2023-06-08(Thu) 10:52:56.615
[ADL] 2023-06-08(Thu) 20:22:56.615
TimeZone:        ADL
SerialNumber:    No.24
TimeDifference:  UTC + 9.5
City:            Australia / Adelaide
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           20
Minutes:         22
Seconds:         56
Milliseconds:    615
[UTC] 2023-06-08(Thu) 10:52:56.616
[SYD] 2023-06-08(Thu) 20:52:56.616
TimeZone:        SYD
SerialNumber:    No.25
TimeDifference:  UTC + 10
City:            Australia / Sydney
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           20
Minutes:         52
Seconds:         56
Milliseconds:    616
[UTC] 2023-06-08(Thu) 10:52:56.618
[NOU] 2023-06-08(Thu) 21:52:56.618
TimeZone:        NOU
SerialNumber:    No.26
TimeDifference:  UTC + 11
City:            New Caledonia / Noumea
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           21
Minutes:         52
Seconds:         56
Milliseconds:    618
[UTC] 2023-06-08(Thu) 10:52:56.621
[AKL] 2023-06-08(Thu) 22:52:56.621
TimeZone:        AKL
SerialNumber:    No.27
TimeDifference:  UTC + 12
City:            New Zealand / Auckland
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           22
Minutes:         52
Seconds:         56
Milliseconds:    621
[UTC] 2023-06-08(Thu) 10:52:56.622
[SUV] 2023-06-08(Thu) 22:52:56.622
TimeZone:        SUV
SerialNumber:    No.28
TimeDifference:  UTC + 12
City:            The Republic of Fiji / sSuva
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           22
Minutes:         52
Seconds:         56
Milliseconds:    622
[UTC] 2023-06-08(Thu) 10:52:56.623
[MDY] 2023-06-07(Wed) 23:52:56.623
TimeZone:        MDY
SerialNumber:    No.29
TimeDifference:  UTC - 11
City:            The United States of America / Midway Atoll
FullYear:        2023
Month:           06
Date:            07
Day:             Wed
Hours:           23
Minutes:         52
Seconds:         56
Milliseconds:    623
[UTC] 2023-06-08(Thu) 10:52:56.624
[HNL] 2023-06-08(Thu) 00:52:56.624
TimeZone:        HNL
SerialNumber:    No.30
TimeDifference:  UTC - 10
City:            The United States of America / Honolulu
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           00
Minutes:         52
Seconds:         56
Milliseconds:    624
[UTC] 2023-06-08(Thu) 10:52:56.625
[ANC] 2023-06-08(Thu) 01:52:56.625
TimeZone:        ANC
SerialNumber:    No.31
TimeDifference:  UTC - 9
City:            The United States of America / Anchorage
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           01
Minutes:         52
Seconds:         56
Milliseconds:    625
[UTC] 2023-06-08(Thu) 10:52:56.626
[YVR] 2023-06-08(Thu) 02:52:56.626
TimeZone:        YVR
SerialNumber:    No.32
TimeDifference:  UTC - 8
City:            Canada / Vancouver
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           02
Minutes:         52
Seconds:         56
Milliseconds:    626
[UTC] 2023-06-08(Thu) 10:52:56.627
[LAX] 2023-06-08(Thu) 02:52:56.627
TimeZone:        LAX
SerialNumber:    No.33
TimeDifference:  UTC - 8
City:            The United States of America / Los Angeles
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           02
Minutes:         52
Seconds:         56
Milliseconds:    627
[UTC] 2023-06-08(Thu) 10:52:56.628
[DEN] 2023-06-08(Thu) 03:52:56.628
TimeZone:        DEN
SerialNumber:    No.34
TimeDifference:  UTC - 7
City:            The United States of America / Denver
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           03
Minutes:         52
Seconds:         56
Milliseconds:    628
[UTC] 2023-06-08(Thu) 10:52:56.629
[MEX] 2023-06-08(Thu) 04:52:56.629
TimeZone:        MEX
SerialNumber:    No.35
TimeDifference:  UTC - 6
City:            Mexico / Mexico City
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           04
Minutes:         52
Seconds:         56
Milliseconds:    628
[UTC] 2023-06-08(Thu) 10:52:56.629
[CHI] 2023-06-08(Thu) 04:52:56.629
TimeZone:        CHI
SerialNumber:    No.36
TimeDifference:  UTC - 6
City:            The United States of America / Chicago
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           04
Minutes:         52
Seconds:         56
Milliseconds:    629
[UTC] 2023-06-08(Thu) 10:52:56.630
[NYC] 2023-06-08(Thu) 05:52:56.630
TimeZone:        NYC
SerialNumber:    No.37
TimeDifference:  UTC - 5
City:            The United States of America / New York
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           05
Minutes:         52
Seconds:         56
Milliseconds:    630
[UTC] 2023-06-08(Thu) 10:52:56.631
[YMQ] 2023-06-08(Thu) 05:52:56.631
TimeZone:        YMQ
SerialNumber:    No.38
TimeDifference:  UTC - 5
City:            Canada / Montreal
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           05
Minutes:         52
Seconds:         56
Milliseconds:    631
[UTC] 2023-06-08(Thu) 10:52:56.632
[MAO] 2023-06-08(Thu) 06:52:56.632
TimeZone:        MAO
SerialNumber:    No.39
TimeDifference:  UTC - 4
City:            Brazil / Manaus
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           06
Minutes:         52
Seconds:         56
Milliseconds:    632
[UTC] 2023-06-08(Thu) 10:52:56.633
[BUE] 2023-06-08(Thu) 07:52:56.633
TimeZone:        BUE
SerialNumber:    No.40
TimeDifference:  UTC - 3
City:            Argentina / Buenos Aires
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           07
Minutes:         52
Seconds:         56
Milliseconds:    633
[UTC] 2023-06-08(Thu) 10:52:56.634
[RIO] 2023-06-08(Thu) 07:52:56.636
TimeZone:        RIO
SerialNumber:    No.41
TimeDifference:  UTC - 3
City:            Brazil / Rio de Janeiro
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           07
Minutes:         52
Seconds:         56
Milliseconds:    634
[UTC] 2023-06-08(Thu) 10:52:56.637
[FEN] 2023-06-08(Thu) 08:52:56.637
TimeZone:        FEN
SerialNumber:    No.42
TimeDifference:  UTC - 2
City:            Brazil / Fernando de Noronha
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           08
Minutes:         52
Seconds:         56
Milliseconds:    637
[UTC] 2023-06-08(Thu) 10:52:56.638
[PDL] 2023-06-08(Thu) 09:52:56.638
TimeZone:        PDL
SerialNumber:    No.43
TimeDifference:  UTC - 1
City:            Portuguese / Azores
FullYear:        2023
Month:           06
Date:            08
Day:             Thu
Hours:           09
Minutes:         52
Seconds:         56
Milliseconds:    638
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

〇〇\node_modules\@reiwa_info_fin_corp\localtime>
```

## License
The MIT License (MIT)

Copyright (c)2023 reiwa_info_fin_corp

