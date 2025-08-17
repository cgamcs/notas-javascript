# Funciones Flecha y Código Reducido en JavaScript

## Explicación del concepto

Las **funciones flecha** permiten escribir funciones de forma más breve. Cuando la función solo devuelve una expresión, no es necesario usar `return` ni llaves `{ }`. Esto ayuda a reducir código y hacerlo más legible.

## Ejemplo explicado

```js
const mayor400 = p => p.precio > 400
const resultado = carrito.filter(mayor400)
console.log(resultado)
```

1. `mayor400` es una función flecha que recibe un producto `p` y retorna `true` si su precio es mayor a 400.
2. `.filter()` aplica esta función a cada elemento del arreglo `carrito`.
3. Se obtiene un nuevo arreglo solo con los productos que cumplen la condición.

```js
const obtenerNombres = p => p.nombre
const resultado2 = carrito.map(obtenerNombres)
console.log(resultado2)
```

1. `obtenerNombres` es otra función flecha que retorna directamente la propiedad `nombre` de cada producto.
2. `.map()` recorre cada producto y construye un nuevo arreglo solo con los nombres.

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

* Las funciones flecha permiten escribir funciones más cortas.
* Si la función solo tiene un parámetro, no se necesitan paréntesis.
* Si solo retorna una expresión, se pueden omitir las llaves `{}` y la palabra `return`.
* `.filter()` y `.map()` funcionan igual con funciones flecha, pero el código resulta más limpio.
