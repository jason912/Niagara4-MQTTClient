# Niagara4-MQTTClient
MQTT client running on Niagara 4 and communicate messages
This MQTT client can send or receive MQTT messages and display the subscribed messages in the message panel. Whenever a new message, topic, or broker parameter is added or modified, it is necessary to first disable and then re-enable the MQTT client for the changes to take effect. The associated subscribed or published messages can be viewed in the debug log.
<img width="1883" height="1143" alt="image" src="https://github.com/user-attachments/assets/7f771f79-4f72-42b7-b043-e98d1b6dcff2" />


This MQTT client is designed for quick debugging of MQTT broker communication. Each MQTT client consumes CPU resources, so it is not suitable for large-scale deployment, as it may slow down the station's performance. It is recommended to use our other BQL query tool to convert large amounts of data points into JSON format via BQL, and then send the data through the MQTT client.

Apr 28, 2026: We have only tested the compatibility with EMQX. Currently, the identified issues include: if a single message carries a large amount of data (such as over 200 JSON-formatted Niagara points data), it will occupy the station's memory space. We are currently making further adjustments. If you discover any issues, feel free to email me to inform me.

Apr 28, 2026 corrections:

Revised the Client ID to be read only and avoid conflict when copy from existing MQTT client.
Add the log enable/disable button. The log button will display the MQTT details in platform debug but not in the module. This will avoid the memory consumption to the Niagara station.

The JAR package has been successfully tested and runs on N4.14 version, and requires importing the gline.pem certificate. If you are further interested in this, please contact us at jason.zhang@gline-net.com.
