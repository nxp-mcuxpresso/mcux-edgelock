# ELE HSEB Firmware

The MCXE3xx devices require HSE firmware to be installed to enable security
features. The firmwares are device-specific and can be found in the
corresponding **MCXE3xx** subfolders.

## ELE HSEB Firmware Installation Guide

To install the ELE HSEB FW, the flash must be programmed and a reset must be
performed. Below you can find an overview of the installation preparation steps
and the installation steps themselves.

### Firmware Installation Preparation

The most convenient way to program the firmware is by using **J-Link Commander**
with the **on-board debugger**.

For detailed instructions on setting up the J-Link firmware for the on-board
debugger, please refer to the **Getting Started** documentation of your device.
A simplified version of the setup steps is provided below for the `frdmmcxe31b`
board:
  - Close jumper **JP3**
  - Use **MCU-Link scripts** (version v3.160 or higher) for J-Link programming

### Firmware Installation

The following was tested with J-Link version V9.32.
Please use the latest available J-Link version for best device support.

The firmware binaries are provided as `.bin.pink` files. Such files are not
readily recognizable by J-Link, but can be simply *renamed* to `.bin` format
before loading.

#### J-Link Commands for Firmware Programming
    Erase 0x400000 0x440000           // For IVT (Initial Vector Table) variant: Erase 0x420000 0x460000
    Loadfile <FW_binary> 0x400000     // Address 0x420000 for IVT
    W8 0x1b000000 0xAABBCCDDDDCCBBAA  // Write special flags to trigger FW installation
    R                                 // Perform reset

#### (Optional) Verify Flag Write
    Mem8 0x1b000000 8

## ELE HSEB Firmware Erasure
If the device is in the `CUST_DEL` lifecycle, the firmware may also be erased.
The easiest way to delete such firmware is during runtime by utilizing the
firmware erasure service. Below you can find a code snippet for utilizing this
service.

Note that this service erases Sys-Img, Backup FW as well Current running HSE FW
from code flash.

    #include "hse_host.h"
    ...
    uint8_t muIf                    = 0U;
    uint8_t muChannelIdx            = 1U;
    hseSrvDescriptor_t* pHseSrvDesc = &gHseSrvDesc[muIf][muChannelIdx];
    pHseSrvDesc->srvId              = HSE_SRV_ID_ERASE_FW;
    hseSrvResponse_t response       = HSE_Send(muIf, muChannelIdx, gSyncTxOption, pHseSrvDesc);

An erased firmware can be reinstalled by following the **Firmware Installation**
steps described above.
