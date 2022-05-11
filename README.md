# Docker hw5
Kafka 1
## Team: [Liia_Dulher](https://github.com/LiiaDulher)

### Usage
````
$ sudo chmod +x run-cluster.sh
$ sudo chmod +x shutdown-cluster.sh
$ sudo chmod +x create-topic.sh
````
````
$ ./run-cluster.sh
$ ./create-topic.sh
$ # use kafka
$ ./shutdown-cluster.sh
````
Producer
````
docker run -it --rm --network dulher-kafka-network -e KAFKA_CFG_ZOOKEEPER_CONNECT=zookeeper-server:2181 bitnami/kafka:latest kafka-console-producer.sh --broker-list kafka-server:9092 --topic test-topic
````
Consumer
````
docker run -it --rm --network dulher-kafka-network -e KAFKA_CFG_ZOOKEEPER_CONNECT=zookeeper-server:2181 bitnami/kafka:latest kafka-console-consumer.sh --bootstrap-server kafka-server:9092 --topic test-topic
````
