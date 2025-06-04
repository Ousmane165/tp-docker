ous@ubuntu:~/tp-docker/tp-docker$ nano Dockerfile
ous@ubuntu:~/tp-docker/tp-docker$ docker build -t mon-nginx .
[+] Building 0.2s (7/7) FINISHED                                 docker:default
 => [internal] load build definition from Dockerfile                       0.0s
 => => transferring dockerfile: 101B                                       0.0s
 => [internal] load metadata for docker.io/library/nginx:latest            0.0s
 => [internal] load .dockerignore                                          0.0s
 => => transferring context: 2B                                            0.0s
 => [internal] load build context                                          0.0s
 => => transferring context: 100B                                          0.0s
 => [1/2] FROM docker.io/library/nginx:latest                              0.0s
 => [2/2] COPY web/index.html /usr/share/nginx/html/index.html             0.1s
 => exporting to image                                                     0.0s
 => => exporting layers                                                    0.0s
 => => writing image sha256:da0491057b867097e4c58cd71e0332d278d22eef66c40  0.0s
 => => naming to docker.io/library/mon-nginx                               0.0s
ous@ubuntu:~/tp-docker/tp-docker$ docker run -d -p 8080:80 mon-nginx
9823acb4fd6a6848d6b982081ef86047ef0cbb6ce753dc06052f050fdb234f0b
