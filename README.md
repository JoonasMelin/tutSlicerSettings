# tutSlicerSettings
=================
These settings are a good baseline for printing models with the department's MiniFactory and LulzBot TAZ 4 3D-printers

Quick instructions on how to slice and print your models:

# Configuration
This section describes how to configure your own settings for the printer. The printing room has all of these configured so you only need to bring your STL files.

## Repetierhost
* Download and install Repetier Host from http://www.repetier.com/download/
* Download this repository as zip, and unpack the files
* In Repetier's slic3r tab, click manage and enter correct path to the config

## Slic3r
Currently Slic3r also has support for a plater so its possible to ommit repetierhost entirely.

* Download Slic3r http://slic3r.org/download
* Use the settings bundle here

OR

* Configure bed sizes (1)
* Add Z offset if using MF2
* Configure other settings to your liking, most important are the Temperatures
* Bed: 70-80C for PLA and 100-110C for PET & ABS
* Nozzle: 220C for PLA and 230-245C for PET & ABS
* Many filaments list their recommended temperatures on the side of the roll

# Printing
* Save your model as STL file
* Open it in Repetier Host
* Move it into the middle of the print bed (1) and correct orientation, the plater size can be configured in Repetier
* Go to slicer tab and select appropriate settings in the drop down menus, then slice
* Save gcode, the button is located on top of the gcode text
* Go to http://www.botqueue.com/, login, add new job, upload gcode and watch it print


(1): MF bed size 150x150x150, LulzBot 298x275x250
