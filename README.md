# LOG METER
Log multi-meter measurements over Infra Red couples RS232 connection to a file.

This <a href="https://en.wikipedia.org/wiki/Psion_Organiser"> Organiser II</a> <a href="https://en.wikipedia.org/wiki/Open_Programming_Language">OPL progam</a> periodically queries the multimeter and dependant on change or period logs the data a file.

<div align="center">
  <div style="display: flex; align-items: flex-start;">
  <img src="https://github.com/nofitnessforpurpose/LOGMETER/blob/main/images/2025-06-03-METLOGGER-02.jpg?raw=true" width="400px" alt="NotFitForPurpose Image copyright (c) 01 June 2025 nofitnessforpurpose All Rights Reserved">
  </div>
</div>
<BR>

[![Organiser](https://img.shields.io/badge/gadget-Organiser_II-blueviolet.svg?%3D&style=flat-square)](https://en.wikipedia.org/wiki/Psion_Organiser)
[![GitHub License](https://img.shields.io/github/license/nofitnessforpurpose/LOGMETER?style=flat-square)](https://github.com/nofitnessforpurpose/LOGMETER/blob/main/LICENSE)
[![Maintenance](https://img.shields.io/badge/maintained%3F-yes-green.svg?style=flat-square)](https://github.com/nofitnessforpurpose/TopSlotCase/graphs/commit-activity)
![GitHub repo size](https://img.shields.io/github/repo-size/nofitnessforpurpose/LOGMETER?style=flat-square)

<br>  

## Use Case
Presented in this repository is straightforward logging application written in OPL that configures and uses the COMMS link to record data from a multimeter. In the example image, batteries are under test to determine the useful life on the target device. As the terminal voltage of the (typically Alkaline) battery falls the program monitors the measured voltage to determine if the data should be appended to the logging file.


<BR>

## Considerations
The code does not attempt to detect if there is sufficent room on the data pack.  
The Organiser 2 file system does not permit file extentions. 
File names are 8 characters long, starting with the letter A through Z.
See Notes below.  

<BR>

## Questions / Discussion
See <a target="_blank" rel="noopener noreferrer" href="https://www.organiser2.com/"> Organiser 2 Hardware </a> forum, though see note below first.


<BR>

## Please note:  
All information is For Indication only.
No association, affiliation, recommendation, suitability, fitness for purpose should be assumed or is implied.
Registered trademarks are owned by their respective registrants.
