# Emulate FreeRTOS on QEMU Ubuntu
To emulate the FreeRTOS on Stellaris LM3S6965 using QEMU

## Step 1: Download Eclipse Embedded CDT (C/C++ Development Tools)
Download and install Eclipse Embedded CDT from [here](https://www.eclipse.org/downloads/packages/).

## Step 2 : Download the FreeRTOS source code
Download and extract the FreeRTOS source code from [here](https://www.freertos.org/a00104.html)
 
Note: Don't download the LTS release

## Step 3: Install the GNU Arm Embedded Toolchain
Download the GNU arm embedded toolchain from [here](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) and extract to the opt directory

## Step 4: Open LM3S6965 Demo project on Eclipse
- Click "File->Import" and 
- Select Existing projects into workspace
- Navigate to the FreeRTOS/Demo/CORTEX_LM3S6965_GCC_QEMU and click Finish

![image](https://user-images.githubusercontent.com/31447839/127738571-8994fbd9-4ccc-42a8-98c4-ea41b18d22c3.png)

## Step 5: Build the project

- Make sure the project is built without any error

## Step 6(Optional): Start the QEMU manually
 **Note: Skip this step if you add qemu to the system PATH variable.Step 7 will start the QEMU automatically**

- Open the terminal and navigate to the FreeRTOS/Demo/CORTEX_LM3S6965_GCC_QEMU directory
- Start QEMU by entering the command **"qemu-system-arm -kernel ./Debug/RTOSDemo.elf -S -s -machine lm3s6965evb"**
- QEMU window will wait for the gdb connection


![image](https://user-images.githubusercontent.com/31447839/127738805-c738c11f-680d-4dad-a14c-cfbeed8e5a6a.png)

## Step 7: Launch the Debug session on Eclipse
- In the project explorer, right click on "start_quem_and_debug.launch"
- Click "Debug As->1 start_quem_and_debug" 

![image](https://user-images.githubusercontent.com/31447839/127738873-d92da98a-77b0-447f-adc3-fc635e361cb4.png)


Debug Session will be launched, create breakpoint and analyze the code. 
![image](https://user-images.githubusercontent.com/31447839/127746206-d9fec50a-1932-4ae0-b9b9-540ed193237d.png)


## References
[https://www.freertos.org/install-and-start-qemu-emulator/](https://www.freertos.org/install-and-start-qemu-emulator/)   
[https://www.freertos.org/cortex-m3-qemu-lm3S6965-demo.html](https://www.freertos.org/cortex-m3-qemu-lm3S6965-demo.html)
