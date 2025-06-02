ous@ubuntu:~/tp-docker/tp-docker$ docker run -it ubuntu bash
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
0622fac788ed: Pull complete 
Digest: sha256:6015f66923d7afbc53558d7ccffd325d43b4e249f41a6e93eef074c9505d2233
Status: Downloaded newer image for ubuntu:latest

docker images

docker ps -a

docker run -p 80:80 nginx

docker run -d -p 8080:80 nginxroot@472d5e067433:/# 
root@472d5e067433:/# docker images
bash: docker: command not found
root@472d5e067433:/# 
root@472d5e067433:/# docker ps -a
bash: docker: command not found
root@472d5e067433:/# 
root@472d5e067433:/# docker run -p 80:80 nginx
bash: docker: command not found
root@472d5e067433:/# 
root@472d5e067433:/# docker run -d -p 8080:80 nginx
bash: docker: command not found
root@472d5e067433:/# 
root@472d5e067433:/# ^C
root@472d5e067433:/# ex
bash: ex: command not found
root@472d5e067433:/# q
bash: q: command not found
root@472d5e067433:/# exit
exit
ous@ubuntu:~/tp-docker/tp-docker$ docker images
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
ubuntu        latest    a0e45e2ce6e6   5 weeks ago    78.1MB
hello-world   latest    74cc54e27dc4   4 months ago   10.1kB
ous@ubuntu:~/tp-docker/tp-docker$ 
ous@ubuntu:~/tp-docker/tp-docker$ docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED         STATUS                        PORTS     NAMES
472d5e067433   ubuntu        "bash"     2 minutes ago   Exited (127) 25 seconds ago             quirky_hodgkin
a901efd38668   hello-world   "/hello"   3 minutes ago   Exited (0) 3 minutes ago                hopeful_goldstine
a3fc597efaa0   hello-world   "/hello"   2 weeks ago     Exited (0) 2 weeks ago                  angry_margulis
ous@ubuntu:~/tp-docker/tp-docker$ 
ous@ubuntu:~/tp-docker/tp-docker$ docker run -p 80:80 nginx
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
61320b01ae5e: Pull complete 
670a101d432b: Pull complete 
405bd2df85b6: Pull complete 
cc80efff8457: Pull complete 
2b9310b2ee4b: Pull complete 
6c4aa022e8e1: Pull complete 
abddc69cb49d: Pull complete 
Digest: sha256:fb39280b7b9eba5727c884a3c7810002e69e8f961cc373b89c92f14961d903a0
Status: Downloaded newer image for nginx:latest
docker: Error response from daemon: failed to set up container networking: driver failed programming external connectivity on endpoint quizzical_murdock (19831cf0e0e54f54eade7c1ab0b536d3df15138f8d86dcc488f7085da35004bf): failed to bind host port for 0.0.0.0:80:172.17.0.2:80/tcp: address already in use

Run 'docker run --help' for more information
ous@ubuntu:~/tp-docker/tp-docker$ 
ous@ubuntu:~/tp-docker/tp-docker$ docker run -d -p 8080:80 nginx
30a5c15be1ee4083288fec7e979eb2c77f5f36e81c1850db46d2e4f6eba6ceaf
ous@ubuntu:~/tp-docker/tp-docker$ nano etape2_commandes.md
