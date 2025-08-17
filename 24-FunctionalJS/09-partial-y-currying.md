# Partial Application y Currying en JavaScript

## Explicación del concepto

* **Currying**: transformar una función que recibe varios parámetros en una serie de funciones que reciben un parámetro cada una.
* **Partial Application**: fijar uno o varios argumentos de una función para obtener una nueva función más específica.

Ambos conceptos permiten reutilizar funciones y componerlas de manera flexible.

## Ejemplo explicado

```js
const suma = (a, b, c) => a + b + c

const parcial = a => b => c => suma(a, b, c)

const primerNumero = parcial(5)
const segundoNumero = primerNumero(3)
const resultado = segundoNumero(2)

console.log(resultado)

const resultadoParcial = parcial(5)(3)(2)

console.log(resultadoParcial)
```

1. `suma` es una función normal que recibe tres parámetros y devuelve su suma.
2. `parcial` es una versión curried de `suma`: recibe un argumento `a` y devuelve otra función que recibe `b`, y otra que recibe `c`.
3. `const primerNumero = parcial(5)` fija el valor `a = 5`.
4. `const segundoNumero = primerNumero(3)` fija el valor `b = 3`.
5. `const resultado = segundoNumero(2)` aplica el último valor `c = 2` y ejecuta la suma `5 + 3 + 2 = 10`.
6. La llamada encadenada `parcial(5)(3)(2)` hace lo mismo en una sola línea.

## Salida

```js
10
10
```

## Concepto clave

* **Currying** convierte funciones de múltiples parámetros en funciones de un parámetro.
* **Partial application** permite fijar argumentos para crear funciones más especializadas.
* Esto mejora la **reutilización de funciones** y facilita la **composición funcional**.
