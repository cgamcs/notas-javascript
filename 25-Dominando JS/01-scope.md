# Scope en JavaScript

## Explicación del concepto

**Scope** (ámbito) en JavaScript define el alcance o la accesibilidad de las variables en distintas partes del código. Existen principalmente dos tipos:

* **Scope global**: variables accesibles desde cualquier parte del programa.
* **Scope local o de bloque**: variables declaradas dentro de una función o bloque (`{}`) solo existen ahí y no afectan a variables con el mismo nombre fuera de ese ámbito.

## Ejemplo explicado

En el código dado:

```js
const login = true
const cliente = "Cesar"

function mostrarCliente() {
    const cliente = "Gael"
    console.log(cliente) // imprime "Gael"
}

function clienteLogueado() {
    const cliente = "Pedro"
    console.log(cliente) // imprime "Pedro"

    if(login) {
        const cliente = "Admin"
        console.log(cliente) // imprime "Admin"
    }
}

console.log(cliente) // imprime "Cesar"

mostrarCliente()
clienteLogueado()
```

* Se define `cliente = "Cesar"` en el scope global.
* `console.log(cliente)` fuera de funciones imprime **"Cesar"**.
* La función `mostrarCliente()` crea una nueva variable local `cliente = "Gael"`, que **oculta** la global dentro de la función. Imprime **"Gael"**.
* La función `clienteLogueado()` crea otra variable local `cliente = "Pedro"`. Imprime **"Pedro"**.
* Dentro del `if`, se declara `cliente = "Admin"`, solo válido en ese bloque. Imprime **"Admin"**.

## Salida

El resultado de ejecutar el programa es:

```
Cesar
Gael
Pedro
Admin
```

## Concepto clave

* Variables con el mismo nombre pueden coexistir en distintos scopes sin interferir.
* `const` y `let` respetan el **scope de bloque**.
* El **scope más cercano** tiene prioridad al acceder a una variable.
