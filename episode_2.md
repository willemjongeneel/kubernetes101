# Episode 2 - Containers

### Why Containers?
- IT WORKS on my machine
- it works on my machine, then we'll ship your machine, and that is how docker was born
- portable - Build in one place, move it to another machine
- isolated - Containers are isolated from eachother 
- consistent - everytime you deploy it, it will be exactly the sAME
- lightweight
- build once, deploy anywhere

### History (is complex)
- Docker (2013)
- CoreOS (2013) - Not in use anymore
- Open Container Initiative 
- RUNC (2015) 
- crun (2019) 
- bwrap-oci (2016)
- cri-o (2017)
- https://www.capitalone.com/tech/cloud/container-runtime/

### Building Containers
- docker
- buildah
- `docker build -t geerlingguy/kube-101:intro .` - build an image based on Dockerfile
- `docker run -rm -p 80:80 geerlingguy/kube-101:intro` - run the image 
 
### Multistage Dockerfile example:
`FROM golang:1-alpine as build`  
`WORKDIR /app`  
`COPY cmd cmd`  
`RUN go build cmd/hello/hello.go`  


`FROM alpine:latest`  
`WORKDIR /app`  
`COPY --from=build /app/hello /app/hello`  
`EXPOSE 8180`  
`ENTRYPOINT ["./hello"]`  

You do this because the first image is large. We need it to build the go programme, but we do not need it later. Then we use the small alpine image.

