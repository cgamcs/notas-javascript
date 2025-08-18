# Event Loop en JavaScript

## Explicación del concepto

El **Event Loop** en JavaScript administra la ejecución de tareas en un único hilo dividiéndolas en:

* **Síncronas**: se ejecutan de inmediato en orden de aparición.
* **Asíncronas**: se delegan a la cola de tareas (macrotasks y microtasks) y se ejecutan después de las síncronas.

  * **setTimeout** → entra en la cola de *macrotasks*.
  * **Promises (`.then`)** → entran en la cola de *microtasks*, que tienen prioridad sobre las *macrotasks*.

## Ejemplo explicado

Código:

```js
console.log('Primero')

setTimeout(() => {
    console.log('Segundo')
}, 0);

console.log('Tercero')

setTimeout(() => {
    console.log('Cuarto')
}, 0);

new Promise(function(resolve) {
    resolve('Definiendo...')
}).then(console.log)

console.log('Ultimo')

function hola() {
    console.log("Hola")
}
hola()
```

1. **`console.log('Primero')`** → síncrono, imprime **"Primero"**.
2. **`setTimeout(..., 0)`** → se agenda en la cola de *macrotasks*.
3. **`console.log('Tercero')`** → síncrono, imprime **"Tercero"**.
4. Otro **`setTimeout(..., 0)`** → también se agenda en *macrotasks*.
5. **`new Promise(...).then(...)`** → se resuelve de inmediato, pero el `.then` va a la cola de *microtasks*.
6. **`console.log('Ultimo')`** → síncrono, imprime **"Ultimo"**.
7. **`hola()`** → síncrono, imprime **"Hola"**.
8. Event Loop revisa la cola → primero *microtasks* → imprime **"Definiendo..."**.
9. Luego ejecuta las *macrotasks* en orden → imprime **"Segundo"** y luego **"Cuarto"**.

## Salida esperada

```
Primero
Tercero
Ultimo
Hola
Definiendo...
Segundo
Cuarto
```

## Concepto clave

* **Orden de ejecución**: código síncrono → *microtasks* → *macrotasks*.
* `Promise.then` siempre se ejecuta antes que cualquier `setTimeout` aunque tengan `0 ms`.
* El **Event Loop** asegura que JavaScript no se bloquee y ejecute tareas de manera ordenada en un solo hilo.
