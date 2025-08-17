# Closures en JavaScript

## Explicación del concepto

Un **closure** ocurre cuando una función interna recuerda y accede a las variables de su función externa, incluso después de que la función externa haya terminado de ejecutarse.

## Ejemplo explicado

```js
const obtenerCliente = () => {
    const nombre = "Gael"

    function muestraNombre() {
        console.log(nombre)
    }

    return muestraNombre
}

const cliente = obtenerCliente()

cliente()
```

1. `obtenerCliente` define una variable local `nombre = "Gael"`.
2. Dentro de `obtenerCliente`, se declara la función `muestraNombre` que imprime `nombre`.
3. `obtenerCliente` retorna la función `muestraNombre`.
4. Cuando se ejecuta `obtenerCliente()`, se guarda en `cliente` la función retornada.
5. Aunque `obtenerCliente` ya terminó su ejecución, al llamar `cliente()`, la función aún recuerda el valor de `nombre`.

## Salida

```js
Gael
```

## Concepto clave

* Un closure es una función interna que **conserva acceso a las variables** de su entorno.
* Permite encapsular datos y protegerlos del acceso externo directo.
* Se usa en patrones como **encapsulación, funciones privadas y creación de fábricas de funciones**.
