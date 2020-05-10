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

# Credits
Thanks to wachin for mui & translation : https://github.com/wachin/wps-office-all-mui-win-language
