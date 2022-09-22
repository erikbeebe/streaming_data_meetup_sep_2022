# Cloudera Streaming Data Meetup  (September 21, 2022)

If you missed the meetup, here's the recorded link:

https://www.youtube.com/watch?v=s80sz3NWwHo

- honeypot_login_attempts.json contains raw SSH connection attempts
- honeypot_successful_hack.json contains an artificial successful login from an attacker

# To load data into Kafka
```shell
$ docker run -i --network cspce_csp-ce-net confluentinc/cp-kafkacat kafkacat -b cspce_kafka_1:9092 -t honeypot_logs -u -e -P < honeypot_login_attempts.json
$ docker run -i --network cspce_csp-ce-net confluentinc/cp-kafkacat kafkacat -b cspce_kafka_1:9092 -t honeypot_logs -u -e -P < honeypot_successful_hack.json
```

## Note - adjust docker network name as required, if yours does not match.  You can find the name with:
```shell
$ docker network ls
```
