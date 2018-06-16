*¿Qué comando utilizaste en el paso 11? ¿Por qué?*

	git reset --hard HEAD~1

	Porque le tengo que indicar --hard para que git me permita dejar como estaba antes el working copy (perdiendo los cambios en el mismo)

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

  	Primero git reflog e identifico el primer commit de la rama styled que es el que hemos deshecho

1b79f9f (HEAD -> styled, master) HEAD@{0}: reset: moving to HEAD~1
582cd02 HEAD@{1}: commit: Commit 2 - Rama styled - git nuestro con estilo
1b79f9f (HEAD -> styled, master) HEAD@{2}: checkout: moving from master to styled
1b79f9f (HEAD -> styled, master) HEAD@{3}: commit (initial): Commit 1 - Rama Master - Commit inicial git nuestro

        Luego lo rehago con:

	git reset 582cd02

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
  git merge master
	No generó ningún conflicto porque la rama styled ya tiene todos los cambios de master
	Devuelve :
	Already up to date.

- El merge del paso 19, ¿Causó algún conflicto? ¿Porqué?

	Si causó conflictos porque el fichero git-nuestro.md ha sido
  modificado en las mismas lineas en la rama htmlify que en styled, que son ramas bifurcadas (en styled no está el trabajo de htmlify).
  Hemos de revisar el código y hacer el commit para resolver el conflicto.

- El merge del paso 21, ¿Causó algún conflicto? ¿Porqué?

No causó conflicto, es un fast forward porque las ramas se pueden apilar con lo que se mueve HEAD->master al último commit de styled.

- ¿Qué comando o comandos utilizaste en el paso 25?

   git log --graph --decorate --pretty=oneline

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

  Si podría ser fast-forward ya que es su padre y todo el trabajo de master está en title, basta con apuntar el HEAD en master al último commit con el cambio en el que incluimos el titulo.gi

- ¿Qué comando o comandos utilizaste en el paso 27?

  git reset HEAD~1

  No uso la opción hard para no perder los cambios del working copy.

- ¿Qué comando o comandos utilizaste en el paso 28?

  git reset --hard HEAD

  Descartamos los cambios en el working copy pero nos quedamos en el commit actual.

- ¿Qué comando o comandos utilizaste en el paso 29?

Si intento usar:

git branch -d title
error: The branch 'title' is not fully merged.
If you are sure you want to delete it, run 'git branch -D title'.

No me deja porque está más avanzada que master --> recurro a:

git branch -D title

git branch -D title
Deleted branch title (was 54d4e5b).

- ¿Qué comando o comandos utilizaste en el paso 30?

git reflog para localizar el commit donde se hizo el merge de title
git reset --hard 552c586 para rehacerlo

- ¿Qué comando o comandos usaste en el paso 32?

git log
git reset --hard 1b79f9f

- ¿Qué comando o comandos usaste en el punto 33?

git reflog
git reset --hard 54d4e5b

