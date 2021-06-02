# Dia 8
---

> Parte 1

## Componentes

Nuevo componente  
Carpeta src --> nueva carpeta "components"

**Import** --> teniendo en cuenta que cada uno de los archivos es un módulo, me permite importar un código de otro módulo o un código de una dependencia instalada en el proyecto

Al inicio:
```
Import React from 'react';
```

Al final:
```
export default Tasks;
```

Esto nos permite usar este componente desde cualquier parte de la aplicación

en app.js:  
```
import Tasks from './components/Tasks';
```

Tasks.js:
```
import React from 'react';

function Tasks ({tasks}) {
 return tasks.map((task) \=> {
 return (
 <div key\={task.id} className\={\`task-${task.id}\`}\>
 <h2\>{task.tittle}</h2\>
 <span\>{task.done ? 'Completed' : 'In progress'}</span\>
 {!task.done ?
 <button\>Complete</button\>:
 <span\>Congrats</span\>
 }

 </div\>
 ); 
 }
 );
}

export default Tasks;
```

