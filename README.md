# Niagara4-MQTTClient
MQTT client running on Niagara 4 and communicate messages
This MQTT client can send or receive MQTT messages and display the subscribed messages in the message panel. Whenever a new message, topic, or broker parameter is added or modified, it is necessary to first disable and then re-enable the MQTT client for the changes to take effect. The associated subscribed or published messages can be viewed in the platform director debug.

<img width="1885" height="1146" alt="image" src="https://github.com/user-attachments/assets/55db2abb-8435-45ec-9c6c-523ae00fa283" />


This MQTT client is designed for quick debugging of MQTT broker communication. Each MQTT client consumes CPU resources, so it is not suitable for large-scale deployment, as it may slow down the station's performance. It is recommended to use our other BQL query tool to convert large amounts of data points into JSON format via BQL, and then send the data through the MQTT client. Here is a BQL sample:
station:|slot:/Drivers/MQTT/Liyu/points/BA_7F|bql:select name,slotPath,type,out.value as 'value',out.status as 'status' from control:ControlPoint
The above BQL query will list all points value & status under specific folder "BA_7F", such as:
<img width="2854" height="539" alt="image" src="https://github.com/user-attachments/assets/ae5fb1e2-7f8e-46c5-8082-ae1b72df8ea6" />
With the bql2json module, users can directly transform BQL data into JSON format.
<img width="2154" height="695" alt="image" src="https://github.com/user-attachments/assets/6c146fe0-2482-4e57-a2d6-4b1df68ed7e6" />
On the MQTT receiving end, users can develop a retrieval program to filter payloads by JSON fields. Below is a sample case
<img width="491" height="221" alt="image" src="https://github.com/user-attachments/assets/0ba04b7f-f4bf-4939-8b1e-f7018957eeee" />

Apr 28, 2026 corrections:
Revised the Client ID to be read only and avoid conflict when copy from existing MQTT client.
Add the log enable/disable button. The log button will display the MQTT RX only details (no TX details) in platform debug but not in the module. This will avoid the memory consumption to the Niagara station.
<img width="2616" height="39" alt="image" src="https://github.com/user-attachments/assets/0dbb8076-4e01-4fb5-ad0e-f5e0360902e4" />

May 6, 2026 corrections:
The MQTT broker authentication has been updated. We now support QoS 0/1/2 messages and encrypted username/password logins for EMQX and Aedes (Node-RED) brokers. SSL authentication is not available at this time. Contact us if you need additional features.
<img width="920" height="155" alt="image" src="https://github.com/user-attachments/assets/f5de9c63-5cc1-4362-ab9b-31a24dcaeae9" />

May 7 2026 corrections:
Removed the log enable/disable function. All mqtt logs will be displayed in the platform director. 
<img width="2588" height="438" alt="image" src="https://github.com/user-attachments/assets/23180827-e6b8-4c24-b816-aecc9f1cf874" />

The JAR package has been successfully tested and runs on N4.14 version, EMQX and Node-Red Aedes MQTT broker, and requires importing the gline.pem certificate. If you are further interested in this, please contact us at jason.zhang@gline-net.com. If you discover any issues, feel free to email me to inform me.
