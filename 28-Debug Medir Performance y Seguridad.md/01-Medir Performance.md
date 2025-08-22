# Medir performance en JavaScript

```JS
function selectCriptomonedas(criptomonedas) {
    const inicio = performance.now()

    // criptomonedas.forEach( cripto => {
    //     const { FullName, Name } = cripto.CoinInfo;
    //     const option = document.createElement('option');
    //     option.value = Name;
    //     option.textContent = FullName;
    //     // insertar el HTML
    //     criptomonedasSelect.appendChild(option);
    // });

    for(let i = 0; i < criptomonedas.length; i++) {
        const { FullName, Name } = criptomonedas[i].CoinInfo;
        const option = document.createElement('option');
        option.value = Name;
        option.textContent = FullName;
        // insertar el HTML
        criptomonedasSelect.appendChild(option);
    }

    const fin = performance.now()

    console.log(fin - inicio)
}
```

## Explicación del concepto

La **API `performance`** en JavaScript permite medir el tiempo que tarda en ejecutarse un bloque de código. Es útil para comparar diferentes implementaciones y determinar cuál es más eficiente en términos de velocidad.

## Ejemplo explicado

En este código se define la función `selectCriptomonedas` que recibe un arreglo de criptomonedas y mide cuánto tarda en recorrerlo para insertar elementos en un `select` del DOM.

1. `const inicio = performance.now()`
   Guarda el tiempo inicial en milisegundos justo antes de ejecutar el bucle.

2. El comentario muestra una primera opción con `.forEach()`, pero está desactivada.
   En su lugar se usa un **bucle `for` clásico** para iterar sobre el arreglo:

   * Se accede a la información de cada criptomoneda (`FullName`, `Name`) desde `CoinInfo`.
   * Se crea un elemento `<option>`.
   * Se asignan valores al `value` y al texto visible.
   * Se inserta en el `select` del DOM.

3. `const fin = performance.now()`
   Registra el tiempo final justo después del bucle.

4. `console.log(fin - inicio)`
   Imprime en consola la diferencia entre los dos tiempos, es decir, la duración de la operación.

El comentario en el código muestra posibles resultados de las pruebas:

* Usando `.forEach()` → \~1.5 ms
* Usando `for` clásico → \~0.09 ms

## Salida

En consola aparecerá un número en milisegundos, representando el tiempo que tardó el bucle en ejecutar toda la inserción. Ejemplo:

```
0.09
```

## Concepto clave

* `performance.now()` devuelve el tiempo actual en milisegundos con alta precisión.
* Comparar diferentes estructuras de control (`for`, `forEach`, `map`, etc.) permite identificar la más rápida.
* El bucle `for` clásico suele ser más eficiente que `forEach` al trabajar con grandes colecciones.
