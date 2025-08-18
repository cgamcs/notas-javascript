# New Binding y Window Binding en JavaScript

## Explicación del concepto

* **New binding**: cuando una función se invoca con `new`, se crea un nuevo objeto y `this` apunta a ese objeto. Se usa en funciones constructoras para inicializar propiedades.
* **Window binding**: si `this` no encuentra un objeto al cual hacer referencia, en modo no estricto toma como valor el objeto global (`window` en navegadores).

## Ejemplo explicado

Código:

```js
function Auto(modelo, color) {
    this.modelo = modelo
    this.color = color
}

const auto = new Auto('Camaro', 'Negro')
console.log(auto)
```

* `new Auto('Camaro', 'Negro')` crea un nuevo objeto.
* `this.modelo = modelo` asigna `"Camaro"`.
* `this.color = color` asigna `"Negro"`.
* Resultado: `{ modelo: "Camaro", color: "Negro" }`.

```js
window.color = "Negro"

function hola() {
    console.log(color)
}

hola()
```

* Se asigna `color = "Negro"` en el objeto global `window`.
* La función `hola()` imprime `color`, que se resuelve en el ámbito global.
* Resultado: `"Negro"`.

## Salida esperada

```
Auto { modelo: 'Camaro', color: 'Negro' }
Negro
```

## Concepto clave

* **New binding**: `this` se refiere al nuevo objeto creado con `new`.
* **Window binding**: si `this` no está definido en otro contexto, apunta al objeto global (`window`). En **modo estricto**, sería `undefined`.
