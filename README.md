This "project" is me playing around, integrating a Raspberry Pi Pico W in to Home Assistant ESPHome to be used as a Garage Door Opener.

Items used in the project:

1 x Raspberry Pi Pico W <br>
1 x FREENOVE Breakout Board for Raspberry Pi Pico W <br>
1 x 47K Ohm resistor <br>
2 x DS18B20 Digital Temperature Sensor <br>
1 x Ultrasonic Distance Sensor HC-SR04 <br>
3 x Wago Splicing Connectors with Levers (221 Series - 3 Conductor) <br>
1 x Right angle micros usb cable <br>
1 x British General IP55 weatherproof outdoor enclosure (180MM X 99MM X 111MM) <br>
2 x British General plastic cable gland 20mm <br>
1 x British General plastic cable gland 25mm <br>

4 x m2 Nylon stand offs <br>
4 x m2 Nylon screws <br>
4 x m2 Nylon washers <br>
4 x m2 Nylon bolts <br>

1 x 2mm Drill bit <br>
1 x Countersink Drill bit <br>

1 x Waterproof button box 22mm (4 hole) <br>
2 x 22mm Momentary button arrow (black background, white arrow) (LA38A-11BN) <br>
1 x 22mm Self Locking Red Emergency push button (LA38A-11ZS) <br>
1 x 22mm 2 position rotating switch (LA38-11x/21) <br>

5 core cable, length depends on distance to run from PiCOW to control box <br>
4 core cable, length depends on distance to run from PiCOW to Garage door motor <br>
4 kynar wires, from the HC-SR04 to the PiCOW for the Ultrasonic sensor <br><br>


###########################################<br>
Things to change before deploying the code:<br>
The majority of the config are in the substitutions within the header<br><br>

  devicename: picow_garage<br>
  friendlyname: PiCOW_Garage<br><br>

  fallback_ssid: <<ap_ssid_name>> <br>
  fallback_ssid_password: <<ap_ssid_password>><br><br>
  
  api_encryption_key: <<api_encryption>> <br>
  ota_password: <<ota_password>><br>
###########################################<br>
<br><br>
Running the esp code as is will produce the following controls and sensors on the default dashboard:
<br>
![Screenshot of a Home Assistant garage door entities.](https://github.com/thenextbutton/PiCOW-Garage/blob/main/_readme_images/home_assistant_garage_area_overview.png?raw=true)
<br><br>
In devices the following config and diagnostics are available:
<br>
![Screenshot of a Home Assistant garage door entities.](https://github.com/thenextbutton/PiCOW-Garage/blob/main/_readme_images/home_assistant_garage_config_diagnostic.png?raw=true)<br><br>
If using Apple Car Play, then it is possible via home assitant to publish the garage door cover to homekit to dispay the garage door controls when the car is near the home loation, just ensure Siri Suggestions is enabled:<br>
![Screenshot of Siri Suggesstions in Dashboard.](https://github.com/thenextbutton/PiCOW-Garage/blob/9af56f3565fba93c72edb1e208e576e03d3eb1d9/_readme_images/Siri_Suggestions_in_Dashboard.PNG?raw=true)<br><br>
![Screenshot of Garage Door OPEN in Dashboard.](https://github.com/thenextbutton/PiCOW-Garage/blob/main/_readme_images/CarPlay_Garage_Door_Open.PNG?raw=true)<br><br>
![Screenshot of Garage Door CLOSING in Dashboard.](https://github.com/thenextbutton/PiCOW-Garage/blob/main/_readme_images/CarPlay_Garage_Door_Closing.PNG?raw=true)<br><br>
