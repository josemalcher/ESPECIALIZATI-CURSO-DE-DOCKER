# CURSO DE DOCKER

https://academy.especializati.com.br/curso/docker

NESSE CURSO VOCÊ VAI APRENDER DE UMA VEZ POR TODAS COMO TRABALHAR COM O DOCKER, COMO CRIAR CONTAINERS E MUITO MAIS.

## <a name="indice">Índice</a>

1. [01 - Intro ao Docker](#parte1)     
2. [02 - Docker na Prática](#parte2)     
3. [03 - Dockerfile](#parte3)     
4. [04 - Docker Compose](#parte4)     
---


## <a name="parte1">01 - Intro ao Docker</a>

01 - O que é o Docker

![](img/aula01.png)

02 - Ferramentas para o Curso de Docker

- https://docs.docker.com/desktop/windows/install/

03 - Conhecendo o Docker Hub

- https://hub.docker.com/

[Voltar ao Índice](#indice)

---


## <a name="parte2">02 - Docker na Prática</a>

01 - Iniciando com o Docker

```text
$ docker --help

Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Options:
      --config string      Location of client config files (default
                           "C:\\Users\\josem\\.docker")
  -c, --context string     Name of the context to use to connect to the
                           daemon (overrides DOCKER_HOST env var and
                           default context set with "docker context use")
  -D, --debug              Enable debug mode
  -H, --host list          Daemon socket(s) to connect to
  -l, --log-level string   Set the logging level
                           ("debug"|"info"|"warn"|"error"|"fatal")
                           (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this CA (default
                           "C:\\Users\\josem\\.docker\\ca.pem")
      --tlscert string     Path to TLS certificate file (default
                           "C:\\Users\\josem\\.docker\\cert.pem")
      --tlskey string      Path to TLS key file (default
                           "C:\\Users\\josem\\.docker\\key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Management Commands:
  builder     Manage builds
  buildx*     Docker Buildx (Docker Inc., v0.7.1)
  compose*    Docker Compose (Docker Inc., v2.2.1)
  config      Manage Docker configs
  container   Manage containers
  context     Manage contexts
  image       Manage images
  manifest    Manage Docker image manifests and manifest lists
  network     Manage networks
  node        Manage Swarm nodes
  plugin      Manage plugins
  scan*       Docker Scan (Docker Inc., 0.9.0)
  secret      Manage Docker secrets
  service     Manage services
  stack       Manage Docker stacks
  swarm       Manage Swarm
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

Commands:
  attach      Attach local standard input, output, and error streams to a running container   
  build       Build an image from a Dockerfile
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  images      List images
  import      Import the contents from a tarball to create a filesystem image
  info        Display system-wide information
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  login       Log in to a Docker registry
  logout      Log out from a Docker registry
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  run         Run a command in a new container
  save        Save one or more images to a tar archive (streamed to STDOUT by default)        
  search      Search the Docker Hub for images
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  version     Show the Docker version information
  wait        Block until one or more containers stop, then print their exit codes

Run 'docker COMMAND --help' for more information on a command.

To get more help with docker, check out our guides at https://docs.docker.com/go/guides/ 
```

```text
$ docker pull hello-world
Using default tag: latest
latest: Pulling from library/hello-world
2db29710123e: Pull complete
Digest: sha256:cc15c5b292d8525effc0f89cb299f1804f3a725c8d05e158653a563f15e4f685
Status: Downloaded newer image for hello-world:latest
docker.io/library/hello-world:latest
```

```text
λ docker images
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
hello-world   latest    feb5d9fea6a5   2 months ago   13.3kB
```

```text
λ docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```

```text
λ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

```

```text
λ docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED         STATUS                     PORTS     NAMES
cf459cb37b28   hello-world   "/hello"   2 minutes ago   Exited (0) 2 minutes ago             condescending_swartz

```

02 - Rodar Comandos dentro de um container Docker

```text
λ docker run ubuntu
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
7b1a6ab2e44d: Pull complete
Digest: sha256:626ffe58f6e7566e00254b638eb7e0f3b11d4da9675088f4781a50ae288f3322
Status: Downloaded newer image for ubuntu:latest
```

```text
λ docker run -it ubuntu ls
bin   dev  home  lib32  libx32  mnt  proc  run   srv  tmp  var
boot  etc  lib   lib64  media   opt  root  sbin  sys  usr

```

```text
λ docker run -it ubuntu bash
root@86c76e7bd106:/# ls
bin  boot  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@86c76e7bd106:/#
```

03 - Acessar container Docker

```text
λ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

λ docker run -itd ubuntu
3379a47c9376ae638284c07e9f91e4d85805cfd636761431e4d*******

λ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED         STATUS         PORTS     NAMES
3379a47c9376   ubuntu    "bash"    6 seconds ago   Up 2 seconds             quizzical_brahmagupta
```

```text
λ docker run -itd ubuntu
c93cebdd139628650e75157474ed25e872e58d4026dc2b2f58026********

λ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED          STATUS          PORTS     NAMES
c93cebdd1396   ubuntu    "bash"    20 seconds ago   Up 16 seconds             epic_sinoussi
3379a47c9376   ubuntu    "bash"    4 minutes ago    Up 4 minutes              quizzical_brahmagupta

```

```text
λ docker exec -it c93 bash
root@c93cebdd1396:/# ls -a
.  ..  .dockerenv  bin  boot  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var root@c93cebdd1396:/# exit
exit
```

```text
λ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED         STATUS         PORTS     NAMES
c93cebdd1396   ubuntu    "bash"    3 minutes ago   Up 3 minutes             epic_sinoussi
3379a47c9376   ubuntu    "bash"    7 minutes ago   Up 7 minutes             quizzical_brahmagupta

λ docker stop c93
c93

λ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED         STATUS         PORTS     NAMES
3379a47c9376   ubuntu    "bash"    7 minutes ago   Up 7 minutes             quizzical_brahmagupta

λ docker stop 337
337

λ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

λ docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED          STATUS                      PORTS     NAMES
c93cebdd1396   ubuntu        "bash"     4 minutes ago    Exited (0) 42 seconds ago             epic_sinoussi
3379a47c9376   ubuntu        "bash"     8 minutes ago    Exited (0) 6 seconds ago              quizzical_brahmagupta
86c76e7bd106   ubuntu        "bash"     12 minutes ago   Exited (0) 9 minutes ago              ecstatic_dewdney
39b76ecbd594   ubuntu        "ls"       20 minutes ago   Exited (0) 20 minutes ago             reverent_clarke
47c9cf1068b3   ubuntu        "bash"     23 minutes ago   Exited (0) 23 minutes ago             trusting_hofstadter
cf459cb37b28   hello-world   "/hello"   11 hours ago     Exited (0) 11 hours ago               condescending_swartz

```

04 - Excluir Containers e Imagens Docker

```text
$ docker rm 337
337

$ docker rm 337
337

$ docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED          STATUS                      PORTS     NAMES
86c76e7bd106   ubuntu        "bash"     18 minutes ago   Exited (0) 15 minutes ago             ecstatic_dewdney
39b76ecbd594   ubuntu        "ls"       26 minutes ago   Exited (0) 26 minutes ago             reverent_clarke
47c9cf1068b3   ubuntu        "bash"     29 minutes ago   Exited (0) 29 minutes ago             trusting_hofstadter
cf459cb37b28   hello-world   "/hello"   11 hours ago     Exited (0) 11 hours ago               condescending_swartz

```

```text
λ docker images
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
ubuntu        latest    ba6acccedd29   7 weeks ago    72.8MB
hello-world   latest    feb5d9fea6a5   2 months ago   13.3kB

λ docker rmi feb5d9fea6a5
Untagged: hello-world:latest
Untagged: hello-world@sha256:cc15c5b292d8525effc0f89cb299f1804f3a725c8d05e158653a563f15e4f685
Deleted: sha256:feb5d9fea6a5e9606aa995e879d862b825965ba48de054caab5ef356dc6b3412
Deleted: sha256:e07ee1baac5fae6a26f30cabfe54a36d3402f96afda318fe0a96cec4ca393359

λ docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
ubuntu       latest    ba6acccedd29   7 weeks ago   72.8MB
```

05 - Alterando o Status de Containers Docker

```text
λ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

λ docker run -itd ubuntu
dad495a5c3899882166267f00bf6fbed85d3fbe84341a9ba352f1da7b23abfb9

λ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED         STATUS         PORTS     NAMES
dad495a5c389   ubuntu    "bash"    9 seconds ago   Up 4 seconds             pensive_brattain

λ docker restart dad
dad

λ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED          STATUS         PORTS     NAMES
dad495a5c389   ubuntu    "bash"    56 seconds ago   Up 8 seconds             pensive_brattain

λ docker stop dad
dad

λ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

λ docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED         STATUS                      PORTS     NAMES
dad495a5c389   ubuntu    "bash"    2 minutes ago   Exited (0) 37 seconds ago             pensive_brattain

λ docker rm dad
dad

λ docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

```


06 - Docker Tags e Versões

07 - Expor Portas de um Container Docker

08 - Criar Containers Docker com Nome

09 - Criar Container Docker e Acessar Remotamente

10 - Montar Volumes de Containers Docker

11 - Limitar Memória e CPU em Containers Docker

12 - Inspecionar Containers Docker

[Voltar ao Índice](#indice)

---


## <a name="parte3">03 - Dockerfile</a>



[Voltar ao Índice](#indice)

---


## <a name="parte4">04 - Docker Compose</a>



[Voltar ao Índice](#indice)

---

