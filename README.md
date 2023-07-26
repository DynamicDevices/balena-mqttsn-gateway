
# Balena block upport for Paho MQTT-SN Gateway

This builds all SENSORNET types of MQTT-SNGateway 

[![balena deploy button](https://www.balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy)

It currently runs the UDP MQTT-SNGateway

The following environment variables need to be set within the Balena environment. These are then set into the MQTT-SN gateway.conf file

| Balena Variable | MQTT-SNGateway build |
| --------------- | ------- |
| SENSORNET       |  [udp (default) / udp6 / xbee / loralink / rfcomm / dtls / dtls6] |

| Balena Variable | gateway.conf Setting |
| --------------- | ------- |
| ENV_BROKER_NAME | BrokerName |
| ENV_BROKER_PORT | BrokerPortNo |
| ENV_BROKER_SECURE_PORT | BrokerSecurePortNo |
| ENV_GATEWAY_PORT | GatewayPortNo |
| ENV_GATEWAY_IPV6_PORT | GatewayIPv6PortNo |

# TODO

- Add more environment variables for configuring upstream broker / port etc.
- Currently runs in host network mode. Need to look at configuring up custom network in `docker-compose.yml`
