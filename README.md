# HOgit
Repositorio con ejercicios para practicar comandos básicos de git

## Qué podemos hacer

### Commits
Modificar un archivo y agregarlo al repositorio como un nuevo commit

### Branches
Creamos un branch acerca de las charlas, y decimos que nos parecen buenísimas
Pasos con los que armamos el repo de github de HOgit.


## Cómo creamos este repositorio

Inicialmente estaba creado en github (desde la WEB) con 
sólo un README. EN cualquier lugar pueden (y deberían!)
correr `git status` y `git branch -a` para chequear
en qué estado está el repositorio y en qué branch están:


Clonamos un repositorio de github con sólo un README

```
git clone https://github.com/wtpc/HOgit.git
cd HOgit
```

Editamos el archivo de README y hacemos un nuevo commit

```
vi README.md
.........
git add README.md
git commit
```

Ya hay un nuevo snapshot. Ahora creamos una branch

```
git branch charlas
```

y nos movemos a ella

```
git checkout charlas
```

en esta branch, editamos README.md de nuevp

```
vi README.md
...
git add README.md
git commit
```

ahora vamos a master (que no tiene estos cambios, porque es otra branch!)

```
git checkout master
```

y a partir de master creamos una nueva branch

```
git branch ejercicios
git checkout ejercicios
```

editamos un archivo nuevo, ejercicios.md

```
vi ejercicios.md
...
git add ejercicios.md
git commit
```

Y ahora, en master, hacemos un merge de ambas branches por separado:
(fíjense que no importa que el orden sea el mismo que en el que 
las modificamos. es sensato porque las branches no se comunican)

```
git merge --no-ff ejercicios
git merge --no-ff charlas
```

la opción --no-ff sirve para que no "mezcle" las dos branches, y queda más prolijo el network. recomienod que la usen siempre, pero no es fundamental.

si quieren ver cómo quedó la historia del repo:

```
git log --oneline --graph
```

finalmente, hacemos un push de todas las branches:

```
git push -u origin master
git push -u origin ejercicios
git push -u origin charlas
```

y listo! en nuestra cuenta de github ya tiene que estar subido. pueden ver el network de github que les va a mostrar la historia

Luego también editamos este readme para agregar los comandos con los que hicimos el repositorio


```
vi README.md
...
git add README.md
git commit
```

y el push

```
git push
```
