# Micorpython DS1302 RTC Clock driver
This is a pure Micropython DS1302 RTC Clock driver. This is based on microbit code of microbit-lib https://github.com/shaoziyang/microbit-lib

This has been tested and working on ESP32 but should work with any micropython supported device.

# Dirver documentation
(Adapted from https://github.com/shaoziyang/microbit-lib/blob/master/misc/DS1302/README.md)

DS1302 is real-time clock (RTC) with serial interface, 31 * 8 data ram.

![](ds1302.jpg)


## API

* **start()**  
start RTC.  

* **stop()**  
stop/pause RTC

* **DateTime(DT = None)**  
get / set DateTime. If no paramter given, it will return current datetime, otherwise it will set datatime.  
datatime format: [Year, month, day, weekday, hour, minute, second]

* **Year(year = None)**  
get / set year.  

* **Month(month = None)**  
get / set month.  

* **Day(day = None)**  
get / set day.  

* **Weekday(weekday = None)**  
get / set month.  

* **Hour(hour = None)**  
get / set hour.  

* **Minute(minute = None)**  
get / set minute.  

* **Second(second = None)**  
get / set second.  

* **ram(reg, dat = None)**  
get / set ram data (31 bytes).  


## example

```
from machine import Pin
import DS1302

ds = DS1302.DS1302(Pin(5),Pin(18),Pin(19))

ds.DateTime()
ds.DateTime([2018, 3, 9, 4, 23, 0, 1, 0])

ds.Hour()
ds.Second(10)
```
