__Software needed for Windows__
[Vivado HL WebPack](https://xilinx.com/support/download.html)

__Windows Subsystem for Linux and Ubuntu 20.04 LTS setup__

Follow the "Manual Installation Steps" listed [here](https://docs.microsoft.com/en-us/windows/wsl/install-win10) to get WSL enabled.
Next install Ubuntu 20.04 LTS.

![image](https://user-images.githubusercontent.com/8312541/132419142-06126be2-6136-42b6-95b9-35481e2224c8.png)

![image](https://user-images.githubusercontent.com/8312541/132419192-3ea90f13-8488-4f3d-8c20-457a072dea25.png)

![image](https://user-images.githubusercontent.com/8312541/132419235-d373bba2-bf01-499d-82ba-f54e795c713f.png)

![image](https://user-images.githubusercontent.com/8312541/132419262-55bc7a7a-d92e-43dc-b368-06cd46f98eae.png)

If you take a close look at the screen you'll notice that the IP address may be different than your actual hosts IP address.

If you look in the Virtual Switch Manager w/in Hyper-V Manager you'll notice that WSL creates it's own internal networking virtual switch.  This will be an important thing to keep in mind when we later configure X11 in Ubuntu and go to export the display for the Linux Vivado install.  ;-)

![image](https://user-images.githubusercontent.com/8312541/132419796-b2ac726b-4e83-46dd-b65f-1ac28b3a53b8.png)





