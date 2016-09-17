# dockersbackstopjs

CSS Regression Testing within a prepared Docker Container

##Installation

* Checkout the code
```bash
$ git clone git@github.com:Forestsoft-de/dockersbackstopjs.git $PROJECT_ROOT/docker
```
* Modify or create your docker-compose configuration with the [example](docker-compose-example.yml)
* Build docker container
```bash
$ docker-compose up --build backstop
```
* Start the Shell on Container
```bash
docker exec -i -t docker_backstop_1 /bin/bash
```
* Create backstop.json with
 ```bash
 /opt/BackstopJS/$ gulp genConfig
 ```
* Make reference of Page
```bash
/opt/BackstopJS/$ ref
```
* Test these references.
```bash
/opt/BackstopJS/$ ts
```

For further informations read the backstopjs [documentation](https://github.com/garris/BackstopJS/README.md)



##Configuration
```yaml
version: '2'
services:
  backstop:
    build: ./backstopjs
    volumes:
      - ../backstop.json:/opt/BackstopJS/backstop.json
      - ../backstop_data:/opt/BackstopJS/backstop_data
    ports:
      - "3001:3001"
```

###Troubleshoot

iptables: No chain/target/match by

```bash
iptables -N DOCKER
```
