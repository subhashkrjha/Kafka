STEP 1: Start ZooKeeper
C:\kafka_2.13-3.7.0>bin\windows\zookeeper-server-start.bat config\zookeeper.properties

Follow below link if you found any issues with Kafka Server startup.
https://javasneo.blogspot.com/2021/01/install-apache-kafka-on-windows-10.html

STEP 2- Start Kafka Server
C:\kafka_2.13-3.7.0>bin\windows\kafka-server-start.bat config\server.properties

STEP 3- Add Below lines in application.yml file.
spring:
  kafka:
    producer:
      bootstrap-servers: localhost:9092
      key-serializer: org.apache.kafka.common.serialization.StringSerializer
      value-serializer: org.apache.kafka.common.serialization.StringSerializer
      
STEP 4: After starting Spring boot application, test the application by hitting below url in broser or use postman to test.      
http://localhost:8080/rest/api/producer?message="WelcomeToKafkaFirstMessage"
