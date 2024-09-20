[Document](https://wiki.dfrobot.com/APRS_Weather_Station_Sensor_Kit_SEN0186)

## Specification
- Operating Voltage: 3.3V
- Temperature Range: -40~ 125℃
- Humidity Range: 0~100%
## Board Overview

![[Pasted image 20240703012818.png]]

| No. | Desc                                            |
| --- | ----------------------------------------------- |
| A   | PMS5003,PMS5003ST                               |
| B   | Rainfall                                        |
| C   | Wind speed and direction                        |
| D   | Data output                                     |
| E   | Indicator light                                 |
| F   | Serial Port                                     |
| I   | I2C temperature, humidity and air pressure port |
| J1  | Metric & Imperialb Jumpers                      |
| J2  | Data interface 2400/9600 baud rate Jumpers      |
## Indicator Light
- DAT flashes synchronously when sending data
- TX flashes synchronously when sampling wind speed
- RX flashes synchronously when rain sensor is working
## Data Output Format
	37 bytes / second (include CR/LF)
Example:
```
c000s000g000t082r000p000h48b10022*3C
```

- c000: Wind direction angle, unit: degree.
- s000: wind speed in 1 minute, unit: miles per hour
- g000: the highest wind speed in 5 minutes, unit: miles per hour
- t086: Temperature (Fahrenheit)
- r000: Rainfall in 1 hour (0.01 inches)
- p000: Rainfall in 24 hours (0.01 inches)
- h53: Humidity (00% = 99%)
- b10022: Air pressure (0.1 hpa)

## References
- [DWM-51WS3 APRS weather station EVB board](https://dwmzone.com/en/usd6-usd10/687-dwm-51ws3-aprs-weather-station-evb-board.html)
- [WeatherPi:一個 Raspberry Pi 和 Python 的微型氣象站專案](https://speakerdeck.com/piepie_tw/introduction-to-weather-pi?slide=52)