# Hoisting en JavaScript

## Explicación del concepto

**Hoisting** es el comportamiento de JavaScript en el que las **declaraciones** de variables y funciones se "elevan" al inicio de su contexto de ejecución antes de que el código se ejecute.

* Las **funciones declaradas** con `function` se pueden invocar antes de su definición.
* Las **funciones expresadas** (asignadas a variables con `const` o `let`) no se elevan de la misma forma. Solo se eleva la declaración de la variable, pero no su asignación. Si se usan antes de definirse, generan un error.

## Ejemplo explicado

En el código:

```js
obtenerNombre('Cesar')
function obtenerNombre(nombre) {
    console.log(`El nombre del cliente es ${nombre}`)
}
```

* La función `obtenerNombre` está declarada con `function`.
* Gracias al **hoisting**, se puede llamar antes de su definición.
* Imprime: **"El nombre del cliente es Cesar"**.

Luego:

```js
obtenerNombre2('Gael')
const obtenerNombre2 = function(nombre) {
    console.log(`El nombre del cliente es ${nombre}`)
}

// Lo que JS ve
const obtenerNombre2 // Para este nomento esta declarada como NULL

obtenerNombre2 = function(nombre) {
    console.log(`El nombre del cliente es ${nombre}`)
}
```

* Aquí `obtenerNombre2` es una **función expresión** almacenada en una constante.
* Durante el hoisting, la variable `obtenerNombre2` se declara pero no tiene valor asignado.
* Al intentar llamarla antes de la asignación, produce un **ReferenceError**.

## Salida esperada

```
El nombre del cliente es Cesar
ReferenceError: Cannot access 'obtenerNombre2' before initialization
```

## Concepto clave

* **Declaraciones de funciones (`function`)** se elevan completas y se pueden usar antes de definirlas.
* **Expresiones de funciones (`const`, `let`)** solo elevan la variable, no la asignación. No se pueden invocar antes.
* El **hoisting** ayuda a entender por qué algunas funciones funcionan antes de definirse y otras no.
