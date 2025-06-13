# MCUXpresso SDK : mcux-edgelock

## Overview
This repository is for MCUXpresso SDK EdgeLock firmware delivery and it contains
the components officially provided in NXP MCUXpresso SDK. This repository is
part of the MCUXpresso SDK overall delivery which is composed of several
sub-repositories/projects. Navigate to the top/parent repository
(mcuxsdk-manifests) for the complete delivery of MCUXpresso SDK.

## Documentation
Overall details can be reviewed here: [MCUXpresso SDK Online Documentation](https://mcuxpresso.nxp.com/mcuxsdk/latest/html/introduction/README.html)

## Setup
Instructions on how to install the MCUXpresso SDK provided from GitHub via
west manifest [Getting Started with SDK - Detailed Installation Instructions](https://mcuxpresso.nxp.com/mcuxsdk/latest/html/gsd/installation.html#installation)

## Contribution
Contributions are not currently accepted.
Guidelines to contribute will be posted in the future.

---------------------------------

## Using the Firmware
This repository contains precompiled loadable firmware for the EdgeLock S200
and S400 enclaves. The firmware files are provided in binary format and are
intended to be loaded into memory alongside the application binary.

For demonstration purposes, all SDK examples that utilize loadable
firmwares use a C-array representation of the corresponding firmware binary.

Loading the firmwares is done by using the provided APIs for each of the SXXX
systems' messaging units:
* S200: `ELEMU_loadFw()`,
* S400: `ELE_LoadFw()`.
