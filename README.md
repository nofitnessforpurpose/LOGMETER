# LOG METER
Log multi-meter measurements over Infra Red coupled RS232 connection to a file.

This <a href="https://en.wikipedia.org/wiki/Psion_Organiser"> Organiser II</a> <a href="https://en.wikipedia.org/wiki/Open_Programming_Language">OPL progam</a> periodically queries the multimeter and dependant on change or period logs the data to a file.

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
Presented in this repository is straightforward logging application written in OPL that uses and configures the <a href="https://www.jaapsch.net/psion/mancomms2.htm">COMMS Link</a> to record data from a multimeter. In the example image, batteries are under test to determine the useful life on the target device. As the terminal voltage of the (typically Alkaline) battery falls the program monitors the measured voltage to determine if the data should be appended to the logging file.

<BR>

## Connection
A COMMS link interface was used as it generates 12 Volt RS232 signals needed to power, via the DTR and RTS lines, the Infra Red connection module used to communicate with the multi-meter. A <a href="https://en.wikipedia.org/wiki/Null_modem">Null Modem</a> connection is required to effect communication. The connection parameters were 9600 baud, 8 data bits, 1 stop bit, no parity, no flow control and <CR> end of line terminator, these parameters are configured in the OPL code. The Null Modem connection can be implemented at the DB 25 or DE 9 Pin connectors. The data strings from the multimeter are relatively short (typically < 20 characters) and relatively infrequent (typically a few seconds interval), well within the RS232 buffer capacity of the Organiser 2 device.

<div align="center">
  <div style="display: flex; align-items: flex-start;">
  <img src="https://github.com/nofitnessforpurpose/LOGMETER/blob/main/images/20250605_COMMS_LINK.jpg?raw=true" width="400px" alt="NotFitForPurpose Image copyright (c) 01 June 2025 nofitnessforpurpose All Rights Reserved">
  </div>
</div>
<BR>

When using the COMMS Link cable for extended periods, a mains adaptor is highly recomended due to the relatively high current consumption of the classic COMMS Link adaptor. A mains adaptor can be connected via the Barrel Jack connector in the COMMS Link. The power supply voltage is 10.4 Volts DC nominal.

<BR>

## Installation
Download the single OPL file onto the target device, typically via a Serial COMMS connection and terminal program. Tranlsate the OPL file. Connect to the target multi-meter and run. Logging will commence following initialisation of the code.

<BR>

## Protocol
The multi-meter protocol comprises two letter upper case ASCII text commands and the response (CMD_ACK) is an ASCII 0 (command OK) or 1 (command or syntax error). Both commands and acknoledgements are follwed by a < CR > (carriage return).  

Commands are:  
| Command | Comment |  
|----|-----------------------------------------------------------|
| DS | Initiate instrument power cycle process |   
| QM | Initiate instrument measurement and response process |  
| RI | Reset all instrument settings to factory (excluding calibrations) |  
| SF | Initiate Special Function Key press |  

Only the first two commands, DS & QM are utlised.

The response to the QM command takes two parts a status response followed by the measurement if the command syntax is correct e.g.:  
0< CR >  
QM,+09.001 V DC< CR >  

Which will be logged as:  
SUN 01 JAN 1989 16:49:45, QM,+06.764 V DC  

High speed logging is limited by the instrument performance, though fast peak capture modes allows capture of short duratation events. To be read out via the infra red interface at low data rates ~960 characters per second.
<BR>

## Considerations
The code does not currently attempt to detect if there is sufficient room on the data pack.  
File names and storage locations are hard coded.  
The Organiser 2 file system does not permit file extensions.  
File locations are A: through D:  
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
