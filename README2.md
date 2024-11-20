Ejercicio 1

git tag -a v1.0 -m "Versión 1.0"

git push origin --tags
Username for 'https://github.com': HectorPoleo
Password for 'https://HectorPoleo@github.com': 
Enumerando objetos: 13, listo.
Contando objetos: 100% (13/13), listo.
Compresión delta usando hasta 4 hilos
Comprimiendo objetos: 100% (9/9), listo.
Escribiendo objetos: 100% (9/9), 1.86 KiB | 475.00 KiB/s, listo.
Total 9 (delta 1), reusados 0 (delta 0), pack-reusados 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/HectorPoleo/ejercicio-git-libro
 * [new tag]         v1.0 -> v1.0

git tag v1.0

Ejercicio 2

sudo nano capitulo1.txt

git add capitulo1.txt

git commit -m "Agregada una línea en capítulo 1"
[main 095d5fc] Agregada una línea en capítulo 1
1 file changed, 1 insertion(+)

git revert HEAD
[main bcf58a8] Revert "Revierte el último commit"
1 file changed, 1 deletion(-)

git log --oneline
bcf58a8 (HEAD -> main) Revert "Revierte el último commit"
095d5fc Agregada una línea en capítulo 1
7f26bf4 (tag: v1.0, origin/main, origin/HEAD) Fin

Ejercicio 3

git checkout -b nueva-funcionalidad
Cambiado a nueva rama 'nueva-funcionalidad'

echo "En este capítulo veremos cómo gestionar múltiples ramas en Git." > capitulo5.txt

git add capitulo5.txt

git commit -m "Agregar capítulo 5 sobre gestión de ramas"
[nueva-funcionalidad 88f2991] Agregar capítulo 5 sobre gestión de ramas
1 file changed, 1 insertion(+)
create mode 100644 capitulos/capitulo5.txt

git checkout main
Cambiado a rama 'main'

git log --oneline nueva-funcionalidad
88f2991 (nueva-funcionalidad) Agregar capítulo 5 sobre gestión de ramas
bcf58a8 (HEAD -> main) Revert "Revierte el último commit"
095d5fc Agregada una línea en capítulo 1
7f26bf4 (tag: v1.0, origin/main, origin/HEAD) Fin

git cherry-pick 88f2991
[main f568cd6] Agregar capítulo 5 sobre gestión de ramas
Date: Wed Oct 23 16:16:46 2024 +0100
1 file changed, 1 insertion(+)
create mode 100644 capitulos/capitulo5.txt

git log --oneline
f568cd6 (HEAD -> main) Agregar capítulo 5 sobre gestión de ramas
bcf58a8 Revert "Revierte el último commit"
095d5fc Agregada una línea en capítulo 1
7f26bf4 (tag: v1.0, origin/main, origin/HEAD) Fin

Ejercicio 4

nano README.md

git add README.md

git commit -m "Agregar una breve descripción en README.md"
[main 84e69a2] Agregar una breve descripción en README.md
1 file changed, 5 insertions(+), 1 deletion(-)

git diff main nueva-funcionalidad
diff --git a/README.md b/README.md
index 1429575..d6dd642 100644
--- a/README.md
+++ b/README.md
@@ -368,8 +368,4 @@ git log --graph --all --oneline
* a9c6e13 Añadido capítulo 2
* 850c7cf Añadido capítulo 1.
* 26e6745 Initial commit
-``` 
- - - -
-##Pequeño cambio
+```
\ No newline at end of file

Ejercicio 5

echo "Este es un cambio en la rama main." >> capitulo2.txt

git add capitulo2.txt

git commit -m "Modificado capitulo2.txt en la rama main"
[main 4581503] Modificado capitulo2.txt en la rama main
1 file changed, 1 insertion(+)

git checkout nueva-funcionalidad
Cambiado a rama 'nueva-funcionalidad'

echo "Este es un cambio en la rama nueva-funcionalidad." >> capitulo2.txt

git add capitulo2.txt

git commit -m "Modificado capitulo2.txt en la rama nueva-funcionalidad"
[nueva-funcionalidad e345998] Modificado capitulo2.txt en la rama nueva-funcionalidad
1 file changed, 1 insertion(+)

git checkout main
Cambiado a rama 'main'

git merge nueva-funcionalidad
Auto-fusionando capitulo2.txt
CONFLICTO (agregar/agregar): Conflicto de fusión en capitulo2.txt
Fusión automática falló; arregle los conflictos y luego realice un commit con el resultado.

sudo nano capitulo2.txt

git add capitulo2.txt

git commit -m "Resolver conflicto de fusión entre main y nueva-funcionalidad"
[main 59dbd83] Resolver conflicto de fusión entre main y nueva-funcionalidad

git log --oneline
59dbd83 (HEAD -> main) Resolver conflicto de fusión entre main y nueva-funcionalidad
e345998 (nueva-funcionalidad) Modificado capitulo2.txt en la rama nueva-funcionalidad
4581503 Modificado capitulo2.txt en la rama main
84e69a2 Agregar una breve descripción en README.md
f568cd6 Agregar capítulo 5 sobre gestión de ramas
88f2991 Agregar capítulo 5 sobre gestión de ramas
bcf58a8 Revert "Revierte el último commit"
095d5fc Agregada una línea en capítulo 1
7f26bf4 (tag: v1.0, origin/main, origin/HEAD) Fin

Ejercicio 6

git checkout nueva-funcionalidad
Cambiado a rama 'nueva-funcionalidad'

echo "Esta es una nueva funcionalidad." > funcionalidad.txt

git add funcionalidad.txt

git commit -m "Añadir nueva funcionalidad"
[nueva-funcionalidad 26992e5] Añadir nueva funcionalidad
1 file changed, 1 insertion(+)
create mode 100644 funcionalidad.txt

git checkout main
Cambiado a rama 'main'
Tu rama está actualizada con 'origin/main'

echo "Este es el archivo principal." > main.txt

git add main.txt

git commit -m "Añadir archivo principal"
[main b696cd3] Añadir archivo principal
1 file changed, 1 insertion(+)
create mode 100644 main.txt

git checkout nueva-funcionalidad
Cambiado a rama 'nueva-funcionalidad'

echo "Más detalles sobre la funcionalidad." >> funcionalidad.txt

git add funcionalidad.txt

git commit -m "Actualizar funcionalidad"
[nueva-funcionalidad 7218afd] Actualizar funcionalidad
1 file changed, 1 insertion(+)

git checkout main
Cambiado a rama 'main'

git merge nueva-funcionalidad
Merge made by the 'ort' strategy.
funcionalidad.txt | 2 ++
1 file changed, 2 insertions(+)
create mode 100644 funcionalidad.txt

git log
commit c76a24046b3161e66bf5bc25da4ab227031f5066 (HEAD -> main)
Merge: b696cd3 7218afd
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Wed Oct 23 18:09:15 2024 +0100
    Merge branch 'nueva-funcionalidad'

commit 7218afd9c9345b8fd3c3b3ec70323f98e9d49bc5 (nueva

Ejercicio 7

git tag -d v1.0
Etiqueta 'v1.0' eliminada (era 8c03415)

git push origin :refs/tags/v1.0
Username for 'https://github.com': HectorPoleo
Password for 'https://HectorPoleo@github.com': 
To https://github.com/HectorPoleo/ejercicio-git-libro
 - [deleted]         v1.0

git tag

Ejercicio 8

echo "Este es un nuevo archivo" > nuevo-archivo.txt

git add nuevo-archivo.txt

git commit -m "Añadir nuevo archivo"
[main 271680f] Añadir nuevo archivo
 1 file changed, 1 insertion(+)
 create mode 100644 nuevo-archivo.txt

git reset --hard HEAD~1
HEAD está ahora en d343265 Revert "Merge branch 'nueva-funcionalidad'"

git status
En la rama main
Tu rama está actualizada con 'origin/main'.

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que será confirmado)
	Ejercicio6.txt

no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)

git log
commit d3432650e95549ab7d2ad417c5111768e2fd8556 (HEAD -> main, origin/main, origin/HEAD)
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Wed Oct 23 18:11:58 2024 +0100

    Revert "Merge branch 'nueva-funcionalidad'"
    
    This reverts commit c76a24046b3161e66bf5bc25da4ab227031f5066, reversing
    changes made to b696cd36b6c73e41832509b2eef7d6661b570008.

commit c76a24046b3161e66bf5bc25da4ab227031f5066
Merge: b696cd3 7218afd
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Wed Oct 23 18:09:15 2024 +0100

    Merge branch 'nueva-funcionalidad'

commit 7218afd9c9345b8fd3c3b3ec70323f98e9d49bc5 (nueva-funcionalidad)
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Wed Oct 23 18:08:55 2024 +0100

    Actualizar funcionalidad

commit b696cd36b6c73e41832509b2eef7d6661b570008
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Wed Oct 23 18:08:26 2024 +0100

    Añadir archivo principal

commit 26992e5d1955528c6678d4469d5f3593361c3396
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Wed Oct 23 18:07:27 2024 +0100

    Añadir nueva funcionalidad

commit d2157f54b528f16a7b1ab78ef92f2622c38d02f5
Merge: 59dbd83 b2a3ea6
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Wed Oct 23 16:58:37 2024 +0100

    Merge branch 'main' of https://github.com/HectorPoleo/ejercicio-git-libro

commit 59dbd83cccf4f4b66e6029175f1f2229c090908e
Merge: 4581503 e345998
Author: HectorPoleo <hectorpoleo2007@gmail.com>
Date:   Wed Oct 23 16:40:46 2024 +0100
