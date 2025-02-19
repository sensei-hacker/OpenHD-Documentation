# First Time Setup

When a project reaches a certain stage, the amount of options to choose from can get pretty overwhelming. This section of the documentation is intended to help guide newcomers to the project towards their first functional Open.HD implementation.

{% hint style="info" %}
If you have a pre-existing hardware requirement that is not met in this guide, it is still a good idea to follow the guide and make sure you have this, the simplest setup, working before venturing into the more complex setups. Every setup, no matter how complex uses the elements in this guide at it's base.
{% endhint %}

## Sourcing hardware

{% hint style="info" %}
In today's Chip Shortage sourcing hardware can be stressful, but there are a few hints to get your Raspberry devices even when they're quite hard to get. In Europe ([Berrybase](https://www.berrybase.de/)) always have some devices in stock for it's club members (membership is free). In addition to that ([RpiLocator](https://rpilocator.com/)) can help you get raspberry hardware worldwide.
{% endhint %}

Assuming you are starting with nothing, we recommend you get the following Hardware:

* A Raspberry Pi4B for the Ground SBC
* A SD-Card with at least 8GB of space
* A Raspberry CM4 with EMMC with:
  * An [Ochin CM4 carrier](ochin.md) board
  * We recommend fitting a cooler to the CM4, because it really can get hot.
* Two WiFi cards that support the band you want to use. (See [WiFi Adapters](wifi-adapters.md))
* An HDMI cable for connecting the Ground SBC to a screen
* An HDMI capable screen (use your TV for testing!)
* High Quality BEC's, AT LEAST one for air or ground each. You can also use four BEC's for powering the Air and Ground SBC's, and the Wifi-Adapters independently. (See Wiring -> Power)
* A supported Camera ([Original Raspberry Camera](broken-reference)) and the required cable (keep in mind, the ochin uses a zero-csi cable)
* Various lengths of connection wires.
* A soldering iron and required disposables.

## Step-by-step

Now that you have your prerequisite Hardware, we can get down to business.

### Step 1: Powering the Ground SBC

The ground SBC needs enough "juice" to be able to decode, display and control the OpenHD-Link. That's why we recommend the more "performant" device to be used on the Ground. We recommend 3A or more.

### Step 2: Connecting the WiFi Adapter

Since we use very powerfull WiFi-Cards and most SBC's have limited USB-Output-Power, we need a dedicated BEC for that Card's. In Addition to that it's common practice to not connect the Wifi-Card directly to the SBC. On the Air-SBC Vibrations and movement in general will result in connection problems, that's why we recommend to remove the USB-Connector or at least solder to the USB-Connector. If you need help with that look in our forums, there are some extensive guides how to do it nicely. Also writing in the Telegram or Discord Chat can help you.

### Step 3: Connecting a display

Just connect an HDMI-Display, most Displays should just work out of the box.

### Step 5: Flashing the Ground SBC for the first time

First you should download our latest stable release and unpack it on your Computer. Keep in mind, that evo is not have compatible with version 2.x or earlier. You need to flash your SD-Card before plugging it into the SBC. We suggest using our configuator (which isn't released, yet) or the official (RPi [Image Writer](https://www.raspberrypi.com/software/)). After that step plug in the SD-Card to the SBC.

### Step 6: Flashing the AIR SBC for the first time

If using the Ochin board, you first need to install your CM4 into the Ochin board and flash it. The Ochin board requires external power even when the usb-c is connected. To enter the "flash-mode" push the Button while connecting power. Now you can continue with the normal setup shown in this Video. And choose our image.

{% embed url="https://www.youtube.com/watch?v=jp_mF1RknU4&t=70s" %}

Keep in mind, flashing is very slow, because some limitations of the RPi-Foundation. Do not disconnect while flashing, it can brick your device.

### Step 7: Starting the Ground SBC for the first time

Plug in the Wifi-Stick,SD-Card and Monitor.Power up the SBC. The first boot can take several minutes, so be patient, reboots are normal. When initialised QOpenHD should automatically start and show our OSD.

### Step 7: Starting the Air SBC

Plug in the Wifi-Stick, connect the camera (please use copper tape to protect against interference) Check wiring and plug in the Power. The first boot will take several Minutes, because initial configs and setups are executed. The SBC will reboot multiple times. OpenHD will automatically start to transmit Video, if everything is correct.
