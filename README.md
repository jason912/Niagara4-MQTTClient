# Niagara4-MQTTClient
MQTT client running on Niagara 4 and communicate messages
This MQTT client can send or receive MQTT messages and display the subscribed messages in the message panel. Whenever a new message, topic, or broker parameter is added or modified, it is necessary to first disable and then re-enable the MQTT client for the changes to take effect. The associated subscribed or published messages can be viewed in the debug log.
<img width="1883" height="1143" alt="image" src="https://github.com/user-attachments/assets/7f771f79-4f72-42b7-b043-e98d1b6dcff2" />


This MQTT client is designed for quick debugging of MQTT broker communication. Each MQTT client consumes CPU resources, so it is not suitable for large-scale deployment, as it may slow down the station's performance. It is recommended to use our other BQL query tool to convert large amounts of data points into JSON format via BQL, and then send the data through the MQTT client.

The JAR package has been successfully tested and runs on N4.14 version, and requires importing the gline.pem certificate. If you are further interested in this, please contact us at jason.zhang@gline-net.com.
