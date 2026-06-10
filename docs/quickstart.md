In this Quick Start guide we'll demonstrate how to assemble and use the Qwiic Power Meter to measure voltage, current and power using the SparkFun ACS37800 Power Monitor Arduino Library. This guide assumes you have an understanding of measuring current, using Qwiic breakouts and the Arduino IDE. If you're not familiar with any of these concepts we recommend reading through the Hardware and Software sections of this guide as they provide more thorough information about this Qwiic breakout and how to use it with Arduino.

## Power Monitoring Demo Assembly

### Voltage Supply and Load Assembly

We'll start by connecting the Qwiic Power Meter to our voltage supply and load. For this demo, we're using a 10 Watt power resistor to simulate the load but the concepts and circuit design can be applied to an actual power monitor circuit for something like a 3D printer or motor. Make sure to leave the load circuit powered OFF before completing the assembly to avoid damaging anything. Since we're measuring power in series we'll need to interrupt the voltage supply going to the power resistor by completing the following steps:

* Connect the the voltage supply to the IP+ pin.
* Connect the power resistor or "load" to the IP- pin.
* Connect the load to ground. In the case of this demo, we've connected the opposite side of the power resistor to the ground rail on our breadboard so we can create a common ground with the RedBoard IoT next.

<figure markdown>
[![Voltage supply and load circuit assembled](./assets/img/Qwiic_Power_Meter-Load_Assembly.jpg){ width="600"}](./assets/img/Qwiic_Power_Meter-Load_Assembly.jpg "Click to enlarge")
</figure>

### Qwiic Assembly

Next we'll connect the Qwiic Power Meter to the RedBoard IoT - ESP32. 

* Connect the two boards together using a Qwiic cable.
* Create a connection between the grounds of the voltage source, Qwiic Power Meter and RedBoard. Since this connection is a low current path and we're using a breadboard and power resistor for this demo, we just need to connect the breadboard's ground rail to a ground pin on the RedBoard IoT using a jumper wire.
* Connect the RedBoard to a computer over USB.

The completed demo circuit should look similar to the photo below:

<figure markdown>
[![Completed demo circuit](./assets/img/Qwiic_Power_Meter-Completed_Demo_Assembly.jpg){ width="600"}](./assets/img/Qwiic_Power_Meter-Completed_Demo_Assembly.jpg "Click to enlarge")
</figure>

## Arduino Example

With the power meter circuit built, let's move on to uploading code to monitor it.

* Install the SparkFun ACS37800 Power Monitor Arduino library using the [library manager](https://docs.arduino.cc/software/ide-v2/tutorials/ide-v2-installing-a-library/) by searching for "SparkFun ACS37800".
* If you don't already have the RedBoard IoT - ESP32 board definition installed, you'll need to install the "esp32" boards package by Espressif Systems. Copy this JSON URL: `https://espressif.github.io/arduino-esp32/package_esp32_dev_index.json` to the "Additional Boards Manager URLs" in the "Preferences" menu and then search for "esp32" in the [boards manager](https://docs.arduino.cc/software/ide-v2/tutorials/ide-v2-board-manager) tool and install the latest version of the "esp32 by Espressif Systems" boards package.
* Open Example 1 - Read Voltage Current Power.
* Select your Board and Port and click the "Upload" button.
* Once the code finishes uploading, open the serial monitor with the baud set to **115200** and you should see values for Volts, Amps and Watts print out every 250ms.
