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
 
5 In case you cancel the print
 * Make sure that the hotend and bed are cooled properly
 * TAZ4 can be cooled down manually from the LCD menu on the printer.
 * MF2 has to be manually connected with repetierhost, or power cycled, or then you can upload one of the jobs that give the right commands to the BotQueue. (none of these are ideal choices, easiest is to not mess up)

# Slicing
This section will give more in depth instructions on how to slice your models with different programs.

## Mattercontrol
You can download Mattercontrol from http://www.mattercontrol.com/#jumpMatterControlDownloads

The program has a fairly well documented process as to how to add files to the build platform and how to reorient them to print well. You can also finetune your settings if needed.

This repository will have the settings for Lulzbot Taz4 that you can import to the program.
Import the settings by selecting/creating a new printer (TAZ4 is already a predefined choice). Click Settings&controls -> Options -> Import and import the ini file from the Mattercontrol folder in this repository.
After importing the settings, you need to select/create new printer and select that as active and simply click "Export" and select Gcode as the option. Once you have the Gcode exported, you can move on to uploading the file to Botqueue

## Slic3r
Download Slic3r http://slic3r.org/download

The usage of the Slic3r is straight forward but the program tends to be somewhat unstable with larger models. The general process is the same as with Mattercontrol; load the STL files and export Gcode. You also need to import the configurations bundled for Slic3r in this repository.

## Repetierhost
* Download and install Repetier Host from http://www.repetier.com/download/
* Download this repository as zip, and unpack the files
* In Repetier's slic3r tab, click manage and enter correct path to the config

It is not recommemded to use this technique anymore as it has many disadvantages compared to using Slic3r or Mattercontrol as you need to setup your Slic3r paths etc. which can get slightly complicated especially when there are updates to either of the programs. However, this is mainly a matter of personal preference.

# Maintenance
This section will briefly describe the different maintenance task required for the printers.

## TAZ4
The smooth rods use linear bearings which wil require some greasing roughly once a year or so, like the threaded rods. It is recommended to use fairly thick grease that will not spill to the plastic parts as they are not too tolerant of oils.

## MF2
MF2 should only require oiling of the smooth rods every once in a while. The connector to the bed also has a tendency to break due to wear every once in a while, be carefull while soldering as the same connector also has a thermistor. Breakign wires already once shorted the thermistor to the heated bed wires which resulted in a burned controller board.

## Getting more filament
3dprima http://www.3dprima.com/en/ Has been a good supplier of filaments, any other place should also be OK as long as the quality of the plastic is descent. TAZ4 uses 3 mm filaments and mf2 uses 1.75 mm filament. 1.75 mm has several advantages over the 3 mm filament and should be preferred down the line.

## Printing surfaces

 * GLASS: PLA sticks to the plain glass as long as it is clean. Glass is technically free as the beds are glass but printing on plain glass erodes the surface faster as printing on the surface creates tension which will eventually(~500-2000h) make the glass shatter.
 * KAPTON tape is the best surface for many materials but it is slightly brittle and requires maintenance. Kapton also has the advantage of being very cheap. Replacing the surface requires some effort as bubbles are easily created.
 * PET surfaces are ideal from the maintenance point of view but there seem to be differences between different tape manufacturers and the current tape we have has very poor adhesion. Replacing requires some fines.
 * BUILDTAK is supposedly ideal for many materials and is easy to replacing the surface is easy as the surface is quite rigid. This is the most expensive of the surface choices.

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


# Future
The most critical part that is likely to break is the BotQueue https://github.com/Hoektronics/bumblebee/issues Where I have reported few issues and proposed quick solutions, but the development deos not seem all too interested to properly address these, so its likely that the Queue operations will break at some point (Currently the script running in the startup keeps on restarting the service every time it crashes)

## Alternatives
There are few alternative projects that might be viable replacements to the BotQueue 

 * http://www.printtopeer.com/
 * www.3dprinteros.com
 
These have a fairly small yearly subscription fee that will likely pay itself as there is less work required to maintain the code.


