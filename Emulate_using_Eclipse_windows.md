# Emulate FreeRTOS on QEMU Windows
To emulate the FreeRTOS on Stellaris LM3S6965 using QEMU

## Step 1: Download Eclipse Embedded CDT (C/C++ Development Tools)
Download and install Eclipse Embedded CDT from [here](https://www.eclipse.org/downloads/packages/).

## Step 2 : Download the FreeRTOS source code
Download and extract the FreeRTOS source code from [here](https://www.freertos.org/a00104.html)
 
Note: Don't download the LTS release

## Step 3: Install the GNU Arm Embedded Toolchain
Download the GNU arm embedded toolchain from [here](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) and add to the PATH variable

## Step 4: Install QEMU for Windows
Download QEMU for windows [here](https://www.qemu.org/download/#windows) and add to the PATH variable

## Step 5: Open LM3S6965 Demo project on Eclipse
- Click **"File->Import"** and 
- Select Existing projects into workspace
- Navigate to the **FreeRTOS/Demo/CORTEX_LM3S6965_GCC_QEMU** and click Finish

![windows](https://user-images.githubusercontent.com/31447839/128664337-50aab27c-91b8-4cb0-a5f7-718900fda32f.png)

## Step 6: Install Make and add to the PATH 
Download Make for Windows from [here](http://gnuwin32.sourceforge.net/packages/make.htm)

## Step 7: Add the Make and GNU Arm Embedded Toolchain to the PATH variable on Eclipse
- Go to **"Project -> Properties"** 
- Naviagte to **"C/C++build->Environment"**
- Add the PATH variable.

![image](https://user-images.githubusercontent.com/31447839/128664591-bae5bfa5-a654-4caa-848f-0115574d6a7f.png)

## Step 8: Build the project

- Make sure the project is built without any error

## Step 9(Optional): Start the QEMU manually
 **Note: Skip this step if you add qemu to the system PATH variable.Step 10 will start the QEMU automatically**
 
- Open the terminal and navigate to the FreeRTOS/Demo/CORTEX_LM3S6965_GCC_QEMU directory
- Start QEMU by entering the command **"qemu-system-arm.exe -kernel .\Debug\RTOSDemo.elf -S -s -machine lm3s6965evb"**
- QEMU window will wait for the gdb connection


![image](https://user-images.githubusercontent.com/31447839/128665014-2248b6eb-ad31-4f3d-be87-403c58e749b7.png)


## Step 10: Launch the Debug session on Eclipse
- In the project explorer, right click on "start_quem_and_debug.launch"
- Click **"Debug As->1 start_quem_and_debug"** 

![image](https://user-images.githubusercontent.com/31447839/127738873-d92da98a-77b0-447f-adc3-fc635e361cb4.png)


Debug Session will be launched, create breakpoint and analyze the code. 
![image](https://user-images.githubusercontent.com/31447839/128665101-81118240-1c6c-4a07-98ee-e9a3f7d7f3ab.png)



## References
[https://www.freertos.org/install-and-start-qemu-emulator/](https://www.freertos.org/install-and-start-qemu-emulator/)   
[https://www.freertos.org/cortex-m3-qemu-lm3S6965-demo.html](https://www.freertos.org/cortex-m3-qemu-lm3S6965-demo.html)
