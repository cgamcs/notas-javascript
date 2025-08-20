# Patrón Módulo en JavaScript

## Explicación del concepto

El **patrón Módulo** organiza el código en bloques independientes y reutilizables, encapsulando lógica y exponiendo solo lo necesario. En JavaScript moderno se implementa con **ES Modules** usando `export` y `import`, lo que permite dividir el código en archivos más claros y mantener un mejor control de dependencias.

## Ejemplo explicado

En el código:

1. Se define una función `mostrarCliente(nombre)` que recibe un nombre y lo imprime en consola.

2. La palabra clave `export default` expone la función como el valor principal del módulo.

   * Esto permite que pueda importarse en otro archivo con cualquier nombre.

3. Ejemplo de uso en otro archivo:

   ```JS
   import mostrarCliente from './cliente.js'

   mostrarCliente('César')
   ```

   Aquí se importa la función y se ejecuta pasando el nombre como argumento.

## Salida

```txt
César
```

## Concepto clave

* El patrón Módulo encapsula funcionalidad en archivos independientes.
* `export default` permite exponer una función, clase u objeto para ser reutilizado en otros módulos.
* Facilita la organización, escalabilidad y mantenimiento del código.
