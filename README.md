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

```
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

```
$ docker pull hello-world
Using default tag: latest
latest: Pulling from library/hello-world
2db29710123e: Pull complete
Digest: sha256:cc15c5b292d8525effc0f89cb299f1804f3a725c8d05e158653a563f15e4f685
Status: Downloaded newer image for hello-world:latest
docker.io/library/hello-world:latest
```

```
λ docker images
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
hello-world   latest    feb5d9fea6a5   2 months ago   13.3kB
```

```
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

```
λ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

```

```
λ docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED         STATUS                     PORTS     NAMES
cf459cb37b28   hello-world   "/hello"   2 minutes ago   Exited (0) 2 minutes ago             condescending_swartz

```

02 - Rodar Comandos dentro de um container Docker

03 - Acessar container Docker

04 - Excluir Containers e Imagens Docker

05 - Alterando o Status de Containers Docker

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

