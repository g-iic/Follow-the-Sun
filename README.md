# Follow-the-Sun
Control Tesla charging using Home Assistant and Huawei inverter

There are two ways to sense solar production when using Huawei inverters: using modbus or using the FusionSolar application.
The first way provides production information almost instantaneously and can be managed by Home Assistant using the Huawei Solar Integration. The second way uses the Home Assistant FusionSolar Integration. This is simpler and does not use additional hardware but it has the inconvenience of using the Huawei servers and a considerable delay. As an advantage, this method provides solar production already filtered. 
Here we describe the use of the second alternative. 
The steps are the following:
1.- Install using HACS the Home Assistant FusionSolar Integration.
2.- Create a sensor in configuration.yaml adding the lines included in the file configuration.yaml of this repository after changing the XXXXXXXXXX in 'sensor.XXXXXXXXXX_realtime_power' with the code given by the FusionSolar Integration (as stated before, is not realtime at all...). After reloading the configuration.yaml, a new entity called sensor.charging_amps_kiosk must be visible. Create the switch 'switch.followthesun', as is also described, that will be used to control the automation. 
3.- Install using HACS the Tesla integration.
4.- Create a HA automation as described in the file charging_automation.yaml. The automation has three triggers. If sensor.charging_amps_kiosk value changes or the switch.followthesun changes to "On" or binary_sensor.XXXXXX_charger changes from "Off" to "On". The XXXXXX represents the optional name of the vehicle given when installing the Tesla integration. The are three conditions that must be fulfilled to continue the automation execution. The car must be at home. HOMELOCATION must be replaced with the value provided by the Tesla integration when at home. The entity 'binary_sensor.XXXXXX_charger' must be "on". The state of the 'switch.followthesun' must by "on". The EMAIL in charging_automation.yaml must be replaced with the email used for registration at tesla.com. 
5. Create a card using the file card.yaml to control the switch.followthesun. This card uses the "History explorer card" which is a frontend that can be installed using HACS. 

