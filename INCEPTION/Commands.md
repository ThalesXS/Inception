
# docker

| Comando  | Descrição                                                                             | Flags     |
| :------: | ------------------------------------------------------------------------------------- | --------- |
|  `pull`  | Usado para buscar uma imagem no [[Docker Registry]] e salva o mesmo em nosso sistema. | [[#pull]] |
| `images` | Imprime a lista de images instaladas localmente.                                      | [[#ima]]  |
|  `run`   | Usado para correr um _container_.                                                     | [[#run]]  |
|   `ps`   | Usado para apresentar todos os _containers_ que estão a correr atualmente.            | [[#ps]]   |
|   `rm`   | Elimina _containers_.                                                                 | [[#rm]]   |
|  `rmi`   | Elimina _images_.                                                                     |           |
|  `stop`  |                                                                                       |           |
|  `port`  |                                                                                       |           |

## pull
Usado para buscar uma imagem no [[Docker Registry]] e salva o mesmo em nosso sistema.
```sh
docker pull IMAGE
```

---

## images
Usado para verificar as imagens instaladas localmente.

---
## run

Usado para correr um _container_.
```sh
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```


|         Option         | Descrição                                                                                                                |
| :--------------------: | ------------------------------------------------------------------------------------------------------------------------ |
|   `-a` / `--attach`    | Adiciona ao STDIN, STDOUT ou STDERR.                                                                                     |
| `-i` / `--interactive` | Mantém o STDIN aberto, mesmo que não tenha sido adicionado.                                                              |
|      `-t` / `tty`      | Aloca um "pseudo-TTY".                                                                                                   |
|        `--help`        | Imprime instruções de uso.                                                                                               |
|   `-d` / `--detach`    | Corre o _container_ no plano de fundo e imprime o seu ID.                                                                |
|   `-p` / `--publish`   | Divulga uma porta do _container_ para o host.                                                                            |
| `-P` / `--publish-all` | Divulga a(s) porta(s) de um _container_ ao host.                                                                         |
|        `--name`        | Permite que especifiquemos identificadores customizados para um _container_. Podendo então ser usado no lugar de sua ID. |


---

## ps
Usado para apresentar todos os _containers_ que estão a correr atualmente.
```sh
docker ps [OPTIONS]
```

###### Flags

| Option | Descrição                                         |
| ------ | ------------------------------------------------- |
| `-a`   | Apresenta todos os comandos previamente corridos. |
|        |                                                   |

---

## rm
