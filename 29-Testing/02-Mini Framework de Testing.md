# Mini Framework de Testing en JavaScript

## Explicación del concepto

Este código implementa un **mini framework de testing** en JavaScript. El objetivo es simular el comportamiento básico de librerías de testing como **Jest**, permitiendo comprobar si los resultados obtenidos en una función coinciden con los esperados. Se incluyen funciones para realizar aserciones (`toBe`, `toEqual`) y una utilidad (`test`) para ejecutar pruebas con mensajes descriptivos.

## Ejemplo explicado

1. Se definen funciones simples:

   * `suma(a, b)`: devuelve la suma de `a + b`.
   * `restar(a, b)`: devuelve la resta de `a - b`.
   * `sumaAsync(a, b)`: versión asíncrona de `suma` que devuelve una *Promise*.

2. Se realizan pruebas directas:

   ```js
   let resultado = suma(1, 2)      // resultado = 3
   let esperado = 4

   expected(esperado).toBe(resultado)   // Falla, porque 3 !== 4
   expected(esperado).toEqual(resultado) // También falla
   ```

   Después:

   ```js
   resultado = restar(10, 5)      // resultado = 5
   esperado = 5

   expected(esperado).toBe(resultado)   // Pasa, 5 === 5
   expected(esperado).toEqual(resultado) // Pasa
   ```

3. Se ejecuta una prueba asíncrona con `test`:

   ```js
   test('Suma 10 + 20 y el resultado debe ser 30', async () => {
       const resultado = await sumaAsync(10, 20)  // resultado = 30
       const esperado = 30
       expected(esperado).toBe(resultado)         // Pasa
   })
   ```

4. La función `expected(valorEsperado)` retorna un objeto con dos métodos:

   * `toBe(resultado)`: compara con `!==`.
   * `toEqual(resultado)`: también compara con `!==` (igualdad estricta en este caso).

5. La función `test(mensaje, callback)` maneja la ejecución de pruebas asíncronas y muestra en consola si la prueba fue exitosa o falló.

## Salida

* Cuando la prueba falla:

  ```
  toBe: El 3 es diferente de lo esperado; la prueba no paso
  ```
* Cuando la prueba pasa:

  ```
  toBe: La prueba paso correctamente
  El Test: Suma 10 + 20 y el resultado debe ser 30 se ejecuto correctamente
  ```

## Concepto clave

* Un **framework de pruebas** valida que el código produzca los resultados esperados.
* `toBe` y `toEqual` en este ejemplo hacen la misma verificación (`!==`).
* `test` organiza y ejecuta pruebas, soportando funciones asíncronas.
* Este patrón es la base de herramientas más avanzadas como **Jest**.

## Código

```js
// Probar dos valores

function suma(a, b) {
    return a + b
}

function restar(a, b) {
    return a - b
}

async function sumaAsync(a, b) {
    return Promise.resolve( suma(a, b) )
}

let resultado = suma(1,2)
let esperado = 4

expected(esperado).toBe(resultado)
expected(esperado).toEqual(resultado)

resultado = restar(10, 5)
esperado = 5

expected(esperado).toBe(resultado)
expected(esperado).toEqual(resultado)

test('Suma 10 + 20 y el resultado debe ser 30', async () => {
    const resultado = await sumaAsync(10, 20)
    const esperado = 30
    expected(esperado).toBe(resultado)
})

async function test(mensaje, callback) {
    try {
        await callback()
        console.log(`El Test: ${mensaje} se ejecuto correctamente`)
    } catch (error) {
        console.error('Error:')
        console.error(error)
    }
}

function expected(esperado) {
    return {
        toBe(resultado) {
            if (resultado !== esperado) {
                console.error(`toBe: El ${resultado} es diferente de lo esperado; la prueba no paso`)
            } else {
                console.log('toBe: La prueba paso correctamente')
            }
        },
        toEqual(resultado){
            if (resultado !== esperado) {
                console.error(`toEqual: El ${resultado} no es igual a lo esperado; la prueba no paso`)
            } else {
                console.log('toEqual: La prueba paso correctamente')
            }
        }
    }
}
```