ous@ubuntu:~/tp-docker/tp-docker$ sudo apt install -y docker-ce docker-ce-cli containerd.io
Reading package lists... Done
Building dependency tree       
Reading state information... Done
containerd.io is already the newest version (1.7.27-1).
docker-ce-cli is already the newest version (5:28.1.1-1~ubuntu.20.04~focal).
docker-ce is already the newest version (5:28.1.1-1~ubuntu.20.04~focal).
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
ous@ubuntu:~/tp-docker/tp-docker$ sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100 12.1M  100 12.1M    0     0   428k      0  0:00:29  0:00:29 --:--:-- 1042k
ous@ubuntu:~/tp-docker/tp-docker$ sudo chmod +x /usr/local/bin/docker-compose
ous@ubuntu:~/tp-docker/tp-docker$ docker-compose --version
docker-compose version 1.29.2, build 5becea4c
ous@ubuntu:~/tp-docker/tp-docker$ echo "# TP Docker - DevOps" > README.md
ous@ubuntu:~/tp-docker/tp-docker$ git add README.md
ous@ubuntu:~/tp-docker/tp-docker$ git commit -m "Initialisation du projet avec README"
[main a13d7de] Initialisation du projet avec README
 1 file changed, 1 insertion(+), 1 deletion(-)
ous@ubuntu:~/tp-docker/tp-docker$ git push README.md
fatal: invalid gitfile format: README.md
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
ous@ubuntu:~/tp-docker/tp-docker$ ^C
ous@ubuntu:~/tp-docker/tp-docker$ git push origin main
Username for 'https://github.com': Ousmane165
Password for 'https://Ousmane165@github.com': 
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/Ousmane165/tp-docker.git/'
ous@ubuntu:~/tp-docker/tp-docker$ git push origin main
Username for 'https://github.com': Ousmane165
Password for 'https://Ousmane165@github.com': 
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 290 bytes | 290.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/Ousmane165/tp-docker.git
   24f295d..a13d7de  main -> main
ous@ubuntu:~/tp-docker/tp-docker$ 
