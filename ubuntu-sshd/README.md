# Sample Ubuntu 17.04 Docker image with sshd installed

## Build

```
docker build -t ubuntu-sshd .
```

## Run

```
docker run -d -P --name ubuntu-sshd ubuntu-sshd
```

To list the port mapping run
```
docker run ubuntu-sshd 22
```

It will output a line like this
```
0.0.0.0:32772
```

Now you can ssh into the container from the host
```
ssh -p 32772 root@localhost
```