# Ender-3_SKR-Mini-E3-1.2
SKR Mini E3 1.2 configuration for Marrlin 2.X with BLtouch
Download and install the correct version Git
https://git-scm.com/downloads

Download and install VScode
https://code.visualstudio.com/Download

Install the PlatformIO plugin to VScode
https://github.com/bigtreetech/Document/blob/master/How%20to%20install%20VScode+Platformio.md

Download the Marlin Firmware and extract 
https://marlinfw.org/

Download the Marlin Firmware Configurations and extract 
https://github.com/MarlinFirmware/Marlin/tree/2.0.x/config

Download the BigTreeTech Firmware and extract 
https://github.com/bigtreetech / https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3

Browse to *Unzipped Dir*\Configurations-master\config\examples\Creality\Ender-3
Copy the 4 files (Configuration.h, Configuration_avd.h, _Bootscreen.h and _Statusscrren.h)
Pastet the 4 files in *Unzipped Dir*\Marlin-2.0.x\Marlin

Open VScode > PlatformIO > Open Project > *Unzipped Dir*\Marlin-2.0.x
Open platformio.ini , Marlin > Configuration.h and Marlin > Configuration_avd.h

Version 02.00.04 #define CONFIGURATION_ADV_H_VERSION 020004

platformio.ini
Change: default_envs = megaatmega2560
To: default_envs = STM32F103RC_btt

Configuration_avd.h
Disable: //#define BLTOUCH_DELAY 200
#define BLTOUCH_SET_5V_MODE
Disable: //#define BLTOUCH_HS_MODE
*Save Space on Rom*
Disable: #define DOUBLECLICK_FOR_Z_BABYSTEPPING

Configuration.h
Disable: #define STRING_CONFIG_H_AUTHOR "(BIGTREETECH, SKR-mini-E3-V1.2)"

Change: #define SERIAL_PORT 2

Enable: #define SERIAL_PORT_2 -1

Change: #define MOTHERBOARD BOARD_BTT_SKR_MINI_E3_V1_2

Disable: #define CUSTOM_MACHINE_NAME "SKR-mini-E3-V1.2, TFT35-V3.0"

Change: #define X_DRIVER_TYPE  A4988
	To: #define X_DRIVER_TYPE  TMC2209
Change: #define Y_DRIVER_TYPE  A4988
	To: #define Y_DRIVER_TYPE  TMC2209
Change: #define Z_DRIVER_TYPE  A4988
	To: #define Z_DRIVER_TYPE  TMC2209
Change: #define E0_DRIVER_TYPE  A4988
	To: #define E0_DRIVER_TYPE TMC2209

Enable: #define Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN

Enable: #define EEPROM_AUTO_INIT

Disable: //#define SD_CHECK_AND_RETRY

Enable: #define INDIVIDUAL_AXIS_HOMING_MENU

Disable: //#define SPEAKER
BLtouch
Enable: #define BLTOUCH

Enable: #define Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN

Change: #define NOZZLE_TO_PROBE_OFFSET { -40, -10, -1.85 }

Change: #define MIN_PROBE_EDGE 15

Change: #define XY_PROBE_SPEED 10000

Disable: //#define MESH_BED_LEVELING

Enable: #define AUTO_BED_LEVELING_BILINEAR

Enable: #define RESTORE_LEVELING_AFTER_G28

Disable: //#define MIN_SOFTWARE_ENDSTOP_Z

Enable: #define Z_SAFE_HOMING

BLtouch Speed-up
#define GRID_MAX_POINTS_X 3
#define Z_CLEARANCE_DEPLOY_PROBE   5 //WAS 10
#define Z_CLEARANCE_BETWEEN_PROBES  4 //WAS 5
#define HOMING_FEEDRATE_XY (30*60) //WAS 20 
#define HOMING_FEEDRATE_Z  (6*60) //WAS 4
#define SERVO_DELAY { 200 }  //WAS 300



Additional Marlin Firmware changes
Change: #define BAUDRATE 115200
Change: #define DEFAULT_NOMINAL_FILAMENT_DIA 1.75
Change: #define TEMP_SENSOR_BED 1
Change: #define BED_MAXTEMP      125
Change: #define DEFAULT_AXIS_STEPS_PER_UNIT   { 80, 80, 400, 93 }
Change: #define DEFAULT_MAX_FEEDRATE          { 500, 500, 5, 25 }
Change: #define MAX_FEEDRATE_EDIT_VALUES    { 600, 600, 10, 50 } 
Change: #define DEFAULT_MAX_ACCELERATION      { 500, 500, 100, 5000 }
Change: #define DEFAULT_ACCELERATION          500 
    #define DEFAULT_RETRACT_ACCELERATION  500
    #define DEFAULT_TRAVEL_ACCELERATION   500
Change: #define JUNCTION_DEVIATION_MM 0.08
Enable: #define S_CURVE_ACCELERATION
Disable //#define DISABLE_INACTIVE_EXTRUDER
Change: #define INVERT_X_DIR true
Change: #define INVERT_E0_DIR true
Change: #define X_BED_SIZE 235
    #define Y_BED_SIZE 235
Change: #define Z_MAX_POS 250
Change: #define LCD_BED_LEVELING
Change: #define HOMING_FEEDRATE_XY (50*60)
Enable: #define EEPROM_SETTINGS
Enable: #define EEPROM_AUTO_INIT
Change: #define PREHEAT_1_FAN_SPEED   255
	    #define PREHEAT_2_FAN_SPEED   255
Change: #define DISPLAY_CHARSET_HD44780 WESTERN
Enable: #define SDSUPPORT
Enable: #define INDIVIDUAL_AXIS_HOMING_MENU
Enable: #define CR10_STOCKDISPLAY
