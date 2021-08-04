# Emulate FreeRTOS on QEMU Ubuntu in command line
To emulate the FreeRTOS running on Stellaris LM3S6965 using QEMU and use gdb to debug

## Step 1 : Download the FreeRTOS source code
Download and extract the FreeRTOS source code from [here](https://www.freertos.org/a00104.html)
 
Note: Don't download the LTS release

## Step 2 : Install the GNU Arm Embedded Toolchain
Download the GNU arm embedded toolchain from [here](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) and extract to the opt directory
Add the gnu-arm toolchain to the PATH variable

## Step 3 : Build the LM3S6965 QEMU Demo project 
Refer [eclipse_build](https://github.com/AskarKani/Emulate-FreeRTOS-on-QEMU/blob/main/Emulate_on_Eclipse.md)

## Step 4 : Start the QEMU 

- Make sure the project is built without any error
- Open the terminal and navigate to the FreeRTOS/Demo/CORTEX_LM3S6965_GCC_QEMU directory
- Start QEMU by entering the command **"qemu-system-arm -kernel ./Debug/RTOSDemo.elf -S -s -machine lm3s6965evb"**
- QEMU window will wait for the gdb connection.

Note: The -s option will make QEMU listen for an incoming connection from gdb on TCP port 1234 and -S will make QEMU not start the guest until you tell it to from gdb

![image](https://user-images.githubusercontent.com/31447839/127738805-c738c11f-680d-4dad-a14c-cfbeed8e5a6a.png)

## Step 5 : Start gdb and connect to the target QEMU
- Open the terminal and navigate to the FreeRTOS/Demo/CORTEX_LM3S6965_GCC_QEMU directory
- Start gdb by typing **"arm-none-eabi-gdb Debug/RTOSDemo.elf"** in the terminal
- Type **"target remote localhost:1234"** in gdb terminal

![gdb](https://user-images.githubusercontent.com/31447839/128199885-c422217a-96e2-4177-b3a5-bb052dee854a.png)

Keep breakpoint and start debugging!!
