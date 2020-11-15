# Comandos Git/GitHub

### INDICE de comandos 
- [GIT ALIAS](https://github.com/Lekanda/github2/blob/gh-pages/index.md#alias)
- [GIT ADD](https://github.com/Lekanda/github2/blob/gh-pages/index.md#git-add)
- [GIT COMMIT](https://github.com/Lekanda/github2/blob/gh-pages/index.md#git-commit)
- [GIT CONFIG](https://github.com/Lekanda/github2/blob/gh-pages/index.md#git-config)
- [GIT INIT](https://github.com/Lekanda/github2/blob/gh-pages/index.md#git-init)
- [GIT LOG](https://github.com/Lekanda/github2/blob/gh-pages/index.md#git-log)
- [GIT STATUS](https://github.com/Lekanda/github2/blob/gh-pages/index.md#git-status)

---

- Tu puedes usar el [editor on GitHub](https://github.com/Lekanda/github2/edit/gh-pages/index.md) utilizando para editar, **Markdown**.

---

### GIT HELP
- Estos comandos nos dan la lista de comandos posibles.
    - **git help** => Nos da lista simple
    - **git help -a** => Nos da lista completa
    - **git help -g** => Nos da lista completa








### ALIAS
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







### GIT ADD
- **git add .** => Añade todos los archivos con cambios en repositorio.
- **git add -A** => Añade todos los archivos con cambios en repositorio.
- **git add --all** => Añade todos los archivos con cambios en repositorio, parecido **-A**.
- **git add _nombreArchivo.ext_**=> Anade archivo dado.
- __git add *.png__=> Añade todos los archivos **_.png_**.
- __git add "*.txt"__ => Añade todos los **_.txt_** del **_proyecto_**.
- **git add folder/** => Añade todos los archivos con cambios de la carpeta dada.
- __git reset *.xml__ =>  Quita del Stage todos los archivos _.xml_
> Comandos para añadir archivos al Stage




### GIT COMMIT
##### Hacer commits
- **git commit -m "_mensaje de commit_"** => Hace commit a **repositorio local**
- **git commit -am "_mensaje de commit_"** => Hace commit y Stage a **repositorio local**





### CAMBIOS EN STAGE Y COMMIT
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






### GIT CONFIG
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
> Configuracion inicial para instalar Git -Cap.9







### GIT INIT
- Crea un repositorio nuevo en el _folder/carpeta_ que se ejecuta.
```
        git init
```

- Se puede **tambien** clonar un repositorio de alguien
 
- Para poder ver los remotos que se tienen en el repositorio.
```
        git remote -v
```





### GIT LOG
- Listado de commits hechos. **Lista completa con mucha informacion**
> Con el Alias actual seria: **git lg**. Añane mas opciones
>> Pero se puede usar tambien **git log**





### GIT STATUS
- Con alias utilizamos 
        `git s`
- Nos dice los cambios que hay en en **work directory y stage**






### GIT DIFF
- Nos da diferencias del **ultimo commit y lo actual**
    - `git diff`
- Nos da diferencias entre **2 commits dados**
    - `git diff hashviejo hashnuevo`
- Nos da la diferencia **con un numero de orden de commit**. En este caso el penultimo(**~** = anterior ; **HEAD** = Donde apunta actualmente)
    - `git diff HEAD~1 HEAD`





### GIT RESET
> ES PELIGROSO, mejor usar el **REVERT**, pero bien usado es una buena herramienta.

 #### GIT RESET
- Para **eliminar** un commmit con **hash dado**:
    `git reset f6e2697`

#### GIT RESET --HARD
- **PELIGROSO**. Para **eliminar** todo lo que hay **despues** de un hashCommit dado, y los cambios son borrados y no se pueden recuperar:
    - `git reset --hard hashCommit`

#### GIT RESET --SOFT
- Va a **eliminar** los commits antes de un **hashCommit** dado , y los cambios **los guarda en el Stage**
    - `git reset --soft hashCommit`

#### GIT RESET --MIXED
- Retorna al commit seleccionado
    - `git reset --mixed hashCommit`





### GIT REVERT
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





### GIT BRANCH (RAMAS)(Con Alias git br)
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






### GIT MERGE (Unir Ramas)
- Para **unir ramas** , **estando en la rama en la que se va ha fusionar** (_main por ejemplo_)
    - `git merge nombre-rama`
    - **Hay que hacer un commit final en el que se integran las 2 ramas**

#### Tipos de merge/uniones
- **Fast forward** -> Rapida. **No hay cambios**
- **Automatica** -> **No hay discordias** entra ramas y se unen
-  **Manual** -> Hay conflictos entre ramas y se debe hacer la union de forma **manual**













### BIBLIOGAFIA
- Makigas: Tutoriales de programacion - (Canal de YouTube)[http://www.google.es]
- Curso de Git y GitHub por  - Udemy Formacion Online
- 