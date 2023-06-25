# LocalTime
When using the Date construct in Node.js to generate a date object, it is not possible to set an arbitrary time zone.
This means that the date and time will differ depending on the environment in which the date object is generated using the Date construct.
Therefore, we will create a LocalTime module that displays the local time in an arbitrarily set time zone, no matter what environment it is executed in.
The time zone is selected from 43 different cities.
The way it works is that UTC(Coordinated Universal Time) will have the same value no matter what environment it is run in, so the UTC value and the city's time difference value are used to find the local time for the set city.

(Node.jsでDateコンストラクを使ってdateオブジェクトを生成するときに任意のタイムゾーンを設定できない。
つまり、Dateコンストラクを使ってdateオブジェクトを生成する環境によって日時が異なることを意味する。
そこで今回、どんな環境で実行しても任意で設定したタイムゾーンの現地時間を表示するLocalTimeモジュールを作る。
タイムゾーンは、43種類の都市から選択する。
仕組みとして、どんな環境で実行してもUTC(協定世界時)は同じ値になるため、UTCの値と都市の時差の値を使用して、設定した都市の現地時間を求める。)

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
On the other hand, when the Get method is executed, no processing is performed in the LocalTime module to obtain UTC time and the local time of the set city.
When the Get method is executed, the year, month, day, weekday, hour, minute, second, and millisecond of the local time can be obtained.
This local time is exactly the same local time obtained when executing the SetTimeZone method or the GetUTCTimeString method or the GetLocalTimeString method before executing the Get method.

(SetTimeZoneメソッド、GetUTCTimeStringメソッド、GetLocalTimeStringメソッドを実行する際は、必ずLocalTimeモジュール内でUTC時間と設定した都市の現地時間を求める処理が実行される。  
一方、Getメソッドを実行する際は、LocalTimeモジュール内でUTC時間と設定した都市の現地時間を求める処理は一切行われない。Getメソッドを実行すると、現地時間の年、月、日、曜日、時、分、秒、ミリ秒を取得することができる。この現地時間は、Getメソッド実行前に、SetTimeZoneメソッドまたはGetUTCTimeStringメソッドまたはGetLocalTimeStringメソッドを実行時に求めた現地時間と全く同じ現地時間である。)

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

> @reiwa_info_fin_corp/localtime@〇.〇.〇 test
> node LocalTime_sample.js

[UTC] 2023-06-25(Sun) 22:09:03.136
[LON] 2023-06-25(Sun) 22:09:03.139
TimeZone:        LON
SerialNumber:    No.01
TimeDifference:  UTC + 0
City:            The United Kingdom / London
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           22
Minutes:         09
Seconds:         03
Milliseconds:    136
[UTC] 2023-06-25(Sun) 22:09:03.140
[MAD] 2023-06-25(Sun) 23:09:03.140
TimeZone:        MAD
SerialNumber:    No.02
TimeDifference:  UTC + 1
City:            Spain / Madrid
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           23
Minutes:         09
Seconds:         03
Milliseconds:    140
[UTC] 2023-06-25(Sun) 22:09:03.141
[PAR] 2023-06-25(Sun) 23:09:03.141
TimeZone:        PAR
SerialNumber:    No.03
TimeDifference:  UTC + 1
City:            France / Paris
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           23
Minutes:         09
Seconds:         03
Milliseconds:    141
[UTC] 2023-06-25(Sun) 22:09:03.141
[ROM] 2023-06-25(Sun) 23:09:03.141
TimeZone:        ROM
SerialNumber:    No.04
TimeDifference:  UTC + 1
City:            Italy / Rome
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           23
Minutes:         09
Seconds:         03
Milliseconds:    141
[UTC] 2023-06-25(Sun) 22:09:03.142
[BER] 2023-06-25(Sun) 23:09:03.142
TimeZone:        BER
SerialNumber:    No.05
TimeDifference:  UTC + 1
City:            Germany / Berlin
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           23
Minutes:         09
Seconds:         03
Milliseconds:    142
[UTC] 2023-06-25(Sun) 22:09:03.142
[CAI] 2023-06-26(Mon) 00:09:03.142
TimeZone:        CAI
SerialNumber:    No.06
TimeDifference:  UTC + 2
City:            Egypt / Cairo
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           00
Minutes:         09
Seconds:         03
Milliseconds:    142
[UTC] 2023-06-25(Sun) 22:09:03.143
[AHI] 2023-06-26(Mon) 00:09:03.143
TimeZone:        AHI
SerialNumber:    No.07
TimeDifference:  UTC + 2
City:            Greece / Athens
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           00
Minutes:         09
Seconds:         03
Milliseconds:    142
[UTC] 2023-06-25(Sun) 22:09:03.143
[JNB] 2023-06-26(Mon) 00:09:03.143
TimeZone:        JNB
SerialNumber:    No.08
TimeDifference:  UTC + 2
City:            South Africa / Johannesburg
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           00
Minutes:         09
Seconds:         03
Milliseconds:    143
[UTC] 2023-06-25(Sun) 22:09:03.144
[RUH] 2023-06-26(Mon) 01:09:03.144
TimeZone:        RUH
SerialNumber:    No.09
TimeDifference:  UTC + 3
City:            Saudi Arabia / Riyadh
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           01
Minutes:         09
Seconds:         03
Milliseconds:    143
[UTC] 2023-06-25(Sun) 22:09:03.144
[THR] 2023-06-26(Mon) 01:39:03.144
TimeZone:        THR
SerialNumber:    No.10
TimeDifference:  UTC + 3.5
City:            Iran / Tehran
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           01
Minutes:         39
Seconds:         03
Milliseconds:    144
[UTC] 2023-06-25(Sun) 22:09:03.144
[DXB] 2023-06-26(Mon) 02:09:03.144
TimeZone:        DXB
SerialNumber:    No.11
TimeDifference:  UTC + 4
City:            United Arab Emirates / Dubai
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           02
Minutes:         09
Seconds:         03
Milliseconds:    144
[UTC] 2023-06-25(Sun) 22:09:03.145
[KBL] 2023-06-26(Mon) 02:39:03.145
TimeZone:        KBL
SerialNumber:    No.12
TimeDifference:  UTC + 4.5
City:            Afghanistan / Kabul
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           02
Minutes:         39
Seconds:         03
Milliseconds:    145
[UTC] 2023-06-25(Sun) 22:09:03.146
[KHI] 2023-06-26(Mon) 03:09:03.146
TimeZone:        KHI
SerialNumber:    No.13
TimeDifference:  UTC + 5
City:            Pakistan / Karachi
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           03
Minutes:         09
Seconds:         03
Milliseconds:    145
[UTC] 2023-06-25(Sun) 22:09:03.146
[DEL] 2023-06-26(Mon) 03:39:03.146
TimeZone:        DEL
SerialNumber:    No.14
TimeDifference:  UTC + 5.5
City:            India/Delhi
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           03
Minutes:         39
Seconds:         03
Milliseconds:    146
[UTC] 2023-06-25(Sun) 22:09:03.146
[DAC] 2023-06-26(Mon) 04:09:03.146
TimeZone:        DAC
SerialNumber:    No.15
TimeDifference:  UTC + 6
City:            Bangladesh / Dhaka
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           04
Minutes:         09
Seconds:         03
Milliseconds:    146
[UTC] 2023-06-25(Sun) 22:09:03.147
[RGN] 2023-06-26(Mon) 04:39:03.147
TimeZone:        RGN
SerialNumber:    No.16
TimeDifference:  UTC + 6.5
City:            Myanmar / Yangon
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           04
Minutes:         39
Seconds:         03
Milliseconds:    147
[UTC] 2023-06-25(Sun) 22:09:03.147
[BKK] 2023-06-26(Mon) 05:09:03.147
TimeZone:        BKK
SerialNumber:    No.17
TimeDifference:  UTC + 7
City:            Bangkok, Thailand
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           05
Minutes:         09
Seconds:         03
Milliseconds:    147
[UTC] 2023-06-25(Sun) 22:09:03.147
[SIN] 2023-06-26(Mon) 06:09:03.147
TimeZone:        SIN
SerialNumber:    No.18
TimeDifference:  UTC + 8
City:            Singapore / Singapore
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           06
Minutes:         09
Seconds:         03
Milliseconds:    147
[UTC] 2023-06-25(Sun) 22:09:03.148
[HKG] 2023-06-26(Mon) 06:09:03.148
TimeZone:        HKG
SerialNumber:    No.19
TimeDifference:  UTC + 8
City:            Hong Kong / Hong Kong
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           06
Minutes:         09
Seconds:         03
Milliseconds:    147
[UTC] 2023-06-25(Sun) 22:09:03.148
[BJS] 2023-06-26(Mon) 06:09:03.148
TimeZone:        BJS
SerialNumber:    No.20
TimeDifference:  UTC + 8
City:            China / Beijing
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           06
Minutes:         09
Seconds:         03
Milliseconds:    148
[UTC] 2023-06-25(Sun) 22:09:03.148
[TPE] 2023-06-26(Mon) 06:09:03.148
TimeZone:        TPE
SerialNumber:    No.21
TimeDifference:  UTC + 8
City:            Taiwan / Taipei
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           06
Minutes:         09
Seconds:         03
Milliseconds:    148
[UTC] 2023-06-25(Sun) 22:09:03.148
[TYO] 2023-06-26(Mon) 07:09:03.148
TimeZone:        TYO
SerialNumber:    No.22
TimeDifference:  UTC + 9
City:            Japan / Tokyo
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           07
Minutes:         09
Seconds:         03
Milliseconds:    148
[UTC] 2023-06-25(Sun) 22:09:03.149
[SEL] 2023-06-26(Mon) 07:09:03.149
TimeZone:        SEL
SerialNumber:    No.23
TimeDifference:  UTC + 9
City:            South Korea / Seoul
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           07
Minutes:         09
Seconds:         03
Milliseconds:    149
[UTC] 2023-06-25(Sun) 22:09:03.149
[ADL] 2023-06-26(Mon) 07:39:03.149
TimeZone:        ADL
SerialNumber:    No.24
TimeDifference:  UTC + 9.5
City:            Australia / Adelaide
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           07
Minutes:         39
Seconds:         03
Milliseconds:    149
[UTC] 2023-06-25(Sun) 22:09:03.149
[SYD] 2023-06-26(Mon) 08:09:03.149
TimeZone:        SYD
SerialNumber:    No.25
TimeDifference:  UTC + 10
City:            Australia / Sydney
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           08
Minutes:         09
Seconds:         03
Milliseconds:    149
[UTC] 2023-06-25(Sun) 22:09:03.150
[NOU] 2023-06-26(Mon) 09:09:03.150
TimeZone:        NOU
SerialNumber:    No.26
TimeDifference:  UTC + 11
City:            New Caledonia / Noumea
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           09
Minutes:         09
Seconds:         03
Milliseconds:    149
[UTC] 2023-06-25(Sun) 22:09:03.150
[AKL] 2023-06-26(Mon) 10:09:03.150
TimeZone:        AKL
SerialNumber:    No.27
TimeDifference:  UTC + 12
City:            New Zealand / Auckland
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           10
Minutes:         09
Seconds:         03
Milliseconds:    150
[UTC] 2023-06-25(Sun) 22:09:03.151
[SUV] 2023-06-26(Mon) 10:09:03.151
TimeZone:        SUV
SerialNumber:    No.28
TimeDifference:  UTC + 12
City:            The Republic of Fiji / Suva
FullYear:        2023
Month:           06
Date:            26
Day:             Mon
Hours:           10
Minutes:         09
Seconds:         03
Milliseconds:    151
[UTC] 2023-06-25(Sun) 22:09:03.151
[MDY] 2023-06-25(Sun) 11:09:03.151
TimeZone:        MDY
SerialNumber:    No.29
TimeDifference:  UTC - 11
City:            The United States of America / Midway Atoll
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           11
Minutes:         09
Seconds:         03
Milliseconds:    151
[UTC] 2023-06-25(Sun) 22:09:03.151
[HNL] 2023-06-25(Sun) 12:09:03.151
TimeZone:        HNL
SerialNumber:    No.30
TimeDifference:  UTC - 10
City:            The United States of America / Honolulu
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           12
Minutes:         09
Seconds:         03
Milliseconds:    151
[UTC] 2023-06-25(Sun) 22:09:03.151
[ANC] 2023-06-25(Sun) 13:09:03.151
TimeZone:        ANC
SerialNumber:    No.31
TimeDifference:  UTC - 9
City:            The United States of America / Anchorage
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           13
Minutes:         09
Seconds:         03
Milliseconds:    151
[UTC] 2023-06-25(Sun) 22:09:03.152
[YVR] 2023-06-25(Sun) 14:09:03.152
TimeZone:        YVR
SerialNumber:    No.32
TimeDifference:  UTC - 8
City:            Canada / Vancouver
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           14
Minutes:         09
Seconds:         03
Milliseconds:    152
[UTC] 2023-06-25(Sun) 22:09:03.152
[LAX] 2023-06-25(Sun) 14:09:03.152
TimeZone:        LAX
SerialNumber:    No.33
TimeDifference:  UTC - 8
City:            The United States of America / Los Angeles
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           14
Minutes:         09
Seconds:         03
Milliseconds:    152
[UTC] 2023-06-25(Sun) 22:09:03.152
[DEN] 2023-06-25(Sun) 15:09:03.152
TimeZone:        DEN
SerialNumber:    No.34
TimeDifference:  UTC - 7
City:            The United States of America / Denver
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           15
Minutes:         09
Seconds:         03
Milliseconds:    152
[UTC] 2023-06-25(Sun) 22:09:03.152
[MEX] 2023-06-25(Sun) 16:09:03.153
TimeZone:        MEX
SerialNumber:    No.35
TimeDifference:  UTC - 6
City:            Mexico / Mexico City
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           16
Minutes:         09
Seconds:         03
Milliseconds:    152
[UTC] 2023-06-25(Sun) 22:09:03.153
[CHI] 2023-06-25(Sun) 16:09:03.153
TimeZone:        CHI
SerialNumber:    No.36
TimeDifference:  UTC - 6
City:            The United States of America / Chicago
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           16
Minutes:         09
Seconds:         03
Milliseconds:    153
[UTC] 2023-06-25(Sun) 22:09:03.153
[NYC] 2023-06-25(Sun) 17:09:03.153
TimeZone:        NYC
SerialNumber:    No.37
TimeDifference:  UTC - 5
City:            The United States of America / New York
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           17
Minutes:         09
Seconds:         03
Milliseconds:    153
[UTC] 2023-06-25(Sun) 22:09:03.153
[YMQ] 2023-06-25(Sun) 17:09:03.153
TimeZone:        YMQ
SerialNumber:    No.38
TimeDifference:  UTC - 5
City:            Canada / Montreal
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           17
Minutes:         09
Seconds:         03
Milliseconds:    153
[UTC] 2023-06-25(Sun) 22:09:03.154
[MAO] 2023-06-25(Sun) 18:09:03.154
TimeZone:        MAO
SerialNumber:    No.39
TimeDifference:  UTC - 4
City:            Brazil / Manaus
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           18
Minutes:         09
Seconds:         03
Milliseconds:    154
[UTC] 2023-06-25(Sun) 22:09:03.154
[BUE] 2023-06-25(Sun) 19:09:03.154
TimeZone:        BUE
SerialNumber:    No.40
TimeDifference:  UTC - 3
City:            Argentina / Buenos Aires
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           19
Minutes:         09
Seconds:         03
Milliseconds:    154
[UTC] 2023-06-25(Sun) 22:09:03.154
[RIO] 2023-06-25(Sun) 19:09:03.154
TimeZone:        RIO
SerialNumber:    No.41
TimeDifference:  UTC - 3
City:            Brazil / Rio de Janeiro
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           19
Minutes:         09
Seconds:         03
Milliseconds:    154
[UTC] 2023-06-25(Sun) 22:09:03.155
[FEN] 2023-06-25(Sun) 20:09:03.155
TimeZone:        FEN
SerialNumber:    No.42
TimeDifference:  UTC - 2
City:            Brazil / Fernando de Noronha
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           20
Minutes:         09
Seconds:         03
Milliseconds:    154
[UTC] 2023-06-25(Sun) 22:09:03.155
[PDL] 2023-06-25(Sun) 21:09:03.155
TimeZone:        PDL
SerialNumber:    No.43
TimeDifference:  UTC - 1
City:            Portuguese / Azores
FullYear:        2023
Month:           06
Date:            25
Day:             Sun
Hours:           21
Minutes:         09
Seconds:         03
Milliseconds:    155
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

