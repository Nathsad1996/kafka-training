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

## consuming message to a topic

command:

        ./kafka-console-consumer.sh \
            --bootstrap-server <ip and port of leader in the topic> \
            --topic kafka.learning.tweets \
            --from-beginning
            
 - [x] :warning: if you run this command within kafka in a docker container you should specify the internal port 
 - [x] :warning: kafka 2.2+ doesn't need the zookeeper connection string (ex : --zookeeper zookeeper:2181 )

## deleting a topic

command:

        ./kafka-topics.sh \
            --bootstrap-server <ip and port of the firts broker in the kafka cluster> \
            --delete \
            --topic kafka.learning.alerts

 - [x] :warning: kafka 2.2+ doesn't need the zookeeper connection string (ex : --zookeeper zookeeper:2181 )