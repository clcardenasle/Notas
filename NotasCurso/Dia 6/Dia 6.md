# Dia 6
---

> Parte 1

## Errores JS

- Eval: Poco común.
- internal: Motor de JS consumió todos sus recursos. Ciclo infinito.
- Range: Valor que se sale de algún rango.
- Reference: CUando tratamos de acceder a una variable que no existe. Invocar una función que no existe.
- type: invocar un valor de una variable como una función
- Syntax: error en la forma de escribir el código. pueden ser signos de puntuación

```
let bar = "foo";

// console.log(bar);

let obj = { 
 name: "name",
 lastname: "lastname"
};

let foos = {};
foos.name;

// throw "ups algo salió mal";
throw new Error("ups algo malio sal");
```

```
try{
 let pass = "12345"
 if(pass!=="678910"){
 throw Error("Invalid Password")
 }
}
console.log("Valid Password");
catch (error) {
 console.log(error);
}

console.log("here");
```

## Programación Funcional

Se abstraen funcionalidades básicas en varias funciones y luego se crea una funcionalidad mayor compuesta de esas funciones

Todo se basa en funciones:
```
function greet(){
 console.log("hola mundo");
}
let greet2 = greet;

//callback
function greet3(cb){
 cb()
}

greet3(greet);
  
function multiply(factor){
 return function (num){
 return factir\*num
 }
}

multiply(10)(3);
```

inmutabilidad: 
```
let arr = \[1,2,3,5\];
let arr = arr.slice(0,2);
```

pure functions: funcion que dados los mismos argumentos siempre retorna el mismo resultado.
```
function sum(a,b){
 return a + b;
}

sum(1,2); //3
sum(1,2); //3
sum(1,2); //3
```

 no tiene "side effect" (todo lo causado por fuera de la función). ej: al invocar una variable del entorno global (o que esté por fuera de la función), es un efecto secundario
 ```
let res =1;

function multiply(num){
 console.log(res);
 return res\*=num;
}

console.log (multiply(2));
console.log (multiply(2));
console.log (multiply(2));
```

**Métodos**

```
let arr3 = \[1,2,3,4,5\];

//arr.map();
//arr.filter();
//arr.forEach();
//arr.concat();
//arr.every();
//arr.some();

function callback(element, index,array){
 return element \*2;
}

arr3 = arr3.map(callback);
console.log(arr3);
```

```
//métodos

let arr3 = \[1,2,3,4,5\];

//arr.map();
//arr.filter();
//arr.forEach();
//arr.concat();
//arr.every();
//arr.some();

function callback(element, index,array){
 return element \*2;
}

// arr3 = arr3.map(callback);
// console.log(arr3);

Array.prototype.customMap = function(cb){
 let result =\[\];
 console.log(this);
 for(let i =0; i<this.length; i++){
 const op = cb(this\[i\], i, this);
 result = result.concat(op)
 }
 return result;
}

arr3 = arr3.customMap(callback);
console.log(arr3);
```

> parte 2

## react

consola:
instalar react de forma global:
```
npm install -g react
```

create-react-app: de forma local
```
npm i -g create-react-app
```

```
yarn global add create-react-app
```

crear nuevo proyecto con react:
```
create-react-app nombre-proyecto
```

ejecutar 
 ```
 npm run start
 ```
 
npm install --save moment --> dependencia de produccion  
npm install --save-dev moment --> dependencia de desarrollo

**Declarativo**  
Que es lo que se quiere lograr, más no el paso a paso.

**Componentes**  
cada componente de la página

class --> className
for --> htmlFor




