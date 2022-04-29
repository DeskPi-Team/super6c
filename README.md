# super6c
![sudper6c](./assets/main_super6c.jpg)

## Super6c stands for Super 6 CM4 Cluster.

## What Can Super6C do? 
* Learn, upskill, experiment on Raspberry Pi Cluster, and research DEV-OPS.
* Build your Own home pi cluster
* Build your home assisstant center
* Build your Home NAS sharing service 
* Build your Self-Hosted Private Cloud
* Host Your Own High-available Web Server cluster
* Handle Heavy Loads calculation.
* Fast multimedia conversion station
* Build Your Own Supercomputer
* Even build your Customized Super Router at home or company
* Minecraft and other games server
* CI/CD pipeline
* Use a Raspberry Pi cluster for home automation
* Build your own streaming server cluster at home
* Build your own blender rendering server farm 
## About IT management
Use a Raspberry Pi cluster to learn Linux or learn how to handle a MySQL or Postgres database. 
Learn how to install an Apache server or how to do scripting in BASH, Python, and other scripting languages to make those cluster nodes interoperate. 
Learn programming, managing resources in Linux. Learn how to make and manage your own cloud service. 

A Raspberry Pi cluster also allows you to learn Docker, Kubernetes, Serverless. Or how to turn all the cluster nodes’ resources into one supercomputer with the help of simultaneous processing software like OpenMPI. 
Deploy Kubernetes and containers almost instantly to learn how to do the same when you’ll be employed in a large corporation. A Raspberry Pi cluster will keep you learning for years on end as Linux and cloud native are vast and interesting ecosystems.

## Features
* Support plug-in 6PCS CM4 standard module
* Stable power supply processing of separate DC-DC power supply inside each module
* The modules on the board are interconnected through the gigabit switch chip RTL8370N
* DC&ATX dual external power input ports <NOTE> DC priority higher than ATX if DC & ATX being plugged at the same time. 
* Full-speed gigabit external network interface*2
* External network interface POE power pin *2
* Standard HDIM video output interface of the main module*2
* Main module MICRO USB2.0 master-slave device interface
* Main module AF USB2.0 master-slave device interface*2
* Main module pin USB2.0 master-slave device interface*2
* Slave module MICRO USB2.0 master-slave device interface*5
* All modules external module start indicator green*6
* Module start indicator on the full module board Green LED*6
* The network connection status indicator in the full module board Yellow LED*6
* The network data communication indicator lamp in the full module board Green LED*6
* Module power indicator on the board of all modules Red LED*6
* DC12V fan interface *3
* The total power switch button of the whole board
* Total reset button for all modules
* Mainboard external control indicator pin
* Full module Micro SD card slot, used to support non-eMMC version of CM4 *6
* Full module M.2 2280 M-KEY interface socket *6
* Support PCIe device 
--- 

## Block Scheme
![Block Scheme](./assets/block_diagram.png)

---

## Software Supports
Super6c supports Kubernetes software ecosystem, as well as machine learning and serverless stacks
![Support_OS](./assets/support_software.png)

---

## Product Outlook
* Frontal
![Frontal](./assets/Frontal_face_super6c.jpg)

* Bottom 
![Bottom](./assets/Back_face_super6c.jpg)

* IO View
![IO VIEW](./assets/io_views.jpg)

### Render Images
![45degree](./assets/Render_super6c.png)
![90degree](./assets/Render_super6c_02.png)
![360degree](./assets/Render_super6c_03.png)
![480degree](./assets/Render_super6c_04.png)
![180degree](./assets/Render_super6c_05.png)

### Mechanical Drawing
* Unit: milimeter(mm)
* PCB Thickness: 1.6mm
![Mechanical01](./assets/Mechanical Top View.png)
![Mechanical02](./assets/Mechanical Back View.png)

---

### IO SPEC
* Back IO 
![Back IO](./assets/Main Board Back IO.png)

* Front IO
![Front IO](./assets/Main Board Top View IO.png)

---

## How to assemble
* Attach the CM4 to the board by simply aligning it with the two connectors on the IO board, then give it a good squeeze. It’ll crunch into place and you should be set.

## How to build your own cluster and manage the cluster via ansible.

### Fit for CM4 Lite version
> Note: The latest Raspberry Pi OS does not contain `pi` user and it may not
> need to add `dtoverlay=dwc2,dr_mode=host` to config.txt file.

* Assume you are using the old version (Raspberry Pi OS 2021-11-08) 
* CM4 Lite means Raspberry Pi Computer module come `without` a EMMC storage onboard.　That means you need purchase MicroSD card(TF card).
* Steps:
 1. Download the latest Raspberry Pi OS 64bit image from: `https://downloads.raspberrypi.org/raspios_arm64/images/raspios_arm64-2021-11-08/`
 2. Unzip it and flash the `*.img` file to TF card by using `Etcher` tool, which can be downloaded via `https://www.balena.io/etcher/`
 3. Modify `config.txt` file in TF card and adding `dtoverlay=dwc2,dr_mode=host` to it and save it. (Do not need to execute this step if your using the latest version)
<pre> Before we unplug, now that your CM4 is fully flashed and ready to go, you’ll be surprised to learn that the USB Ports are disabled by default. Yes, really. Remember, this is a board designed to be embedded elsewhere and not for consumer-level off-the-shelf use.

In the “boot” folder, find the config.txt and add the following:

dtoverlay=dwc2,dr_mode=host

This will turn on the USB ports when you boot up, but if you accidentally keep the micro USB in, you will run into issues. Before you begin your first boot, make sure everything is unplugged. Boot and then plug in your mouse or keyboard.

If you’re like me and couldn’t get a wi-fi version, this is where you’ll plug in your dongle or ethernet cable.
</pre>
 5. Create a new file named `ssh` on TF card `/boot` folder
 6. Insert TF card into card slot on Super6C board. 
 7. Connect the power supply to DC Socket or Using ATX Power supply. (Max. 24V/6.15A)  
 8. Connect Full-sized HDMI cable to super6C, Other head connect to your TV or Monitor.
 9. Connect Keyboard and mouse to USB2.0 port on board.
 10. Connect Ethernet cable to `ETH1` to your Router.
 11. Press `pwr buttom` to booting up the CM4.
 12. Login to Raspberry Pi via username: `pi` password: `raspberry` 
 13. Make sure your OS can access internet.
 14. Install `ansible` via following command: `pip3 install ansible --user` 
 15. Configure environment of PATH by editing `sudo nano /home/pi/.bashrc` 

 ---
### FAQ 
* What can I do with Super6C ?
> Home server (homelab) and cloud apps hosting.
> Learn Kubernetes, Docker Swarm, Serverless, Microservices on bare metal
> Cloud-native apps testing environment
> Learn concepts of distributed Machine Learning apps
> Prototype and learn cluster applications, parallel computing, and distributed computing concepts
> Host K8S, K3S, Minecraft, Plex, Owncloud, Nextcloud, Seafile, Minio, Tensorflow

* Which Raspberry Pi models are compatible ?
> Super6C supports all Raspberry Pi CM4 with and without eMMC.
	
* Does Raspberry Pi include compute modules ?
> No, the product only have cluster motherboard and power adapter.

* From where Super6C boots OS ?
> You can boot the OS either from eMMC, SD Card or netboot.

* Does each node get its own IP address?
> Yes

* How the compute modelues communicate with each other ?
> The nodes interconnected with the onboard 1 Gbps switch. And, each node has 1Gbps speed. 

* Do all the slots need to be filled in ?
> The cluster works with any amount of nodes. You can start with a couple of nodes and scale when needed.

* Can I flash compute modules through the board ?
> Yes, you can flash a compute module using a Micro USB cable.

* How do the NIC, Ethernet, USB, HDMI, and audio ports work ?
> There are 2 USB-A an 2 USB 2.54 Pins on the board.They only connect to CM4 1$. The two HDMI ports are also the same.
> NIC – There is an 8-port gigabit switch on the board.
> Each port goes to each node plus one uplink. 
> Two RJ45 out are from the switch. 
> You can use them connect to other network device without extern switch.

* Can Super6C function from either an ATX power supply 12V ?
> Yes.

* Can I use this cluster io expansion board to just running my MySQL server? 
> Yes, you can running not only MySQL server but also PostgresSQL, SQLite,
> Mongo DB and so on.

---

