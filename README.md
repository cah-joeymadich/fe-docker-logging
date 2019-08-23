# Docker Logging Demo

* this is a demonstration of how you can use syslog to send container logs directly to a remote endpoint using the ELK stack to aggregate and analyze logging output.
* `docker-compose up --build -d` to get started

### Known issues

* May have to run `docker-compose` twice bringing up the containers. Since the demo web docker container build attempts to connect to the remote endpoint as part of configuring the driver, the demo web container may not start as the logstash url does not resolve until logstash has completely started. Even in attempts to use `wait-for-it` and `depends-on` because this happens during buildtime, it can fail. In production environments, logstash would be running in its own hosted environment and likely out of scope of a particular application's containers.