# **BEACON RevH "Normal" INSTALL ON QIDI PLUS 4**

## ***---IMPORTANT---***
## These MACRO SCRIPT FILES are from my own QIDI PLUS 4 modifications in order to make Beacon3D probe to work and is mainly, a copy of Stew675's AMAZING script.
##


### :+1:Please be advise that these modifications are not PART of QIDI's own Klipper and therefor, i will not take any responsability for any issues that could prevail from using these scripts. I have also made many more adjusments that have been taken from the community page and that are fully integrated into these, thanks to crew of Discord, and that you can read here : [Qidi-Community](https://github.com/qidi-community/Plus4-Wiki/tree/main). :+1:

#### *** This install is fully working and should be followed very carefully :wink:*** ####

## Install the PROBE on the toolhead
Download my files from Printables:
https://www.printables.com/model/1165232-qidi-plus-4-beacon-cooling-fan

Or you can use Stew's setup :
https://www.printables.com/model/1170120-beacon3d-mount-for-qidi-plus4

> ***NOTE that by using my Beacon Module installation, the probe will be on the right side on the tool head and requires to replace the cooling DUCT !!! I have added the STL for this puposes and my fan/duct system is more efficient than the original one***
> ![blower-beacon](https://github.com/user-attachments/assets/ac217672-79cd-4453-a933-b221f627b6b5)


Remove old probe, fan housing, and replace with new printed one.
**I will make some DEMO pic soon**

## Let's get ready in the KLIPPER :

In order to install Beacon, you will need to SSH into MKS folder with Mobaxterm 

Follow this to SSH how to: [SSH Communtity](https://github.com/qidi-community/Plus4-Wiki/blob/main/content/ssh-access/README.md).

Once in SSH, you will need to install the Beacon script:
> ***Install Beacon Module***
#### Clone beacon_klipper from git and run the install script:

```
cd ~
git clone https://github.com/beacon3d/beacon_klipper.git
./beacon_klipper/install.sh
```

Now that **BEACON** is installed, we need to replace the ***PROBE.PY*** inside the **KLIPPER**.
Navigate to the ***/home/mks/klipper/klippy/extras/*** like so : 

https://github.com/user-attachments/assets/80a6965c-9cf2-4efb-97a6-fbfab288c99c
#### From here, we have two choice in order to replace the Python File ####
You can simply **DRAG & DROP** the file you recovered earlier from your PC, or double click the PROBE.PY, this will open the **MobaTextEditor** ,select ALL, and paste the PROBE.PY file over-write it. 
> [!NOTE]
> Saving will bring you to a contextual menu for you to agree to **SAVE**.
After this, we are done in SSH mode.

## Copy/Paste of the .cfg files
> [!IMPORTANT]
***First -***, in your QP4 configuration, locate the **printer.cfg** and **gcode_macro.cfg**, rename those as ***park-printer.cfg*** and ***park-gcode_macro.cfg*** so that you can revert to it later (saving it on your PC with notepad or your favorite editor, *Mobaxterm* as is own that you can use, is even better as a backup)
>
> ***NOTE -*** My config files have been tuned for my OWN printer and might need to be readjusted to your printer setup. I have removed the mods that are not necessary, but, i would HIGLY suggest that you install SHAKETUNE :
> https://github.com/qidi-community/ShakeTune-For-Plus4

Open the ***printer.cfg & gcode_macro.cfg*** from this repository and copy them into each of your ***Configuration Files*** by creating each new files like so :

***NOTE THAT I OMIT THE ".CFG" AFTER WRITING "PRINTER" ...PLEASE REMEMBER TO ADD IT WHEN CREATING YOUR FILE*** 

https://github.com/user-attachments/assets/59b034cf-4111-4476-8d64-ce53f5c2da31
> [!IMPORTANT]
Then, simply COPY / PASTE each macro into their own folder .... **Save & Restart** will be ask at each file closer. I have also include KAMP settings if you want to adjust it to your taste (but it is set for quick purging  **NOTE:** ***LINE_PURGE need to be added to your printer setings Machine_start-gcode***)
>
> Now that Beacon is install, we are ready to do the **calibrations**.
>
## Calibration of your new Beacon
With all the above changes in place (and the firmware restarted) your Beacon can now be easily calibrated with the following typed into the Gcode Console:
```
G32
G29
G31
SAVE_CONFIG
```
This will set the Plus4 to generate a default bed mesh (G32), then do a full calibration home and bed mesh (G29), and then finally put the Plus4 back into Kamp mode meshing ready for the next print (G31). The whole lot gets saved afterwards (SAVE_CONFIG)


>
> Please refer to the "Beacon Instal Page" in the link below for proper calibration and better understanding of the probe.

# Links to External

SSH software: [MobaXterm](https://mobaxterm.mobatek.net/download.html).

Beacon Install page: [Beacon](https://docs.beacon3d.com/quickstart/).

Beacon Probe RevH: [Beacon Probe RevH Model : Normal](https://beacon3d.com/product/beacon-h/).

Qidi Community Work : [Qidi-Community Github](https://github.com/qidi-community/Plus4-Wiki/tree/main).

Facebook QidiTech : [QidiTech Officia](https://www.facebook.com/groups/qiditechofficialusers).
