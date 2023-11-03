# SFTP Server Docker emulation

## Description
This is a simple repositry for emulating the SFTP server on a docker container.

## How to Run?
To build a docker image you can either pull the same from [Github Package](https://github.com/rpai9/sftp-emulation-docker/pkgs/container/sftp-emulation-docker) or you can use the command below

```
DOCKER_BUILDKIT=1  docker build -t sftp_test_server .
```

By default the `USERNAME` for the server will be `sftp_user` and the `PASSWORD` will be `Testing123`. (This applies if you get the image from github)

If you want to define the username and password you can pass them in the Docker Run command as shown below

```
DOCKER_BUILDKIT=1 docker build -t sftp_test_server .  --build-arg "USERNAME=cat_says" --build-arg "PASSWORD=Meow"
```

For running the image as a container run the following command

```
docker run -d -p 21:22 sftp_test_server
```

The server will be available on 0.0.0.0:21

Note: I know I'm mapping the port to 21 beacuse most of the operating system by default uses 0.0.0.0:21 for handling incoming SSH connections. (Port 21 is usually used for FTP.)


## Pre-requesites

 - Install [docker engine](https://docs.docker.com/get-docker/).
 - Install Docker Desktop Client. I prefer [Rancher Desktop](https://rancherdesktop.io/) which is open source.
