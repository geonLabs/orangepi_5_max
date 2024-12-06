# orangepi_5_max
### 1. password change
`sudo vim /etc/pam.d/common-password`  
password        [success=1 default=ignore]      pam_unix.so sha512 minlen=1 -> change  
`passwd`  

---
### 2. Kernel header install
sudo dpkg -i /opt/linux-headers-legacy-rockchip-rk3588_1.0.0_arm64.deb  

---

### 3. python env
```
sudo apt-get update
sudo apt-get install python3-pip python3-venv -y
```
---
### 4. hailo install
#### ------------------------------------------------------------------------------
https://hailo.ai/developer-zone/software-downloads/  
Hailo Accelerator Integration Tool – Ubuntu package (deb) for arm64  
HailoRT – PCIe driver Ubuntu package (deb)  
HailoRT – Ubuntu package (deb) for arm64  
HailoRT – Python package (whl) for Python 3.8, aarch64  
#### ------------------------------------------------------------------------------
```
mkdir hailo && cd hailo
sudo dpkg -i hailort-pcie-driver_4.19.0_all.deb hailort_4.19.0_arm64.deb
python3 -m venv hailo_venv
source ./hailo_venv/bin/activate
pip install wheel
pip install netifaces
pip install hailort-4.19.0-cp38-cp38-linux_aarch64.whl
```
---

### 5. Gnome Interface
```
sudo apt-get install wget -y
wget http://ports.ubuntu.com/ubuntu-ports/pool/main/x/xorg-server/xserver-common_1.20.13-1ubuntu1~20.04.18_all.deb
sudo dpkg -i xserver-common_1.20.13-1ubuntu1~20.04.18_all.deb
sudo apt --fix-broken install

sudo apt install xwayland -y 
sudo apt install gnome-session gnome-terminal gdm3 ubuntu-gnome-desktop -y
sudo apt install gnome-tweaks gnome-shell-extensions -y
```
---

### 6. OAK-D Cam (Python)
```
sudo wget -qO- https://docs.luxonis.com/install_depthai.sh | bash
sudo apt-mark unhold $(sudo apt-mark showhold)
sudo apt --fix-broken install
sudo apt update

sudo wget -qO- https://docs.luxonis.com/install_depthai.sh | bash
sudo apt install libopencv-dev
git clone https://github.com/luxonis/depthai-python.git
cd depthai-python/examples
python3 install_requirements.py
pip3 install opencv-python
```
---

### 7. ROS
official homepage  
https://wiki.ros.org/noetic/Installation/Ubuntu  
---

### 8. OAK-D Cam(ROS)
