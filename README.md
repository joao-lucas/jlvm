[![GitHub issues](https://img.shields.io/github/issues/joao-lucas/jlvm.svg?style=plastic)](https://github.com/joao-lucas/jlvm/issues)
[![GitHub forks](https://img.shields.io/github/forks/joao-lucas/jlvm.svg?style=plastic)](https://github.com/joao-lucas/jlvm/network)
[![GitHub stars](https://img.shields.io/github/stars/joao-lucas/jlvm.svg?style=plastic)](https://github.com/joao-lucas/jlvm/stargazers)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg?style=plastic)](https://raw.githubusercontent.com/joao-lucas/jlvm/master/LICENSE)


# JLVM - Joao Logical Volume Manager

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



## Esquema de funcionamento do LVM
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

## Clonando o projeto e utilizando o script
```
$ git clone https://github.com/joao-lucas/jlvm
$ cd jlvm
$ chmod +x jlvm.sh
# ./jlvm.sh     # Executar o script como root

```

## Menu principal
![1](https://github.com/joao-lucas/jlvm/blob/master/screenshots/1.png)

## Criando volume fisico
![2](https://github.com/joao-lucas/jlvm/blob/master/screenshots/2.png)

## Removendo volume fisico
![3](https://github.com/joao-lucas/jlvm/blob/master/screenshots/3.png)

## Criando grupo de volume
![4](http://url/to/4.png)

## Removendo volume fisico de um grupo de volume
![alt tag](http://url/to/5.png)

## Removendo todo um grupo de volume
![6](http://url/to/6.png)

## Estendendo um grupo de volume
![7](http://url/to/7.png)

## Criando um volume logico
![8](http://url/to/8.png)

## Estendendo um volume logico
![9](http://url/to/9.png)

## Diminuindo um volume logico
![alt tag](http://url/to/10.png)

## Removendo um volume logico
![11](http://url/to/11.png)



## Atenção
Ao utilizar esse script é imprescindível conhecimento em sistemas de arquivos, criar partições, manter a integridade do sistema de arquivo, montagen e desmontagem de sistemas de arquivos. Deve-se saber usar comandos como: 

* fdisk
* parted
* gdisk
* mkfs
* mount
* umount
* e2fsck
* df
* du
* mke2fs
* dumpe2fs
* tune2fs
* debugfs

## Tome muito cuidado quando esta trabalhando com sistema de arquivos, caso você faça alguma coisa errada, pode perder todos seus dados.

## Autor
João Lucas <<joaolucas@linuxmail.org>>
