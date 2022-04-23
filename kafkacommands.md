//Go to C folder where kafka is installed in command line(change directory) and then execute these commands.
//Change log directory path in server.properties and zookeeper.properties files(which will be installed as part of Kafka) and then run below commands.

Follow the below order to send real time data from Producer to Consumer
----------------------------------------------------------------------------

To start Zookeeper:
----------------------------
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties


To start Apache Kafka:
------------------------
.\bin\windows\kafka-server-start.bat  .\config\server.properties

To Create topics:
-------------------
.\bin\windows\kafka-topics.bat --create --topic HorseRace --bootstrap-server localhost:9092
.\bin\windows\kafka-topics.bat --create --topic HorseRace2 --bootstrap-server localhost:9092 --replication-factor 1 --partitions 29
.\bin\windows\kafka-topics.bat --create --topic HorseRace3 --bootstrap-server localhost:9092 --replication-factor 1

To list the topics created:
------------------------
.\bin\windows\kafka-topics.bat --list --bootstrap-server localhost:9092


To Start the Producer:
--------------------------
.\bin\windows\kafka-console-producer.bat --topic HorseRace --bootstrap-server localhost:9092


To Start the Consumer:
--------------------------
.\bin\windows\kafka-console-consumer.bat --topic HorseRace --from-beginning --bootstrap-server localhost:9092