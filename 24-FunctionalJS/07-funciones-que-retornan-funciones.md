# Funciones que Retornan Otras Funciones en JavaScript

## Explicación del concepto

En JavaScript, una función puede **retornar otra función**. Esto se conoce como **función de orden superior** y permite crear funciones dinámicas, reutilizables o configurables.

## Ejemplo explicado

```js
const obtenerCliente = () => () => console.log("Gael")

const fn = obtenerCliente()

fn()
```

1. `obtenerCliente` es una función flecha que retorna otra función.
2. La función interna, al ejecutarse, muestra `"Gael"` en consola.
3. Al llamar `obtenerCliente()`, no imprime nada aún, solo devuelve la función interna.
4. Esa función retornada se guarda en `fn`.
5. Finalmente, al ejecutar `fn()`, se imprime `"Gael"`.

## Salida

```js
Gael
```

## Concepto clave

* Una función puede devolver otra función.
* Esto permite **crear closures**: funciones internas que pueden usar datos del contexto donde fueron creadas.
* Es útil para **encapsular lógica** o generar funciones personalizadas a partir de otras.
