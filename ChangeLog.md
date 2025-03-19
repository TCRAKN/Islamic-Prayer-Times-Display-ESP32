ESP32 Islamic Prayer Time display

Basic retreival and output Completed 22 Nov 2024 - V1.00

23 Nov 2024 - V1.10
1. Added GeoIP library to pass Lat/Long and TZ to Muwaqqit.
2. Added Asr 2

24 Nov 2024 - V2.00
1. Found that GeoIP/IPAPI.co is not accurate for mobile/cellular networks.
To correct this, have incorporated WifiLocation library to retrieve Geolocation from Google Maps
WifiLocation cannot retrieve Timezone information, so have removed "tz" data from api_url string.
2. Added Deep Sleep code - Display times on TFT for 60 seconds and then Deep Sleep for 30 minutes
Auto-wakeup after 30 minutes.

25 Nov 2024 - V2.10
1. Added real-time update of time on TFT via use of Millis() delay.
2. Added on-screen feedback of each stage of data aquisition.
3. Added Battery percentage to TFT

26 Nov 2024 - V3.00
1. Incorporated WiFiManager to provide a WiFi Configuration Portal rather than
   having hard-coded WiFi credentials.

27 Nov 2024 - V3.10
1. Added code to restart if Lat or Long return Zero.
   This behaviour has been observed on one occasion, hence the trap.
2. Added Function to force reset of WiFi credentials
   after press and hold of right button for 3 seconds

29 Nov 2024 - V3.20
1. Tidied up WiFi connection to guide user

30 Nov 2024 - V3.30
1. Added code to timeout WiFi Config Portal after 60 seconds to avoid home screen
   remaining on if WiFi not configured.

1 Dec 2024 - V4.00
1. Added code to highlight current prayer time
2. Added Palestinial flag at start - on-screen for 3 seconds

2 Dec 2024 - V4.10
1. Added Palestinian flag when deep-sleep invoked

7 Dec 2024 - V4.20
1. Device started to restart immediately after Deep_Sleep invoked.  
   Added ULL to multiplier factor to reserve appropriate memory for large number.
2. Added function to return reason for wake-up for diagnostics.
   Reason returned to serial port.

9 Dec 2024 - V4.30
1. Added Button on GPIO 0 as Wake-up button during Deep-Sleep.

13 Dec 2024 - V4.40 
1. Added trap to detect "TOO MANY REQUESTS" from Muwaqqit and to restart device.

21 Dec 2024 - V5.00
1. Added function [getTZ()] to automatically determine Timezone, DST Offset and UTC Offset via Google Maps Timezone API.

23 Dec 2024 - V5.10
1. Added test for battery charging and to display "Charging" on TFT.  Otherwise, display battery %.

24 Dec 2024 - V6.00
1. Display location address to confirm to user that prayer times are accurate.

27 Dec 2024 - V7.00
1. TFT display now enters Low Power mode before ESP32 enters Deep Sleep mode.

27 Dec 2024 - V7.10
1. Incorporated Battery18650Stats library for accurate battery monitoring

28 Dec 2024 - V8.00
1. Display map of current location along with line marking direction of Qibla.  Remains on screen for 20 seconds 

01 Jan 2025 - V9.00
1. During Map view, use buttons to zoom in and out. 
2. Both buttons pressed - Toggle map between Roadmap and Hybrid.
3. If no buttons pressed for 20 seconds, exit map display routine

07 Jan 2025 - V9.10
1. Bypass Address and map display if bottom button is held during startup

11 Jan 2025 - V9.20
1. Corrected comparison of time boundary-checks for highlighting current prayer time.

09 Feb 2025 - V9.21
1. Added current time sync during display of prayer times. Mitigating incorrect highlighting of prayer time when close to transition.

10 Mar 2025 - V9.22
1. Corrected non-update of DST and UTC offset - Shown time was incorrect.  Removed "const" from initial definition of gmt_offset_sec & daylight_offset_sec

19 Mar 2025 - V9.23
1. Added '°' sign to TFT display of Fajr and Isha angles.

Mecca Lat/Long - 21.4224779,39.8262775
