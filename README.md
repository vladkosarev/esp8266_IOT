esp8266_IOT
===========

__Trying out different things using official SDK + IOT Example__

This is based on a copy of Espressif's SDK+IoT demo.

Here are some changes -  
Rudimentary CORS support. Webserver now understands ajax requests (did it for mobile app).

Added another sensor - RAIN, just to demo what adding a simple sensor looks like in code. For now it's just doing adc read but since ESP-01 doesn't have ADC pin out it's just sending garbage data. Will actually add a sensor to this if GPIO00 and GPIO02 allow.

In user_config you can define DEEP_SLEEP_OVERRIDE. This will override deep sleep settings. I added it because I have ESP-01 which is missing GPIO16 pin so esp never wakes up from deep sleep. I wanted to make a clear define for that scenario. As soon as I get ESP-03 I'll just remove that define and off we go.

You can direct all os_printf to UART0 by defining TRACE_TO_UART0 in uart.c

You can enable more tracing by defining TRACE_ESPCONN in espconn.h

