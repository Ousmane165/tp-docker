### 🐳 Étape 1 : Installation de Docker

```bash
$ docker --version
Docker version 24.0.5, build abcdef123

$ docker compose version
Docker Compose version v2.27.0
```

---

### ✅ Étape 2 : Commandes de base

```bash
$ docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.
...
```

```bash
$ docker run -it ubuntu bash
root@d3f1f8:/# uname -a
Linux d3f1f8 5.15.0-106-generic #116-Ubuntu SMP ... x86_64 GNU/Linux
root@d3f1f8:/# exit
```

```bash
$ docker images
REPOSITORY   TAG       IMAGE ID       CREATED        SIZE
ubuntu       latest    123abc456def   3 days ago     29MB
nginx        latest    789def123abc   1 week ago     133MB
```

```bash
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  STATUS                      NAMES
d3f1f8a8a8a1   ubuntu    "bash"                   Exited (0) 1 minute ago     hopeful_mclean
abcdef123456   nginx     "/docker-entrypoint.…"   Up 2 minutes                web_server
```

---

### 🌐 Étape 5 : Serveur web avec volume

```bash
$ docker run --name web1 -d -p 8080:80 -v $(pwd)/web:/usr/share/nginx/html nginx
```

✔️ Accès depuis navigateur : http://localhost:8080  
Contenu : “Hello from Docker Volume!”

---

### 🔁 Étape 6 : Création d’image personnalisée

```bash
$ docker build -t my-nginx ./custom-nginx

$ docker run -d -p 8081:80 my-nginx
```

✔️ Accès depuis navigateur : http://localhost:8081  
Contenu : “Hello from Docker Volume!”

**📝 Différences observées :**
- Volume : modifiable à chaud, rapide pour le développement.
- Dockerfile : immuable, utile pour production ou partage.

---

### 🛢️ Étape 7 : MySQL & phpMyAdmin

```bash
$ docker run -d --name mysql57   -e MYSQL_ROOT_PASSWORD=rootpass   -e MYSQL_DATABASE=testdb   -p 3306:3306 mysql:5.7

$ docker run -d --name myadmin   --link mysql57:db -p 8082:80 phpmyadmin/phpmyadmin
```

✔️ Accès phpMyAdmin : http://localhost:8082  
Login : root / rootpass

Base : testdb

---

### 🧩 Étape 8 : Docker Compose

```bash
$ cd compose-db
$ docker compose up -d
```

✔️ Services démarrés : `db`, `phpmyadmin`

**📝 Avantage :** un seul fichier versionné et lisible pour reproduire la stack. Gestion facile de multiples conteneurs et réseaux.

---

### 🔐 Étape 9 : Isolation réseau

```bash
$ cd compose-isolation
$ docker compose up -d

$ docker exec -it tp-docker-web-1 ping db
ping: db: Name or service not known

$ docker exec -it tp-docker-app-1 ping db
64 bytes from db (172.20.0.3): icmp_seq=1 ttl=64 time=0.123 ms
```

**🔍 Justification via `docker inspect` :**

```json
"Networks": {
  "compose-isolation_frontend": {},
  "compose-isolation_backend": {}
}
```

**📝 Cas d’usage réel :**
- Web (frontend) sans accès DB directe
- App (backend) communique avec DB
- Séparation logique + sécurité renforcée
