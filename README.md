Vera Home Automation
====================

This repository contains helpful info on other utilities or applications for Home Automation using a Vera Edge controller

URLs
----

To enquire about a devices API endpoints:
http://192.168.1.120:49451/data_request?id=invoke

Complete list of Luup requests:
http://wiki.micasaverde.com/index.php/Luup_Requests


To call a HTTP GET from within a scene using Luua:

```
local status, result = luup.inet.wget("http://lesterthomas.ddns.net:1880/api/haEvent?manRoomSwitch=On", 5)
```

This calls a flow running in node-red with a HTTP timeout of 5 seconds. The Luua documentation for GET and POST are at: http://wiki.micasaverde.com/index.php/Luup_Scenes_Events



Temperature and Light Sensors can be queried, as well as setting off scenes. To query the value:

```
http://192.168.1.120:49451/data_request?id=variableget&DeviceNum=25&serviceId=urn:micasaverde-com:serviceId:LightSensor1&Variable=CurrentLevel
http://192.168.1.120:49451/data_request?id=variableget&DeviceNum=24&serviceId=urn:upnp-org:serviceId:TemperatureSensor1&Variable=CurrentTemperature
http://192.168.1.120:49451/data_request?id=variableget&DeviceNum=26&serviceId=urn:micasaverde-com:serviceId:SecuritySensor1&Variable=Tripped
```