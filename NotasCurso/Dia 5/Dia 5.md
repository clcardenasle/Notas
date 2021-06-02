# Dia 5
---

> Parte 1

## Programación Orientada a Objetos

Objetos literales:
```
let juan = {
 name: "Juan",
 age; 24
}

let maria = {
 name: "María"
 age: 28
}
```

Fabrica de objetos:
```
function person(name,age){
 return{
 name: name,
 age: age
 };
}

let juan = person("juan", 24)
let maria = person("María",28)
```

Métodos: una función que está asignada a una propiedad de un objeto
```
let juan = {
 name: "Juan",
 age; 24,
 greet: function(){
 console.log(this.name);
 }
}

let maria = {
 name: "María"
 age: 28
 greet: function(){
 console.log(this.name);
}
```

```
function person(name,age){
 return {
 name: name,
 age: age,
 greet: function(){
 console.log(this.name);
 }
}
}
 
let juan = person("juan", 24);
let maria = person("María",28);

console.log(juan);
console.log(maria);
```

Funciones constructoras - Objected Oriented Programing (OOP):  
Abstracción de un elemento de la vida real. Plano de arquitectura a tyraves del cual se pueden crear elementos de la vida real

Objeto/Clase - Plano

Instancias 

```
//OOP
//Objeto/Clase - Plano

function Person(name,age){
 this.name = name;
 this.age = age;
}

//Instancias
let juan = new Person("Juan", 24);
let maria = new Person ("María", 28)

console.log(juan);
console.log(maria);
```


Prototipos:
```
function Person (name,age){
 this.name = name;
 this.age = age;
}

Person.prototype.greet = function(){
 console.log(this.name)
}

//Instancias
let juan = new Person("Juan", 24);
let maria = new Person ("María", 28)

function Teacher(lesson){
 this.lesson = lesson;
}

Teacher.prototype = new Person();

const simon = new Teacher("TOP");

console.log(juan);
console.log(maria);

console.log(simon);
```

prototipo dentro de otro prototipo:
```
// Op 1:
Teacher.prototype = new Person();

// Op 2:
Teacher.prototype = Object.create(Person.prototype);
```

Mayuscula: Prototipo  
minuscula: Objeto

### Clases

 ```
class Person {
 constructor(name, age){
 	this.name = name;
 	this.age = age;
 }
 greet (){
 console.log(this.name);
 }
}

let persona1 = new Person("Juan", 24);
let persona2 = new Person ("Maria", 28);

console.log(persona1);
persona1.greet();
persona2.greet();
console.log(persona2);

class Teacher extends Person {
 constructor (name, age, lesson) {
 	super(name, age);
 	this.lesson = lesson;
 }
 teach() {
 	console.log("currently teaching top v6");
 }
}

const simon = new Teacher("Simon",29,"TOP");
console.log(simon);
simon.greet();
simon.teach();
```


> Parte 2

## ECMAScript

Ecmascript 5
Parámetros por defecto

```
function sum(a,b) {
 if(!a){
 	a\=0;
 }
 if(!b){
	b\=0;
 }
 return a + b;
}

console.log(sum());
```

Ecmascript 6
```
function sum(a = 0, b = 0) {
 return a + b;
}

console.log(sum());
```

Palntillas Literales
- Comillas dobles " "
- Comillas sencillas ' '
- Comillas invertidas ` `

```
let name = 'Ana';

console.log("Hola "+name+"!");
console.log(\`Hola ${name}!\`); //interpolación
console.log(\`${1234}\`);
console.log(\`${\["a",1,"b"\]}\`);
console.log(\`Hola ${name}!
este es un espacio de linea ${name}\`);
```

Desestructuración
```
let obj = {a: 1, b: 2, c: 3};
let {a, b,c} = obj;
console.log(a);

let arr =\[1,2,3,4,5\];
let \[number, two, loquesea, nose\] = arr;
console.log(number,loquesea);
```

tres puntos + operador restante [...var+' ']
- var --> definir el arreglo
- ' ' --> lo convierte en string
- ... --> cada uno de los caracteres se convierte en un elemento del arreglo
itarables: cadenas de texto, arreglos. Objetos NO son iterables (tienen otro tipo de iteración):
```
console.log(...[1,2,3]);
console.log({...12345+''});
```

propiedades y métodos concisos
```
let lesson\="TOP"

// function person(name,age){
//   return{
//     name:name,
//     age: age,
//     lesson: lesson,
//   }
// }

function person(name,age){
 return{name,age,lesson};
}
```








