# Stream-Starts-Per-Second
SPS: the Pulse of Netflix Streaming


Run Standalone Machine:
The Producer and Consumer with embedding inside SSPDriverStandalone Class

```
java -cp Stream-Starts-Per-Second-1.0-SNAPSHOT-jar-dependencies.jar com.kal.ssps.SSPDriverStandalone </path/to/file/kafkaconfig>
```


In Order to Scale out the system to consumer from multipe source : Event-Driver Sent

Run Producer in multiple Machine:
The source will consume and sent to kafka cluster with specific kafka topic
```
java -cp target/Stream-Starts-Per-Second-1.0-SNAPSHOT-jar-dependencies.jar com.kal.ssps.SSPSProducer </path/to/file/kafkaconfig>
```

Capture the result by Kafka Stream and aggregate on one second intervals grouped by device, title, country to compute counts for these combinations. Events with sev = “success” count as a successful stream start, this is what we want to count.
The result will print out in system, or will be send to the other kafka topic for client can consume.

```
java -cp target/Stream-Starts-Per-Second-1.0-SNAPSHOT-jar-dependencies.jar com.kal.ssps.SSPSStream </path/to/file/kafkaconfig>
```


