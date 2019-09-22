# ci-demo

ci-demo is a just a demo for Jenkins ci. This project describe how to build and deploy a project using Jenkins continue integration.

## Build

Use following command to build this project as a docker image.

```bash
 docker build -f docker/Dockerfile -t <docker image tag> --force-rm .
```

## Run

Use following command to run built docker image.

```bash
docker run -p <port:port> <image name> --name <container name>
```
