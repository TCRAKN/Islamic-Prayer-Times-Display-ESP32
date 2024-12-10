# Islamic-Prayer-Times-Display-ESP32

This is an Arduino IDE project that uses a readily-available development board that includes a small TFT 
screen - LilyGo TTGO T-Display - to retrieve and display Islamic prayer time data according to the 
geolocation of the user.

Follow my Instructable here:  https://www.instructables.com/Islamic-Prayer-Times-ESP32-TTGO-T-Display/

The project uses JSON data from https://muwaqqit.com for prayer time data and Google for Geolocation.

The project uses a readily-available ESP32 development board that includes a small TFT screen - TTGO T-Display,
available from all the usual outlets.  The standard 'shell' available makes a glaringly obvious omission - space for a battery!
There are a number of freely-available .stl files for this board that incorporates space for a lithium battery.
https://www.printables.com/model/817468-ttgo-t-display-cases/files

Arduino IDE Board - TTGO LoRa32.OLED or ESP32 Dev Module - Default settings

TFT-eSPI Library - Ensure that the User_Setup.h file is correctly configured for the ST7789 driver.
Uncomment line containing - #define ST7789_DRIVER
Edit lines defining height & width - 
#define TFT_WIDTH  128
#define TFT_HEIGHT 160
Edit the following to:
#define TFT_BL   4
#define TFT_BACKLIGHT_ON HIGH

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
Choose WiFi network, enter password and select "Save"
Configuration portal will close and the device will connect to the chosen WiFi network and continue.

If nothing is configured from the portal within 60 seconds, the device will be set to deep-sleep mode.

Some visual feedback is provided, indicating WiFi status, Time sync from NNTP server, Geolocation retrieval
and of course, retrieval of Prayer times data.
If any stage fails, the device will restart.

After prayer time data has been retrieved, it will be displayed on the TFT screen and pushed out to the serial port.
The device will be set to deep-sleep mode after 60 seconds.  The device will restart after 60 minutes.

To force display of prayer times, press the Reset button.

To clear the saved WiFi network, press and hold the right-hand button for 3 seconds after prayer times are displayed.
The device will restart.  The previously saved network will be erased and the device will return to WiFi the
WiFi configuration screen and the portal will be enabled to complete WiFi network setup.
