# Kafka Server  

Purpose: To provide Kafka in the environment.     

## Configuration  

| Component | Value |
|-----------|-------|
| Server | Ubuntu Core  |
| RAM | 1024 MB  |
| IP | 10.200.1.92/24 |     
| Hostname | soc-kafka |
| Zone | SOC-Shock |


## Prerequisites  

- OpenJDK 8  


    sudo apt install openjdk-8-jdk

## Installation

In a tmux shell:  

    sudo bash
    wget https://downloads.apache.org/kafka/2.4.0/kafka_2.12-2.4.0.tgz        
    tar -xzf kafka_2.12-2.4.0.tgz
    cd kafka_2.12-2.4.0
    
Edit the ./config/server.properties file and put IP Address of zookeeper.  

    zookeeper.connect=10.200.1.92:2181
    
### Starting the server

In tmux, separate panes:
    
    ./bin/zookeeper-server-start.sh config/zookeeper.properties
    ./bin/kafka-server-start.sh config/server.properties

## Usage  

*TODO*
