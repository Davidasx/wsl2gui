# wsl2gui
GUI for wsl2
# Usage
## 1.Enable WSL
Run in powershell:
```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
## 2.Enable VM
Run in powershell:
```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
Then,restart.
## 3.Download Kernel Update
Run in powershell:
For x64:
```powershell
curl https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi -o wsl.msi
```
For ARM64:
```powershell
curl https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_arm64.msi -o wsl.msi
```
Then run wsl.msi
## 4.Set WSL2 as default
```powershell
wsl --set-default-version 2
```
## 5.Install WSL
Open `https://aka.ms/wslstore`.
Open Microsoft Store.
Choose Ubuntu and install.
## 6.Settings
```powershell
notepad %USERPROFILE%\.wslconfig
```
Paste the text:
```
[wsl2]
memory=4GB
```
Then save and close.
## 7.Install
```powershell
explorer %LOCALAPPDATA%\packages
```
You will find a 'CanonicalGroup.....' subfolder.
Right-click it.
In the 'High-Level settings',deselect 'Compress folder to save space'.Then confirm all prompts.
```powershell
ubuntu
```
Follow instructions to install.
## 8.Install desktop
After installing WSL,run 'ubuntu' again.
Then:
```bash
sudo apt install xfce4 xfce4-session xrdp
```
After installing XFCE4:
```bash
echo "xfce4-session" > ~/.xsession
sudo service xrdp restart
```
Run in powershell:
```powershell
mstsc.exe /v:localhost:3389
```
A window will popup.
Log-on with your WSL account.
Then the desktop will show in a few seconds!
