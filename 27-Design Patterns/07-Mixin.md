# Patrón Mixin en JavaScript

## Explicación del concepto

El **patrón Mixin** permite **compartir funcionalidades entre distintas clases** sin necesidad de herencia directa. Un Mixin es un objeto que contiene métodos o propiedades que pueden ser añadidos a otros prototipos u objetos, extendiendo su comportamiento.

## Ejemplo explicado

En el código:

1. Se definen dos clases: `Persona` y `Cliente`, ambas con propiedades `nombre` y `email`.

2. Se crea el objeto `funcionesPersona`, que actúa como un **mixin**.

   * Contiene dos métodos: `mostrarInformacion` y `mostrarNombre`.

3. Con `Object.assign`, se copian las funciones de `funcionesPersona` a los prototipos de `Persona` y `Cliente`.

   * Esto significa que ambos tipos de objetos podrán usar esos métodos, aunque no exista relación de herencia entre ellos.

4. Al instanciar `persona` y `cliente`, ambos objetos pueden llamar a los métodos agregados por el mixin.

## Salida

```txt
Persona { nombre: 'César', email: 'cesar@correo.com' }
Nombre Persona: César | Email: cesar@correo.com
Mi nombre es César
Persona { nombre: 'Gael', email: 'gael@correo.com' }
Nombre Persona: Gael | Email: gael@correo.com
Mi nombre es Gael
```

## Concepto clave

* Un **mixin** es una forma de reutilizar código compartiendo métodos entre diferentes clases.
* Se implementa copiando propiedades y funciones en el prototipo de cada clase.
* A diferencia de la herencia, los mixins permiten extender varias clases sin depender de jerarquías rígidas.
