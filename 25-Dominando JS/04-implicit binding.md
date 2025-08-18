# Implicit Binding en JavaScript

## Explicación del concepto

**Implicit binding** ocurre cuando una función se ejecuta como un método de un objeto. En este caso, la palabra clave `this` hace referencia al objeto que está a la izquierda del punto (`.`) en la llamada.

## Ejemplo explicado

Código:

```js
const usario = {
    nombre: "Cesar",
    edad: 21,
    informacion() {
        console.log(`Mi nombre es ${this.nombre} y mi edad es ${this.edad}`)
    },
    mascota: {
        nombre: "Simba",
        edad: 4,
        informacion() {
            console.log(`Mi nombre es ${this.nombre} y mi edad es ${this.edad}`)
        }
    }
}

usario.informacion()
usario.mascota.informacion()
```

1. `usario.informacion()`

   * `this` apunta al objeto `usario`.
   * Imprime: **"Mi nombre es Cesar y mi edad es 21"**.

2. `usario.mascota.informacion()`

   * `this` apunta al objeto `mascota`.
   * Imprime: **"Mi nombre es Simba y mi edad es 4"**.

## Salida esperada

```
Mi nombre es Cesar y mi edad es 21
Mi nombre es Simba y mi edad es 4
```

## Concepto clave

* En **implicit binding**, `this` siempre se refiere al objeto desde el cual se invoca el método.
* El valor de `this` depende del **contexto de ejecución**, no de dónde se define la función.
