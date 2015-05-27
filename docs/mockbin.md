# Mockbin

## intro

First install docker and be sure you have it working. In my case I'm using:

>
> $ boot2docker version
> Boot2Docker-cli version: v1.3.1
> Git commit: 57ccdb8
>

Something I spend a lot of time in this setup was the EXPOSE on MAC. Basically
the setup is described [here](https://github.com/boot2docker/boot2docker#container-port-redirection).

TL;DR
>
> http://$(boot2docker ip):8080 is where you will have access to all the EXPOSE
> ports.
>
> And remember to inject the exports using
> `eval "$(boot2docker shellinit)"`
>

## setup

1. `cd mockbin`
2. `docker build -t="<username>/mockbin" .`
3. `cd ../redis`
4. `docker build -t="<username>/redis" .`
5. replace /dendril/<username>/ inside `docker-compose.yml`
6. `docker-compose up` the first time to create both containers.
7. `docker-compose help up` for more information.
8. `curl -v http://$(boot2docker ip):8080` should answer "hello world".
9. `docker-compose [stop|start|restart|logs]` for the next runs.
