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

#### J-Link Commands for Firmware Programming
    Erase 0x400000 0x440000           // For IVT (Initial Vector Table) variant: Erase 0x420000 0x460000
    Loadfile <FW_binary> 0x400000     // Address 0x420000 for IVT
    W8 0x1b000000 0xAABBCCDDDDCCBBAA  // Write special flags to trigger FW installation
    R                                 // Perform reset

#### (Optional) Verify Flag Write
    Mem8 0x1b000000 8
