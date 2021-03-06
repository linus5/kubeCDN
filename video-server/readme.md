# kubeCDN: Video Server 

If you are here to deploy a demo service to your kubeCDN deployment, skip the "Docker Image" section below and proceed to [this](#kubeCDN-demo-installation) section. 

## Docker Image 
The docker image generated by the `Dockerfile` in this directory has been pushed to docker hub and is available [here](https://hub.docker.com/r/ilhaan/nginx-rtmp-sample). Pull this image using: 
```
docker pull ilhaan/nginx-rtmp-sample
```

If you would like to build and run this locally using the [Dockerfile](./Dockerfile) in this directory, you can use `./start-container.sh`. 


After running this docker image, open a video player capable of RTMP streams ([VLC](https://www.videolan.org/vlc/index.html) is a good choice) and open a network stream using the following: 
```
rtmp://localhost/vod/video.mp4
```

---------

## kubeCDN Demo Installation 
Deploy this to all k8s clusters using: 
```
./cluster_deploy.sh
```

This will deploy the video server to all regions that were setup in earlier steps of the instructions shown [here](https://github.com/ilhaan/kubeCDN#deploy-clusters--service). Access video streams using the URL that EKS exposes for the service based on the instructions in the [section above](#docker-image). 

## References: 
* [Source Image](https://hub.docker.com/r/tiangolo/nginx-rtmp/): This is the base image used to build the video server docker image in this directory. 
* [RTMP Documentation](https://github.com/arut/nginx-rtmp-module/wiki/Directives): Documentation for the [Real-Time Messaging Protocol](https://en.wikipedia.org/wiki/Real-Time_Messaging_Protocol) that is used by the video server here to stream videos. 
* [Sample Video Source](https://github.com/mediaelement/mediaelement-files): Source of sample video used for demonstration purposes. This video file consists of a small portion of [this](https://en.wikipedia.org/wiki/Big_Buck_Bunny) open-source film. 
