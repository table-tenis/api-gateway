## **API Gateway**

## **Requirements**
- traefik
## **Installation**

- Open https://github.com/containous/traefik/releases. Download latest version with linux_amd64 architecture.
- Unpack the archive: ```tar -zxvf traefik_v2.8.4_linux_amd64.tar.gz```. Version 2.8.4 is latest version in this time.
- ls -la
  - ```CHANGELOG.md```
  - ```LICENSE.md```
  - ```traefik```

## **Structure Of Traefik API Gateway**
- *traefik-static-conf.yml* is static file config for traefik when it start. It includes entryPoints and Providers.
- *traefik-dynamic-conf.yml* is dynamic provider file of traefik. It will auto update changements of this file in runtime. This file contains informations about servers, services, routing, middlewares,...
- Traefik can has some additional providers such as: etcd, consul, redis...
## **What This API Gateway Do**
- Routing api services.
- Load balance.
## **How To Run**
- Run traefik api gateway with file provider.
```
sudo ./traefik --configfile=traefik-static-conf.yml
```
- Run traefik api gateway with docker provider.
```
docker-compose -p traefik up -d
```
- View services registered in traefik api gateway.
```
http://localhost:8080/dashboard#/ for static file provider
http://localhost:8880/dashboard#/ for docker provider
```


