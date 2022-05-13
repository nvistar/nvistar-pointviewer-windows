# How to Use NVISTAR LIDAR POINTVIEWER

## Hardware Connection
The nvistar lidar is a USB device, which can be directly inserted into the computer for use. WINDOWS 10 can be installed without driver. Other systems may require the driver.eg WINDOWS 7
To install the driver software. The serialport identification content is as follows:

![image](https://github.com/nvistar/nvistar-pointviewer-windows/raw/master/image/comm_show.png)

If the recognition error, you need to download the virtual [serialport driver](https://github.com/nvistar/nvistar-lidar-tools/blob/master/virtual%20com%20driver/VirtualCOM_DriverInstall.exe) on the website

Once the serialport is installed, the serial device can be displayed on the PC.
Similarly, the client can support network interface, the default IP address of the adapter board is 192.168.1.200. The communication protocol with radar is UDP communication by default, and the port is 8100.
By default, it is UDP communication, port 8100.
The IP address, gateway and subnet mask can also be modified by this client, which will be explained in detail later. The communication interface is TCP protocol, port 8200.
If you use serial communication, you can ping the IP address first, and if it is normal, you can receive a ping answer.

![image](https://github.com/nvistar/nvistar-pointviewer-windows/raw/master/image/ping_show.png)

## Software use and instructions

### Software Introduction

After opening the software, it will open normally, the interface is shown below:

![image](https://github.com/nvistar/nvistar-pointviewer-windows/raw/master/image/soft_show_1.png)
![image](https://github.com/nvistar/nvistar-pointviewer-windows/raw/master/image/soft_show_2.png)

### Parameter Configuration

![image](https://github.com/nvistar/nvistar-pointviewer-windows/raw/master/image/soft_show_3.png)

As shown above, the radar information can be configured, mainly the speed, sampling rate and trailing intensity information can be configured. The same can be selected
Whether with signal quality information.

![image](https://github.com/nvistar/nvistar-pointviewer-windows/raw/master/image/soft_show_4.png)

As shown above, you can configure the network parameters, i.e. IP address, gateway, subnet mask, etc. After saving, restart the network adapter to take effect

### Software Use

Click the 'Run' button, and you can use the radar map normally.

![image](https://github.com/nvistar/nvistar-pointviewer-windows/raw/master/image/soft_show_5.png)


### Shortcut Operation

|  Button     | Operation results |
|  :----:  | :----:  |
| ↑  | Pointcloud moving up |
| ↓  | Pointcloud moving down |
| ← | Pointcloud moving left |
| →  | Pointcloud moving right |
| + | Pointcloud Zoom in|
| -  | Pointcloud Zoom out |
| Enter  | Start/Stop LidarData Out |



# For Ubuntu

## granting file execution rights
      $ sudo chmod 777 NVISTAR_Lidar_PointViewer_Ubuntu_V1.0.8
## The library needs to be installed
      $ wget http://security.ubuntu.com/ubuntu/pool/main/i/icu/libicu55_55.1-7_amd64.deb
      $ sudo dpkg -i libicu55_55.1-7_amd64.deb
note: if you can open the software,the above don't installation required

## Giving serialport access

### Temporary solution:
View device list:

        $ls/dev 

Check if there are any ttyACM* files 

Then, execute the following command to grant permission
  
      $ sudo chmod 777 /dev/ttyACM0

### Permanent solution
View current user:

    $ whoami

 Processing command (dev is my user name, you need to change it to your own user name)

    $ sudo usermod -aG dialout dev

Restart effective
