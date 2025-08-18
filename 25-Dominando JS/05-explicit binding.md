# Explicit Binding en JavaScript

## Explicación del concepto

**Explicit binding** ocurre cuando se fuerza a que una función use un objeto específico como su `this`, mediante los métodos **`call`**, **`apply`** y **`bind`**.

* `call(obj, arg1, arg2, ...)` → ejecuta la función inmediatamente pasando argumentos separados.
* `apply(obj, [args])` → ejecuta la función inmediatamente pasando los argumentos en un arreglo.
* `bind(obj, arg1, arg2, ...)` → devuelve una nueva función con `this` vinculado al objeto dado, pero no la ejecuta automáticamente.

## Ejemplo explicado

Código:

```js
function persona(el1, el2) {
    console.log(`Mi nombre es ${this.nombre} y escucho ${el1} y ${el2}`)
}

const informacion = {
    nombre: "Cesar"
}

const musica = ["Pop", "Rap"]

persona.call(informacion, musica[0], musica[1])
persona.apply(informacion, musica)
const nuevaFn = persona.bind(informacion, musica[0], musica[1])
nuevaFn()
```

1. **`call`**

   * `persona.call(informacion, "Pop", "Rap")`.
   * `this` apunta a `informacion`.
   * Resultado: **"Mi nombre es Cesar y escucho Pop y Rap"**.

2. **`apply`**

   * `persona.apply(informacion, ["Pop", "Rap"])`.
   * Similar a `call`, pero recibe los argumentos en un array.
   * Resultado: **"Mi nombre es Cesar y escucho Pop y Rap"**.

3. **`bind`**

   * `persona.bind(informacion, "Pop", "Rap")` devuelve una nueva función.
   * Al ejecutar `nuevaFn()`, se usa `informacion` como `this`.
   * Resultado: **"Mi nombre es Cesar y escucho Pop y Rap"**.

## Salida esperada

```
Mi nombre es Cesar y escucho Pop y Rap
Mi nombre es Cesar y escucho Pop y Rap
Mi nombre es Cesar y escucho Pop y Rap
```

## Concepto clave

* **`call` y `apply`** ejecutan la función de inmediato, cambiando el valor de `this`.
* **`bind`** no ejecuta la función, solo devuelve una nueva con `this` ligado al objeto.
* `apply` es útil cuando ya tienes los argumentos en un array.
