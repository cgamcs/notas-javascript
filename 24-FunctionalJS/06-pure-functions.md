# Funciones Puras en JavaScript

## Explicación del concepto

Una **función pura** es aquella que:

1. Siempre devuelve el mismo resultado si recibe los mismos argumentos.
2. No modifica valores externos ni depende de ellos.

Esto las hace predecibles y fáciles de probar.

## Ejemplo explicado

```js
const numero1 = 20
const duplicar = numero => numero * 2

const resultado = duplicar(numero1)

console.log(resultado)
console.log(numero1)
```

1. Se define `numero1` con valor `20`.
2. La función `duplicar` recibe un número y devuelve su valor multiplicado por `2`.
3. Se llama a `duplicar(numero1)` y se guarda en `resultado`.
4. Se imprime `resultado` y también `numero1`.

## Salida

```js
40
20
```

## Concepto clave

* Una función pura no altera el estado externo.
* El mismo input siempre produce el mismo output.
* `numero1` no se modifica, lo que confirma la pureza de la función.
