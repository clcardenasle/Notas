# Dia 3
---

> Parte 1

### Bases de Datos

ERM --> Entity relationship model

### Variables

| Tipo | Redeclara | Reasigna | Scope |
|---|---|---|---|
| var | x | x | Global, Bloque |
| let |  | x | Local |
| const |  |  | Local |

> Parte 2

Arreglo:  
`let arr = [1,2,3,4,5,6,7,8,9,10];`

Obtener un elemento:  
`console.log(arr[0];`

**Asignación por valor:**  
`let str = "Hola mundo";`  
`let num )3;`  
`let bool = true;`

**Asignación por referencia:**
`let obj = {}`  
`let str = String()`  
`let arr = []`  

**Agregar elementos a un arreglo**  
- Push: Agregar elemento al final de la referencia
```
arr.push(11); 
console.log(arr);    
let arr2 = arr;  
console.log(arr2);
```
- unshift: Agregar un elemento al inicio de la referencia
```
arr.unshift(0);
console.log(arr);
```
- splice: borrar y agregar elementos
```
//Syntax: arr.splice('indice', 'cantidad de elementos a eliminar', 'elementos a agregar');

arr.splice(5, 0, 50, 51, 52);
console.log(arr);
```

**Agregar elementos, sin modificar el arreglo original**
- concat()
```
let arr3 = arr2.concat([1,2,3]);
console.log(arr2);
console.log(arr3);

let arr4 = [-2,-1].concat(arr2);  
console.log(arr4);
```

**Agregar elementos en medio de un arreglo, sin modificar original**  
- slice: crear un arreglo nuevo con los elementos indicados  
```
//Syntax: let arr5 = arr2.slice('indice inicial', 'indice final').concat('valor a agregar')concat(arr2.slice('indice final'));

let arr5 = arr2.slice(0, 5).concat(49).concat(arr2.slice(5);
console.log(arr5);
```

**Remover elementos en arreglo original**  
- `arr.pop();` --> final
- `arr.shift();` --> inicio
- `arr.splice();` --> indice especifico:
	```
	//Syntax: arr.splice('indice a partir del que se quiere eliminar','cantidad de elementos a eliminar');
	
	arr.splice(5, 2);
	```


### Objetos

`let obj = {name: 'Maria', 'last-name': 'lopez'};`  

Obtener un valor:

``` 
console.log(obj.name);
let prop = "last-name";
console.log (obj[prop]);
console.log (obj["name"]) 
```

**Agregar un valor:**

Modificando el objeto original
```
let obj = { name: "Maria", "last-name": "Lopez" };
let obj2 = obj;
obj2.age = 20;
console.log(obj1)
```

```
let obj = { name: "Maria", "last-name": "Lopez" };
obj2['age']=20;
let obj2 = obj;
console.log(obj);
```

Sin modificar el objeto original
- Object.assign: Crea un nuevo objeto a partir de varios objetos
```
let obj = { name: "Maria", "last-name": "Lopez" };
let obj3 = Object.assign({},obj, {age: 20});
console.log(obj);
console.log(obj3);
```

Modificar objeto original
```
let obj = { name: "Maria", "last-name": "Lopez" };
let obj2 = obj;
delete obj2.name;
console.log(obj)
```

Iteraciones
```
let arr = [0,1,2,3,4,5,6,7,8,9,10];
arr.push(11); 
let arr2 = arr;  
let arr8 = arr2.slice(0,5).concat(arr.slice(6));

//iteración
for(let value of arr8) {
consol.log(value);
}
```

iteración objetos
```
let obj = { name: "Maria", "last-name": "Lopez" };
let obj3 = Object.assign({},obj, {age: 20});

//iteracion objeto
for(let key in obj3){
console.log(key)
}

//para imprimir con valores
for(let key in obj3){
let value = obj3[key];
console.log(key, value);
}
```











