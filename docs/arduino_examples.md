Let's take a look at a few of the examples included in the SparkFun ACS37800 Power Monitor library.

## Example 1 - Read Voltage, Current, Power

The first example is a basic example that enables the Qwiic Power Meter and prints out measured values for voltage (Volts), current (Amps) and power (Watts). Open the example by navigating to **File** > **Examples** > **SparkFun ACS37800 Power Monitor Arduino Library** > **Example1_ReadVoltageCurrentPower**. Select your Board and Port and click the upload button. Once the code finishes compiling and uploading, open the [serial monitor](https://docs.arduino.cc/software/ide-v2/tutorials/ide-v2-serial-monitor) with the baud set to **115200** and you should see values print out every 250ms for Volts, Amps and Watts. 

If you see "ACS37800 not detected. Check connections and I2C address. Freezing..." print out, check to make sure the Qwiic Power Meter is wired correctly and properly connected to your RedBoard. If values print out as all 0's, make sure the voltage source, load and RedBoard all share a common ground.

## Example 2 - Set I<sup>2</sup>C Address

The second example shows how to adjust the ACS37800's I<sup>2</sup>C address in the IC's EEPROM. The ACS37800 accepts any valid I<sup>2</sup>C address set in the definition for `NEW_ADDRESS` in the line below:

``` c++
#define NEW_ADDRESS 0x60
```

Adjust the value for `NEW_ADDRESS` if needed and then click the "Upload" button. After the code finishes uploading, open the serial monitor with the baud set to **115200** and follow the prompts to complete the address change.

