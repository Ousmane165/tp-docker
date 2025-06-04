ous@ubuntu:~/tp-docker/tp-docker$ mkdir web
ous@ubuntu:~/tp-docker/tp-docker$ echo "<h1>Bienvenue sur Docker !</h1>" > web/index.html
bash: !: event not found
ous@ubuntu:~/tp-docker/tp-docker$ echo '<h1>Bienvenue sur Docker !</h1>' > web/index.html
ous@ubuntu:~/tp-docker/tp-docker$ docker run --name web-volume -v $(pwd)/web:/usr/share/nginx/html:ro -p 8081:80 nginx
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2025/06/04 06:40:01 [notice] 1#1: using the "epoll" event method
2025/06/04 06:40:01 [notice] 1#1: nginx/1.27.5
2025/06/04 06:40:01 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14) 
2025/06/04 06:40:01 [notice] 1#1: OS: Linux 5.15.0-139-generic
2025/06/04 06:40:01 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2025/06/04 06:40:01 [notice] 1#1: start worker processes
2025/06/04 06:40:01 [notice] 1#1: start worker process 29
2025/06/04 06:40:01 [notice] 1#1: start worker process 30

^C2025/06/04 06:40:55 [notice] 1#1: signal 2 (SIGINT) received, exiting
2025/06/04 06:40:55 [notice] 30#30: exiting
2025/06/04 06:40:55 [notice] 29#29: exiting
2025/06/04 06:40:55 [notice] 29#29: exit
2025/06/04 06:40:55 [notice] 30#30: exit
2025/06/04 06:40:55 [notice] 1#1: signal 14 (SIGALRM) received
2025/06/04 06:40:55 [notice] 1#1: signal 17 (SIGCHLD) received from 29
2025/06/04 06:40:55 [notice] 1#1: worker process 29 exited with code 0
2025/06/04 06:40:55 [notice] 1#1: signal 29 (SIGIO) received
2025/06/04 06:40:55 [notice] 1#1: signal 17 (SIGCHLD) received from 30
2025/06/04 06:40:55 [notice] 1#1: worker process 30 exited with code 0
2025/06/04 06:40:55 [notice] 1#1: exit
ous@ubuntu:~/tp-docker/tp-docker$ docker run --name web-volume -v $(pwd)/web:/usr/share/nginx/html:ro -p 8081:80 nginx
docker: Error response from daemon: Conflict. The container name "/web-volume" is already in use by container "190c90983b55acd566e7d4f25a10c2dca035352ec4c91c049fd90e03c982ec8a". You have to remove (or rename) that container to be able to reuse that name.

Run 'docker run --help' for more information
ous@ubuntu:~/tp-docker/tp-docker$ docker run -d --name web-copy -p 8082:80 nginx
0bd92aec7515ab4bdd451fb4334a68d51acb4b995f12ac44a9f41efcf851a907
ous@ubuntu:~/tp-docker/tp-docker$ docker cp web/index.html web-copy:/usr/share/nginx/html/index.html
Successfully copied 2.05kB to web-copy:/usr/share/nginx/html/index.html
