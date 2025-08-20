# Patrón Constructor en JavaScript

## Explicación del concepto

El **patrón Constructor** es un diseño que permite crear objetos de manera estructurada utilizando funciones constructoras o clases. Define cómo se inicializan las propiedades de un objeto y, en combinación con la herencia, permite extender y reutilizar código.

## Ejemplo explicado

En el código:

1. La clase `Persona` actúa como constructor base.

   * Recibe `nombre` y `email` en el constructor y los asigna al objeto.

2. La clase `Cliente` extiende a `Persona`.

   * Usa `super(nombre, email)` para llamar al constructor de la clase padre y heredar esas propiedades.
   * Añade una nueva propiedad `empresa` específica de los clientes.

3. Se crea un objeto `persona` con la clase `Persona`.

4. Se crea un objeto `cliente` con la clase `Cliente`, que incluye tanto las propiedades heredadas como la adicional.

## Salida

```txt
Persona { nombre: 'César', email: 'cesar@correo.com' }
Cliente { nombre: 'Gael', email: 'gael@gmail.com', empresa: 'ProfeScore' }
```

## Concepto clave

* El patrón Constructor define cómo inicializar un objeto con propiedades específicas.
* La herencia permite crear constructores más especializados basados en otros.
* `super` se utiliza en clases hijas para reutilizar la inicialización del padre.
