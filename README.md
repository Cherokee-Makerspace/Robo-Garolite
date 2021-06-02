# Marlin 2.0.8.2 for Robo 3D R1

<img align="right" width=175 src="buildroot/share/pixmaps/logo/marlin-250.png" />

Download [Marlin Firmware](https://marlinfw.org/).
Reset settings with M502 and M500 after flashing with new firmware.

## Setup

This is for a Robo 3D R1 with the following mods:
* Garolite Surface
* [300mm Y-Axis Linear Rods](https://amzn.to/3cceJ6K)
* RepRap Smart Controller
* OctoPrint

##### Notes
1. Glass bed had a small chip so the garolite sheet was a quick and easy fix.
2. 300mm rods were a little shorter than the stock rods so we had to move 2 bed magnets to accomodate. Y_BED_SIZE was reduced to 200 for this reason.
3. Some Robo R1 (non +) models use a different Z lead screw. STEPS/UNIT for this model is 800 and not 2560.

---
### Summary of Changes

#### configuration.h
`#define BAUDRATE 115200`

`#define CUSTOM_MACHINE_NAME "Robo 3D R1"`

//============================= Thermal Settings ============================
`#define TEMP_SENSOR_BED 1`

//============================== Movement Settings ==========================
`#define DEFAULT_AXIS_STEPS_PER_UNIT   { 80, 80, 800, 723.38 }`

//============================= Z Probe Options =============================
`#define FIX_MOUNTED_PROBE`

`#define XY_PROBE_FEEDRATE (180*60)`


`#define INVERT_X_DIR true`

`#define INVERT_Y_DIR false`

`#define INVERT_Z_DIR true`


`#define X_BED_SIZE 220`

`#define Y_BED_SIZE 200`


`#define MIN_SOFTWARE_ENDSTOPS false`

//=============================== Bed Leveling ==============================
`#define AUTO_BED_LEVELING_BILINEAR`

`#define ENABLE_LEVELING_AFTER_G28`

`#define PREHEAT_BEFORE_LEVELING`

`#define LCD_BED_LEVELING`

//============================= Additional Features ===========================
`#define PREHEAT_2_LABEL       "PETG"`

`#define PREHEAT_2_TEMP_HOTEND 240`

`#define PREHEAT_2_TEMP_BED     75`

`#define PREHEAT_2_TEMP_CHAMBER 35`

`#define PREHEAT_2_FAN_SPEED     0` // Value from 0 to 255

//============================= LCD and SD support ============================
`#define SDSUPPORT`

`#define SD_CHECK_AND_RETRY`

`#define SLIM_LCD_MENUS`

`#define SPEAKER`

//======================== LCD / Controller Selection =========================
//========================   (Character-based LCDs)   =========================
`#define REPRAP_DISCOUNT_SMART_CONTROLLER`

#### configuration_adv_.h
`#define BABYSTEPPING`

`#define BABYSTEP_MILLIMETER_UNITS`

`#define BABYSTEP_MULTIPLICATOR_Z  0.05`

`#define BABYSTEP_MULTIPLICATOR_XY  0.05`


`#define HOST_ACTION_COMMANDS`