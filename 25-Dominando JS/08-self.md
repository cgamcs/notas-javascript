# Uso de `self` en JavaScript

## Explicación del concepto

En JavaScript, `self` puede tener dos significados según el contexto:

1. **En el navegador**, `self` es un alias del objeto global `window`.
2. **Dentro de métodos**, algunos desarrolladores usan una variable local llamada `self` para guardar la referencia de `this`, evitando que se pierda dentro de funciones anidadas.

## Ejemplo explicado

Código:

```js
self.onload = () => {
    console.log('Ventana Lista')
}
```

* Aquí `self` es lo mismo que `window`.
* Cuando la ventana termina de cargar, imprime: **"Ventana Lista"**.

```js
window.nombre = "Gael"

const producto = {
    nombre: "Television de 20 Pulgadas",
    precio: 20,
    mostrarInfo() {
        const self = this
        console.log(`El nombre del producto es ${self.nombre} y el precio es de ${self.precio}`)
    }
}
```

* `producto.mostrarInfo()` guarda `this` en `self`.
* `self` apunta al objeto `producto`.
* Imprime: **"El nombre del producto es Television de 20 Pulgadas y el precio es de 20"**.

```js
const cliente = {
    mosrtarCliente() {
        console.log(`El nombre del cliente es ${self.nombre}`)
    }
}
```

* Aquí no se declara ninguna variable `self` dentro del método.
* Por tanto, `self` hace referencia al objeto global (`window`).
* Como se definió `window.nombre = "Gael"`, imprime: **"El nombre del cliente es Gael"**.

## Salida esperada

```
Ventana Lista
El nombre del producto es Television de 20 Pulgadas y el precio es de 20
El nombre del cliente es Gael
```

## Concepto clave

* `self` en navegadores es un alias de `window`.
* Guardar `this` en una variable `self` era una técnica común antes de `=>` (arrow functions).
* Si no se redefine, `self` apunta siempre al objeto global.
