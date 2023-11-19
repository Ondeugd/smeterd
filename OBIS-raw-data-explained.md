Raw output: OBIS standard 
=========================

(also see IEC 62056-21:2002 Direct local data exchange)

Snapshot of raw output:

1-3:0.2.8(50)  
0-0:1.0.0(231117134202W)  
0-0:96.1.1(4530312345678901234563436333343139)  
1-0:1.8.1(007054.890\*kWh)  
1-0:1.8.2(006526.370\*kWh)  
1-0:2.8.1(003063.961\*kWh)  
1-0:2.8.2(007038.075\*kWh)  
0-0:96.14.0(0002)  
1-0:1.7.0(00.000\*kW)  
1-0:2.7.0(02.203\*kW)  
0-0:96.7.21(00006)  
0-0:96.7.9(00008)  
1-0:99.97.0(6)(0-0:96.7.19)(200804153917S)(0000003442\*s)(200804194909S)(0000014826\*s)(211214143734W)(0000016036\*s)(220208151920W)(0000001982\*s)(220318115848W)(0000004054\*s)(220902151419S)(0000000243\*s)  
1-0:32.32.0(00006)  
1-0:52.32.0(00006)  
1-0:72.32.0(00004)  
1-0:32.36.0(00002)  
1-0:52.36.0(00002)  
1-0:72.36.0(00002)  
0-0:96.13.0()  
1-0:32.7.0(233.2\*V)  
1-0:52.7.0(240.1\*V)  
1-0:72.7.0(235.7\*V)  
1-0:31.7.0(000\*A)  
1-0:51.7.0(009\*A)  
1-0:71.7.0(000\*A)  
1-0:21.7.0(00.025\*kW)  
1-0:41.7.0(00.000\*kW)  
1-0:61.7.0(00.062\*kW)  
1-0:22.7.0(00.000\*kW)  
1-0:42.7.0(02.301\*kW)  
1-0:62.7.0(00.000\*kW)  
0-2:24.1.0(003)  
0-2:96.1.0(4730303738123456789012345430303230)  
0-2:24.2.1(231117134000W)(04473.981\*m3)  
!2FCB  

Explanation:
- 1-3:0.2.8(50)  
  Voltage sags per phase: 50
- 0-0:1.0.0(231117134202W)  
  Date-time timestamp: November 23, 2017, 13:42:02 (W indicates the time zone)
- 0-0:96.1.1(4530312345678901234563436333343139)  
  Serial number of the electricity meter: 4530312345678901234563436333343139  
- ${\textsf{\color{green}1-0:1.8.1}}$(007054.890\*kWh)  
  ${\textsf{\color{green}Positive active energy}}$ (A+) in tariff T1 [kWh]: 7054.890 kWh  
- ${\textsf{\color{green}1-0:1.8.2}}$(006526.370\*kWh)  
  ${\textsf{\color{green}Positive active energy}}$ (A+) in tariff T2 [kWh]: 6526.370 kWh
- ${\textsf{\color{green}1-0:2.8.1}}$(003063.961\*kWh)  
  ${\textsf{\color{green}Negative active energy}}$ (A-) in tariff T1 [kWh]: 3063.961 kWh
- ${\textsf{\color{green}1-0:2.8.2}}$(007038.075\*kWh)  
  ${\textsf{\color{green}Negative active energy}}$ (A-) in tariff T2 [kWh]: 7038.075 kWh
- 0-0:96.14.0(0002)  
  Number of long power failures: 2
- ${\textsf{\color{green}1-0:1.7.0}}$(00.000\*kW)  
  ${\textsf{\color{green}Positive active instantaneous power}}$ (A+) [kW]: 0.000 kW
- ${\textsf{\color{green}1-0:2.7.0}}$(02.203\*kW)  
  ${\textsf{\color{green}Negative active instantaneous power}}$ (A-) [kW]: 2.203 kW
- 0-0:96.7.21(00006)  
  Number of voltage sags in phase L1: 6
- 0-0:96.7.9(00008)  
  Number of voltage sags in phase L2: 8
- 1-0:99.97.0(6)(0-0:96.7.19)(200804153917S)(0000003442\*s)(200804194909S)(0000014826\*s)(211214143734W)(0000016036\*s)(220208151920W)(0000001982\*s)(220318115848W)(0000004054\*s)(220902151419S)(0000000243\*s)  
  Additional information related to voltage sags and timestamps, historical data
- 1-0:32.32.0(00006)  
  Number of voltage sags in phase L1
- 1-0:52.32.0(00006)  
  Number of voltage sags in phase L2
- 1-0:72.32.0(00004)  
  Number of voltage sags in phase L3
- 1-0:32.36.0(00002)  
  Number of voltage swells in phase L1
- 1-0:52.36.0(00002)  
  Number of voltage swells in phase L2
- 1-0:72.36.0(00002)  
  Number of voltage swells in phase L3
- 0-0:96.13.0()  
  No information available
- ${\textsf{\color{green}1-0:32.7.0}}$(233.2\*V)  
  ${\textsf{\color{green}Instantaneous voltage}}$(U) in ${\textsf{\color{green}phase L1}}$ [V]: 233.2 V
- ${\textsf{\color{green}1-0:52.7.0}}$(240.1\*V)  
  ${\textsf{\color{green}Instantaneous voltage}}$ (U) in ${\textsf{\color{green}phase L2}}$ [V]: 240.1 V
- ${\textsf{\color{green}1-0:72.7.0}}$(235.7\*V)  
  ${\textsf{\color{green}Instantaneous voltage}}$ (U) in ${\textsf{\color{green}phase L3}}$ [V]: 235.7 V
- ${\textsf{\color{green}1-0:31.7.0}}$(000\*A)  
  ${\textsf{\color{green}Instantaneous current}}$ (I) in ${\textsf{\color{green}phase L1}}$ [A]: 0.000 A
- ${\textsf{\color{green}1-0:51.7.0}}$(009\*A)  
  ${\textsf{\color{green}Instantaneous current}}$ (I) in ${\textsf{\color{green}phase L2}}$ [A]: 9.000 A
- ${\textsf{\color{green}1-0:71.7.0}}$(000\*A)  
  ${\textsf{\color{green}Instantaneous current}}$ (I) in ${\textsf{\color{green}phase L3}}$ [A]: 0.000 A
- ${\textsf{\color{green}1-0:21.7.0}}$(00.025\*kW)  
  ${\textsf{\color{green}Positive active instantaneous power}}$ (A+) in ${\textsf{\color{green}phase L1}}$ [kW]: 0.025 kW
- ${\textsf{\color{green}1-0:41.7.0}}$(00.000\*kW)  
  ${\textsf{\color{green}Positive active instantaneous power}}$ (A+) in ${\textsf{\color{green}phase L2}}$ [kW]: 0.000 kW
- ${\textsf{\color{green}1-0:61.7.0}}$(00.062\*kW)  
  ${\textsf{\color{green}Positive active instantaneous power}}$ (A+) in ${\textsf{\color{green}phase L1}}$ [kW]: 0.062 kW
- ${\textsf{\color{green}1-0:22.7.0}}$(00.000\*kW)  
  ${\textsf{\color{green}Negative active instantaneous power}}$ (A-) in ${\textsf{\color{green}phase L1}}$ [kW]: 0.000 kW
- ${\textsf{\color{green}1-0:42.7.0}}$(02.301\*kW)  
  ${\textsf{\color{green}Negative active instantaneous power}}$ (A-) in ${\textsf{\color{green}phase L2}}$ [kW]: 2.301 kW
- ${\textsf{\color{green}1-0:62.7.0}}$(00.000\*kW)  
  ${\textsf{\color{green}Negative active instantaneous power}}$ (A-) in ${\textsf{\color{green}phase L3}}$ [kW]: 0.000 kW
- 0-2:24.1.0(003)  
  Device type identifier: 3
- 0-2:96.1.0(4730303738123456789012345430303230)  
  Serial number of gas meter: 4730303738123456789012345430303230
- ${\textsf{\color{green}0-2:24.2.1}}$(231117134000W)(04473.981\*m3)  
  Time of last gas meter update: November 23, 2017, 13:40:00 (W indicates the time zone),
  ${\textsf{\color{green}Gas meter value: 4473.981 m³}}$
- !2FCB  
  Telegram end-marker

This breakdown is based on the structure of the OBIS codes and their meanings as described in the provided sources.


| Electricity | Voltage | Current | Power A+ (consumption)| Power A- (production) |
|---|---|---|---|---|
|L1 	| 1-0:32.7.0 | 1-0:31.7.0 | 1-0:21.7.0 | 1-0:22.7.0
|L2		| 1-0:52.7.0 | 1-0:51.7.0 | 1-0:41.7.0 | 1-0:42.7.0
|L3		| 1-0:72.7.0 | 1-0:71.7.0 | 1-0:61.7.0 | 1-0:62.7.0
||||||
|Combined || tarif 1: | 1-0:1.8.1 | 1-0:2.8.1
|		  || tarif 2: | 1-0:1.8.2 | 1-0:2.8.2
|		  || total: 	 | 1-0:1.7.0 | 1-0:2.7.0
||||||						
| **Gas** |		**consumption (m3)**
|meter 1|		0-1:24.2.1		
|meter 2|		0-2:24.2.1	

Note:
Gas meter OBIS code for measurement datetime and value in m3 is 0-2:24.2.1.
But the original python code used 0-1:24.2.1 with a slightly different regex.
I've received a new gasmeter some while back, so the 0-1 vs 0-2 might be because of that: old meter was 0-1, new one got a new id: 0-2.  
