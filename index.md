# Comandos Git/GitHub

- Tu puedes usar el [editor on GitHub](https://github.com/Lekanda/github2/edit/gh-pages/index.md) utilizando para editar, **Markdown**.



### GIT ADD
- **git add .** => Añade todos los archivos con cambios en repositorio.
- **git add -A** => Añade todos los archivos con cambios en repositorio.
- **git add --all** => Añade todos los archivos con cambios en repositorio, parecido **-A**.
- **git add _nombreArchivo.ext_**=> Anade archivo dado.
- __git add *.png__=> Añade todos los archivos **_.png_**.
- __git add "*.txt"__ => Añade todos los **_.txt_** del **_proyecto_**.
- **git add folder/** => Añade todos los archivos con cambios de la carpeta dada.
- __git reset *.xml__ =>  Quita del Stage todos los archivos _.xml_

---

### GIT COMMIT
 - **git commit -m "_mensaje de commit_"** => Hace commit a **repositorio local**.
 
 
 ---
 
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
