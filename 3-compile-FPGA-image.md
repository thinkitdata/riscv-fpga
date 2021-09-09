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
The board we are targeting (arty-a7-100) is highlighted in the above image.

# 2. Build the Arty A7-100T RISC-V FPGA image
The RISC-V FPGA image is compiled using __Chisel__ but we need to first edit the makefile because by default it targets the Arty A7-35T FPGA board and we are using the Arty A7-100T FPGA board.

We need to edit /mnt/f/dev/fpga/freedom/Makefile.e300artydevkit (again adjust for your particular directory location)
![image](https://user-images.githubusercontent.com/8312541/132752022-b364ef66-8a14-41fe-b80f-76c78f556041.png)

Notice the highlighted BOARD type of arty
![image](https://user-images.githubusercontent.com/8312541/132753217-c2b4f68c-f682-45fd-923c-73154bc22347.png)


We need to change this to arty_a7_100
![image](https://user-images.githubusercontent.com/8312541/132752936-9b4700fd-7765-4817-b360-0db7d7f3aa78.png)

