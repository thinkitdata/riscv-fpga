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
