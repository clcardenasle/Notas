# Dia 2 Make it Real
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
`git checkout -b 'rama'` --> permite cambiar de rama.

