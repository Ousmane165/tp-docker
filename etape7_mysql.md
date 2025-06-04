ous@ubuntu:~/tp-docker/tp-docker$ docker network create tp-net
95ff53ce4cdf76d4efe3c90cd6bfaa3d4f2a8aae93b8e23850e5f590ece3a9d5
ous@ubuntu:~/tp-docker/tp-docker$ docker run -d --name mysql --network tp-net -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=tpdb mysql:5.7
Unable to find image 'mysql:5.7' locally
5.7: Pulling from library/mysql
20e4dcae4c69: Pull complete 
1c56c3d4ce74: Pull complete 
e9f03a1c24ce: Pull complete 
68c3898c2015: Pull complete 
6b95a940e7b6: Pull complete 
90986bb8de6e: Pull complete 
ae71319cb779: Pull complete 
ffc89e9dfd88: Pull complete 
43d05e938198: Pull complete 
064b2d298fba: Pull complete 
df9a4d85569b: Pull complete 
Digest: sha256:4bc6bc963e6d8443453676cae56536f4b8156d78bae03c0145cbe47c2aad73bb
Status: Downloaded newer image for mysql:5.7
472830c394d3b5169fcfb30c9cc4c6799a53b29bc863d26306441362e18dfdd9
ous@ubuntu:~/tp-docker/tp-docker$ docker run -d --name phpmyadmin --network tp-net -e PMA_HOST=mysql -p 8084:80 phpmyadmin/phpmyadmin
Unable to find image 'phpmyadmin/phpmyadmin:latest' locally
latest: Pulling from phpmyadmin/phpmyadmin
af302e5c37e9: Pull complete 
71a74ed03dab: Pull complete 
3ef8d0774deb: Pull complete 
11d17388a3b8: Pull complete 
0814cbbf72a2: Pull complete 
3a28acedadf8: Pull complete 
2ab7ef40feaf: Pull complete 
88324ccb20a1: Pull complete 
ad5f2fca9132: Pull complete 
9df2a6231627: Pull complete 
b3207e60ff9a: Pull complete 
d18c9f420b35: Pull complete 
673faad72ba8: Pull complete 
4f4fb700ef54: Pull complete 
a5c74661bb9e: Pull complete 
1cf5cbfd971f: Pull complete 
e92d8472eb26: Pull complete 
7755344c0dda: Pull complete 
b0f9dd503cef: Pull complete 
2ee0fe041682: Pull complete 
Digest: sha256:95e01f723b5e55fabf16d0473f1df2354c4c6352b35902b51d6a6245e074aee4
Status: Downloaded newer image for phpmyadmin/phpmyadmin:latest
e3567d94f3a4129893b25f695e505292cdd0efba4d4ec55d5f9fe69bebe19d17
