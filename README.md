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
[branca2 72d39c6] [FEAT] Initial File
 1 file changed, 1 insertion(+)
 create mode 100644 D.txt
$ echo "canvi D1 branca 2" >> D.txt
$ git add D.txt
$ git commit -m "[FEAT] Added text to file D"
[branca2 b8729c3] [FEAT] Added text to file D
 1 file changed, 1 insertion(+)
```

### Block 5

```
$ git branch
  branca1
* branca2
  master
$ git checkout branca1
S'ha canviat a la branca «branca1»
$ git merge branca2
Merge made by the 'recursive' strategy.
 D.txt     |  2 ++
 README.md | 63 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++-
 2 files changed, 64 insertions(+), 1 deletion(-)
 create mode 100644 D.txt
```

At this point nano editor has been opened by default to put a comment for the extra commit done by merge.

```
$ git checkout master
S'ha canviat a la branca «master»
$ git merge branca1
S'estan actualitzant 356bd4f..b9f3b3a
Fast-forward
 C.txt     |  1 +
 D.txt     |  2 ++
 README.md | 63 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++-
 3 files changed, 65 insertions(+), 1 deletion(-)
 create mode 100644 C.txt
 create mode 100644 D.txt
```

### Block 6

```
$ git checkout master
Ja en «master»
$ touch E.txt
$ git add E.txt
$ git commit -m "[FEAT] Initial File"
[master 15f5a44] [FEAT] Initial File
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 E.txt
$ git checkout -b branca3
S'ha canviat a la branca nova «branca3»
$ git status
En la branca branca3
no hi ha res a cometre, l'arbre de treball està net
$ echo "canvia E1 branca 3" >> E.txt
$ git add E.txt
$ git commit -m "[FEAT] Added text to E"
[branca3 c5f3809] [FEAT] Added text to E
 1 file changed, 1 insertion(+)
$ git checkout master
S'ha canviat a la branca «master»
$ git checkout -b branca4
S'ha canviat a la branca nova «branca4»
$ echo "canvia E1 branca 4" >> E.txt
$ git add E.txt
$ git commit -m "[FEAT] Adding text to file E"
[branca4 2d462fa] [FEAT] Adding text to file E
 1 file changed, 1 insertion(+)
$ git checkout master
S'ha canviat a la branca «master»
$ git merge branca3
S'estan actualitzant 15f5a44..c5f3809
Fast-forward
 E.txt | 1 +
 1 file changed, 1 insertion(+)
$ git merge branca4
S'està autofusionant E.txt
CONFLICTE (contingut): Conflicte de fusió en E.txt
La fusió automàtica ha fallat; arregleu els conflictes i després cometeu el resultat.
$ git status
En la branca master
Teniu camins sense fusionar.
  (arregleu els conflictes i executeu "git commit")
  (useu "git merge --abort" per a avortar la fusió)

Camins sense fusionar:
  (useu "git add <fitxer>..." per a senyalar resolució)

	modificat per ambdós:   E.txt

no hi ha canvis afegits a cometre (useu "git add" o "git commit -a")
```

As spected a conflict has appeared, to resolve the conflict will open the file with a text editor and will conserve both changes.

```
$ nano E.txt
$ cat E.txt
canvia E1 branca 3
canvia E1 branca 4
$ git add -A
$ git commit -m "[FEAT] Solved conflicts in E file, README updated with blocks 5 and 6"
[master cff2e7b] [FEAT] Solved conflicts in E file, README updated with blocks 5 and 6
```

### Block 7

Changing to master and showing actual branches...

```
$ git checkout master
$ git branch
  branca1
  branca2
  branca3
  branca4
* master
```

At this point we will undo a commit.

```
$ echo "Canvi A2" >> A.txt
$ git add A.txt
$ git commit -m "[FEAT] Another change to A file"
[master f6f7963] [FEAT] Another change to A file
 1 file changed, 1 insertion(+)
$ git log --oneline
 f6f7963 (HEAD -> master) [FEAT] Another change to A file
 cff2e7b [FEAT] Solved conflicts in E file, README updated with blocks 5 and 6
 2d462fa (branca4) [FEAT] Adding text to file E
 c5f3809 (branca3) [FEAT] Added text to E
 15f5a44 [FEAT] Initial File
 b9f3b3a (branca1) Merge branch 'branca2' into branca1
 97e1db4 (branca2) [FEAT] Added documentation for blocks 1 - 4
 b8729c3 [FEAT] Added text to file D
 72d39c6 [FEAT] Initial File
 695f795 [FEAT] Added text to file C
 e15596f [FEAT] Initial File
 356bd4f [FEAT] Added first changes to files A and B
 5db6ab6 [FEAT] adding documentation for project
 9807f6d [FC] Initial File
 8cf5f68 [FC] Initial File
```

As we are working on branch master we can undo this commit using two strategies.

The first one is using git revert, which will create a new commit with the changes made as an inverted way, it means changes will be persisted on our branch history.

The second way is using git reset which will erase commit from which we execute the command to target where will make the reset. Must be carefull with merges.

I will choose git reset strategy.

```
$ git reset --hard cff2e7b
HEAD ara és a cff2e7b [FEAT] Solved conflicts in E file, README updated with blocks 5 and 6
$ git log --oneline
cff2e7b (HEAD -> master) [FEAT] Solved conflicts in E file, README updated with blocks 5 and 6
2d462fa (branca4) [FEAT] Adding text to file E
c5f3809 (branca3) [FEAT] Added text to E
15f5a44 [FEAT] Initial File
b9f3b3a (branca1) Merge branch 'branca2' into branca1
97e1db4 (branca2) [FEAT] Added documentation for blocks 1 - 4
b8729c3 [FEAT] Added text to file D
72d39c6 [FEAT] Initial File
695f795 [FEAT] Added text to file C
e15596f [FEAT] Initial File
356bd4f [FEAT] Added first changes to files A and B
5db6ab6 [FEAT] adding documentation for project
9807f6d [FC] Initial File
8cf5f68 [FC] Initial File
```

### Block 8

```
$ echo "Canvi A3" >> A.txt
$ git add A.txt
$ git commit -m "[FEAT] Adding text to A"
[master e64908a] [FEAT] Adding text to A
 1 file changed, 1 insertion(+)
$ echo "Canvi B2" >> B.txt
$ git add B.txt
$ git commit -m "[FEAT] Adding text to B"
[master 231a6cd] [FEAT] Adding text to B
 1 file changed, 1 insertion(+)
$ echo "Canvi C1" >> C.txt
$ git add C.txt
$ git commit -m "[FEAT] Adding text to C"
[master 2a85ff9] [FEAT] Adding text to C
 1 file changed, 1 insertion(+)
 ```

Now I will take the revert strategy to undo only the change made by commit 231a6cd that stands for the change in B file.

```
$ git log --oneline
49016af (HEAD -> master) [FEAT] Adding block 8
2a85ff9 [FEAT] Adding text to C
231a6cd [FEAT] Adding text to B
e64908a [FEAT] Adding text to A
cff2e7b [FEAT] Solved conflicts in E file, README updated with blocks 5 and 6
2d462fa (branca4) [FEAT] Adding text to file E
c5f3809 (branca3) [FEAT] Added text to E
15f5a44 [FEAT] Initial File
b9f3b3a (branca1) Merge branch 'branca2' into branca1
97e1db4 (branca2) [FEAT] Added documentation for blocks 1 - 4
b8729c3 [FEAT] Added text to file D
72d39c6 [FEAT] Initial File
695f795 [FEAT] Added text to file C
e15596f [FEAT] Initial File
356bd4f [FEAT] Added first changes to files A and B
5db6ab6 [FEAT] adding documentation for project
9807f6d [FC] Initial File
8cf5f68 [FC] Initial File

$ git revert 231a6cd
[master d2e67c4] Revert "[FEAT] Adding text to B"
 1 file changed, 1 deletion(-)

 $ git log --oneline
 d2e67c4 (HEAD -> master) Revert "[FEAT] Adding text to B"
 49016af [FEAT] Adding block 8
 2a85ff9 [FEAT] Adding text to C
 231a6cd [FEAT] Adding text to B
 e64908a [FEAT] Adding text to A
 cff2e7b [FEAT] Solved conflicts in E file, README updated with blocks 5 and 6
 2d462fa (branca4) [FEAT] Adding text to file E
 c5f3809 (branca3) [FEAT] Added text to E
 15f5a44 [FEAT] Initial File
 b9f3b3a (branca1) Merge branch 'branca2' into branca1
 97e1db4 (branca2) [FEAT] Added documentation for blocks 1 - 4
 b8729c3 [FEAT] Added text to file D
 72d39c6 [FEAT] Initial File
 695f795 [FEAT] Added text to file C
 e15596f [FEAT] Initial File
 356bd4f [FEAT] Added first changes to files A and B
 5db6ab6 [FEAT] adding documentation for project
 9807f6d [FC] Initial File
 8cf5f68 [FC] Initial File
```
