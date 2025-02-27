
# docker

| Comando  | Descrição                                                                             | Flags     |
| :------: | ------------------------------------------------------------------------------------- | --------- |
|  `pull`  | Usado para buscar uma imagem no [[Docker Registry]] e salva o mesmo em nosso sistema. | [[#pull]] |
| `images` | Imprime a lista de images instaladas localmente.                                      | [[#ima]]  |
|  `run`   | Usado para correr um _container_.                                                     | [[#run]]  |
|   `ps`   | Usado para apresentar todos os _containers_ que estão a correr atualmente.            | [[#ps]]   |
|   `rm`   | Elimina _containers_.                                                                 | [[#rm]]   |
|  `rmi`   | Elimina _images_.                                                                     |           |

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


|  Option  | Descrição                                                   |
| :------: | ----------------------------------------------------------- |
|   `-a`   | Adiciona ao STDIN, STDOUT ou STDERR.                        |
|   `-i`   | Mantém o STDIN aberto, mesmo que não tenha sido adicionado. |
|   `-t`   | Aloca um "pseudo-TTY".                                      |
| `--help` | Imprime instruções de uso.                                  |


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
