# Islamic-Prayer-Times-Display-ESP32

![Grounds](https://github.com/user-attachments/assets/7610a479-7d6d-436f-ac5a-9a5c6013abd8)

This is an Arduino IDE project that uses a readily-available development board that includes a small TFT 
screen - LilyGo TTGO T-Display - to retrieve and display Islamic prayer time data according to the 
geolocation of the user.

Follow my Instructable here:  https://www.instructables.com/Islamic-Prayer-Times-ESP32-TTGO-T-Display/

The project uses JSON data from https://muwaqqit.com for prayer time data and Google for Geolocation.

The TTGO T-Display is available from all the usual outlets.  The standard 'shell' available makes a glaringly 
obvious omission - space for a battery!
There are a number of freely-available .stl files for this board that incorporates space for a lithium battery.
https://www.printables.com/model/817468-ttgo-t-display-cases/files

Arduino IDE Board - TTGO LoRa32.OLED or ESP32 Dev Module - Default settings

TFT-eSPI Library - Ensure that the User_Setup_Select.h file is correctly configured for the TTGO T-Display ST7789 driver.
Comment out the line as below:
//#include <User_Setup.h>                          // Default setup is root library folder
Uncomment line as below:
#include <User_Setups/Setup25_TTGO_T_Display.h>    // Setup file for ESP32 and TTGO T-Display ST7789V SPI bus TFT

Many thanks to the developer at www.muwaqqit.com for making the API available.
Muwaqqit contact -  contact@muwaqqit.com
Please consider supporting Muwaqqit - https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=contact@muwaqqit.com&currency_code=GBP

Benoit's ArduinoJson library is invaluable, and of course makes this project possible and with ease.
The ArduinoJson Assistant takes out the headache of writing 'filter' code!
Please also consider supporting Benoit - https://github.com/sponsors/bblanchon

A WiFi manager is incorporated, eliminating the need to hard-code one's WiFi credentials.
If no connection or no SSID defined, the WiFi Configuration Portal is enabled.
On a mobile device, connect to SSID "Muwaqqit-AP" - You may have to browse to 192.168.4.1
Select "Configure WiFi"
Choose your WiFi network, enter the password and select "Save"
The configuration portal will close and the device - if in range - will connect to the chosen WiFi network and continue.

If there is no activity for 60 seconds while connected to the portal, the device will enter deep-sleep mode.

Some visual feedback is provided, indicating WiFi status, Time sync from NNTP server, Geolocation retrieval
and of course, retrieval of Prayer times data.
If any stage fails, the device will restart.

Since July 2018, Google has updated the terms for their Maps APIs. You must link a billing method to the Google Cloud Console 
to access it. For more details, visit: [Google Maps Platform Pricing](https://cloud.google.com/maps-platform/pricing/). Please be mindful of the number of requests you make. 
While there is a free monthly allowance, it is subject to change at any time. I am not liable for any billing costs 
incurred through the use of the Google API.

Firstly, a rough address of the current location will be displayed for 3.5 seconds.

Secondly, A map image showing the current location. A red path is drawn indicating the qibla direction for prayer.
    Zoom in/out with the top and bottom buttons.
    Both buttons pressed together will toggle between Road/ and Satellite view.
    If none of the buttons are pressed for 30 secs, the display moves on to show the prayer timetable.
    This function can be bypassed by pressing and holding the wake-up button until the prayer timetable is displayed.

Finally, The prayer timetable is shown along with the current date, time and battery status.
   If there is no button interaction for 30 seconds, the device switches off and enters Deep-Sleep mode.  
   Press and hold top button for 3 seconds to enable the WiFi config portal to reset WiFi credentials 
   and/or to update the firmware over the air with a compiled .bin file.  Connect as instructed on screen.

To Wake-up the device press the bottom right-hand button.
