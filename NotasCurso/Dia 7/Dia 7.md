# Dia 7
---

> Parte 1

## Componentes
```
import logo from './logo.svg';
import './App.css';
import react from 'react';

class Counter extends react.Component{
 render(){
 return(
 <div\>
 <button\>+</button\>
 <count\>0</count\>
 <button\>\-</button\>
 </div\>
 )
 }
}

function App() {
 return (
 <div className\="App"\>
 <Counter/>
 </div\>
 );
}

export default App;
```

Clases de datos:  
1. Datos internos del componente (estado)
```
import logo from './logo.svg';
import './App.css';
import react from 'react';

class Counter extends react.Component{
 constructor(){
 super();
 this.state\={
 count:0,
 }
 }
 render(){
 return(
 <div\>
 <button\>+</button\>
 <span\>{this.state.count}</span\>
 <button\>\-</button\>
 </div\>
 )
 }
}

function App() {
 return (
 <div className\="App"\>
 <Counter/>
 </div\>
 );
}

export default App;
```

2. props: Se pasan de un componente padre a un componente Hijo
```
import logo from './logo.svg';
import './App.css';
import react from 'react';

class Counter extends react.Component{
 constructor(props){
 super(props);
 this.state\={
 count:0,
 }
 }
 render (){
 return (
 <div\>
 <p\>Hola {this.props.name}</p\>
 <p\>{this.props.age}</p\>
 <button\>+</button\>
 <span\>{this.state.count}</span\>
 <button\>\-</button\>
 </div\>
 );
 }
}

function App() {
 let name = "Maria"
 return (
 <div className\="App"\>
 <Counter name\={name} age\={23}/>
 <Counter name\="Juan"/>
 </div\>
 );
}

export default App;
```

*incrementar contador:*

- setState: se va a encargar de mantener la inmutabilidad del estado {objeto con las propiedades del estado que se quiere modificar}
- onClick: ejecutar función al hacer click
- .bind: enlace fuerte. crea una nueva función que queda enlazada a la función donde se está ejecutando (en este caso se ejecuta dentro de la función "constructor")

```
import logo from './logo.svg';
import './App.css';
import react from 'react';

class Counter extends react.Component{
 constructor(props){
 super(props);
 this.state\={
 count:0,
 }
 this.countIncrease = this.increaseCount.bind(this);
 }

 increaseCount(){
 this.setState({count: this.state.count + 1});
 }

 render (){
 return (
 <div\>
 <p\>Hola {this.props.name}</p\>
 <p\>{this.props.age}</p\>
 <button onClick\={this.countIncrease}\>+</button\>
 <span\>{this.state.count}</span\>
 <button\>\-</button\>
 </div\>
 );
 }
}
  
function App() {
 let name = "Maria"
 return (
 <div className\="App"\>
 <Counter name\={name} age\={23}/>
 <Counter name\="Juan"/>
 </div\>
 );
}

export default App;
```

*decrementar contador:*

```
 decreaseCount = () \=> {
 this.setState({count: this.state.count -1})
 }
```
con las funciones flecha, el this siempre va a ser el contexto donde se crea.

```
import logo from './logo.svg';
import './App.css';
import react from 'react';

class Counter extends react.Component{
 constructor(props){
 super(props);
 this.state\={
 count:0,
 }
 this.countIncrease = this.increaseCount.bind(this);
 }

 increaseCount(){
 this.setState({count: this.state.count + 1});
 }
  
// Se usa función flecha, por tanto no requiere bind:
 decreaseCount = () \=> {
 this.setState({count: this.state.count -1})
 }

 render (){
 return (
 <div\>
 <p\>Hola {this.props.name}</p\>
 <p\>{this.props.age}</p\>
 <button onClick\={this.countIncrease}\>+</button\>
 <span\>{this.state.count}</span\>
 <button onClick\={this.decreaseCount}\>\-</button\>
 </div\>
 );
 }
}

function App() {
 let name = "Maria"
 return (
 <div className\="App"\>
 <Counter name\={name} age\={23}/>
 <Counter name\="Juan"/>
 </div\>
 );
}

export default App;
```

> Parte 2

## DOM

Árbol de etiquetas y componentes del HTML. contiene información sobre cada uno de los elementos

mock: 

Complejidad temporal: Big O notation 
- O(1) --> Complejidas constante
- O(logN) --> siempre que tengamos una funcion que recorre únicamente la mitad del arreglo
- O(n) --> n representa la longitud de los elementos. cuantas veces tiene que correr por cada uno de los elementos

```
[1,2,3\].push(4); //O(1)
[1,2,3\].pop(); //O(1)
[1,2,3\].unshift(0); //O(n)
```


- Array.prototype.map: repite n cantidad de veces una función
- array.prototype.filter: Filtra la información del arreglo según las condiciones de la función
- array.prototype.reduce: ejecuta la 

```
import logo from './logo.svg';
import './App.css';

// \[1,2,3\].push(4); //O(1)
// \[1,2,3\].pop(); //O(1)
// \[1,2,3\].unshift(0); //O(n)

let mockTasks=[
 {
 id:0,
 tittle: "task 1",
 done: true
 },
 {
 id:1,
 tittle: "task 2",
 done: false
 },
 {
 id:2,
 tittle: "task 3",
 done: false
 }
]

function App() {
 return mockTasks.map((task)=> {
 return(
 <div key\={task.id}\>
 <p\>{task.id}</p\>
 <h2\>{task.tittle}</h2\>
 <span\>{task.done}</span\>
 </div\>
 )
 })
}
  

export default App;
```
