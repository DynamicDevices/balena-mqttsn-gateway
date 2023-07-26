
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

# Testing

You can use the code here to publish and subscribet to messages flowing through the MQTT-SN broker

https://github.com/njh/mqtt-sn-tools

## To Subscribe to 'sensor' topic

```
$ ./mqtt-sn-sub -h $LOCAL_IP_ADDRESS -p 10000 -t sensor -v
```

## To Publish to 'sensor' topic

```
$ ./mqtt-sn-pub -h $LOCAL_IP_ADDRESS -p 10000 -t sensor -m Hello
```

# TODO

- Add more environment variables for configuring upstream broker / port etc.
- Currently runs in host network mode. Need to look at configuring up custom network in `docker-compose.yml`
