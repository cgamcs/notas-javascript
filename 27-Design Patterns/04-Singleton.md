# Patrón Singleton en JavaScript

## Explicación del concepto

El **patrón Singleton** es un diseño que garantiza que una clase solo tenga **una única instancia** en todo el programa. Además, proporciona un punto de acceso global a esa instancia. Esto es útil cuando se necesita un único objeto que controle cierta lógica central (ejemplo: configuración, conexión a base de datos, manejador de logs).

## Ejemplo explicado

En el código:

1. Se declara una variable externa `instancia = null`. Esta variable guarda la referencia al único objeto creado.
2. La clase `Persona` recibe `nombre` y `email` en el constructor.
3. Al crear un objeto:

   * Si `instancia` es `null`, se asignan los valores recibidos y se guarda la referencia del objeto en `instancia`.
   * Si `instancia` ya existe, en lugar de crear un nuevo objeto, se devuelve la instancia existente.
4. Esto asegura que siempre exista **una sola persona compartida**, aunque se intente crear más.

## Salida

```txt
Persona { nombre: 'César', email: 'cesar@correo.com' }
Persona { nombre: 'César', email: 'cesar@correo.com' }
```

La segunda creación ignora los nuevos datos y devuelve el mismo objeto creado primero.

## Concepto clave

* El patrón Singleton restringe la creación de objetos a una sola instancia.
* Útil cuando se requiere un único punto de control.
* En JavaScript, se implementa utilizando variables externas al constructor y devolviendo siempre la misma referencia.
