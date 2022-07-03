# kafka commands

# create topic

    ./kafka-topics.sh \
        --bootstrap-server <ip and port of the firts broker in the kafka  cluster>\
        --create \
        --topic <topic name> \
        --partitions <number of partition> \
        --replication-factor <number of replication. :warning: should be equal to the number of the boker if we work in cluster>


    :warning: kafka 2.2+ doesn't need the zookeeper connection string (ex : --zookeeper zookeeper:2181 )

    :eight_pointed_black_star:

