# Steps necessary for compiling the FPGA image

# 1. Download the Digilent board files
__(adjust the below paths to match your particular directory locations)__
```
git clone https://github.com/Digilent/vivado-boards.git
sudo cp -r /mnt/f/dev/fpga/vivado-boards/new/board_files/* /mnt/f/dev/fpga/tools/Xilinx/Vivado/2021.1/data/boards/
```
My target directory before copying the board files:
![image](https://user-images.githubusercontent.com/8312541/132749166-c2ae15ce-b775-4525-b124-95ba3be2eee9.png)

My target directory after copying the board files:
![image](https://user-images.githubusercontent.com/8312541/132750982-d3ba05dd-079c-4210-bdea-47b2dfb27ea0.png)

# 2. Build the Arty A7-100T RISC-V FPGA image
The RISC-V FPGA image is compiled using __Chisel__.
