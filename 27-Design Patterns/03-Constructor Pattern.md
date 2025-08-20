# Patrón Constructor en JavaScript

## Explicación del concepto

El **patrón constructor** permite crear múltiples objetos con una misma estructura mediante clases. En JavaScript, las clases pueden heredar de otras usando la palabra clave **extends**, lo que facilita la reutilización de código y la creación de jerarquías.

## Ejemplo explicado

```js
// Clase base
class Persona {
    constructor(nombre, email) {
        this.nombre = nombre    // propiedad nombre
        this.email = email      // propiedad email
    }
}

// Clase que hereda de Persona
class Cliente extends Persona {
    constructor(nombre, email, empresa) {
        super(nombre, email)    // llama al constructor de la clase Persona
        this.empresa = empresa  // nueva propiedad exclusiva de Cliente
    }
}

// Creación de un objeto de la clase Persona
const persona = new Persona('César', 'cesar@correo.com')
console.log(persona)

// Creación de un objeto de la clase Cliente
const cliente = new Cliente('Gael', 'gael@gmail.com', 'ProfeScore')
console.log(cliente)
```

1. `Persona` es la clase base con dos propiedades: `nombre` y `email`.
2. `Cliente` extiende de `Persona` usando `extends`.
3. En el constructor de `Cliente`, la llamada a `super(nombre, email)` invoca el constructor de `Persona` para inicializar esas propiedades.
4. `Cliente` añade una propiedad extra: `empresa`.
5. Se crean dos instancias: una de `Persona` y otra de `Cliente`.

## Salida

```js
Persona { nombre: 'César', email: 'cesar@correo.com' }
Cliente { nombre: 'Gael', email: 'gael@gmail.com', empresa: 'ProfeScore' }
```

## Concepto clave

* El **patrón constructor** usa clases para crear objetos con propiedades inicializadas.
* `extends` permite heredar de otra clase.
* `super` ejecuta el constructor de la clase padre antes de usar `this`.
* Una subclase puede añadir propiedades o métodos adicionales sin duplicar código.

¿Quieres que te muestre cómo agregar **métodos** en estas clases para diferenciar comportamientos entre `Persona` y `Cliente`?