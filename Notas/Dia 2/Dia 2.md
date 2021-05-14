# Dia 2
---

> Parte 1

## GitHub

`git init` --> iniciar git  
`git clone https.......` --> clona repositorio remoto localmente.  
`git remote -v` --> enlistar repositorios remotos.  
`ls .force` --> Mostrar archivos ocultos (.git).  
`git status` --> muestra documentos que han tenido un cambio.  
`git add .` --> Agrega todos los archivos.  
`git add 'Nombre archivo'` --> alistar cambios para commit.  
`git add -p` --> muestra uno a uno los cambios (n / y).  
`git diff 'Nombre archivo"` --> comparar versión anterior con versión actual.  
`git log`--> Historial de commits (cambios).  
`git push origin 'rama' ` --> cargar al repositorio remoto.  
`git commit -m "Nombre del cambio"` --> cargar cambios y nombre del cambio.  

`git branch --set-upstream-to origin/'rama'` --> conectarse con una rama del repositorio remoto (de ahí en adelante con solo hacer `git push` los cambios se van a cargar en el repositorio remoto).  
`git branch --all` --> miestra las ramas que hay creadas en el remoto  
`git checkout -b 'rama'` --> crea y cambia de rama  
`git push -u origin 'rama'`--> crea rama nueva y carga los cambios en ella  

`git fetch` --> mostrar cambios en repositorio remoto sin aplicarlos  

`cat 'documento.md'`--> mostrar contenido documento

#### Cambio de rama - suspención temporal trabajo actual

`git stash` --> deja cambios almacenados en stash (no incluye documentos nuevos)  
`git stash list` --> muestra lista de cambios almacenados  
`git stash apply stash@{0}`--> trae nuevamente los cambios para continuar trabajando  
`git stash pop` --> trae cambios y de una vez los remueve  

##### Edición de archivos

`git rm 'documento.md'` -->  eliminar documento, luego requiere commit y push para terminar de ejecutar   
`git mv 'documento.md' 'carpeta' `--> mover archivos de ubicación  
`git mv 'documento.md' 'documentov2.md' `--> cambiar nombre de archivo  
`git rm --cached 'documento'` --> eliminar archivo de repositorio github  

---
## GitFlow

> Parte 2

### Ramas
- marter / producción: Código principal, código estable, código que tiene la interfaz en uso
- QA: Listas para probar
- Staging / dev / development: rama en la cual se ejecuta el desarrollo, nuevas funcionalidades

*Siempre que se va a crear una nueva rama se debe hacer `git pull origin 'rama actual'` para ver las actualizaciones que han hecho las demás personas en esa rama* 

### PR

Se recomienda poner como titulo del PR algo descriptivo de lo que se ejecutará.  
En las observaciones se recomienda poner todos los detalles posibles.


















