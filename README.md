# Follow-the-Sun
Control Tesla charging using Home Assistant and Huawei inverter

There are two ways to sense solar production when using Huawei inverters: using modbus or using the FusionSolar application.
The firts way, provides production information almost instantaneusly and can be managed by Home Assistant using the Huawei Solar Integration. The second way uses the Home Assistant FusionSolar Integration. This is simpler and does not uses aditional hardware but has the inconvenient of using the Huawei servers and a considerable delay. As an advantage, this method provides solar production already filtered. 
Here we describe the use of the second alternative. 
The steps are the following.
1.- Install using HACS the Home Assistant FusionSolar Integration
2.- Create a sensor in configuration.yaml
3.- Install using HACS the Tesla integration
4.- Create a HA automation
