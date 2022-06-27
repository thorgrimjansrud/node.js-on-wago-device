# Install and test Node.js on a Wago Device.
Be aware of the device partition sizes and space required for the installation and future apps.

## Installation of WSL and Ubuntu distribution
This is a hyperlink: [Install Windows Subsystem for Linux.](https://nodejs.org/en/download/) <br/>

Picture:
<div align="left">
 <br>
 <img src="Img\Powershell_wsl2.PNG" width="300" hight="300"> <br><br>
</div>

> Hyper-V/Hypervisor platform is not needed for WSL. Only support for "Windows Subsystem" <br/>
> *** Currently there is an issue with WSL + Wago SDK. Ptxdist go -q will throw an error. Pending. *** <br/>

Code:
```
sudo apt remove openssh-server
sudo apt install openssh-server
```
