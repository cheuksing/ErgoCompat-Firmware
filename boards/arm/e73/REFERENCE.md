# Ebyte E73 Module Configuration References

This custom board configuration for the Ebyte E73 module (specifically the E73-2G4M08S1C which uses the Nordic nRF52840 SoC) was created using the following open-source resources and references:

- **ZMK Firmware (`zmkfirmware/zmk`)**: The core structure was modeled after leading nRF52840-based boards in the official ZMK repository.
    - **[nRFMicro](https://github.com/zmkfirmware/zmk/tree/main/app/boards/arm/nrfmicro)**: Used heavily as a reference for a raw Ebyte E73 implementation. The nRFMicro implements the E73 directly, providing the baseline for partition layouts, bootloader parameters, and SoC definitions.
    - **[nice!nano v2](https://github.com/zmkfirmware/zmk/tree/main/app/boards/arm/nice_nano)**: Used as a reference for modern ZMK `defconfig` settings, USB core definitions, and BLE controller flags on the nRF52840.

- **Zephyr RTOS (`nordic/nrf52840_qiaa.dtsi`)**: Leverages Zephyr's upstream device tree structures for the nRF52840, establishing the standard storage/bootloader partitions and providing the `zmk,battery-nrf-vddh` node compatibilities.

- **Ebyte E73-2G4M08S1C Datasheet**: Used to map the 48 available pseudo-GPIO pins of the module into a generic `ebyte,e73-header` connector interface, enabling straightforward pin routing in `arc.dtsi`.