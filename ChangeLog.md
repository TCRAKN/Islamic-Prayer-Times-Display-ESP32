ESP32 Islamic Prayer Time display

Basic retreival and output Completed 22 Nov 2024

23 Nov 2024 -
1. Added GeoIP library to pass Lat/Long and TZ to Muwaqqit.
2. Added Asr 2

24 Nov 2024 -
1. Found that GeoIP/IPAPI.co is not accurate for mobile/cellular networks.
To correct this, have incorporated WifiLocation library to retrieve Geolocation from Google Maps
WifiLocation cannot retrieve Timezone information, so have removed "tz" data from api_url string.
2. Added Deep Sleep code - Display times on TFT for 60 seconds and then Deep Sleep for 30 minutes
Auto-wakeup after 30 minutes.

25 Nov 2024 -
1. Added real-time update of time on TFT via use of Millis() delay.
2. Added on-screen feedback of each stage of data aquisition.
3. Added Battery percentage to TFT

26 Nov 2024 -
1. Incorporated WiFiManager to provide a WiFi Configuration Portal rather than
   having hard-coded WiFi credentials.

27 Nov 2024 -
1. Added code to restart if Lat or Long return Zero.
   This behaviour has been observed on one occasion, hence the trap.
2. Added Function to force reset of WiFi credentials
   after press and hold of right button for 3 seconds

29 Nov 2024 -
1. Tidied up WiFi connection to guide user

30 Nov 2024 -
1. Added code to timeout WiFi Config Portal after 60 seconds to avoid home screen
   remaining on if WiFi not configured.

1 Dec 2024 -
1. Added code to highlight current prayer time
2. Added Palestinial flag at start - on-screen for 3 seconds

2 Dec 2024 -
1. Added Palestinian flag when deep-sleep invoked

7 Dec 2024 - 
1. Device started to restart immediately after Deep_Sleep invoked.  
   Added ULL to multiplier factor to reserve appropriate memory for large number.
2. Added function to return reason for wake-up for diagnostics.
   Reason returned to serial port.

9 Dec 2024 -
1. Added Button on GPIO 0 as Wake-up button during Deep-Sleep

13 Dec 2024 - 
1. Added trap to detect "TOO MANY REQUESTS" from Muwaqqit and to restart device.
