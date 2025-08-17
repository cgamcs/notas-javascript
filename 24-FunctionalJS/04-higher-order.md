# Funciones de Orden Superior en JavaScript

## Explicación del concepto

Una **función de orden superior** es aquella que recibe como argumento otra función o devuelve una función. En JavaScript, métodos como `.filter()` y `.map()` son ejemplos comunes: toman funciones como parámetros para procesar arreglos.

## Ejemplo explicado

### Uso de `.filter()`

```js
const mayor400 = producto => {
  return producto.precio > 400
}

const resultado = carrito.filter(mayor400)
console.log(resultado)
```

1. Se define la función `mayor400` que recibe un objeto `producto` y retorna `true` si su precio es mayor a 400.
2. `.filter()` recorre el arreglo `carrito` y aplica la función `mayor400` a cada elemento.
3. Si la función retorna `true`, el producto se incluye en el nuevo arreglo.
4. `resultado` contendrá solo los productos con precio mayor a 400.

### Uso de `.map()`

```js
const obtenerNombres = producto => {
  return producto.nombre
}

const resultado = carrito.map(obtenerNombres)
console.log(resultado)
```

1. Se define la función `obtenerNombres` que recibe un objeto `producto` y retorna su propiedad `nombre`.
2. `.map()` recorre cada elemento del arreglo `carrito` y aplica la función `obtenerNombres`.
3. El nuevo arreglo `resultado` contendrá únicamente los nombres de los productos.

## Salida

### Con `.filter()`

```js
[
  { nombre: 'Monitor 20 Pulgadas', precio: 500 },
  { nombre: 'Televisión 50 Pulgadas', precio: 700 },
  { nombre: 'Celular', precio: 500 },
  { nombre: 'Laptop', precio: 800 }
]
```

### Con `.map()`

```js
[
  'Monitor 20 Pulgadas',
  'Televisión 50 Pulgadas',
  'Tablet',
  'Audifonos',
  'Teclado',
  'Celular',
  'Bocinas',
  'Laptop'
]
```

## Concepto clave

* Una función de orden superior puede recibir funciones como argumentos.
* `.filter()` devuelve un nuevo arreglo con elementos que cumplen una condición.
* `.map()` devuelve un nuevo arreglo transformado con la lógica definida en la función.
* Estos métodos no modifican el arreglo original, generan uno nuevo.
