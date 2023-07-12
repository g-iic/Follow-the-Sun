# Follow-the-Sun
Control Tesla charging using Home Assistant and Huawei inverter

There are two ways to sense solar production when using Huawei inverters: using modbus or using the FusionSolar application.
The firts way, provides production information almost instantaneusly and can be managed by Home Assistant using the Huawei Solar Integration. The second way uses the Home Assistant FusionSolar Integration. This is simpler and does not uses aditional hardware but has the inconvenient of using the Huawei servers and a considerable delay. As an advantage, this method provides solar production already filtered. 
Here we describe the use of the second alternative. 
The steps are the following:
1.- Install using HACS the Home Assistant FusionSolar Integration.
2.- Create a sensor in configuration.yaml adding the lines included in the file configuration.yaml of this repository after changing the XXXXXXXXXX in 'sensor.XXXXXXXXXX_realtime_power' with the code given by the FusionSolar Integration. After reload the configuration.yaml a new entity called sensor.charging_amps_kiosk must be visible. Create a switch as is also described that will be used to control the automation. 
3.- Create a switch to control the automation using
4.- Install using HACS the Tesla integration
5.- Create a HA automation as described in the file charging_automation.yaml. The automation have three triggers. If sensor.charging_amps_kiosk value changes or the switch.followthesun changes to "On" or binary_sensor.XXXXXX_charger changes from "Off" to "On"


