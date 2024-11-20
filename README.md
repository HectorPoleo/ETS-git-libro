# ETS-git-libro
Trabajando con log/branch y el HEAD en git
Ejercicio 1

   git log
   commit 26e674563fe66c6be68ab4a9223134592a3491c5 (HEAD -> main, origin/main, origin/HEAD)
   Author: HectorPoleo <hectorpoleo2007@gmail.com>
   Date:   Thu Oct 10 17:55:55 2024 +0100

   Initial commit

   cat capitulos/capitulo1.txt
   Git es un sistema de control de versiones ideado por Linus Torvalds.

   git add .

git commit -m "Añadido capítulo 1."
[main 850c7cf] Añadido capítulo 1.
 2 files changed, 26 insertions(+), 1 deletion(-)
 create mode 100644 capitulos/capitulo1.txt

git log
commit 850c7cfd0ac53be5886c460fdc7f84a0273af053 (HEAD -> main)
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Thu Oct 10 18:30:24 2024 +0100

    Añadido capítulo 1.

commit 26e674563fe66c6be68ab4a9223134592a3491c5 (origin/main, origin/HEAD)
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Thu Oct 10 17:55:55 2024 +0100

    Initial commit

Ejercicio 2

cat capitulos/capitulo2.txt 
El flujo de trabajo básico con Git consiste en:
 1- Hacer cambios en el repositorio.
 2- Añadir los cambios a la zona de intercambio temporal.
 3- Hacer un commit de los cambios.

git add .

git commit -m "Añadido capítulo 2"
[main a9c6e13] Añadido capítulo 2
 2 files changed, 45 insertions(+)
 create mode 100644 capitulos/capitulo2.txt

git log
commit a9c6e13733c44e3525cd733f33f8c580c48e5379 (HEAD -> main)
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Thu Oct 10 18:40:09 2024 +0100

    Añadido capítulo 2

commit 850c7cfd0ac53be5886c460fdc7f84a0273af053
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Thu Oct 10 18:30:24 2024 +0100

    Añadido capítulo 1.

commit 26e674563fe66c6be68ab4a9223134592a3491c5 (origin/main, origin/HEAD)
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Thu Oct 10 17:55:55 2024 +0100

    Initial commit

Ejercicio 3

cat capitulos/capitulo3.txt 
Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultanea en ellas.

git add .

git commit -m "Añadido capítulo 3"
[main 2492158] Añadido capítulo 3
 2 files changed, 31 insertions(+)
 create mode 100644 capitulos/capitulo3.txt
adrianssd@adrianssd:~/Descargas/ejercicio-git-libro$ git log
commit 249215813daf01873e368a37c7915a720ecbd8c8 (HEAD -> main)
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Sun Oct 13 00:09:58 2024 +0100

    Añadido capítulo 3

commit a9c6e13733c44e3525cd733f33f8c580c48e5379
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Thu Oct 10 18:40:09 2024 +0100

    Añadido capítulo 2

commit 850c7cfd0ac53be5886c460fdc7f84a0273af053
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Thu Oct 10 18:30:24 2024 +0100

    Añadido capítulo 1.

commit 26e674563fe66c6be68ab4a9223134592a3491c5 (origin/main, origin/HEAD)
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Thu Oct 10 17:55:55 2024 +0100

    Initial commit

Ejercicio 4

cat capitulos/índice.txt 
Indice de los cápitulos, con conceptos avanzados de git

git add .

git commit -m "Se crea el indice."
[main 60dd9ad] Se crea el indice.
 2 files changed, 67 insertions(+)
 create mode 100644 "capitulos/\303\255ndice.txt"

git annotate índice.txt
60dd9adc        (AdrianRoguez   2024-10-13 00:19:57 +0100       1)Indice de los cápitulos, con conceptos avanzados de git

Ejercicio 5

git branch bibliografia

git branch -av
  bibliografia        e2c45b5 Añadido el índice
* main                e2c45b5 [adelante 1] Añadido el índice
  remotes/origin/HEAD -> origin/main
  remotes/origin/main 60dd9ad Se crea el indice.

Ejercicio 6

cat capitulos/capitulo4.txt 
En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto.

git add .

git commit -m "Añadido capítulo 4."
[main 59151c3] Añadido capítulo 4.
 2 files changed, 42 insertions(+)
 create mode 100644 capitulos/capitulo4.txt

git log --graph --all --oneline
* 59151c3 (HEAD -> main) Añadido capítulo 4.
* e2c45b5 (bibliografia) Añadido el índice
* 60dd9ad (origin/main, origin/HEAD) Se crea el indice.
* 2492158 Añadido capítulo 3
* a9c6e13 Añadido capítulo 2
* 850c7cf Añadido capítulo 1.
* 26e6745 Initial commit

Ejercicio 7

git checkout bibliografia 
Cambiado a rama 'bibliografia'

cat bibliografia.txt 
Chacon, S. and Straub, B. Pro Git. Apress.

git add .

git commit -m "Añadida primera referencia bibliográfica."
[bibliografia 72661bc] Añadida primera referencia bibliográfica.
 2 files changed, 5 insertions(+), 2 deletions(-)
 create mode 100644 bibliografia.txt

git log --graph --all --oneline
* 72661bc (HEAD -> bibliografia) Añadida primera referencia bibliográfica.
* 14839ab (origin/main, origin/HEAD, main) Se realiza un commit con los cambios del README.txt para cambiar de rama
* 59151c3 Añadido capítulo 4.
* e2c45b5 Añadido el índice
* 60dd9ad Se crea el indice.
* 2492158 Añadido capítulo 3
* a9c6e13 Añadido capítulo 2
* 850c7cf Añadido capítulo 1.
* 26e6745 Initial commit

Ejercicio 8

git checkout main 
Cambiado a rama 'main'
Tu rama está actualizada con 'origin/main'.

git merge bibliografia
Merge made by the 'ort' strategy.
 bibliografia.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 bibliografia.txt

git log --graph --all --oneline
*   8d601d4 (HEAD -> main) Merge branch 'bibliografia'
|\  
| * 7a3fff9 (bibliografia) Se vuelve a realiza un commit con los cambios del README.txt para cambiar de rama
| * 72661bc Añadida primera referencia bibliográfica.
* | 7c9599a (origin/main, origin/HEAD) Perdiendo la cordura
|/  
* 14839ab Se realiza un commit con los cambios del README.txt para cambiar de rama
* 59151c3 Añadido capítulo 4.
* e2c45b5 Añadido el índice
* 60dd9ad Se crea el indice.
* 2492158 Añadido capítulo 3
* a9c6e13 Añadido capítulo 2
* 850c7cf Añadido capítulo 1.
* 26e6745 Initial commit

git branch -d bibliografia
Eliminada la rama bibliografia (era 7a3fff9).

git log --graph --all --oneline
*   8d601d4 (HEAD -> main) Merge branch 'bibliografia'
|\  
| * 7a3fff9 Se vuelve a realiza un commit con los cambios del README.txt para cambiar de rama
| * 72661bc Añadida primera referencia bibliográfica.
* | 7c9599a (origin/main, origin/HEAD) Perdiendo la cordura
|/  
* 14839ab Se realiza un commit con los cambios del README.txt para cambiar de rama
* 59151c3 Añadido capítulo 4.
* e2c45b5 Añadido el índice
* 60dd9ad Se crea el indice.
* 2492158 Añadido capítulo 3
* a9c6e13 Añadido capítulo 2
* 850c7cf Añadido capítulo 1.
* 26e6745 Initial commit

Ejercicio 9

git branch bibliografia

git checkout bibliografia
Cambiado a rama 'bibliografia'

cat bibliografia.txt 
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.

git add .

git commit -a -m "Añadida nueva referencia bibliográfica."
[bibliografia e539a91] Añadida nueva referencia bibliográfica.
 2 files changed, 8 insertions(+), 4 deletions(-)

git checkout main
Cambiado a rama 'main'
Tu rama está actualizada con 'origin/main'.

cat bibliografia.txt 
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.

git commit -a -m "Añadida nueva referencia bibliográfica."
[main 7274c06] Añadida nueva referencia bibliográfica.
 1 file changed, 2 insertions(+)

git merge bibliografia
Auto-fusionando bibliografia.txt
CONFLICTO (contenido): Conflicto de fusión en bibliografia.txt
Fusión automática falló; arregle los conflictos y luego realice un commit con el resultado.

cat bibliografia.txt 
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.
Hodson, R. Ry’s Git Tutorial. Smashwords (2014)

git commit -a -m "Solucionado conflicto bibliografía."
[main 65e6be2] Solucionado conflicto bibliografía.

git log --graph --all --oneline
*   65e6be2 (HEAD -> main) Solucionado conflicto bibliografía.
|\  
| * 16bab06 (origin/bibliografia, bibliografia) Se realiza otro commit para cambiar de rama en el Ejercicio 9
| * e539a91 Añadida nueva referencia bibliográfica.
* | 7274c06 Añadida nueva referencia bibliográfica.
|/  
* 928f6e6 (origin/main, origin/HEAD) Se realiza un commit antes de comenzar el Ejercicio 9
*   8d601d4 Merge branch 'bibliografia'
|\  
| * 7a3fff9 Se vuelve a realiza un commit con los cambios del README.txt para cambiar de rama
| * 72661bc Añadida primera referencia bibliográfica.
* | 7c9599a Perdiendo la cordura
|/  
* 14839ab Se realiza un commit con los cambios del README.txt para cambiar de rama
* 59151c3 Añadido capítulo 4.
* e2c45b5 Añadido el índice
* 60dd9ad Se crea el indice.
* 2492158 Añadido capítulo 3
* a9c6e13 Añadido capítulo 2
* 850c7cf Añadido capítulo 1.
* 26e6745 Initial commit
