
[![Build Status](https://travis-ci.org/mschwager/gitem.svg?branch=master)](https://travis-ci.org/mschwager/gitem)
[![License](https://img.shields.io/packagist/l/doctrine/orm.svg)](https://img.shields.io/packagist/l/doctrine/orm.svg) 

# JLVM

JLVM é um simples script para automatizar algumas tarefas de Logical Volume Manager, e tem como objetivo:

* Criar volume fisico
* Remover volume fisico
* Criar grupo de volume
* Remover volume fisico de um grupo de volume
* Remover todo um grupo de volume
* Estender grupo de volume
* Criar volume logico
* Remover volume logico
* Estender volume logico
* Reduzir tamanho de volume logico
* Mostrar detalhes de todos itens acima

```
                             +-----+
 +---------------------------| LVM |--------------------------------+
 |                           +-----+                                |
 |                                                                  |
 |    +-------------+           +-----------+      +--------------+ |
 |    | /mnt/backup |           | /mnt/var  |      |              | |->Sistemas de arquivos
 |    +-------------+           +-----------+      |  Espaço não  | |
 |           |                        |            |   alocado    | |
 | +---------------------+   +------------------+  |              | |->Volumes logicos
 | | /dev/storage/backup |   | /dev/storage/var |  |              | |
 | +---------------------+   +------------------+  +--------------+ |
 |           |                        |                   |         |
 | +---------------+ +--------------------------------------------+ |
 | | grupo volume1 | |             grupo volume2                  | |->Grupos de volumes
 | +---------------+ +--------------------------------------------+ |
 |           |             |             |             |            |
 |     +-----------+ +-----------+ +-----------+ +-----------+      |
 |     | /dev/sda1 | | /dev/sda2 | | /dev/sdb1 | | /dev/sdc1 |      |->Volumes fisicos
 |     +-----------+ +-----------+ +-----------+ +-----------+      |
 +------------------------------------------------------------------+
             |             |             |             |
       +-----------+ +-----------+ +-----------+ +-----------+
       | /dev/sda1 | | /dev/sda2 | | /dev/sdb1 | | /dev/sdc1 |->Partições
       +-----------+ +-----------+ +-----------+ +-----------+
                \       /                |             |
               +----------+         +----------+ +----------+
               |----------|         |----------| |----------|
               | DISCO 1  |         |  DISCO 2 | | DISCO 3  |->Disco rigidos
               | /dev/sda |         | /dev/sdb | | /dev/sdc |
               +----------+         +----------+ +----------+
```

# Clonando o projeto e utilizando o script
```
$ git clone https://github.com/joao-lucas/jlvm
$ cd jlvm
$ chmod +x jlvm.sh
$ ./jlvm
```

# Author
João Lucas <joaolucas@linuxmail.org>
