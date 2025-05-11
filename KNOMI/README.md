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
>#### And use the PB4 connector to power your KNomi
```ruby
[output_pin knomi]
pin: PB4
value: 1
shutdown_value: 1
```
![pcb](https://github.com/user-attachments/assets/a925972b-1db3-4970-9f61-1e3f8058a9be)

# Links to External

VS Code software: [Visual Studio Code](https://code.visualstudio.com/).

KNOMI V1: [KNOMI](https://bttwiki.com/KNOMI.html).
