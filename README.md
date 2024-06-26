# Pixie-Net Release Notes

## Version 2.33, June 2024
Release updates include
 
- FW/SW: Add PSA functions for 14bit version. Due to limited resources, the coincidence delay is fixed at 0us. 

Supported variants are <br/>
*Hardware Revision B, 12-bit and 14-bit*
| Firmware Type |	Firmware ID |	Firmware Files |	Software Files | Documentation |
| --------------| ------------| ----------------- | ----------------- | ------------- |
| Standard 12 bit | 0xA991_0232 | [sd-bootfiles-pn-STD: 2.32](./release_packages/sd-bootfiles-pn-STD-2p32.zip)   | [sw-arm-pn: 2.32](./release_packages/sw-arm-pn-2p32.zip) | [Pixie_Net_Manual: 2.32](./release_packages/Pixie_Net_Manual.pdf) | 
| Standard 14 bit | 0xA9A1_0232 | [sd-bootfiles-pn-14B: 2.32](./release_packages/sd-bootfiles-pn-14B-2p32.zip)   | [sw-arm-pn: 2.32](./release_packages/sw-arm-pn-2p32.zip) | [Pixie_Net_Manual: 2.32](./release_packages/Pixie_Net_Manual.pdf) | 
| PSA 12 bit<br/> Includes pulse shape analysis functions e.g. to distinguish gammas and neutrons, and constant fraction timing logic. Licensing required | 0xA991_1231 | [sd-bootfiles-pn-PSA: 2.31](./release_packages/sd-bootfiles-pn-PSA-2p31.zip)   | [sw-arm-pn: 2.30](./release_packages/sw-arm-pn-2p30.zip) | [Pixie_Net_Manual: 2.32](./release_packages/Pixie_Net_Manual.pdf) | 
| PSA 14 bit<br/> Includes pulse shape analysis functions e.g. to distinguish gammas and neutrons, and constant fraction timing logic. Licensing required | 0xA991_1233 | [sd-bootfiles-pn-14B-PSA: 2.33](./release_packages/sd-bootfiles-pn-14B-PSA-2p33.zip)   | [sw-arm-pn: 2.33](./release_packages/sw-arm-pn-2p33.zip) | [Pixie_Net_Manual: 2.32](./release_packages/Pixie_Net_Manual.pdf) | 



## Version 2.27 PTP, May 2023
Release updates include
- FW: Recompiled latest FW with PTP support
- SW: Clarify distinction between "current" and "file" webpages (work in progress)

This version should ONLY be used for Pixie-Net units supporting PTP

Supported variants are <br/>
*Hardware Revision B, 12-bit PTP*
| Firmware Type |	Firmware ID |	Firmware Files |	Software Files | Documentation |
| --------------| ------------| ----------------- | ----------------- | ------------- |
| PTP <br/> Provides hardware time stamping for LinuxPTP utility. Requires use of alternate Ethernet port | 0x2227 | [sd-bootfiles-pn-PTP: 2.27](./release_packages/sd-bootfiles-pn-PTP-2p27.zip)   | [sw-arm-pn: 2.27](./release_packages/sw-arm-pn-2p27.zip) | [Pixie_Net_Manual: 2.25](./release_packages/Pixie_Net_Manual.pdf) | 
 







## Release Information
A full Pixie-Net  software/firmware release consists of the following components

| Component name | Description	| Install & Update |
| -------------- | ------------ | ----------------- |
| Software <br/> sw-arm-pn-[version] | The setup and DAQ procedures that go into /var/www on the Pixie Net’s Linux OS. |	Unzip, then copy to /var/www on the Pixie Net's Linux OS |
| Firmware <br/> sd-bootfiles-pn-[variant]-[version]	| The Zynq controller bootfiles for the FAT partition of the SD card. Includes the pulse processing firmware that is specific to each hardware and firmware variant |	Unzip, then copy the 4 bootfiles to the FAT partition of the SD card. Ensure it matches the hardware (STD = 12bit, 14B = 14bit, PTP = PTP Ethernet) |
| SD image <br/> sd-image-pn-[version] | The full (zip compressed) SD card image, includes sw-arm-pn, sd-bootfiles-pn, and all Linux OS files Only updated for changes in Linux OS |	Unzip, then write to an SD card with a byte-by-byte image writer. If an older version, update software and firmware |
| Manual <br/> Pixie_Net_Manual.pdf | The user manual. It is also included in sw-arm-pnxl. | please read |

Notes 
- For first time users, please also see the [Quick Start guide](./release_packages/PixieNet_QuickStart.pdf)
- The PSA firmware requires the unit to be specifically licensed for the pulse shape analysis and constant fraction timing functions. There is no physical difference in the hardware. 
- Typically, the software (sw-arm-pn) is the same for all firmware variants. FW/SW versions that vary only with the last digit of the ID can be assumed to be compatible. 
- To download, click on the link, then on the download button in the github page


## Older releases

## Version 2.32, February 2024
Release updates include
 
- FW/SW: revise channel swap method in findsettings. Add tau finder
- SW: in avgadc function, capture each channel individually
- Manual: Add notes on using ping to find IP

Supported variants are <br/>
*Hardware Revision B, 12-bit and 14-bit*
| Firmware Type |	Firmware ID |	Firmware Files |	Software Files | Documentation |
| --------------| ------------| ----------------- | ----------------- | ------------- |
| Standard 12 bit | 0xA991_0232 | [sd-bootfiles-pn-STD: 2.32](./release_packages/sd-bootfiles-pn-STD-2p32.zip)   | [sw-arm-pn: 2.32](./release_packages/sw-arm-pn-2p32.zip) | [Pixie_Net_Manual: 2.32](./release_packages/Pixie_Net_Manual.pdf) | 
| Standard 14 bit | 0xA9A1_0232 | [sd-bootfiles-pn-14B: 2.32](./release_packages/sd-bootfiles-pn-14B-2p32.zip)   | [sw-arm-pn: 2.32](./release_packages/sw-arm-pn-2p32.zip) | [Pixie_Net_Manual: 2.32](./release_packages/Pixie_Net_Manual.pdf) | 
| PSA 12 bit<br/> Includes pulse shape analysis functions e.g. to distinguish gammas and neutrons, and constant fraction timing logic. Licensing required | 0xA991_1231 | [sd-bootfiles-pn-PSA: 2.31](./release_packages/sd-bootfiles-pn-PSA-2p31.zip)   | [sw-arm-pn: 2.30](./release_packages/sw-arm-pn-2p30.zip) | [Pixie_Net_Manual: 2.31](./release_packages/Pixie_Net_Manual.pdf) | 




## Version 2.31, November 2023
Release updates include
 
- FW: apply bug fixes for system time
- Manual: Add notes on using arp -a to find IP by MAC

Supported variants are <br/>
*Hardware Revision B, 12-bit and 14-bit*
| Firmware Type |	Firmware ID |	Firmware Files |	Software Files | Documentation |
| --------------| ------------| ----------------- | ----------------- | ------------- |
| Standard 12 bit | 0xA991_0231 | [sd-bootfiles-pn-STD: 2.31](./release_packages/sd-bootfiles-pn-STD-2p31.zip)   | [sw-arm-pn: 2.30](./release_packages/sw-arm-pn-2p30.zip) | [Pixie_Net_Manual: 2.31](./release_packages/Pixie_Net_Manual.pdf) | 
| Standard 14 bit | 0xA9A1_0231 | [sd-bootfiles-pn-14B: 2.31](./release_packages/sd-bootfiles-pn-14B-2p31.zip)   | [sw-arm-pn: 2.30](./release_packages/sw-arm-pn-2p30.zip) | [Pixie_Net_Manual: 2.31](./release_packages/Pixie_Net_Manual.pdf) | 
| PSA 12 bit<br/> Includes pulse shape analysis functions e.g. to distinguish gammas and neutrons, and constant fraction timing logic. Licensing required | 0xA991_1231 | [sd-bootfiles-pn-PSA: 2.31](./release_packages/sd-bootfiles-pn-PSA-2p31.zip)   | [sw-arm-pn: 2.30](./release_packages/sw-arm-pn-2p30.zip) | [Pixie_Net_Manual: 2.31](./release_packages/Pixie_Net_Manual.pdf) | 



## Version 2.30, August 2023
Release updates include
 
- SW: Updates for 14-bit firmware
- SW: Re-introduced MAXWIDTH logic to reject pulses piled up on rising edge
- FW: Updates for 14-bit hardware


Supported variants are <br/>
*Hardware Revision B, 12-bit and 14-bit*
| Firmware Type |	Firmware ID |	Firmware Files |	Software Files | Documentation |
| --------------| ------------| ----------------- | ----------------- | ------------- |
| Standard 12 bit | 0xA991_0227 | [sd-bootfiles-pn-STD: 2.27](./release_packages/sd-bootfiles-pn-STD-2p27.zip)   | [sw-arm-pn: 2.28](./release_packages/sw-arm-pn-2p28.zip) | [Pixie_Net_Manual: 2.30](./release_packages/Pixie_Net_Manual.pdf) | 
| PSA 12 bit<br/> Includes pulse shape analysis functions e.g. to distinguish gammas and neutrons, and constant fraction timing logic. Licensing required | 0xA991_1228 | [sd-bootfiles-pn-PSA: 2.28](./release_packages/sd-bootfiles-pn-PSA-2p28.zip)   | [sw-arm-pn: 2.28](./release_packages/sw-arm-pn-2p28.zip) | [Pixie_Net_Manual: 2.30](./release_packages/Pixie_Net_Manual.pdf) | 
| Standard 14 bit | 0xA9A1_0230 | [sd-bootfiles-pn-14B: 2.30](./release_packages/sd-bootfiles-pn-14B-2p30.zip)   | [sw-arm-pn: 2.30](./release_packages/sw-arm-pn-2p30.zip) | [Pixie_Net_Manual: 2.30](./release_packages/Pixie_Net_Manual.pdf) | 


## Version 2.28, July 2023
Release updates include
 
- webpages:
  Added webops page to view/edit all entries in settings.ini
  Added option to MCA page to update periodically
  Updated webpages and programs copying them to make clearer if data from file or from FPGA

- Doc: Clarify manual for PTP variant

- SW: Add an optional file name argument to startdaq and coincdaq. 


Supported variants are <br/>
*Hardware Revision B*
| Firmware Type |	Firmware ID |	Firmware Files |	Software Files | Documentation |
| --------------| ------------| ----------------- | ----------------- | ------------- |
| Standard | 0x0227 | [sd-bootfiles-pn-STD: 2.27](./release_packages/sd-bootfiles-pn-STD-2p27.zip)   | [sw-arm-pn: 2.28](./release_packages/sw-arm-pn-2p28.zip) | [Pixie_Net_Manual: 2.28](./release_packages/Pixie_Net_Manual.pdf) | 
| PSA <br/> Includes pulse shape analysis functions e.g. to distinguish gammas and neutrons, and constant fraction timing logic. Licensing required | 0x1228 | [sd-bootfiles-pn-PSA: 2.28](./release_packages/sd-bootfiles-pn-PSA-2p28.zip)   | [sw-arm-pn: 2.28](./release_packages/sw-arm-pn-2p28.zip) | [Pixie_Net_Manual: 2.28](./release_packages/Pixie_Net_Manual.pdf) | 



## Version 2.25, March 2023
Release updates include
 
- SW/FW: Added control bit CCSRA_NO_OVERLAP_08. Defaults to 1 (defaults.ini). 
  This suppresses capture of overlapping waveforms, which may be problematic at high count rates. 

- SW: Updated links to XIA support webpages

- SW: Updated messages printed during DAQ by startdaq and acquire. 

- SW: To avoid out-of-memory crashes, acquire will pause taking data when more than 100,000 
 events are queued for writing to file and resume when queue drops to 80,000 events. 

## Version 2.24, December 2022
Release updates include
 
- SW: Added CFD debug values to LM data in run type 0x400

Supported variants are <br/>
*Hardware Revision B*
| Firmware Type |	Firmware ID |	Firmware Files |	Software Files | Documentation |
| --------------| ------------| ----------------- | ----------------- | ------------- |
| Standard | 0x0220 | [sd-bootfiles-pn-STD: 2.20](./release_packages/sd-bootfiles-pn-STD-2p20.zip)   | [sw-arm-pn: 2.24](./release_packages/sw-arm-pn-2p24.zip) | [Pixie_Net_Manual: 2.22](./release_packages/Pixie_Net_Manual.pdf) | 
| PSA <br/> Includes pulse shape analysis functions e.g. to distinguish gammas and neutrons, and constant fraction timing logic. Licensing required | 0x1223 | [sd-bootfiles-pn-PSA: 2.23](./release_packages/sd-bootfiles-pn-PSA-2p23.zip)   | [sw-arm-pn: 2.24](./release_packages/sw-arm-pn-2p24.zip) | [Pixie_Net_Manual: 2.22](./release_packages/Pixie_Net_Manual.pdf) | 
| I2C <br/> Modifies PMOD I/O pins to support I2C and UART from Linux Also includes real time clock driver in Linux kernel | 0x5223 | [sd-bootfiles-pn-I2C: 2.23](./release_packages/sd-bootfiles-pn-I2C-2p23.zip)   | [sw-arm-pn: 2.24](./release_packages/sw-arm-pn-2p24.zip) | [Pixie_Net_Manual: 2.22](./release_packages/Pixie_Net_Manual.pdf) | 



2.23: 
- Added control bit CCSRC_VETO_RSTHI_12 for a custom variant. Ignored in standard or PSA code

2.22:
- Updated webops pages and underlying functions, now usable as basic web API
- Updated Igor Pro demo interface with web API I/O. Please contact XIA to try out
- Added automatic execution of ./progfippi at boot time to Linux OS (systemd)


