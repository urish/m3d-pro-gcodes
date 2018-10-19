# m3d-pro-gcodes

GCodes and Troubleshooting for the [M3D Pro](https://printm3d.com/pro)

Latest software: http://printm3d.com/downloads/pro

## GCodes


* G0 X Y Z E F - [Move](https://reprap.org/wiki/G-code#G0_.26_G1:_Move)
  * G0 Z0 - Go to printer's Z-0 (lowest Z point). Make sure to switch to Absolute Mode first.
* G1 X Y Z E F - [Move](https://reprap.org/wiki/G-code#G0_.26_G1:_Move)
* G4 S P - [Dwell](https://reprap.org/wiki/G-code#G4:_Dwell)
* G20 - [Set Units to Inches](https://reprap.org/wiki/G-code#G20:_Set_Units_to_Inches)
* G28 - [Move to Home Location](https://reprap.org/wiki/G-code#G28:_Move_to_Origin_.28Home.29)
* G30 Z - probably [Single Z-Probe](https://reprap.org/wiki/G-code#G30:_Single_Z-Probe)
* G32 Z - probably [Probe and Calculate](https://reprap.org/wiki/G-code#Probe_and_calculate_in_Reprapfirmware)
* G33 - Save the current Z height as the printer's Z-0
* G90 ; [Set to Absolute](https://reprap.org/wiki/G-code#G90:_Set_to_Absolute_Positioning)
* G91 ; [Set to Relative](https://reprap.org/wiki/G-code#G91:_Set_to_Relative_Positioning)
* G92 X Y Z E ; [Set Position](https://reprap.org/wiki/G-code#G92:_Set_Position)
* G92 E0 ; Reset E

## MCodes

* M0 - [Emergency Stop](https://reprap.org/wiki/G-code#M0:_Stop_or_Unconditional_stop)
* M1 - [Halt All Moves](https://reprap.org/wiki/G-code#M1:_Sleep_or_Conditional_stop)
* M17 - probably [Enable all motors](https://reprap.org/wiki/G-code#M17:_Enable.2FPower_all_stepper_motors)
* M18 - probably [Disable all motors](https://reprap.org/wiki/G-code#M18:_Disable_all_stepper_motors)
* M20 - [Refresh SD Card List](https://reprap.org/wiki/G-code#M20:_List_SD_card)
* M21 - probably [Initialize SD Card](https://reprap.org/wiki/G-code#M21:_Initialize_SD_card)
* M22 - probably [Release SD Card](https://reprap.org/wiki/G-code#M22:_Release_SD_card)
* M23 - probably [Select SD Card](https://reprap.org/wiki/G-code#M23:_Select_SD_file)
* M24 - probably [Start/Resume SD Print](https://reprap.org/wiki/G-code#M24:_Start.2Fresume_SD_print)
* M25 - probably [Pause SD Print](https://reprap.org/wiki/G-code#M25:_Pause_SD_print)
* M26 S - probably [Set SD Position](https://reprap.org/wiki/G-code#M26:_Set_SD_position)
* M27 - probably [Report SD Print Status](https://reprap.org/wiki/G-code#M27:_Report_SD_print_status)
* M28 - probably [Begin Write to SD Card](https://reprap.org/wiki/G-code#M28:_Begin_write_to_SD_card)
* M29 - probably [Stop Write to SD Card](https://reprap.org/wiki/G-code#M29:_Stop_writing_to_SD_card)
* M30 _filename_ - [Delete File from SD Card](https://reprap.org/wiki/G-code#M30:_Delete_a_file_on_the_SD_card)
* M31 - possibly [Output time since last M109 or SD Card Start](https://reprap.org/wiki/G-code#M31:_Output_time_since_last_M109_or_SD_card_start_to_serial)
* M32 - probably [Begin Print from SD Card](https://reprap.org/wiki/G-code#M32:_Select_file_and_start_SD_print)
* M104 S - [Set Extruder Temp](https://reprap.org/wiki/G-code#M104:_Set_Extruder_Temperature)
* M105 - [Get Extruder Temp](https://reprap.org/wiki/G-code#M105:_Get_Extruder_Temperature)
* M106 S - [Fan on](https://reprap.org/wiki/G-code#M106:_Fan_On)
* M107 - [Fan off](https://reprap.org/wiki/G-code#M107:_Fan_Off)
* M109 S - [Set extruder temp and wait](https://reprap.org/wiki/G-code#M109:_Set_Extruder_Temperature_and_Wait)
* M110 - possibly [Set current line number](https://reprap.org/wiki/G-code#M110:_Set_Current_Line_Number)
* M114 ; [Get Extruder Location](https://reprap.org/wiki/G-code#M114:_Get_Current_Position)
* M115 S628 ; Only support S == 628 ; [Go To Bootloader](https://reprap.org/wiki/G-code#M115:_Get_Firmware_Version_and_Capabilities)
* M116 - [Wait](https://reprap.org/wiki/G-code#M116:_Wait)
* M117 - [Get Internal State](https://reprap.org/wiki/G-code#M117:_Get_Zero_Position)
* M140 S - [Set Bed Temp](https://reprap.org/wiki/G-code#M140:_Set_Bed_Temperature_.28Fast.29)
* M190 S - [Wait for bed to reach temp](https://reprap.org/wiki/G-code#M190:_Wait_for_bed_temperature_to_reach_target_temp)
* M303 -  Set Gantry Clips To Off
* M304 - Set Gantry Clips To On
* M333 X - Unknown
* M404 R - probably Clear Power Recovery Fault
* M405 - Unkown
* M420 T - Unknown
* M570 P - Set Filament Id
  * Generates `M618 S P T` based on P value. S: eepromAddress P: value T: size
* M571 X Y - Set Backlash Constants 
  * Generates `M618 S P T` based on X Y values. S: eepromAddress P: value T: size
* M572 - Get Backlash
* M573 - Get Bed Leveling Values
* M575 S P T E I R - Set Filament 
  * S:FilamentColorId, P:FilamentTypeId, T:FilamentTemperatureId, E:FilamentAmount I:FilamentSize R:Unused
  * Generates `M618 S P T` based on S P T E I R values. S: eepromAddress P: value T: size
* M576 - Get Filament Info
* M577 X Y Z E F I ; SetBedOffsets 
  * X:BackLeftOffset, Y:BackRightOffset, Z:FrontRightOffset, E:FrontLeftOffset, F:ZOffset I:CalibrationOffset
  * Generates `M618 S P T` based on X Y Z E F I values. S: eepromAddress P: value T: size
* M578 - Get Current Bed Offsets
* M580 X - Set Backlash Speed
* M581 - Get Backlash Speed
* M582 S - Set Nozzle Width
  * S:NozzleWidth
  * (Doesn't appear to be supported in main switch statement)
  * Generates `M618 S P T` based on S value. S: eepromAddress P: value T: size
* M583 - Get Nozzle Width
* M618 S P T - Unknown
* M619 S T - Unknown
* M682 X Y Z E R - Set Limiting Speed 
  * Generates `M618 S P T` based on X Y Z E R value. S: eepromAddress P: value T: size
* M683 - Get Limiting Speed
* M684 - Print All Eeprom Values
* M997 - Unknown
* M998 - Unknown
* M999 - Unknown
* M1011 - Enable Bounds Checking
* M1012 - Disable Bounds Checking/Unlock Z axis (for calibration)
* M1013 - Stopwatch Start
* M1014 - Stopwatch Stop
* M5321 X - Unknown
* M5680 - Get Hours Used
* M16007 - Unknown
* M17013 - Unknown
* M18010 - Unknown
* M19007 - Unknown
* M20904 - Unknown
* M21914 - Unknown
* M23975 - Unknown

## Technical Documentation

* [How to calibrate the Z axis (nozzle tip)](https://docs.google.com/document/d/1KP7YsxjqRKWcObV6CRK5-KZcS5CjOuIDcJkh4Ew4VcQ/edit)
* [Y Gantry Leveling](https://docs.google.com/document/d/1twPgL7uPxtelTZUukmtbl5FjPYbunJwcp7SGNWFjLC0/edit)
* [Gantry Adjustment Tutorial](https://docs.google.com/document/d/1p7O7IKbsAEbeOfwrJKMb9GbnoKSQBMfOaMnjzr2en0M/edit)
* [Heater PCB installation guide](https://docs.google.com/document/d/1JXeB49xS7k1D9zRDsBQ8U5bSkEgqd0DqDp9KvSZHYv0/edit)
* [Extruder Motor Replacement Tutorial](https://cdn.discordapp.com/attachments/300304086186721283/355750298855407616/Extruder_Gear_Replacement_Guide_for_the_M3D_PRO.pdf)
* [M3D Pro Disassembly Guide (PDF)](https://cdn.discordapp.com/attachments/300304086186721283/312711677369909259/M3DProDisassembly.pdf)

## Troubleshooting 

* [Prints disconnect from the bed mid-printing](prints-dont-stick.md)

## Printable Parts
* [X Axis Gantry Alignment Tool](https://cdn.discordapp.com/attachments/300304086186721283/352598161702912000/X_Axis_Gantry_Alignmment_Tool.stl)
