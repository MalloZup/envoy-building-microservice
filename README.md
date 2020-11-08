# Building golang microservices with envoy:

# Rationale:

This project show **concretely** to build microservice with golang and envoy.

The architecture is that envoy will manage all the route traffic, and you can build all the application (microservices) and API endopoints which are managed by envoy.

In the example, the golang micro service just print some json, but you can modify it with some valid backend code.


# HOWTO:

## 1) Build image of envoy

`docker build -t envoy:v1 .`

Run with:

`docker run --rm --net host --name envoy  envoy:v1 `

After this envoy should up and running.


### 2) Run the microservice

After envoy is up and running, run on a seperate terminal

` go run service_a.go `


### 3) Acess the microservice (centralized) via envoy

http://127.0.0.1:10000/


This will point to our json of microservice.

We configured it on the configuration file of envoy

## Going further:

This basic example can serve you as quick example how to play with envoy and building more complex things ( https/authentification more services etc).


