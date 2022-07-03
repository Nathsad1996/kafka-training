# This is a public repo

so copy anything here as your was the author

# kafka commands

## create topic command

 command : 
    
    ./kafka-topics.sh \
    --bootstrap-server <ip and port of the firts broker in the kafka  cluster>\
    --create \
    --topic <topic name> \
    --partitions <number of partition> \
    --replication-factor <number of replication>

 - [x] :warning: replication-factor should be equal to the number of the boker if we work in cluste
 - [x] :warning: kafka 2.2+ doesn't need the zookeeper connection string (ex : --zookeeper zookeeper:2181 )