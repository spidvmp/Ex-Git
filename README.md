¿Qué comando utilizaste en el paso 11? ¿Por qué?
git reset --hard HEAD~1

reset HEAD~1 lo usamos para irnos al nodo anterios, por lo que nos quedamos con la version anterior y el parametro hard para que no guarde los cambios que hice, asi que "he perdido" los colores hexadecimales

¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
primero hay que localizar cual es el hash del nodo a encontrar, que es en el que cambiabamos los colores a hexadecimal. con git reflog vemos todos los logs ordenados descendentemente. En nuestro caso deberiamos irnos al anterior del reset que sera HEAD@{1} para recuperar el nodo y quedarnos como su hubiera sido el ultimo commit (que lo es) hay que mover la rama htmlify a ese nodo
git reset —hard hash del nodo

El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
No ha creado conflictos. No hay conflicto porque no se han modificado las mismas lineas en el mismo fichero. cuando se creo la rama htmlify, ya venia con los colores de red y blue, y cuando se cambiaron a hexadecimal es un cambio queno choca con blue ni red, que ya estaban antes y simultaneamente en master no se han cambiado por otros diferente

El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
Si. A diferencia del merge de la pregunta 13, htmlify viene con los cambios de master, pero a su vez en la rama matrix se estan cambiando las mismas lineas, por lo que del “Roses are red” pasamos a “Red pills” en lugar de Roses y “#ff0000” en lugar de red, asi que no se sabe que cambio es el que nos vale, si las pills o los hexadecimales

El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
No. Los cambios que han habido en las ramas se han resuelto con un merge y se resolvio el conflicto. Ahora solo se ha hecho un fast-forward y solo ha movido el puntero de master al mismo commit del htmlify

¿Qué comando o comandos utilizaste en el paso 25?
git log —graph —decorate

El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
Si. El arbol es lineal, asi quelo unico que se hace seria mover el puntero de title hacia master

¿Qué comando o comandos utilizaste en el paso 27?
git reset HEAD~1

¿Qué comando o comandos utilizaste en el paso 28?
git checkout — poem.md

¿Qué comando o comandos utilizaste en el paso 29?
git branch -D title

¿Qué comando o comandos utilizaste en el paso 30?
busco el nodo que fue el merge con git reflog y luego
git  reset —hard hash nodo

¿Qué comando o comandos usaste en el paso 32?
con git reflog busco el hash del commit inicial y despues git checkout hash

¿Qué comando o comandos usaste en el punto 33?
git checkout master (esta rama no la hemos borrado, solo el resto)
