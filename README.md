# Pixie-Net Release Notes

## Version 2.27 PTP, May 2023
Release updates include
- FW: Recompiled latest FW with PTP support
- SW: Clarify distinction between "current" and "file" webpages (work in progress)

This version should ONLY be used for Pixie-Net units supporting PTP

Supported variants are <br/>
*Hardware Revision B*
| Firmware Type |	Firmware ID |	Firmware Files |	Software Files | Documentation |
| --------------| ------------| ----------------- | ----------------- | ------------- |
| PTP <br/> Provides hardware time stamping for LinuxPTP utility. Requires use of alternate Ethernet port | 0x2227 | [sd-bootfiles-pn-PTP: 2.27](./release_packages/sd-bootfiles-pn-PTP-2p27.zip)   | [sw-arm-pn: 2.27](./release_packages/sw-arm-pn-2p27.zip) | [Pixie_Net_Manual: 2.25](./release_packages/Pixie_Net_Manual.pdf) | 
 

## Version 2.25, March 2023
Release updates include
 
- SW/FW: Added control bit CCSRA_NO_OVERLAP_08. Defaults to 1 (defaults.ini). 
  This suppresses capture of overlapping waveforms, which may be problematic at high count rates. 

- SW: Updated links to XIA support webpages

- SW: Updated messages printed during DAQ by startdaq and acquire. 

- SW: To avoid out-of-memory crashes, acquire will pause taking data when more than 100,000 
 events are queued for writing to file and resume when queue drops to 80,000 events. 


Supported variants are <br/>
*Hardware Revision B*
| Firmware Type |	Firmware ID |	Firmware Files |	Software Files | Documentation |
| --------------| ------------| ----------------- | ----------------- | ------------- |
| Standard | 0x0225 | [sd-bootfiles-pn-STD: 2.25](./release_packages/sd-bootfiles-pn-STD-2p25.zip)   | [sw-arm-pn: 2.25](./release_packages/sw-arm-pn-2p25.zip) | [Pixie_Net_Manual: 2.25](./release_packages/Pixie_Net_Manual.pdf) | 
| PSA <br/> Includes pulse shape analysis functions e.g. to distinguish gammas and neutrons, and constant fraction timing logic. Licensing required | 0x1225 | [sd-bootfiles-pn-PSA: 2.25](./release_packages/sd-bootfiles-pn-PSA-2p25.zip)   | [sw-arm-pn: 2.25](./release_packages/sw-arm-pn-2p25.zip) | [Pixie_Net_Manual: 2.25](./release_packages/Pixie_Net_Manual.pdf) | 





 
## Release Information
A full Pixie-Net  software/firmware release consists of the following components

| Component name | Description	| Install & Update |
| -------------- | ------------ | ----------------- |
| Software <br/> sw-arm-pn-[version] | The setup and DAQ procedures that go into /var/www on the Pixie Net’s Linux OS. |	Unzip, then copy to /var/www on the Pixie Net's Linux OS |
| Firmware <br/> sd-bootfiles-pn-[variant]-[version]	| The Zynq controller bootfiles for the FAT partition of the SD card. Includes the pulse processing firmware that is specific to each firmware variant |	Unzip, then copy the 4 bootfiles to the FAT partition of the SD card |
| SD image <br/> sd-image-pn-[version] | The full (zip compressed) SD card image, includes sw-arm-pn, sd-bootfiles-pn, and all Linux OS files Only updated for changes in Linux OS |	Unzip, then write to an SD card with a byte-by-byte image writer. If an older version, update software and firmware |
| Manual <br/> Pixie_Net_Manual.pdf | The user manual. It is also included in sw-arm-pnxl. | please read |

Notes 
- For first time users, please also see the [Quick Start guide](./release_packages/PixieNet_QuickStart.pdf)
- The PSA firmware requires the unit to be specifically licensed for the pulse shape analysis and constant fraction timing functions. There is no physical difference in the hardware. 
- Typically, the software (sw-arm-pn) is the same for all firmware variants. FW/SW versions that vary only with the last digit of the ID can be assumed to be compatible. 
- To download, click on the link, then on the download button in the github page


## Older releases 

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


