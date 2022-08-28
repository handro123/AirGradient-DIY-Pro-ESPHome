# Using AirGradient DIY Pro kit with ESPHome / HomeAssistant

I ordered 2 DIY Pro kits. After getting them assembled I flashed them using the provided firmware and added them to the AirGradient Dashboard for a few days to make sure everything was working as expected. After collecting data for a few days, I moved ahead with getting it to work with Home Assistant / ESPHome.


## Changes to the DIY Pro kit compared to previous kits

- Had to use board "d1_mini" as "d1_mini_pro" wouldn't let me flash OTA. From the product page it looks like it has been replaced with a Wemos D1 Mini v4 USB-C with 4MB Flash, but previous DIY kits came with a D1 Mini Pro with 16MB flash. 
- The OLED screen is larger and a different model, need to use model "SH1106 128x64". 
- No TVOC sensor yet. Updated sensor coming soon hopefully: https://forum.airgradient.com/t/sgp40-tvoc-sensor/377/4
- From what I read it was best to change the Sensor names to avoid conflicts in Home Assistant. 
  - I used the board address / ID / serial to keep track of them, replace XXXXXX with your board ID, or if you only have one kit them remove it entirely. 


## Instructions

Great detailed step-by-step instructions by ajfriesen.  I also based my config off his air-gradient.yaml. 
- https://github.com/ajfriesen/ESPHome-AirGradient

**Instructions specific to my implementation:** 
1. Rename “airgradient-XXXXXX.yaml” with your board ID.
2. Update the XXXXXX references with the same board ID.
3. Make sure to upload the “pm25_to_aqi_us.h” file to “config/esphome/” directory
4. Also create a “config/fonts/” folder and upload your font of choice. I used MonospaceTypewriter from below: 
   1. https://www.fontsquirrel.com/fonts/MonospaceTypewriter

I used the “File editor” Add-on in Home Assistant to easily upload files.


## References

**The AirGradient DIY Air Quality Sensor (PRO Version) - Build Instructions**

https://www.airgradient.com/open-airgradient/instructions/diy-pro/

Other config references for previous AirGradient DIY kits:
- https://github.com/ozonejunkieau/airgradient-esphome
- https://github.com/MallocArray/airgradient_esphome
- https://www.esphome-devices.com/devices/AirGradient-DIY


Feel free to contribute or suggest any improvements and I'll figure out how to merge the changes. 
