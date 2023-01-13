# Pixie-Net Release Notes


## Version 2.24, December 2022
Release updates include
 
- Added CFD debug values to LM data

Supported variants are <br/>
*Hardware Revision B*
| Firmware Type |	Firmware ID |	Firmware Revision |	Software Revision | Documentation |
| --------------| ------------| ----------------- | ----------------- | ------------- |
| PSA | 0x1223 | [sd-bootfiles-pn-PSA: 2.23](./release_packages/sd-bootfiles-pn-PSA-2p23.zip)   | [sw-arm-pn: 2.24](./release_packages/sw-arm-pn-2p24.zip) | [Pixie_Net_Manual: 2.22](./release_packages/Pixie_Net_Manual.pdf) | 
| Standard | 0x0220 | [sd-bootfiles-pn-STD: 2.20](./release_packages/sd-bootfiles-pn-STD-2p20.zip)   | [sw-arm-pn: 2.24](./release_packages/sw-arm-pn-2p24.zip) | [Pixie_Net_Manual: 2.22](./release_packages/Pixie_Net_Manual.pdf) | 



 
## Release Information
A full Pixie-Net  software/firmware release consists of the following components

| Component name | Description	| Install & Update |
| -------------- | ------------ | ----------------- |
| sw-arm-pn-[version] | The setup and DAQ procedures that go into /var/www on the Pixie Net’s Linux OS. |	Unzip, then copy to /var/www on the Pixie Net's Linux OS |
| sd-bootfiles-pn-[variant]-[version]	| The Zynq controller bootfiles for the FAT partition of the SD card. Includes the pulse processing firmware that is specific to each firmware variant |	Unzip, then copy the 4 bootfiles to the FAT partition of the SD card |
| sd-image-pn-[version] | The full (zip compressed) SD card image, includes sw-arm-pn, sd-bootfiles-pn, and all Linux OS files Only updated for changes in Linux OS |	Unzip, then write to an SD card with a byte-by-byte image writer |
| Pixie_Net_Manual.pdf | The user manual. It is also included in sw-arm-pnxl. | please read |

For first time users, please also see the [Quick Start guide](./release_packages/PixieNet_QuickStart.pdf)

The PSA firmware requires the unit to be specifically licensed for the pulse shape analysis and constant fravtion timing functions. tehre is no physical difference in the hardware. 

Typically, the software (sw-arm-pn) is the same for all firmware variants. FW/SW versions then vary only with the last digit can be assumed to be compatible.  


## Older releases 

2.23: 
- Added control bit CCSRC_VETO_RSTHI_12 for a custom variant. Ignored in standard or PSA code

2.22:
- Updated webops pages and underlying functions, now usable as basic web API
- Updated Igor Pro demo interface with web API I/O. Please contact XIA to try out
- Added automatic execution of ./progfippi at boot time to Linux OS (systemd)


