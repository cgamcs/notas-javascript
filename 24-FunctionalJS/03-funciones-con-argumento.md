# Funciones como Argumentos en JavaScript

### Concepto

En JavaScript, las funciones pueden recibirse como **argumentos** en otras funciones.
A este tipo de funciones se les llama **funciones de orden superior** (*higher-order functions*).
El parámetro que recibe la función es una **referencia** a otra función, que luego puede ejecutarse dentro.

---

### Ejemplo del Código

```js
// Funciones simples
const suma = (a, b) => a + b
const multiplicar = (a, b) => a * b

// Función que recibe otra función como argumento
const sumarOmultiplicar = fn => fn(10, 20)

// Llamadas
console.log(sumarOmultiplicar(suma))        // 30
console.log(sumarOmultiplicar(multiplicar)) // 200
```

---

### Análisis Paso a Paso

1. **Funciones base**

   ```js
   const suma = (a, b) => a + b
   const multiplicar = (a, b) => a * b
   ```

   * `suma`: retorna la suma de `a` y `b`.
   * `multiplicar`: retorna el producto de `a` y `b`.

2. **Función de orden superior**

   ```js
   const sumarOmultiplicar = fn => fn(10, 20)
   ```

   * `fn` es un **parámetro de tipo función**.
   * Se llama a `fn` pasándole los valores `10` y `20`.

3. **Ejecución con diferentes funciones**

   ```js
   console.log(sumarOmultiplicar(suma))        // 30
   console.log(sumarOmultiplicar(multiplicar)) // 200
   ```

   * Al pasar `suma`, la operación es `10 + 20`.
   * Al pasar `multiplicar`, la operación es `10 * 20`.

---

### Importante

* Pasar funciones como argumentos permite reutilizar código.
* Este patrón es clave en **callbacks**, **map**, **filter**, **reduce** y otros métodos de arreglos.
* La función que recibe otra función puede controlar **cuándo** y **cómo** se ejecuta.