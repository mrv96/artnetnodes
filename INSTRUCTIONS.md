# **General Info:**
**-	First Boot**
On your first boot, the device will start a hotspot called "expanseNode", followed by the node's ID (which looks something like "00178"). The hotspot should be created without a password; however, the default password is  "expanse2021" (case sensitive) if it is unable to do so. 
Once you have connected to the node, log in to the hotspot and head to the IP address: 2.0.0.1 in a web browser.

**-	Web UI**
If used in conjunction with another network: Enter your desired SSID and password in the Wi-Fi tab. Click save (the button should change to green and say "Settings Saved"). Now click "Reboot" in the side menu, and the device should reboot and connect to your desired Wi-Fi network.
If used alone or as a master connection for multiple modes: In the Wi-Fi tab, head over to the bottom of the tab and check the "Stand Alone" checkbox. Click save (the button should change to green and say "Settings Saved"). Now click "Reboot" in the side menu, and the device should reboot and begin it's hotspot once again, but this time will allow both input and output via the hotspot. 
Extra help or notes: If the device can't connect to the Wi-Fi or is unable to be assigned a DHCP assigned address within 15 seconds, it will start the setup hotspot once again and wait for 30 seconds for you to connect. If a client doesn't connect to the hotspot in time, the device will restart and try again.

**-	Configuring DMX Ports**
Everything is customisable via the web, head over to the "Port A" tab. If you will be using the node as an output device, select "DMX Output with RDM" or "DMX Output", and then choose which universe and subnet the node should listen on. If you are using the node as an input device, select "DMX Input" from the dropdown list. Change the settings below according to which universe/subnet the node should send the data to. Make sure to correct the "Broadcast Address" to whatever your console/visualiser is listening to. The default is "2.255.255.255"; however, many programs listen to "255.255.255.255" instead. 

**-	Customising Node name and DHCP / STATIC settings**
Head over to the "IP & Name" tab. Here you will be able to change the "short name" (hotspot SSID) and "long name" (Artnet broadcasted name). The settings that follow are for DHCP or STATIC IP assignments. If the node should connect to a network using a STATIC IP address, make sure to un-check the "DHCP" checkbox and then configure the IP, Subnet Address, and Gateway Address accordingly. 

# **Status LED Indicators:**
The first LED (the one closest to the micro-controller) is the main status indicator, and the two nearer to the DMX connector are the Port Status LEDs. 
-	Main Status Indicator:
PINK – The node is still booting / configuration network is being hosted. 
GREEN flashing – Node status is OK; there are no errors. 
RED flashing – There is an internal error. A WDT reset generally causes this, and the error code will be sent over Artnet. 
-	Port Status Indicators:
PURPLE – Port Initialised in DMX Output mode, but nothing is being out-putted. 
BLUE – DMX received from Artnet, and the output is active. 
WHITE – Port Initialised in DMX Input mode, nothing has been detected as a valid DMX signal.
CYAN - DMX Input is being received and is being broadcasted to Artnet.
GREEN - DMX is being received from Artnet; the port is now outputting WS2812 data. 

# **Complete List of Features:**
-	sACN and ArtNet V4 support
-	One full universe of DMX output with full RDM support 
-	Up to 1360 ws2812(b) pixels - 8 full universes
-	DMX in capability - send any incoming data to any ArtNet universe/subnet
-	Web UI using AJAX & JSON to minimise network traffic used & decrease latency
-	Full DMX Workshop, ETC, and Chamsys MagicQ support 
-	Pixel FX output - a 12 channel mode for ws2812 LED pixel control (requires extra addon PCB)

# **Stuff still to be done:**
-	Scene storage
I have not yet implemented the Scene Storage feature from my previous project. I wish to improve on it and allow for making chases or effects.
-	Handle artRdmSub packets
I haven't yet implemented the artRdmSub messages. This doesn't affect usability as they are optional, and all devices must support artRdm packets. The artRdmSub messages do provide a smaller network load, and this should be coming shortly. 
-	Pixels other than WS2812
A few people have asked for this, and it shouldn't be too hard, except for the Pixel FX engine integration.

I hope this helps you get the nodes up and running. 
All the source code and newer firmware releases will be put onto my website (https://expanseelectronics.com) and the GitHub repository (https://github.com/lonewalkerwolf).
