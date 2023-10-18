# Microcks - Getting started with Docker Compose
Docker Compose is a tool for easily test and run multi-container applications. Microcks offers a simple way to set up the minimal required containers to have a functional environment in your local computer.

## Usage
To get started, make sure you have Docker installed on your system.

[//]: # (In your terminal issue the following commands:)

[//]: # (Clone this repository.)

[//]: # ()
[//]: # (git clone https://github.com/microcks/microcks.git)

[//]: # (Change to the install folder)

[//]: # ()
[//]: # (cd microcks/install/docker-compose)

## Spin up the containers

`docker-compose up -d`

This will start the required containers and setup a simple environment for your usage.

Open a new browser tab and point to the http://localhost:8080 endpoint. This will redirect you to the Keycloak Single Sign On page for login. 

Use the following default credentials:

```text
Username: admin
Password: microcks123
```

You will be redirected to the main dashboard page. You can now start using Microcks.


## Enabling Asynchronous API features

Support for Asynchronous API features of Microcks are not enabled by default into the docker-compose.yml file. If you feel your local machine has enough resources to afford it, you can enable them using a slightly different command line.

In your terminal use the following command instead:

```text
docker compose -f microcks-docker-compose.yml -f microcks-docker-compose-async-addon.yml up -d
```


Docker compose is now launching additional containers, namely zookeeper, kafka and the microcks-async-minion. The above command should produce the following output:


# More experimental things

If you’re feeling lucky regarding your machine, you can even add the Kafdrop utility to visualize and troubleshoot Kafka messages with this command:

```text
docker compose -f docker-compose.yml -f docker-compose-async-addon.yml -f kafdrop-addon.yml up -d
```

## Un-authenticated mode
A “keycloakless” version of docker compose is available thanks to:

```text
docker compose -f docker-compose-devmode.yml up -d
```

This configuration enabled Asynchronous API features in a very lightweight mode using Red Panda broker instead of full-blown Apache Kafka distribution.
