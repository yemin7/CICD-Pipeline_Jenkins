## Build container
```
docker build . -t <repo>:jenkins:2.0
```

## Run the container
```
docker run --name jenkins -d -p 8080:8080 -p 50000:50000 -v /local-machine/jenkins/home:/var/lib/jenkins <repo>/jenkins:2.0
```
