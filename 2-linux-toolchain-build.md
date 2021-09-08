# Here is the procedure for building the development tool chain in Ubuntu

__This is required for building the RISC-V firmware image that will be programmed onto our FPGA__

1. Install **device-tree-compiler**:
```
sudo apt-get install device-tree-compiler
```
2. Install **default-jre**:
```
sudo apt-get install default-jre
```
3. Install **openjdk-8-jdk**:
```
sudo apt install openjdk-8-jdk
```
4. Set **JAVA_HOME** environment variable:
```
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
```
5. Add **JAVA_HOME** to path:
```
export PATH=$PATH:$JAVA_HOME/bin
```
6. Let's update our system (could've done this prior to step 1 but this will suffice):
```
sudo apt-get update
```
__Now we have to install X11 on both our Ubuntu environment and our Windows host__

We'll do the Windows host installation first.

1. On your Windows host install MobaXterm (free version) from [here](https://mobaxterm.mobatek.net/download.html)

Once installed launch it and this is the console you should see:
![image](https://user-images.githubusercontent.com/8312541/132576783-59ea90e4-c32a-4f97-b6d8-6c94ceb5b498.png)

In mobaxterm settings -> Configuration -> x11 -> **set OpenGL Acceleration to: Hardware**
![image](https://user-images.githubusercontent.com/8312541/132580412-290d6166-2765-42c5-977d-0befb85084bd.png)
**Notice that in the yellow circle on the above image that the X11 display is the IP address of your Windows host.**
In our case our X11 display is 10.0.0.48:0.0.  This is what we'll set the $DISPLAY variable to in Ubuntu after X11 is installed.

Now we install X11 on Ubuntu.

2. Install **x11-server-utils**:
```
sudo apt install x11-xserver-utils
```
3. Install **xorg**:
```
sudo apt install xorg
```
4. Export your **DISPLAY** environment variable using the display value from MobaXterm (i.e. your Windows host IP):
```
export DISPLAY=10.0.0.48:0.0
```

__Now we have to download and install Vivado as part of our Linux tool chain__

1.  Download [Vivado Design Suite for Linux](https://www.xilinx.com/member/forms/download/xef.html?filename=Xilinx_Unified_2020.1_0602_1208_Lin64.bin)
2.  Place the downloaded bin file into a convenient and easily accessibly directory to install from and cd into it.  I used /mnt/f/dev/fpga/.
3.  Install **Vivado**:
```
sudo ./Xilinx*.bin
```
You should see the installer launch via your MobaXterm X11 display.
![image](https://user-images.githubusercontent.com/8312541/132583558-94566558-4130-4823-8eea-a22bc2551a31.png)
The installation takes a L-O-N-G time.  Mine took ~3hrs or so...
![image](https://user-images.githubusercontent.com/8312541/132583699-1089bfec-d2de-4d65-9d4e-d49b7b2ac7f0.png)

4.  Install **libncurses5**:
```
sudo apt install libncurses5
```
Test the installation using **YOUR installation path**:
```
kwygbo@thinkitdata-ws1:/mnt/f/dev/fpga/tools/Xilinx/Vivado/2021.1$ ./bin/vivado -help
```
![image](https://user-images.githubusercontent.com/8312541/132586135-1b67bf94-82c2-4204-8259-f1e24c0cc2a6.png)

```
kwygbo@thinkitdata-ws1:/mnt/f/dev/fpga/tools/Xilinx/Vivado/2021.1$ ./bin/vivado -mode gui
```
![image](https://user-images.githubusercontent.com/8312541/132586859-cb51761f-7152-4fea-aaf0-38745dc52f98.png)

![image](https://user-images.githubusercontent.com/8312541/132586994-58715d98-f88a-4626-aa48-c876607dc595.png)

**Stop the gui**
Click on *Tcl Console* in the bottom left of the gui
![image](https://user-images.githubusercontent.com/8312541/132587380-b7342ab7-f61f-412a-9156-19317c35e456.png)

Type *stop_gui* into the bottom command bar
![image](https://user-images.githubusercontent.com/8312541/132588118-96304dcd-759f-4f22-9695-b19212e2b69e.png)

Gui stops and your console is at the *Vivado%* prompt
![image](https://user-images.githubusercontent.com/8312541/132587711-1cc0e248-cbca-4f1b-88b3-a8aa75449e77.png)

Type *exit*
![image](https://user-images.githubusercontent.com/8312541/132587877-bf6a7602-f5ea-4910-9f54-a1bcefeecc57.png)


