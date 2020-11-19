<script src="https://kit.fontawesome.com/9b21360d5e.js" crossorigin="anonymous"></script>
<link rel="stylesheet" href="style.css">

# ![Git Logo](static/icon-git.ico) Comandos Git & GitHub

### INDICE de comandos 
- [GIT HELP](#anclaHelp)
- [GIT CONFIG](#anclaConfig)
- [GIT ALIAS](#anclaAlias)
- [GIT INIT](#anclaInit)
- [GIT ADD](#anclaAdd)
- [GIT COMMIT](#anclaCommit)
- [GIT LOG](#anclaLog)
- [GIT STATUS](#anclaStatus)
- [Cambios en STAGE y COMMIT](#anclaCambios)
- [GIT RESET](#anclaReset)
- [GIT REVERT](#anclaRevert)
- [GIT BRANCH](#anclaBranch)
- [GIT MERGE](#anclaMerge)
- [GIT TAGS](#anclaTags)
- [GIT REMOTE](#anclaRemote)
- [GIT CLONE](#anclaClone)
- [GIT PUSH](#anclaPush)
- [GIT PULL](#anclaPull)

---
[Metodos](metodos.md)
---

- Tu puedes usar el [editor on GitHub](https://github.com/Lekanda/github2/edit/gh-pages/index.md) utilizando para editar, **Markdown**.

- __git add . && git commit -m "*DescripcionDeCommit*"__ => Ejecuta dos comandos a la vez

---

### <a name="anclaHelp"></a>GIT HELP
- Estos comandos nos dan la lista de comandos posibles.
    - **git help** => Nos da lista simple
    - **git help -a** => Nos da lista completa
    - **git help -g** => Nos da lista completa


### <a name="anclaConfig"></a>GIT CONFIG
 - Solo se hace una vez al instalar **GIT**
 - Con esto introducimos el **nombre de usuario de GitHub** y **email**
 ```
        git config --global user.name "nombre de usuario"
        git config --global user.email "password de usuario"
 ```

 - Con este comando entramos en **configuracion de usuario** 
 ```
        git config --global -e => 
 ```
 
  - Con este comando entramos en **configuracion de usuario mejorada**
 ```
        git config --global -l => 
 ```
 
 - Con este comando comprobamos que la configuracion es correcta sí da el nombre metido
 ```
        git config user.name => 
 ```


### <a name="anclaAlias"></a>ALIAS
- Los alias es una forma de abreviar los comandos largos para escribirlos mas cortos. Unos ejemplos
#### git lg
    - `git config --global alias.lg "log --oneline --decorate --all --graph"` --oneline => una linea por commit
- Con esta linea decimos que :
    - Escribir **git lg** para ejecutar el **alias**. Crea una vista mas clara del repositorio en consola

#### git s
`git config --global alias.s "status -s -b"`
- Con esta linea decimos que :
    - Escribir **git s** para ejecutar el **alias**. Nos da los cambios en repositorio

#### git br
- `git config --global alias.s "branch"`
- Con esta line abreviamos **branch**(Rama) a **br**


### <a name="anclaInit"></a>GIT INIT
- Crea un repositorio nuevo en el _folder/carpeta_ que se ejecuta.
```
        git init
```

- Se puede **tambien** clonar un repositorio de alguien
 
- Para poder ver los remotos que se tienen en el repositorio.
```
        git remote -v
```

### <a name="anclaAdd"></a>GIT ADD
- **git add .** => Añade todos los archivos con cambios en repositorio.
- **git add -A** => Añade todos los archivos con cambios en repositorio.
- **git add --all** => Añade todos los archivos con cambios en repositorio, parecido **-A**.
- **git add _nombreArchivo.ext_**=> Anade archivo dado.
- __git add *.png__=> Añade todos los archivos **_.png_**.
- __git add "*.txt"__ => Añade todos los **_.txt_** del **_proyecto_**.
- **git add folder/** => Añade todos los archivos con cambios de la carpeta dada.
- __git reset *.xml__ =>  Quita del Stage todos los archivos _.xml_
> Comandos para añadir archivos al Stage


### <a name="anclaCommit"></a>GIT COMMIT
##### Hacer commits
- **git commit -m "_mensaje de commit_"** => Hace commit a **repositorio local**
- **git commit -am "_mensaje de commit_"** => Hace commit y Stage a **repositorio local**


### <a name="anclaLog"></a>GIT LOG
- Listado de commits hechos. **Lista completa con mucha informacion**
> Con el Alias actual seria: **git lg**. Añane mas opciones
>> Pero se puede usar tambien **git log**


### <a name="anclaStatus"></a>GIT STATUS
- Con alias utilizamos 
        `git s`
- Nos dice los cambios que hay en en **work directory y stage**


### <a name="anclaCambios"></a>CAMBIOS EN STAGE Y COMMIT
#### Actualizar y restaurar COMMITS
- Sí se **olvida algun cambio** que deberia haberse metido en el ultimo commit; ejecutar :
    - **git commit --amend**
    - En **Editor** poner _nombre de commit nuevo_

- Sí se quiere **cambiar la descripcion** del commit; ejecutar :
    - **git commit --amend -m "_mensaje de commit modificado_"**
    - En **Editor** poner _nombre de commit nuevo_

- **Deshace cambios en el commit** de un archivo dado
    - `git reset HEAD _archivo.ext`

- **Mete cambios al ultimo commit con mismo nombre**
    - `gir rest --soft HEAD^`

#### Deshacer cambios en STAGE
- **Como deshacer cambios en el Stage** en un **archivo determinado**
    - `git checkout -- archivo.ext`

- **Como deshacer cambios en el Stage** en **todos** los archivos
    - `git checkout -- .`


### <a name="anclaReset"></a>GIT RESET
> ES PELIGROSO, mejor usar el **REVERT**, pero bien usado es una buena herramienta. <i class="fas fa-exclamation"></i>

---

#### GIT RESET
- Para **eliminar** un commmit con **hash dado**:
    `git reset f6e2697`

---

#### GIT RESET --HARD
- <i class="fas fa-exclamation"></i> **PELIGROSO**. Para **eliminar** todo lo que hay **despues** de un hashCommit dado, y los cambios son borrados y no se pueden recuperar:
    - `git reset --hard hashCommit`

---

#### GIT RESET --SOFT
- Va a **eliminar** los commits antes de un **hashCommit** dado , y los cambios **los guarda en el Stage**
    - `git reset --soft hashCommit`

---

#### GIT RESET --MIXED
- Retorna al commit seleccionado
    - `git reset --mixed hashCommit`

---

### <a name="anclaRevert"></a>GIT REVERT
- Es parecido a **RESET** pero menos peligroso.

- Revierte a commit **dado**
    - `git revert hashCommit`
- Revierte a commit ultimo con **HEAD**
    - `git revert HEAD`
- Revierte uno o varios comits **pero no crea un commit final**, deja los datos en el **Stage**
    - `git revert --no-commit HEAD`
    - `git revert --no-commit HEAD~1`
    - `git revert --no-commit HEAD~2`
- Para terminar de unir los commits en uno
    - `git revert --continue`

---

### <a name="anclaBranch"></a>GIT BRANCH
- Con Alias `git br`

- Para **crear** la rama
    - `git branch nombre-rama`
- Para **cambiar** a otra rama.(main rama por defecto, master antiguamente)
    - `git checkout nombre-rama`
- Para **crear** una _rama_ y *cambiar* a ella **a la vez**
    - `git checkout -b nombre-rama`
- Para **listar** las ramas 
    - `git branch`
- Para **Borrar** una rama
    - `git branch -d nombre-rama`
- Para **renombrar** una Rama
    - `git branch -m nombre-rama-viejo nombre-rama-nuevo`
- Para ver **origenes** y **ramas**
    - `git branch -a`

---

### <a name="anclaMerge"></a>GIT MERGE
- Para **unir ramas** , **estando en la rama en la que se va ha fusionar** (_main por ejemplo_)
    - `git merge nombre-rama`
    - **Hay que hacer un commit final en el que se integran las 2 ramas**
- Para abortar uniones que estan en marcha y tienen muchos conflictos
    - `git merge --abort`
- Para unir dos ramas , una **local** y otra **remota**
    - `git merge origin/master`

---

#### Tipos de merge/uniones
- **Fast forward** -> Rapida. **No hay cambios**
- **Automatica/Recursiva** -> **No hay discordias** entra ramas y se unen
- **Manual** -> Hay conflictos entre ramas y se debe hacer la union de forma **manual** en Editor

---

### <a name="anclaTags"></a>GIT TAGS
- **Crear** un TAG
    - `git tag nombre-tag`
- **Listar** los TAGs
    - `git tag`
- **Borrar** un TAG
    - `git tag -d nombre-tag`
- **Crear TAG poniendo nombre de TAG y  descripcion**
    - `git tag -a v0.0.1 -m "descrpcion de TAG"`
- **Crear TAG poniendo nombre de TAG y  descripcion** con un **hash** dado. Se puede hacer en cualquier commit
    - `git tag -a v0.0.1 hashCommit -m "descrpcion de TAG"`
    - `git tag  v0.0.1 hashCommit`
- **Listar Datos de un TAG dado**
    - `git show nombre-tag`
- Para **regresar a un TAG dado**
    - `git checkout v0.1.0`
- **Filtrar** TAGs que coincidan con la busqueda
    - `git tag -l "v0.1.*"`
---

### <a name="anclaTags"></a>GIT STASH
- Es una forma de guardar los cambios que tengas , sin necesidad de estar en el Stage los cambios, pero si estan tambien vale.

|   Comando	|   Explicacion	|
|---	|---	|
|   **git stash**	|   Guarda en el Stash los archivos modificados, y lo que este en el Stage	|
|   **git stash list**	|   Lista los Stashs creados	|
|   **git stash list --stat**	|   Lista los Stashs creados con mas info	|
|   **git show stash**	|   Mas info de los Stash	|
|   **git show stash@{3}**	|   Mas info de Stash 3	|
|   **git stash -h**	|   Da comandos de ayuda	|
|   **git stash apply**	|   Aplica los ultimos cambios que se han hecho en el stash y lo mete donde estes trabajando	|
|   **git stash apply stash@{3}**	|   Aplica los cambios del Stash 3 y lo mete donde estes trabajando	|
|   **git stash drop**	|   Borra el primero en la lista de los Stash	|
|   **git stash drop stash@{2}**	|   En este ejemplo borra el segundo en la lista de los Stash	|
|   **git stash clear**	|   :warning: CUIDADO: Borra todas las entradas del Stash :warning: |
|   **git stash save** "_Comentario del Stash_"	|   Comentar un Stash	|
|   **git stash pop**	|   Hace los mismo que  **git stash apply**	|

---

### <a name="anclaRemote"></a>GIT REMOTE
- Este SubComando vale para conectarse a repositorios remotos en internet( GitHub, GitLab....)
    - Se puede mandar y recibir(Pull, Push)

|   Comando	|   Explicacion	|
|---	|---	|
|   **git remote add origin  _URLdeRepositorioRemoto_**	|   **Añade** un repositorio remoto al proyecto	|
|   **git remote**	|   Nos **da** los **remotos**	|
|   **git remote -v**	|   Nos da los **push** y **fetch** remotos 	|
|   	|   	|
|   	|   	|

---

### <a name="anclaClone"></a>GIT CLONE
- Clona un repositorio de otra persona. Link en el repositorio en cuestion.
- Se puede hacer un **push** y **pull** a ese repositorio
|   Comando	|   Explicacion	|
|:-:	|:-:	|
|   **git clone urlRepositorioaClonar**	_nombreCarpeta_(opcional)|   Clona el repositorio a la carpeta donde se esta	|
|   	|   	|
|   	|   	|

---

### <a name="anclaPush"></a>GIT PUSH
- Sube al repositorio remoto los cambios
|   Comando	|   Explicacion	|
|---	|---	|
|   **git push origin master**	|   **Sube** cambios al remoto _origin_	|
|   **git push origin --all**	|   _Sube varias ramas_ a la vez de golpe	|
|   **git push**	|   Una vez hecho **git push origin master** con este vale para subir los cambios al repositorio remoto	|

---

### <a name="anclaPull"></a>GIT PULL
- Mira si hay cambios en un repositorio remoto
- Es la combinacion de 2 comandos
    1- `git fetch origin` => Sirve para preguntar a un remoto sí hay novedades, y sí las ahi descargarlas al repo local
    2- 
|   Comando	|   Explicacion	|
|---	|---	|
|   	|   	|
|   	|   	|

---

### GIT REBASE





### BIBLIOGAFIA, CURSOS Y DEMAS FUENTES
- **Makigas**: Tutoriales programacion en You Tube - [Lista de clases](https://www.youtube.com/playlist?list=PLTd5ehIj0goMCnj6V5NdzSIHBgrIXckGU)
- **GIT+GitHub: Todo un sistema de control de versiones** por  Fernando Herrera - [Link a curso](https://www.udemy.com/course/git-github/)
- 