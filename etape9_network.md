ous@ubuntu:~/tp-docker/tp-docker$ nano docker-compose.yml
ous@ubuntu:~/tp-docker/tp-docker$ docker-compose up -d
Creating network "tp-docker_frontend" with the default driver
Creating network "tp-docker_backend" with the default driver
WARNING: Found orphan containers (tp-docker_phpmyadmin_1) for this project. If you removed or renamed this service in your compose file, you can run this command with the --remove-orphans flag to clean it up.
Pulling web (praqma/network-multitool:)...
latest: Pulling from praqma/network-multitool
5758d4e389a3: Pull complete
89d2c42e021e: Pull complete
c56ef2f6b498: Pull complete
fb4370a69dda: Pull complete
003f3d74368c: Pull complete
cd3def2cca55: Pull complete
ba5a2b2d204e: Pull complete
Digest: sha256:97b15098bb72df10f7c4e177b9c0e2435ec459f16e79ab7ae2ed3f1eb0e79d19
Status: Downloaded newer image for praqma/network-multitool:latest
Creating tp-docker_web_1  ... done
Creating tp-docker_app_1  ... done
Recreating tp-docker_db_1 ... 

ERROR: for tp-docker_db_1  'ContainerConfig'

ERROR: for db  'ContainerConfig'
Traceback (most recent call last):
  File "docker-compose", line 3, in <module>
  File "compose/cli/main.py", line 81, in main
  File "compose/cli/main.py", line 203, in perform_command
  File "compose/metrics/decorator.py", line 18, in wrapper
  File "compose/cli/main.py", line 1186, in up
  File "compose/cli/main.py", line 1182, in up
  File "compose/project.py", line 702, in up
  File "compose/parallel.py", line 108, in parallel_execute
  File "compose/parallel.py", line 206, in producer
  File "compose/project.py", line 688, in do
  File "compose/service.py", line 581, in execute_convergence_plan
  File "compose/service.py", line 503, in _execute_convergence_recreate
  File "compose/parallel.py", line 108, in parallel_execute
  File "compose/parallel.py", line 206, in producer
  File "compose/service.py", line 496, in recreate
  File "compose/service.py", line 615, in recreate_container
  File "compose/service.py", line 334, in create_container
  File "compose/service.py", line 922, in _get_container_create_options
  File "compose/service.py", line 962, in _build_container_volume_options
  File "compose/service.py", line 1549, in merge_volume_bindings
  File "compose/service.py", line 1579, in get_container_data_volumes
KeyError: 'ContainerConfig'
[8217] Failed to execute script docker-compose
ous@ubuntu:~/tp-docker/tp-docker$ docker exec -it tp-docker_web_1 sh
/ # ping db 
ping: db: Try again
