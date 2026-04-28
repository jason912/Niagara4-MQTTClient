# Niagara4-MQTTClient
MQTT client running on Niagara 4 and communicate messages
This MQTT client can send or receive MQTT messages and display the subscribed messages in the message panel. Whenever a new message, topic, or broker parameter is added or modified, it is necessary to first disable and then re-enable the MQTT client for the changes to take effect. The associated subscribed or published messages can be viewed in the platform director debug.

<img width="1885" height="1146" alt="image" src="https://github.com/user-attachments/assets/55db2abb-8435-45ec-9c6c-523ae00fa283" />


This MQTT client is designed for quick debugging of MQTT broker communication. Each MQTT client consumes CPU resources, so it is not suitable for large-scale deployment, as it may slow down the station's performance. It is recommended to use our other BQL query tool to convert large amounts of data points into JSON format via BQL, and then send the data through the MQTT client.

Apr 28, 2026 corrections:
Revised the Client ID to be read only and avoid conflict when copy from existing MQTT client.
Add the log enable/disable button. The log button will display the MQTT details in platform debug but not in the module. This will avoid the memory consumption to the Niagara station.

The JAR package has been successfully tested and runs on N4.14 version and EMQX, and requires importing the gline.pem certificate. If you are further interested in this, please contact us at jason.zhang@gline-net.com. If you discover any issues, feel free to email me to inform me.
