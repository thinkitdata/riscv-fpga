# Steps necessary to get WSL2 and Ubuntu 20.04 LTS installed on your Win10 Pro host machine

__Software needed for Windows10 Professional__

* [Sifive Freedom Studio](https://www.sifive.com/software) (RISC-V development environment for Windows)

* [Vivado HL WebPack](https://www.xilinx.com/member/forms/download/xef.html?filename=Xilinx_Unified_2021.1_0610_2318_Win64.exe) (Xilinx FPGA development environment for Windows)

* [MobaXterm](https://download.mobatek.net/2132021082033134/MobaXterm_Installer_v21.3.zip) (X11 for Windows)

__Windows Subsystem for Linux and Ubuntu 20.04 LTS setup__

Follow the "Manual Installation Steps" listed [here](https://docs.microsoft.com/en-us/windows/wsl/install-win10) to get WSL enabled and Ubuntu 20.04 LTS installed.

1. Install **Windows Subsystem for Linux**, launch PowerShell and run:
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
2. Verify that you meet the requirements for **Windows Subsystem for Linux v2**:

* To check your version and build number, select **Windows logo key + R, type winver, select OK**.
* For x64 systems: Version 1903 or higher, with Build 18362 or higher.
![image](https://user-images.githubusercontent.com/8312541/132558464-734dfe60-61e6-4ffb-b692-cf908097b027.png)


3. Enable **Virtual Machine Feature**, launch PowerShell and run:
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

![image](https://user-images.githubusercontent.com/8312541/132419142-06126be2-6136-42b6-95b9-35481e2224c8.png)

4. Enable **Linux Kernel update package for x64** from here: [WSL2 Linux Kernel update package for x64](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

![image](https://user-images.githubusercontent.com/8312541/132419192-3ea90f13-8488-4f3d-8c20-457a072dea25.png)

5. **Set WSL2 as the default**, launch PowerShell and run:
```
wsl --set-default-version 2
```

![image](https://user-images.githubusercontent.com/8312541/132419235-d373bba2-bf01-499d-82ba-f54e795c713f.png)

6. Install **Ubuntu 20.04 LTS** from the [Microsoft Store](https://aka.ms/wslstore)

![image](https://user-images.githubusercontent.com/8312541/132419262-55bc7a7a-d92e-43dc-b368-06cd46f98eae.png)
When the Ubuntu installation completes you'll notice that the IP address may be different than your actual hosts IP address.

If you look in the Virtual Switch Manager w/in Hyper-V Manager you'll notice that WSL creates it's own internal networking virtual switch.  This will be an important thing to keep in mind when we later configure X11 in Ubuntu and go to export the display for the Linux Vivado install.  ;-)

![image](https://user-images.githubusercontent.com/8312541/132419796-b2ac726b-4e83-46dd-b65f-1ac28b3a53b8.png)





