# ApacheKafkaForBeginnersInvolvingDocker
Step 1 :
Apache Kafka setup :

1 Go to cmd prompt and type docker pull confluentinc/cp-zookeeper
                   and this docker pull confluentinc/cp-kafka
				   
2 Create a network to work on using this in CMD Prompt : docker network create kafka 		

3 TO run that network use : docker run -d --network=kafka --name=zookeeper -e ZOOKEEPER_CLIENT_PORT=2181 -e ZOOKEEPER_TICK_TIME=2000
 -p 2181:2181 confluentinc/cp-zookeeper

4 Check logs :  docker logs zookeeper

5 Now to create Kafka container : docker run -d --network=kafka --name=kafka -p 9092:9092 -e KAFKA_ZOOKEEPER_CONNECT=zookeeper:2181 
-e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://localhost:9092 confluentinc/cp-kafka

6 Check logs docker logs kafka

Step 2 :
Dot net part :
1 Create a new console app project
2 After that install all the packages required to run Kafka on dot net via nugget manager. The packages we require are: Confluent.Kafka, kafka-sharp, Microsoft.Extensions.Hosting.
