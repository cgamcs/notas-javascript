# Coerción en JavaScript

## Explicación del concepto

**Coerción** es la conversión de un tipo de dato a otro en JavaScript. Puede ser:

* **Implícita**: el motor de JS convierte automáticamente un valor.
* **Explícita**: el programador convierte el tipo usando funciones o métodos.

## Ejemplo explicado

En el código:

```js
const numero1 = 20
const numero2 = "40"

console.log(numero1 + numero2) // Implicita
```

* `numero1` es número y `numero2` es string.
* El operador `+` fuerza la conversión implícita a string.
* Resultado: `"2040"` (concatenación).

```js
console.log(Number(numero2)) // Explicita
```

* Se convierte explícitamente `"40"` en número con `Number()`.
* Resultado: `40`.

```js
console.log(numero1.toString())
```

* Convierte explícitamente el número `20` en string `"20"`.

```js
const pedido = [1, 2, 3]

console.log(pedido.toString())
```

* El arreglo `[1, 2, 3]` se convierte implícitamente a string.
* Resultado: `"1,2,3"`.

```js
console.log(JSON.stringify(pedido))
```

* Convierte explícitamente el arreglo en un string JSON.
* Resultado: `"[1,2,3]"`.

## Salida esperada

```
2040
40
20
1,2,3
[1,2,3]
```

## Concepto clave

* **Implícita**: conversión automática según contexto (`+` con string convierte a texto).
* **Explícita**: conversión intencional con funciones (`Number()`, `.toString()`, `JSON.stringify()`).
* Comprender la coerción evita errores en operaciones entre tipos diferentes.
