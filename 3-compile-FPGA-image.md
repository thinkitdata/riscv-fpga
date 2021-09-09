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
![image](https://user-images.githubusercontent.com/8312541/132749331-96307175-e4cc-45c0-ba1f-25a0676fd0c2.png)

