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
##### git lg
```
git config --global alias.lg "log --oneline --decorate --all --graph"
```
- Con esta linea decimos que :
    - Escribir **git lg** para ejecutar el **alias**. Crea una vista mas clara del repositorio en consola
> OPERATIVO

##### git s
```
git config --global alias.s "status -s -b"
```
- Con esta linea decimos que :
    - Escribir **git s** para ejecutar el **alias**. Nos da los cambios en repositorio
> OPERATIVO




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
 - **git commit -m "_mensaje de commit_"** => Hace commit a **repositorio local**
 > Crear COMMITS
 
 - Sí se olvida algun cambio que deberia haberse metido en el ultimo commit; ejecutar :
    - **git commit --amend**
    - En **Editor** poner _nombre de commit nuevo_



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
```
        git s
```
- Nos dice los cambios que hay en en **work directory y stage**



### GIT DIFF
- Nos da diferencias del ultimo commit y lo actual
        `git diff`
