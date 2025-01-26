# **Instrucciones para Laboratorio-Git**
## *Crear repositorio en local*
1. Abrir terminal en VSC y navegar al directorio dónde queremos crear la carpeta de nuestro proyecto
2. Crer la carpeta manualmente o con el siguiente comando: 
`mkdir laboratorio-git`

3. Navegar a la carpeta del proyecto:
`cd laboratorio-git`

4. Inicializa Git:
`git init`

## *Subir repositorio en GitHub*
1. Crea un nuevo repositorio en [GitHub](https://https://github.com/)
2. Copia la URL del repositorio que acabas de crear:
![copiar URL del repositorio](./content/1-copiar%20URL%20de%20repo%20GitHub.PNG)
3. Conecta tu repositorio local con tu repositorio remoto con el siguiente comando: 
`git remote add origin "URL copiada"`

 ## Hacer un commit y un push
1. Creo un archivo _README.md_ 
2. Añado el archivo al staging con el comando `git add .`
3. Creo el siguiente commit:  `git commit -m "add readme.md"`
4. Subo cambios al repositorio remoto: `git push -u origin`

## Crear una rama
1. Creo rama llamada __development__ y me cambio a ella 

![Crear rama 'development'](./content/2-crear%20rama%20y%20cambio.PNG)
2. Creo título al archivo README.md, añado el cambio y hago commit. Utilizo el comando `git commit -am "..."` porque el archivo ya había sido añadido y ahora su estado es "modified"

![Cambiar a la rama 'development'](./content/3-cambios%20en%20readme,.PNG)
3. Subo la rama local a GitHub

![Subo rama local a remoto](./content/4-subir%20rama%20development%20a%20remoto.PNG)

![Rama development en GitHub](./content/5-rama%20development%20en%20GitHub.PNG)

![Pull Request para añadir rama a GitHub](./content/6-pull%20request%20para%20añadir%20rama%20development.PNG)

## Hacer un merge
1. Vuelvo a la rama __main__ con el comando `git branch main`
2. Listo todas las ramas, tanto locales como remotas, con el comando `git branch -a` y hago un merge de la rama __development__ con el comando `git merge development`. El término __fast-forward__ aparece porque la rama __main__ no tiene commits nuevos desde que se creó la rama __development__ por lo que Git mueve el puntero de la rama __main__ "hacía adelante".

![Listar ramas y mergear 'development'](./content/7-listar%20ramas%20y%20mergear.PNG)

3. Listo las ramas y los commits con el comando `git log --oneline --decorate --graph --all`. Este comando muestra el historial de commits en una sola línea (--oneline) de todas las ramas (no sólo las activas) (--all), muestra a qué rama pertenece cada commit (--decorate), muestra un gráfico del historial de ramas y fusiones (--graph).

![Mostrar historial de commits](./content/8-historial%20de%20commits.PNG)

4. Hago un push de los cambios al respositorio remoto `git push origin main` 

5. Elimino la rama development en local con el comando `git branch -d development` y en remoto con el comando `git push origin --delete development`, ya que esas ramas ya han sido fusionadas a la rama principal __main__. 

![Eliminar rama development en local y en remoto](./content/9-eliminar%20development.PNG)
