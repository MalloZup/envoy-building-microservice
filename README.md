# Building golang microservices with envoy:

# Rationale:

This mini projects show how to build microservice with golang and envoy.

The architecture is that envoy will manage all the route traffic, and you can build all the application (microservices) which do the API endpoints.

In the example, the service just print some json, but you can modify it with some valid backend code.

# HOWTO:

## Build image of envoy

`docker build -t envoy:v1 .`

Run with:

docker run --rm --net host --name envoy  envoy:v1 

After this envoy should up and running.


# Run the microservice

` go run service_a.go `

# Acess the microservice (centralized) via envoy

http://127.0.0.1:10000/


This will point to our json of microservice.

We configured it on the configuration file of envoy
