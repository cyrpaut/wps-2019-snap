# About wps-2019-snap
Packaging WPS Office 2019 for SNAP with all languages translations available and Internet plug disabled.

WPS Office is a light-weight office for Linux developped by the Kingsoft corporation. This software is free to use, but under commercial licence.
  
This repository share the sources for SNAP packaging of an unofficial WPS 2019 release. It includes available languages interface translation and spell-check dictionnary. 
  
To prevent leakeages of private data, the plug for internet is disabled, which prevents WPS to call home in China. Enjoy WPS securely !


# Availability
This package is available from SnapStore.

  
# Post install configuration
For security reasons, printing from SNAP is disabled by default. In order to have printing from WPS working you need to execute the folloging command:
```
sudo snap connect wps-2019-snap:cups-control :cups-control
```


# How to rebuild this Snap package
For credit reasons, I do not share the complete binaries of WPS here. Yet you can download the official package from http://linux.wps.com/ .

1- Unzip the package in a folder and then unzip the data.tar.xz . Copy all the content of the data.tar.xz into the binaries/ folder of this repository.

2- Then, copy the content of the extra_binaries_custom/ folder into the binaries/ folder and over-write the files that are in common in both folder.

3- Then launch the snap building process ```snapcraft```


# Credits
Thanks to wachin for mui & translation : https://github.com/wachin/wps-office-all-mui-win-language
Thanks to galgalesh for his clear tutorial on GTK-2 integration for Snap : https://snapcraft.io/docs/gtk2-applications 


# Known bugs
* When you launch this snap from the command line ex. ```wps_2019-snap``` you see some warnings comming from the GTK-2 integration. It seems to have no effect on the program functionning. 
