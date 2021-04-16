# ARM7/8 Docker image for Jhead's Phantom proxy

This repo is an update of [nkelemen18 repo](https://github.com/nkelemen18/Minecraft-Phantom-Proxy-Docker) to add arm7/8 image to run on Raspberry PI

## Basic usage:
```bash
docker container run --name phantom-proxy -e SERVER=<server ip>:<server_port> -e ARM_VERSION=arm7 --network host karl0ss/minecraftphantomproxydocker:arm7
```
Or with docker compose:

```bash
docker-compose up -d
```

[Example docker-compose file](https://github.com/karl0ss/Minecraft-Phantom-Proxy-Docker/blob/master/docker-compose.yml)

### Available variables:

 - SERVER: Required: Bedrock/MCPE server IP address and port (ex: 1.2.3.4:19132)
 - ARM_VERSION: Required: You need to specify either arm7 or arm8 depending on the version you wish to run.
 - IPV6: Optional: Enables IPv6 support on port 19133 (experimental). Pass `1` to enable this flag! (Example: `IPV6=1`)
 - BIND_IP: Optional: IP address to listen on. Defaults to all interfaces. (default "0.0.0.0")
 - BIND_PORT: Optional: Port to listen on. Defaults to 0, which selects a random port.
 - DEBUG: Optional: Enables debug logging. Pass `1` to enable this flag! (Example: `DEBUG=1`)
 - REMOVE_PORTS: Optional: Forces ports to be excluded from pong packets (experimental). Pass `1` to enable this flag! (Example: `REMOVE_PORTS=1`)
 - TIMEOUT: Optional: Seconds to wait before cleaning up a disconnected client (default 60)
 - WORKERS: Optional:  Specify the number of "threads" to use to process data from clients. (Example: `WORKERS=16`)

*Note: host network mode required.*

[Github repo](https://github.com/karl0ss/Minecraft-Phantom-Proxy-Docker)

[Dockerhub](https://hub.docker.com/r/karl0ss/minecraftphantomproxydocker)

The proxy is written by jhead.
[Phantom on GitHub](https://github.com/jhead/phantom)