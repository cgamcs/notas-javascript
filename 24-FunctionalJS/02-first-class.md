# Funciones de Primera Clase en JavaScript

### Concepto

En JavaScript, las **funciones de primera clase** (*first-class functions*) son aquellas que pueden:

* Asignarse a variables o constantes.
* Pasarse como argumentos a otras funciones.
* Retornarse desde otras funciones.
* Almacenarse en estructuras de datos.

Esto significa que las funciones son tratadas como cualquier otro valor.

---

### Ejemplo del Código

```js
// Definición de una función como expresión
const suma = function(a, b) {
  return a + b
}

// Asignación de la función a otra variable
const resultado = suma

// Ejecución de la función mediante la nueva referencia
console.log(resultado(10, 20)) // 30
```

---

### Análisis Paso a Paso

1. **Función anónima asignada a una constante**

   ```js
   const suma = function(a, b) { return a + b }
   ```

   * `suma` almacena una referencia a la función.
   * No se usa `function suma()`, sino una función **anónima** asignada a una variable.

2. **Asignación de la referencia de la función a otra variable**

   ```js
   const resultado = suma
   ```

   * No se ejecuta la función aquí, solo se copia la referencia.
   * `resultado` ahora apunta a la misma función que `suma`.

3. **Invocación usando la nueva variable**

   ```js
   console.log(resultado(10,20))
   ```

   * Llama a la función original `suma` a través de `resultado`.
   * Devuelve `30`.

---

### Importante

* Asignar `resultado = suma` **no copia** la función, solo la referencia.
* Esto es posible porque en JavaScript las funciones son **objetos de primera clase**.
* Esta característica habilita patrones como *callbacks*, *funciones de orden superior* y programación funcional.