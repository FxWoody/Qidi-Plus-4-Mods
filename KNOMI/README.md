# **KNOMI V1 INSTALL ON QIDI PLUS 4**

## ***---IMPORTANT---***
## These MACRO SCRIPT FILES are from my own QIDI PLUS 4 modifications in order to make KNOMI to work.
##


### :+1:Please be advise that these modifications are not PART of QIDI's own Klipper and therefor, i will not take any responsability for any issues that could prevail from using these scripts. I have also made many more adjusments that have been taken from the community page and that are fully integrated into these, thanks to crew of Discord, and that you can read here : [Qidi-Community](https://github.com/qidi-community/Plus4-Wiki/tree/main). :+1:

#### *** This install is fully working and should be followed very carefully. Do not forget that this MOD is based on the BEACON mod and is fully implemented for it but should FIT without it too except for some differences on the cover built :wink:*** ####

## Install the KNOMI in the toolhead cover
Download my files from Printables:

Knomi Cover: [Fxwoody Printables](https://www.printables.com/model/1214824-qidi-plus-4-knomi-cover)

## Let's get ready in the CONFIGS :

In order to have KNOMI to hook with our printer, we need to UPDATE the firmware first.

Follow the instructions from BTT page

BTT Knomi: https://bttwiki.com/KNOMI.html


## Add Knomi.cfg to your repo

>In printer.cfg, add the macro link
> `[include KNOMI.cfg]`

>[!IMPORTANT]
>#### Use the PB4 connector to power your Knomi

> Find :
```ruby
[heater_fan hotend_fan2]
pin:PB4
max_power: 1.0
shutdown_speed:1.0
kick_start_time: 0.5
heater: extruder
heater_temp: 50.0
fan_speed: 1.0
off_below: 0
```

and replace with:

```ruby
[output_pin knomi]
pin: PB4
value: 1
shutdown_value: 1
```
![pcb](https://github.com/user-attachments/assets/a925972b-1db3-4970-9f61-1e3f8058a9be)

## Upload KNOMI.cfg
```ruby
[gcode_macro _KNOMI_STATUS]
variable_homing: False
variable_probing: False
variable_qgling: False
variable_heating_nozzle: False
variable_heating_bed: False
gcode:

[gcode_macro M109]
rename_existing: M109.1
gcode:
  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=heating_nozzle VALUE=True
  M109.1 {rawparams}
  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=heating_nozzle VALUE=False

[gcode_macro M190]
rename_existing: M190.1
gcode:
  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=heating_bed VALUE=True
  M190.1 {rawparams}
  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=heating_bed VALUE=False

[gcode_macro G28]
rename_existing: G28.1
gcode:
  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=homing VALUE=True
  G28.1 {rawparams}
  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=homing VALUE=False

[gcode_macro _BED_MESH_CALIBRATE]
rename_existing: BTT_BED_MESH_CALIBRATE
gcode:
  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=qgling VALUE=True
  BTT_BED_MESH_CALIBRATE {rawparams}
  SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=qgling VALUE=False

[gcode_macro Z_TILT_ADJUST]
rename_existing: BTT_Z_TILT_ADJUST
gcode:
 SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=probing VALUE=True
 BTT_Z_TILT_ADJUST
 SET_GCODE_VARIABLE MACRO=_KNOMI_STATUS VARIABLE=probing VALUE=False
```

# Links to External

VS Code software: [Visual Studio Code](https://code.visualstudio.com/).

KNOMI V1: [KNOMI](https://bttwiki.com/KNOMI.html).
