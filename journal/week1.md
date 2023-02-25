# Week 1 — App Containerization

DOCKER BEST PRACTICE
```
1-I used the official Docker image as Base Image: This made my dockerfile not only cleaner, it also let me use the official and verified image which is already built with best practices 
```

```
2- Using Specific Image Version: I also used the latest tag for my image version, instead of using a random tag. In essence I used the official image with the specific version, because the more specific the better
 ```
 
 ```
3- Optimizing Caching Layers:  As each layer is cached by docker and saved on local filesystem, if nothing has changed in a layer, it will be re-used from the cache which make building the image much faster. It is also using when pulling and pushing. 
Once a layer changes, all the following layers are re-created as well, however to take advantage of docker cache so as layers that haven’t change are re-used from cache, giving an advantage that the image will be built faster
I ordered the commands in the dockerfile from the least to the most frequently changing  to take advantage of caching, optimizing how fast the image gets built.
```

```
4- Utilizing the .dockerignore to Explicitly exclude files and folders: I created the .dockerignore file in the root directory and listed files and folders that are to be ignored so as to reduce the image size.
```

```
5-  Scan images for Vulnerabilities: I was unable to scan as multiple attempts on trying to install snyk third-party scanner failed.
For the week 1 challenge, I was able to push my image to a repositoy on dockerhub, research best practices and implemented in my code, also launched an EC2 instance and pulled a container but 
```
