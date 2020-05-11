# About wps-2019-snap
Packaging WPS Office 2019 for SNAP with all languages translations available and Internet plug disabled.

WPS Office is a light-weight office for Linux developped by the Kingsoft corporation. This software is free to use, but under commercial licence.
  
This repository share the sources for SNAP packaging of an unofficial WPS 2019 release. It includes available languages interface translation and spell-check dictionnary. 
  
To prevent leakeages of private data, the plug for internet is disabled, which prevents WPS to call home in China. Enjoy WPS securely !


# Availability
This package is available from SnapStore.

<a href="https://snapcraft.io/wps-2019-snap">
  <img alt="Get it from the Snap Store" src="https://snapcraft.io/static/images/badges/en/snap-store-white.svg" />
</a>
  
# Post install configuration
For security reasons, printing from SNAP is disabled by default. (see: https://ubuntu.com/blog/a-guide-to-snap-permissions-and-interfaces)

In order to have printing, audio and removable-media from WPS working you need to either give the permission from the Snap-Store permission panel or execute the following commands:
```
sudo snap connect wps-2019-snap:cups-control :cups-control
sudo snap connect wps-2019-snap:alsa :alsa
sudo snap connect wps-2019-snap:pulseaudio :pulseaudio
sudo snap connect wps-2019-snap:removable-media :removable-media
```

# How to rebuild this Snap package
For credit reasons, I do not share the complete binaries of WPS here. Yet you can download the official package from http://linux.wps.com/ .

To reproduce this Snap, you should
  1. Unzip the package in a folder and then unzip the ```data.tar.xz```. Copy all the content of the ```data.tar.xz``` into the ```binaries/``` folder of this repository.
  2. Then, copy the content of the ```extra_binaries_custom/``` folder into the ```binaries/``` folder and over-write the files that are in common in both folder.
  3. Then launch the snap building process ```snapcraft```. Wait a bit. It is a big snap!


# Credits
Thanks to wachin for mui & translation : https://github.com/wachin/wps-office-all-mui-win-language

Thanks to galgalesh for his clear tutorial on GTK-2 integration for Snap : https://snapcraft.io/docs/gtk2-applications 


# Issues & Known bugs

**Issues still to be fixed**
* After closing the program, it seems that it continues running in the background for a while. I think it is intentionnal from WPS developpers to keep it alive for faster reopening. I need to check.
* Accessing to the skin center makes the program crash. The general settings seems not to be accessible.
* Do not override the doc/docx icon of the file explorer with the WPS icon. The problem seems to be in the MIME, but the XML file is allright. I need to investigate this.
* The embeded explorer of the welcome page do not show the icon corresponding to de program type. 

**Intentional Behaviour**
* When you launch this snap from the command line ex. ```wps-2019-snap.et``` you see some warnings comming from the GTK-2 integration. It seems to have no effect on the program. 
* For personal use convenience, PDFs do not get automatically associated with WPS when installing WPS from this snap. It is on purpose, as I do not like the PDF reader so much. For me it is missing the very important "Save as" function which is important when reading a temporary PDF from the web. It is not a bug but was done intentionnally. I can easily revert that change if users don't like it.
* The opening page is not translated into local language. There is no available translation for this front page.
* Accessing the WPS official website from the application results in a blank page. It is normal, internet plug is disables for privacy ^_^
* This package does not allow to open file from temporary folder in memory. I may try to fix that.

