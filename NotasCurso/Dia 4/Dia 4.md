# Dia 4
---

> Parte 1

- **Scope:** Alcance de las variables
	- entorno global: en JS todo va a ir al entorno Global
		- Navegador: window
		- NodeJS: global
	- Static scope o lexical scope

- **Hoisting**
	- var, function declaration

Anonymous function
```
let greet = function (){
console.log("hola mundo");
}
```

Arrow function
```
let greet = () =>{
console.log("hola mundo");
}
```

Function Declaration
```
fuction greet() {
console.log("hola mundo");
}
```

- **Closure:** Funciones adndadads que **recuerdan el conjunto de variables a las que podían acceder,** por más que se les invoque desde otro scope. (Funcion que siendo invocada fuera del lexical scope recuerda los valores de ese lexical scope (función que retorna otra función)).
```
function app() {
 	let hoo = "app";
 	return function () {
 		console.log(hoo);
 		}
	}
let far = app();
far();
```

```
function infoMiguel() { 
	let libreDePapa = "3000 Pesos la papa";
	return function () { // (funcion de ir hasta la tienda a preguntar)
		console.log(libraDePapa); //(me llama y me dice está a 3000 pesos)
		} 
	} 
let ivan = infoMiguel();
ivan();
```

```
function filter(num){
	return function(arr) {
		let res = [];
		for (let i = 0; i<arr.length; i++){
			if(arr[i] === num){
				res.push(i);
			}
		}
		return res;
	}
}

let positions1 = filter(1);
let positions2 = filter(2);
let positions3 = filter(3);

console.log(positions1([1,2,3,1,2,3]));
console.log(positions2([1,2,3,1,2,3]));
console.log(positions3([1,2,3,1,2,3]));
```

- **Entorno léxico**: Es un objeto que tienen los contextos de ejecución donde se almacenan los nombres de las variables que existen dentro de una función y los valores actuales que tienen.

**CADA VEZ QUE SE EJECUTA UNA FUNCION EN JAVASCRIPT, SE CREA UN NUEVO CONTEXTO DE EJECUCIÓN CON UN NUEVO ENTORNO LÉXICO**


- **API:** La interfaz que tiene un objeto para interactuar con el mismo. QUé métodos podemos invocar sobre ese objeto y a qué propiedades internas nos permite acceder.

> Parte 2

**this**  
Reglas:  
1. Por defecto es el entorno global. Undefine si JS está en modo estricto
```
//ejecutar em consola web

var foo = "foo";
function bar(){
 console.log(this.foo);
}

bar();
```

2. El this es el objeto desde el cual estamos invocando la función
```
var foo = "foo";
function bar(){
 console.log(this.foo);
}

const obj = {
 foo: "baz",
 bar: bar
}

obj.bar();
```
_(metodos que corren sobre cualqyuier funcion y permiten definir manualmente el significado del this):_  
```
bar.call();
bar.apply();
bar.bind(); //crea una nueva función, la enlaza con el significado del this y los argumentos adicionales que se quieran agregar
```

3. El this es el objeto definido por el usuario.
```
var foo = "foo";
function bar(arg){
 console.log(this, arg);
}

const obj = {
 foo: "baz",
 bar: bar
}

obj.bar(25);
const obj2 = {
 foo:"faz"
}

bar.call(obj2, 1);
bar.apply(obj2, \[25\]);
```

4. al utilizar la palabra clave "new":  
	1. Se crea un nuevo objeto en la fucnión
	2. Al this se le asigna el nuevo objeto crerado
	3. El nuevo objeto es asociado con un prototipo
	4. Si la fucnión no está retornando un objeto, entonces retorna el this
```
function Person(name,age){ 
 this.name = name;
 this.age = age;
 return this;
}

let maria = new Person("Maria", 25);
console.log(maria);
```

_El this dentro de una función flecha es el lexical scope_