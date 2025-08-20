# Patrón Mediator en JavaScript

## Explicación del concepto

El **patrón Mediator** define un objeto central que controla la comunicación entre múltiples objetos. En lugar de que los objetos interactúen directamente entre sí, se comunican a través del mediador. Esto reduce dependencias directas y facilita la coordinación.

## Ejemplo explicado

En el código:

1. Se define la clase `Vendedor`:

   * Tiene `oferta(articulo, precio)` para iniciar la subasta.
   * Tiene `vendido(comprador)` para anunciar el ganador.

2. Se define la clase `Comprador`:

   * Tiene `oferta(cantidad, comprador)` para hacer una oferta en la subasta.

3. La función `Subasta` actúa como **mediador**:

   * Contiene un registro de todos los usuarios (`compradores` y `vendedores`).
   * El método `registrar(usuario)` agrega al usuario a la subasta y establece la referencia `sala`.

4. Se crean los objetos: dos compradores (`César` y `Gael`), un vendedor, y la sala de subasta.

   * Todos se registran en la subasta mediante `subasta.registrar(...)`.

5. Flujo de ejecución:

   * El vendedor abre la subasta del “Mustang 86” en 300.
   * Los compradores ofrecen diferentes cantidades.
   * Finalmente, el vendedor marca el artículo como vendido a Gael.

## Salida

```txt
La subasta se abre con un Mustang 86 empezando desde 300
César: 300
Gael: 350
César: 500
Gael: 700
Vendido a Gael
```

## Concepto clave

* El patrón Mediator centraliza la comunicación en un único objeto (la subasta en este caso).
* Evita dependencias directas entre objetos, lo que mejora la flexibilidad.
* Es útil cuando múltiples objetos deben interactuar de forma coordinada.
