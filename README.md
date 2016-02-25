# tutSlicerSettings
=================
These settings are a good baseline for printing models with the department's MiniFactory and LulzBot TAZ 4 3D-printers

# The general process of printing models
1 Get a model (STL files work the best)
  * You can export your designs from Solidworks
  * Blender supports STL exports as well
  * Or, you can download your models as STL from Thingiverse or other place
  * Bonus points for Using OpenSCAD (For those who like to code their 3D forms)

2 Slicing the file to Gcode
  * Slicing is the process of turning your model into thin slices that the printer interprets. IMPORTANT! This is printer specific.
  * Mattercontrol is the simplest to use.
  * Slic3r also provides an user interface
  * Repetierhost can be used to interface with Slic3r

3 Upload your model to the BotQueue
  * http://www.botqueue.com/ (Login with the user ttyASE and with a password listed in the printer room)
  * Use the Create Job button.
  * Botqueue handles the printer queues and will then print your model.
  * Choose the right queue according to the printer you are using.
  * The password and username is written to the printer PC in the room.

4 Collect your work and cleanup the workspace
  * After the printer is once again operationa, click PASS on the botqueue, this will enable the printer to accept new jobs.
  * If possible, clean the print beds with IPA (Acetone works too, but the buildtak material will be destroyed with it, Glass, PET and Kapton surfaces tolerate either).

# Slicing
This section will give more in depth instructions on how to slice your models with different programs.

## Mattercontrol
You can download Mattercontrol from http://www.mattercontrol.com/#jumpMatterControlDownloads

The program has a fairly well documented process as to how to add files to the build platform and how to reorient them to print well. You can also finetune your settings if needed.

This repository will have the settings for Lulzbot Taz4 that you can import to the program.
After importing the settings, you need to select/create new printer and select that as active and simply click "Export" and select Gcode as the option. Once you have the Gcode exported, you can move on to uploading the file to Botqueue

## Slic3r
Download Slic3r http://slic3r.org/download

The usage of the Slic3r is straight forward but the program tends to be somewhat unstable with larger models. The general process is the same as with Mattercontrol; load the STL files and export Gcode. You also need to import the configurations bundled for Slic3r in this repository.

## Repetierhost
* Download and install Repetier Host from http://www.repetier.com/download/
* Download this repository as zip, and unpack the files
* In Repetier's slic3r tab, click manage and enter correct path to the config
* 
It is not recommemded to use this technique anymore as it has many disadvantages compared to using Slic3r or Mattercontrol as you need to setup your Slic3r paths etc. which can get slightly complicated especially when there are updates to either of the programs. However, this is mainly a matter of personal preference.

# Configuration (Advanced)
This section describes how to configure your own settings for the printer. The printing room has all of these configured so you only need to bring your STL files. This section describes information that is needed if you define your own configurations.

## Slicing configurations
* Configure bed sizes (1)
* Add Z offset if using MF2
* Configure other settings to your liking, most important are the Temperatures
* Bed: 70-80C for PLA and 100-110C for PET & ABS
* Nozzle: 220C for PLA and 230-245C for PET & ABS
* Many filaments list their recommended temperatures on the side of the roll

## Adjusting the Z-height
  * Adjusting the Z-height should not be necessary, but rough handling of the machines can result on offsets.

### TAZ4
  * Taz4 has a Z-height that is adjsutet by an Finger screw on the left side of the platform, small, roughly 1/5th turn adjustments can be made to this to make the nozzle sit at the surface of the bed. 
  * It is recommended to check the final height while the bed and nozzle are warm as they will affect the nozzle height as much as 0.1-0.2 mm.
  
### MF2
  * Minifactory does not have hardware adjustment, but it uses the Z-offset parameter in the Slic3r settings.
  * The advantage is that its easier to define precise height, and its less likely that it will drift.
  * The downside is that the settings need to be updated for everyone using the printer.

(1): MF bed size 150x150x150, LulzBot 298x275x250


