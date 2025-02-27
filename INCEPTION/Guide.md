# Guide

## Contents

- [[Docker]]
- [[Docker Compose]]
- [[Docker Images]]
- [[Dockerfile]]
- [[Docker Registry]]

---
## Index

1. [[#Hello World]]
	1. [[#Correndo um Container]]
	2. [[#Como verificar os processos abertos]]
	3. [[#Mantendo um container aberto]]

---

## Criando um grupo `docker`

1. Crie o grupo docker: `sudo groupadd docker`
2. Adicione seu user: `sudo usermod -aG docker $USER
3. Ative as alterações efetuadas aos grupos: `newgrp docker`
4. Confirme que consegue correr o docker sem `sudo`: `docker run hello-world`

## Hello World
#### Playing with Busybox

Nesta secção, iremos correr um _container_ Busybox em nosso sistema através do comando `docker run`. Para começar, devemos correr `docker pull <image-name>` em nosso terminal:

```sh
docker pull busybox.
```

O comando `pull` busca a imagem `busybox` no [[Docker Registry]] e salva o mesmo em nosso sistema.
#### Correndo um Container

Para corrermos um Docker _container_ baseado nesta imagem, devemos usar o comando `docker run <image-name>`:

```sh
docker run busybox
```
&rdsh; Apesar de não obtermos nenhum _output_, ao correr o comando acima, diversos processos ocorrem por trás das cenas. Basicamente, ao usarmos o comando `run`, o Docker _client_ encontra a imagem (busybox neste caso), carrega o _container_ e então corre um comando neste _container_.
&rdsh; No exemplo acima, nós não fornecemos nenhum comando. Por tanto, o _container_ foi iniciado, correu um comando vazio, e terminou seu processo.

Podemos então tentar:
```sh
docker run busybox echo "hello from busybox"
```
&rdsh; Desta forma, finalmente obtivemos um _output_. Neste caso, o Docker _client_ correu o comando `echo` dentro do nosso container `busybox` e então finalizou seu processo.

Note que todo o processo ocorreu de maneira relativamente rápida. Agora, imagine ter que ligar uma [[Virtual Machine]], correr o comando, e então desligar a VM. É por conta desta facilidade que os _containers_ são uma medida mais rápida e eficiente.

#### Como verificar os processos abertos

O comando `docker ps` é usado para verificar todos os _containers_ que estão a correr atualmente. Caso corramos o mesmo sem que haja _containers_ ativos, iremos obter uma lista vazia. Porém, podemos também correr o comando com a flag `-a`, que faz com que os todos os _containers_ corridos previamente sejam apresentados.

#### Mantendo um container aberto

Ao corrermos o comando `docker run`, podemos usar as flags `-it` para nos conectarmos à um tty dentro do container. Desta forma, é possível correr diversos comandos no container, sem a necessidade de executar `docker run` para cada um deles:
```sh
docker run -it <image-name> sh
```
&rdsh; Ao corrermos o comando acima, podemos tentar executar o comando `rm -rf bin` para remover todos os comandos do `/bin` em nosso container. Assim que tudo parar de funcionar, podemos simplesmente sair do mesmo (`exit` e **Enter**) e executar o `docker run` novamente. Uma vez que o Docker cria um novo _container_ toda vez, o `/bin` deverá voltar a existir, e tudo funcionará normalmente.

> [!DANGER] Cuidado
>  É possível correr `rm -rf bin` dentro do _container_. Porém, ao fazer o mesmo, garanta que está a correr o comando no _container_, e não no seu computador, pois isso irá apagar outros comandos como `ls`, `uptime`, etc.

#### Removendo containers antigos
Como se pode observar [[#Como verificar os processos abertos|acima]], após encerrarmos um _container_ o Docker mantém alguns "restos" dos mesmos, o que pode facilmente consumir grande parte do espaço do disco. Para evitar isto, podemos usar o comando `docker rm` para remover containers, especificando os IDs dos mesmos:
```sh
docker rm CONTAINER_ID...
```
&rdsh; Ao deletarmos um _container_, o programa irá ecoar o ID do mesmo de volta. 

Caso tenhamos diversos _containers_ para deletar, copiar e colar os IDs pode ser trabalhoso. Neste caso, podemos usar:
```sh
docker rm $(docker ps -a -q -f status=exited)
```
&rdsh; Este comando irá deletar todos os containers com estado `exited`.

> [!tip] Dica
> Em versões mais recentes do Docker, o comando `docker container prune` pode ser usado para se obter o mesmo efeito.

Podemos também usar a flag `--rm` com o comando `docker run`. Esta flag faz com que o _container_ seja deletado automaticamente após ser terminado.

---
## Terminologia

Na última seção foram usadas algumas alguns jargões específicos do Docker que inicialmente podem soar confusos. Abaixo estão algumas descrições da terminologia frequentemente usada para descrever o eco-sistema Docker.

- _Images_ – Os esboços (_blueprint_) de nossas aplicações que formam a base dos _containers_.
- _Containers_ – Criados a partir de uma image e responsável por correr a aplicação. Nós criamos um _container_ sempre que usamos `docker run`.
- _Docker Daemon_ – O serviço que está a correr no host. Responsável por montar, correr e destribuir Docker _containers_. O _daemon_ é o processo que corre no sistema operacional no qual os _clients_ se comunicam.
- _Docker Client_ – A ferramenta da linha de comando que permite que usuários interajam com o _daemon_. Existem outras formas de clients - como o [[Kitematic]] que fornece uma GUI aos usuários.
- _Docker Hub_ – Um registro de _Docker Images_. Funciona como um diretório com todos os _Docker Images_ disponíveis. Caso necessário, é possível alocar suas próprias _Docker registries_ e usa-las para puxar _images_.