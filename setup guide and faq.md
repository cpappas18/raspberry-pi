# Table of contents
1. [Quick setup](https://github.com/nadiaenh/raspberry-pi/blob/main/setup%20guide%20and%20faq.md#quick-setup)  
   a. [If you have an extra monitor and keyboard](https://github.com/nadiaenh/raspberry-pi/blob/main/setup%20guide%20and%20faq.md#if-you-have-an-extra-monitor-and-keyboard)  
   b. [If you only have your laptop](https://github.com/nadiaenh/raspberry-pi/blob/main/setup%20guide%20and%20faq.md#if-you-only-have-your-laptop)  
2. [Frequently asked questions](https://github.com/nadiaenh/raspberry-pi/blob/main/setup%20guide%20and%20faq.md#frequently-asked-questions)

# Quick setup

**:heavy_check_mark: You will need:**  
- Your Raspberry Pi board 
- A Raspberry Pi power supply 
- A microSD card and its adapter
- *(optional)* An extra monitor, keyboard, and mouse  
- *(optional)* A Raspberry Pi case

:stop_sign: Do **NOT** plug your Raspberry Pi to a power source until told to.  
:question: If you need help or have a question, ask it on the Discord.  

## If you have an extra monitor and keyboard  

**:one: Setup your microSD:**  
If your microSD didn't come pre-loaded with Raspbian, you will need to install it manually.  
For that, download the [Raspberry Pi Imager](https://www.raspberrypi.org/software/) that matches your computer's operating system.  
Launch the installer and follow the instructions.  
Place your microSD in its adapter into your computer.  
Choose **Raspberry Pi OS**, choose the microSD you want to overwrite, then click on **Write**.  
*Note: anything on the microSD will be overwritten !*  

**:two: How to assemble everything:**  
The software will tell you when it's okay to eject your microSD, and you can then insert it into the Raspberry Pi microSD slot.    
Plug in your keyboard and mouse.   
Plug in the power supply and turn on the Raspberry Pi.  
Follow the setup instructions on the screen, and that's it !  
👏 You're ready to start ! 👏
  
## If you only have your laptop   

**:one: Setup your microSD:**  
If your microSD didn't come pre-loaded with Raspbian, you will need to install it manually.  
For that, download the [Raspberry Pi Imager](https://www.raspberrypi.org/software/) that matches your computer's operating system.  
Launch the installer and follow the instructions.  
Place your microSD in its adapter into your computer.  
Choose **Raspberry Pi OS**, choose the microSD you want to overwrite, then click on **Write**.  
*Note: anything on the microSD will be overwritten !*  

**:two: Setting up the WiFi on the RasPi:**  
Create a new text file named `wpa_supplicant.conf` in the `/boot` folder of the SD card and paste the following code in it:  
```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
 
update_config=1
 
country=US
 
network={
 
    ssid="YOURSSID"
 
    psk="YOURPASSWORD"
 
    scan_ssid=1
 
}
```
with YOURSSID and YOURPASSWORD being your WiFi network's name and its password.  

**:three: Enabling SSH:**  
In the `/boot` folder, add an empty file named `ssh`.
 
**:four: Finding your RasPi:**  
Put the microSD into your Raspberry Pi and turn the power on.  
Make sure your laptop is connected to the same network as `wpa_supplicant.conf`.  
Find the IP address of your Pi (you can use your router's configuration software, or run `arp -a` in a command prompt terminal).  

**:five: Connecting to your RasPi:**  
In a command prompt terminal, run `ssh @your_raspi_ip_address`.  
You will be asked for a password, the default is `raspberry`.  
You now have access to the Raspbery Pi terminal, but you still can't see its desktop.  
 
**:six: Accessing the RasPi desktop:**  
Download and install [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html).  
In the configuration screen, paste your Pi's IP address and leave everything else unchanged. Click on Open.  
Ignore any warning messages. You will be asked for a username and password.  
The default username is `pi` and password is `raspberry`.  
 
**:seven: Viewing the RasPi desktop:**  
Download [VNC Viewer](https://www.realvnc.com/en/connect/download/viewer/).  
Paste the Pi's IP address, and enter the default username and password.  
👏 You're ready to start ! 👏  

# Frequently Asked Questions

:question:**What’s a Raspberry Pi?**  
It is a tiny and affordable computer that runs on a version of Linux called Raspbian. 

:question:**How is it used?**  
You can plug a keyboard and monitor to it and it works exactly the same as a desktop computer. 
Alternatively, you can attach a bunch of extra stuff to it (camera, LED lights, wires, motors, wheels, weather sensors, etc.) and make cool projects ! 

:question:**What language does it use?**  
Raspbian comes pre-loaded with Python, the official language of Raspberry Pi.  
It can use a bunch of other languages though, such as HTML5 and Java.  

:question:**Do I need to have one to work on this project?**  
No. If you want to fiddle with it too then by all means get one (Chloe and I will have one), but it’s not mandatory. 
 
:question:**Which model should I get?**  
Once we decide the scope of this project, I will be updating this document with links to everything you might need.    
Generally speaking, the criterias to consider when choosing a Rasberry Pi are speed (processing power), memory (RAM/ROM/HD), 
size and weight, cost, amount of I/O support available, networking capabilities (WiFi, Bluetooth, etc.)  

:question:**Where can I buy one?**  
[The official website](https://www.raspberrypi.org/), [Canakit](https://www.canakit.com/), [BuyAPi](https://www.buyapi.ca/), or Amazon !  

:question:**Where can I buy extra stuff?**  
Amazon sells starter kits with a bunch of LEDs, wires, motors, wheels etc.  
You can also check out websites like [Canada Robotix](https://www.canadarobotix.com/) !

# Sources 
[Setting up your Raspberry Pi](https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up)  
[Tutorial for connecting your Raspberry Pi to a laptop display](https://spin.atomicobject.com/2019/06/09/raspberry-pi-laptop-display/)
