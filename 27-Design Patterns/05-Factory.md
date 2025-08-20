# Patrón Factory en JavaScript

## Explicación del concepto

El **patrón Factory** es un diseño que permite **crear objetos sin exponer la lógica de creación al cliente**, delegando esta tarea a un método especial (la "fábrica"). Se utiliza cuando se requiere instanciar objetos de una misma familia con variaciones en sus propiedades o comportamiento.

## Ejemplo explicado

En el código:

1. La clase `InputHTML` define un objeto que representa un `<input>` de HTML, con propiedades `type` y `nombre`.

   * Su método `crearInput()` devuelve el elemento HTML en forma de cadena.

2. La clase `HTMLFactory` contiene el método `crearElemento(type, nombre)` que decide qué tipo de `InputHTML` instanciar:

   * Si `type` es `'text'`, crea un input de texto.
   * Si es `'tel'`, crea un input de teléfono.
   * Si es `'email'`, crea un input de correo electrónico.

3. Al llamar a `crearElemento`, no se necesita saber cómo se construye el objeto. La fábrica se encarga de devolver la instancia adecuada.

4. En los `console.log`, cada objeto generado produce su representación en HTML.

## Salida

```txt
<input type="text" name="nombre-cliente" id="nombre-cliente">
<input type="tel" name="telefono-cliente" id="telefono-cliente">
<input type="email" name="email-cliente" id="email-cliente">
```

## Concepto clave

* El patrón Factory centraliza la creación de objetos en un método dedicado.
* Se usa para simplificar la construcción de instancias que comparten una misma estructura pero varían en algunos parámetros.
* En este ejemplo, la fábrica genera distintos campos de formulario HTML según el tipo solicitado.
