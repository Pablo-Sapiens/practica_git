# práctica Git & GitHub
Bootcamp : Big Data, AI & Machine Learning XIV
Profesor : Alberto Casero

En este repositorio se realizan una serie de operaciones desde la consola de comandos. A continucación se responden a las siguientes preguntas:

## ¿Qué comando utilizaste en el paso 11? ¿Por qué?

git reset --hard HEAD~1 : Este comando te permite deshacer el último commit perdiendo lso cambios realizados en el working copy. 

## ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

Para rehacer el commit ejecuto git reset <commit> (miro el commit en reflog) : esto mueve el puntero HEAD y la rama al commit C. Ahora git status me notifica cambios pendientes de meter al staging área y commitear al repositorio.

La opción git reset --hard <hash_commit> también es válida. 

## El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
Es un merge fast forward porque los commits son lineales. No se crea conflicto porque el historial de commits es lineal. ejecuto git merge main y no tendré notificación en git status

## El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

Al hacer el merge es no fast forward porque son ramas diferentes que no son lineales, es decir, el commit donde está la rama main es el padre de los commits de ambas ramas. 
Estas ramas tienen el mismo archivo modificado (en las mismas líneas), por lo que genera un conflicto que tengo que resolver.

## El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
Con este merge se mueve el pnutero main a styled. No hay conflictos porque he mergeado antes htmlife desde styled, por lo que los commits son lineales. es un merge fast forwad (No se genera commit por defecto)

## ¿Qué comando o comandos utilizaste en el paso 25?

Dibujar diagrama : git log --graph --decorate --pretty=oneline
posibilidad de configuras un alias de este comando : 
git log --graph --decorate --pretty=oneline

## El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

No podría ser fast forward porque la rama title tiene un commit realizado.

## ¿Qué comando o comandos utilizaste en el paso 27?
deshacer merge sin perder cambios en working copy: git reset HEAD~1. Los cambios ahora aparecen en git status para traquearlos al staging área y decidir si los descrto o no.

## ¿Qué comando o comandos utilizaste en el paso 28?

descartar los cambios que aparecen en git status: git restore git-nuestro. Ahora tengo el archivo sin el título xq he decartado los cambios.

## ¿Qué comando o comandos utilizaste en el paso 29?

eliminar la rama title: git branch -d title. La rama no está totalmente mergeada (ejecutar git branch -D title) .Si elimino la rama dejaré un commit descolgado (sin rama) pero no me preocupa porque siempre puedo recuperarlo desde reflog.

## ¿Qué comando o comandos utilizaste en el paso 30?

Rehacer el merge para recuperar el título : para rehacer un merge que he desecho yo haría: git checkout al merge + crear una rama temporal+ git add + git commit. Después git checkout a main + mergear la rama temporal. Eliminar la rama incial y cambiar el nombre a la rama temporal.

Sin embargo, es mucho mas sencillo hacer :  git reset --hard <commit> para dejarlo todo tal y como estaba después de hacer el merge que deshice. El commit lo veo en el reflog

## ¿Qué comando o comandos usaste en el paso 32?

Para mover el puntero HEAD uso git checkout <commit>. Imoprtante, este comando no mueve la rama, solo HEAD y me cambia el contenido en el working copy según el commit.

## ¿Qué comando o comandos usaste en el punto 33?

git reset hard~1 y volvemos al commit anterior que aparece en git log,  Si hago esto, git se salta un commit siguiendo la secuencia de commits en git log. porque toma el último commit antes del merge. Es decir, el commit padre al que pertence la rama que se ha mergeado.
Por lo tanto, el comando que hay que ejecutar es git reset hard <commit>


