# This is a public repo

so copy anything here as you was the author

# kafka commands

## create topic command

 command : 
    
    ./kafka-topics.sh \
    --bootstrap-server <ip and port of the firts broker in the kafka cluster>\
    --create \
    --topic <topic name> \
    --partitions <number of partition> \
    --replication-factor <number of replication>

 - [x] :information_source: topic with many partitions can scale easily but too many partitions for a topic can create problem
 - [x] :warning: replication-factor should be equal to the number of the boker if we work in cluster
 - [x] :warning: kafka 2.2+ doesn't need the zookeeper connection string (ex : --zookeeper zookeeper:2181 )

## list kafka topics

 command: 

        ./kafka-topics.sh \
            --bootstrap-server <ip and port of the firts broker in the kafka cluster>  \
            --list

 - [x] :warning: kafka 2.2+ doesn't need the zookeeper connection string (ex : --zookeeper zookeeper:2181 )

## getting details about topic

command:

        ./kafka-topics.sh \
            --bootstrap-server <ip and port of the firts broker in the kafka cluster> \
            --describe

 - [x] :warning: kafka 2.2+ doesn't need the zookeeper connection string (ex : --zookeeper zookeeper:2181 )

## publish message to a topic

command:

        ./kafka-console-producer.sh \
            --bootstrap-server <ip and port of leader in the topic> \
            --topic kafka.learning.tweets

 - [x] :warning: if you run this command within kafka in a docker container you should specify the internal port 
 - [x] :warning: kafka 2.2+ doesn't need the zookeeper connection string (ex : --zookeeper zookeeper:2181 )

## publish message with key in a topic

command:

        ./kafka-console-producer.sh \
            --bootstrap-server localhost:29092 \
            --property "parse.key=true" \
            --property "key.separator=:" \
            --topic kafka.learning.orders

 - :information_source: property parse.key=true specify the broker that messages for this topic will have a key
 - :information_source: property key.separator= specify while symbol will be use as a separator

## consuming message to a topic

command:

        ./kafka-console-consumer.sh \
            --bootstrap-server <ip and port of leader in the topic> \
            --topic kafka.learning.tweets \
            --from-beginning

 - [x] :information_source: adding --group option help to create a consumer group
 - [x] :warning: if you run this command within kafka in a docker container you should specify the internal port 
 - [x] :warning: kafka 2.2+ doesn't need the zookeeper connection string (ex : --zookeeper zookeeper:2181 )

## deleting a topic

command:

        ./kafka-topics.sh \
            --bootstrap-server <ip and port of the firts broker in the kafka cluster> \
            --delete \
            --topic kafka.learning.alerts

 - this command is not synchronous because it's need to delete all physical copies of topic's messages in all brokers
 - [x] :warning: kafka 2.2+ doesn't need the zookeeper connection string (ex : --zookeeper zookeeper:2181 )

## connect to zookeeper client

command:

    ./zkCli.sh

## list all zookeeper commands

command:

    ls /

## list all brokers registered in the zookeeper

command:

    ls /brokers/ids

## get details about a broker

command:

    get /brokers/ids/<brokerId>

## list all topics available

command:
    
    ls /brokers/topics

## get topic details

command:

    get /brokers/topics/<topic name>