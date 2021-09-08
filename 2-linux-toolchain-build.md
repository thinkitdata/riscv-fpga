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
