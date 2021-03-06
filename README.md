# binaryninja_plugins
This repository contains Binary Ninja plugins. Binary Ninja is a reverse engineering platform, more information: https://binary.ninja/

 * [PE Scanner](https://github.com/rootbsd/binaryninja_plugins#pe-scanner)
 * [MSDN documentation](https://github.com/rootbsd/binaryninja_plugins#msdn-documentation)
 * [MSDN documentation (without QT)](https://github.com/rootbsd/binaryninja_plugins#msdn-documentation-without-qt)
 * [Colorize API usage](https://github.com/rootbsd/binaryninja_plugins#colorize-api-usage)
 * [Graph SVG export](https://github.com/rootbsd/binaryninja_plugins#graph-svg-export)

## PE Scanner
This plugin shows an additional QT GUI with additional information concerning the analysed PE.

List of information:
  * PE information (hashes, compilaiton date, metadata...)
  * IAT
  * EAT
  * Sections
  * alert API (list of suspicious API)
  * VirusTotal quota
  * Yara rules support

The code is initially based on pescanner.py available there: https://github.com/hiddenillusion/AnalyzePE/blob/master/pescanner.py
The code was tested on Windows platforms.

Requierements
  * pefile
  * magic (for x64: https://github.com/pidydx/libmagicwin64)
  * yara
  * virus_total_apis
  * pyside
  * json
  * re
The best way to have all the dependencies is to use pip on a standalone python 2.7 install and copy the site-packages directory to the Binary Ninja install path.

TODO:
  * do not use pefile but only Binary Ninja API
  * do not create a temporary file
  * clean the code (specialy the GUI)

Few screenshots:
![Capture 1](https://raw.githubusercontent.com/rootbsd/binaryninja_plugins/master/images/Capture1.PNG)
![Capture 2](https://raw.githubusercontent.com/rootbsd/binaryninja_plugins/master/images/Capture2.PNG)
![Capture 3](https://raw.githubusercontent.com/rootbsd/binaryninja_plugins/master/images/Capture3.PNG)
![Capture 4](https://raw.githubusercontent.com/rootbsd/binaryninja_plugins/master/images/Capture4.PNG)
![Capture 5](https://raw.githubusercontent.com/rootbsd/binaryninja_plugins/master/images/Capture5.PNG)
![Capture 6](https://raw.githubusercontent.com/rootbsd/binaryninja_plugins/master/images/Capture6.PNG)
![Capture 7](https://raw.githubusercontent.com/rootbsd/binaryninja_plugins/master/images/Capture7.PNG)


## MSDN documentation
This plugin shows the MSDN documentation concerning the selected symbol

Requierements
  * PySide

Screenshot:
![Capture 8](https://raw.githubusercontent.com/rootbsd/binaryninja_plugins/master/images/Capture8.PNG)

## MSDN documentation without QT
This plugin is the same than the previous one but without QT. This version opens the web page in the default browser.

## Colorize API usage
**This plugin only works in the dev version of Binary Ninja. The block colorization is not supported in the stable.**

This plugin colorize the instruction block. The color is defined by the kind of API
  * Registry: Blue
  * Network: Green
  * File: Cyan
  * Execution: Red
  * Crypto: Magenta
  * System information: Yellow
  * Memory: Orange

TODO:
  * update the API lists

Screenshot:
![Capture 9](https://raw.githubusercontent.com/rootbsd/binaryninja_plugins/master/images/Capture9.PNG)

## Graph SVG export
**This plugin only works in the dev version of Binary Ninja. The block colorization is not supported in the stable.**

This plugin is a patched version of the export_svg.py plugin with the background color support.
