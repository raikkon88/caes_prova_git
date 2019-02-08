# Git repository for first Practice (PDS)

>> Author : Marc Sànchez Pifarré
>> Teacher : Ignacio Clemente Martín Campos

## Introduction

This repository has been created to show my git domain to the teacher.

## Transcendence

This repository has no transcendence for programmers, is only a degree work.

## Commands done

```
$ mkdir caes_prova_git
$ cd caes_prova_git/
```

### Block 1

```
$ git init
S'ha inicialitzat un dipòsit buit del Git en /home/marc/projects/caes_prova_git/.git/
$ touch A.txt
$ git add A.txt
$ git commit -m "[FC] Initial File"
[master (comissió d'arrel) 8cf5f68] [FC] Initial File
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 A.txt
$ touch B.txt
$ git add B.txt
$ git commit -m "[FC] Initial File"
[master 9807f6d] [FC] Initial File
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 B.txt
 $ git status
En la branca master
no hi ha res a cometre, l'arbre de treball està net
```

### Block 2

```
$ echo "This is the first change to A file" >> A.txt
$ echo "This is the first change to B file" >> B.txt
$ git status
En la branca master
Canvis no «staged» per a cometre:
  (useu "git add <fitxer>..." per a actualitzar què es cometrà)
  (useu "git checkout -- <fitxer>..." per a descartar els canvis en el directori de treball)

	modificat:        A.txt
	modificat:        B.txt
	modificat:        README.md

no hi ha canvis afegits a cometre (useu "git add" o "git commit -a")
$ git add -A
$ git commit -m "[FEAT] Added first changes to files A and B"
[master 356bd4f] [FEAT] Added first changes to files A and B
 3 files changed, 33 insertions(+)
```

### Block 3

```
$ git checkout -b branca1
S'ha canviat a la branca nova «branca1»
$ touch C.txt
$ git add C.txt
$ git commit -m "[FEAT] Initial File"
[branca1 e15596f] [FEAT] Initial File
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 C.txt
$ git status
En la branca branca1
no hi ha res a cometre, l'arbre de treball està net
$ echo "canvi C1 branca1" >> C.txt
$ git add -A
$ git status
En la branca branca1
Canvis a cometre:
  (useu "git reset HEAD <fitxer>..." per a fer «unstage»)

	modificat:        C.txt

$ git commit -m "[FEAT] Added text to file C"
[branca1 695f795] [FEAT] Added text to file C
 1 file changed, 1 insertion(+)
```

### Block 4

```
$ git checkout master
$ git checkout -b branca2
$ touch D.txt
$ git add D.txt
$ git commit -m "[FEAT] Initial File"
$ echo "canvi D1 branca 2" >> D.txt
$ git add D.txt
$ git commit -m "[FEAT] Added text to file D"
```
