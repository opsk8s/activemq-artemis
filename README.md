Artemis ActiveMq

This image can be found oun [Dockerhub](https://hub.docker.com/repository/docker/igorivanovic/activemq-artemis/general)

Helm chart is not added to helm repo yet.


## 1. What is ActiveMQ Artemis?

[Apache ActiveMQ Artemis](https://activemq.apache.org/artemis) is an open source project to build a multi-protocol, embeddable, very high performance, clustered, asynchronous messaging system. Apache ActiveMQ Artemis is an example of Message Oriented Middleware (MoM).

![logo](https://activemq.apache.org/assets/img/activemq_logo_black_small.png)

## 2. Tags and `Dockerfile` links

| Debian Based                                                                                      |
|---------------------------------------------------------------------------------------------------| 
| [`latest`](https://raw.githubusercontent.com/opsk8s/activemq-artemis/master/docker/Dockerfile) |
| [`2.20.0`](https://raw.githubusercontent.com/opsk8s/activemq-artemis/master/docker/Dockerfile) | 
| [`2.19.0`](https://github.com/opsk8s/activemq-artemis/blob/master/docker/Dockerfile-jdk8) |
| [`2.18.0`](https://github.com/opsk8s/activemq-artemis/blob/master/docker/Dockerfile-jdk8) |
| [`2.17.0`](https://github.com/opsk8s/activemq-artemis/blob/master/docker/Dockerfile-jdk8) |


### 5.13 Environment Variables

Additionally, the following environment variables are supported

| Env Var         | Default          | Description                                                       |
|---------------- |----------------- |-------------------------------------------------------------------|
|JAVA_OPTS        |                  |Will pass additional java options to the artemis runtime           |

### 5.14 Mount points

| Mount point                      | Description                                                              |
|--------------------------------- |--------------------------------------------------------------------------|
|`/var/lib/artemis/data`           | Holds the data files used for storing persistent messages                |
|`/var/lib/artemis/etc`            | Holds the instance configuration files                                   |
|`/var/lib/artemis/etc-override`   | Holds the instance configuration files                                   |
|`/var/lib/artemis/lock`           | Holds the command line locks (typically not useful to mount)             |
|`/opt/jmx-exporter/etc-override`  | Holds the configuration file for jmx-exporter `jmx-exporter-config.yaml` |

### 5.15 Exposed ports

| Port    | Description                                                     |
|-------- |-----------------------------------------------------------------|
| `8161`  | Web Server                                                      |
| `9404`  | JMX Exporter                                                    |
| `61616` | Core,MQTT,AMQP,HORNETQ,STOMP,Openwire                           |
| `5445`  | HORNETQ,STOMP                                                   |
| `5672`  | AMQP                                                            |
| `1883`  | MQTT                                                            |
| `61613` | STOMP                                                           |


NOTE:
> Docker code is fork of: https://github.com/vromero/activemq-artemis-docker