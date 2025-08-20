# Clases en JavaScript

## Explicación del concepto

En JavaScript, una **clase** es una plantilla para crear objetos con propiedades y métodos predefinidos. Permite organizar y reutilizar código de forma más clara que con funciones constructoras.

## Ejemplo explicado

```js
// Definición de la clase
class Persona {
    constructor(nombre, email) {
        this.nombre = nombre   // asigna el valor recibido a la propiedad "nombre"
        this.email = email     // asigna el valor recibido a la propiedad "email"
    }
}

// Creación de un objeto de la clase Persona
const persona = new Persona('César', 'cesar@correo.com')

// Mostrar el objeto en consola
console.log(persona)
```

1. Se define la clase `Persona` con un **constructor** que recibe dos parámetros: `nombre` y `email`.
2. Dentro del constructor, `this.nombre` y `this.email` se asignan a las propiedades del objeto.
3. Se crea una nueva instancia con `new Persona('César', 'cesar@correo.com')`.
4. La instancia resultante es un objeto con las propiedades definidas en la clase.

## Salida

```js
Persona { nombre: 'César', email: 'cesar@correo.com' }
```

## Concepto clave

* Una **clase** define cómo se construyen objetos de un mismo tipo.
* El **constructor** inicializa las propiedades de cada objeto.
* Para crear instancias se usa la palabra clave **new**.

¿Quieres que agregue también un ejemplo extendido con **métodos dentro de la clase** para que quede más completo?
