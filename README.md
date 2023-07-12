# Follow-the-Sun
Control Tesla charging using Home Assistant and Huawei inverter

There are two ways to sense solar production when using Huawei inverters: using modbus or using the FusionSolar application.
The firts way, provides production information almost instantaneusly and can be managed by Home Assistant using the Huawei Solar Integration. The second way uses the Home Assistant FusionSolar Integration. This is simpler but has the inconvenient of using the Huawei servers and a considerable delay. As an advantage, this method provides solar production already filtered. 
