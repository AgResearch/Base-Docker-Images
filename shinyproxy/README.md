# Image: shinyproxy

The Dockerfile is based on an
[online](https://raw.githubusercontent.com/openanalytics/shinyproxy-config-examples/master/02-containerized-docker-engine/Dockerfile)
example provided by `shinyproxy`'s developers. This image does not include
its runtime configuration, `application.yml`; therefore it must be mounted into
the container instance when creating the instance.

The following is an example of launching a `shinyproxy` using the host's
Docker engine, a custom network bridge and a local application.yml:

```
# Create the custom network bridge
$ docker network create shinyproxy-net

# Start a shinyproxy
$ docker run -d -v /var/run/docker.sock:/var/run/docker.sock \
    -v $PWD/application.yml:/opt/shinyproxy/application.yml \
    --net shinyproxy-net  -p 8080:8080 --name shiny-proxy \
    agresearch/shinyproxy:latest
```

In this example, all shiny apps launched by this proxy must also be attached to
the custom bridge, `shinyproxy-net`. Therefore, the `container-network`
attribute must be set to `shinyproxy-net` too.
