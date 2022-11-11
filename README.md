# Marlin 2.1.1 - Ender-3_SKR-Mini-E3-1.2
SKR Mini E3 1.2 configuration for Marrlin 2.X with BLtouch <br>
Download and install the correct version Git <br>
https://git-scm.com/downloads

<b> Download and install VScode </b><br>
https://code.visualstudio.com/Download

<b> Install the PlatformIO plugin to VScode </b><br>
https://github.com/bigtreetech/Document/blob/master/How%20to%20install%20VScode+Platformio.md

<b> Download the Marlin Firmware and extract  </b><br>
https://marlinfw.org/

<b> Download the Marlin Firmware Configurations and extract  </b><br>
https://github.com/MarlinFirmware/Marlin/tree/2.1.x/config
https://github.com/MarlinFirmware/Marlin/tree/2.1.1/config

<b> Download the BigTreeTech Firmware and extract  </b><br>
https://github.com/bigtreetech / https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3

Browse to *Unzipped Dir*\Configurations-master\config\examples\Creality\Ender-3 <br>
Copy the 4 files (Configuration.h, Configuration_avd.h, _Bootscreen.h and _Statusscrren.h) <br>
Pastet the 4 files in *Unzipped Dir*\Marlin-2.1.x\Marlin <br>

Open VScode > PlatformIO > Open Project > *Unzipped Dir*\Marlin-2.1.x <br>
Open platformio.ini , Marlin > Configuration.h and Marlin > Configuration_avd.h

<b> Version 02.00.04 #define CONFIGURATION_ADV_H_VERSION 020004 </b>

<b> platformio.ini </b><br>
No Changes > Use "Auto Marlin Builder" extension in Visual Studio Code

<b> Configuration_avd.h </b><br>
Disable: //#define BLTOUCH_DELAY 200 <br>
#define BLTOUCH_SET_5V_MODE <br>
Disable: //#define BLTOUCH_HS_MODE <br>
<b> *Save Space on Rom* </b><br>
Disable: #define DOUBLECLICK_FOR_Z_BABYSTEPPING <br>

<b> Configuration.h </b><br>
Change: #define STRING_CONFIG_H_AUTHOR "(BIGTREETECH, SKR-mini-E3-V1.2)"

Change: #define MOTHERBOARD BOARD_BTT_SKR_MINI_E3_V1_2

Change: #define CUSTOM_MACHINE_NAME "SKR-mini-E3-V1.2, TFT35-V3.0"

Enable: #define Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN

Enable: #define EEPROM_AUTO_INIT


<b> BLtouch </b><br>
Enable: #define BLTOUCH

Enable: #define Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN

Change: #define NOZZLE_TO_PROBE_OFFSET { -40, -10, -1.85 }

Change: #define XY_PROBE_SPEED 10000

Disable: //#define MESH_BED_LEVELING

Enable: #define AUTO_BED_LEVELING_BILINEAR

Disable: //#define MIN_SOFTWARE_ENDSTOP_Z

Enable: #define Z_SAFE_HOMING

<b> BLtouch Speed-up </b><br>
#define GRID_MAX_POINTS_X 3 <br>

#define Z_CLEARANCE_DEPLOY_PROBE   5 //WAS 10 <br>

#define Z_CLEARANCE_BETWEEN_PROBES  4 //WAS 5 <br>

#define HOMING_FEEDRATE_XY (30*60) //WAS 20  <br>

#define HOMING_FEEDRATE_Z  (6*60) //WAS 4 <br>

#define SERVO_DELAY { 200 }  //WAS 300 <br>



<b> Additional Marlin Firmware changes </b><br>
Change: #define BAUDRATE 115200 <br>
Change: #define DEFAULT_NOMINAL_FILAMENT_DIA 1.75 <br>
Change: #define TEMP_SENSOR_BED 1 <br>
Change: #define BED_MAXTEMP      125 <br>
Change: #define DEFAULT_AXIS_STEPS_PER_UNIT   { 80, 80, 400, 93 } <br>
Change: #define DEFAULT_MAX_FEEDRATE          { 500, 500, 5, 25 } <br>
Change: #define MAX_FEEDRATE_EDIT_VALUES    { 600, 600, 10, 50 }  <br>
Change: #define DEFAULT_MAX_ACCELERATION      { 500, 500, 100, 5000 } <br>
Change: #define DEFAULT_ACCELERATION          500  <br>
    #define DEFAULT_RETRACT_ACCELERATION  500 <br>
    #define DEFAULT_TRAVEL_ACCELERATION   500 <br>
Change: #define JUNCTION_DEVIATION_MM 0.08 <br>
Enable: #define S_CURVE_ACCELERATION <br>
Disable //#define DISABLE_INACTIVE_EXTRUDER <br>
Change: #define INVERT_X_DIR true <br>
Change: #define INVERT_E0_DIR true <br>
Change: #define X_BED_SIZE 235 <br>
    #define Y_BED_SIZE 235 <br>
Change: #define Z_MAX_POS 250 <br>
Change: #define LCD_BED_LEVELING <br>
Change: #define HOMING_FEEDRATE_XY (50*60) <br>
Enable: #define EEPROM_SETTINGS <br>
Enable: #define EEPROM_AUTO_INIT <br>
Change: #define PREHEAT_1_FAN_SPEED   255 <br>
	    #define PREHEAT_2_FAN_SPEED   255 <br>
Change: #define DISPLAY_CHARSET_HD44780 WESTERN <br>
Enable: #define SDSUPPORT <br>
Enable: #define INDIVIDUAL_AXIS_HOMING_MENU <br>
Enable: #define CR10_STOCKDISPLAY <br>
