# WIP!
- simple TCP-IP echo example not  tested
- Paho MQTT implementation not added

### This demo project is build for STM32f407VG (Cortex-M4 CPU)

To compile this demo you need to download CrossWorks for ARM - http://www.rowley.co.uk, obtain one-month evaluation
license and additional libs through package manager (search for STM)

After you'll successfully build demo copy .bin file to appropriate directory.

### Download and install Qemu

1. Download and install QEMU: https://github.com/gnuarmeclipse/qemu/releases
2. Check if it works:

`
/Applications/GNU\ ARM\ Eclipse/QEMU/2.8.0-201612271623-dev/bin/qemu-system-gnuarmeclipse --version
`

If you see:

`
GNU ARM Eclipse 64-bits QEMU emulator version 2.8.0 (v2.8.0-646-g2c99a25)
Copyright (c) 2003-2016 Fabrice Bellard and the QEMU Project developers
`

Then you can to continue.

### Run emulation (NETWORK EXAMPLE NOT TESTED YET, BUT NETWORK INTERFACE IMPLEMENTED!)

Switch to dir with your .bin file and run:

`
/Applications/GNU\ ARM\ Eclipse/QEMU/2.8.0-201612271623-dev/bin/qemu-system-gnuarmeclipse --verbose --verbose \
--board NetduinoPlus2 \
--mcu STM32F407VG -gdb tcp::1234 -d unimp,guest_errors \
--nographic --image /Developer/dlt/avianFreeRTOSPaho.bin \
--semihosting-config enable=on,target=native \
--semihosting-cmdline test 1 2 3
`

If you have gdb you can try `gdb 127.0.0.1:1234`

### More detailed information how to run will be provided soon!

=====
TIPS:

To build project we need to set:
Code generartion:
Floating point hardware : fpv4-sp-d16
Floating-point ABI : hard
http://www.openstm32.org/forumthread301
