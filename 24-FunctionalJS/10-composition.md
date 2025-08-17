# Composición de Funciones y Objetos en JavaScript

## Explicación del concepto

La **composición** es una técnica que consiste en combinar funciones pequeñas y específicas para construir objetos o funcionalidades más complejas.
En lugar de usar herencia clásica, se crean **módulos reutilizables** que se asignan dinámicamente a distintos objetos.

## Ejemplo explicado

```js
const obtenerNombre = info => ({
    mostrarNombre() {
        console.log(`Nombre: ${info.nombre}`)
    }
})
```

* Define un módulo que agrega un método `mostrarNombre` al objeto.

```js
const guardarEmail = info => ({
    agregarEmail(email) {
        console.log(`Guardando email en: ${info.nombre}`)
        info.email = email
    }
})
```

* Permite guardar y asociar un email a un objeto.

```js
function Cliente(nombre, email, empresa) {
    let info = { nombre, email, empresa }

    return Object.assign(
        info,
        obtenerNombre(info),
        guardarEmail(info),
        obtenerEmail(info),
        obtenerEmpresa(info)
    )
}
```

* `Cliente` construye un objeto base `info` con `nombre, email, empresa`.
* Usa `Object.assign` para **componer** ese objeto con las funciones auxiliares.

```js
function Empleado(nombre, email, puesto) {
    let info = { nombre, email, puesto }

    return Object.assign(
        info,
        obtenerNombre(info),
        guardarEmail(info),
        obtenerEmail(info),
        obtenerPuesto(info)
    )
}
```

* Similar a `Cliente`, pero en vez de `empresa` agrega el módulo `obtenerPuesto`.

### Uso en ejecución

```js
const cliente = Cliente('César', null, 'ProfeScore')
cliente.mostrarNombre()               // Nombre: César
cliente.agregarEmail('cliente@corre.com')
cliente.mostrarEmail()                // Correo: cliente@corre.com
cliente.mostrarEmpresa()              // Empresa: ProfeScore
```

```js
const empleado = Empleado('Gael', null, 'Programador')
empleado.mostrarNombre()              // Nombre: Gael
empleado.agregarEmail('empleado@corre.com')
empleado.mostrarEmail()               // Correo: empleado@corre.com
empleado.mostrarPuesto()              // Puesto: Programador
```

## Salida

```js
Nombre: César
Guardando email en: César
Correo: cliente@corre.com
Empresa: ProfeScore
---------------
Nombre: Gael
Guardando email en: Gael
Correo: empleado@corre.com
Puesto: Programador
```

## Concepto clave

* La **composición** combina pequeños módulos de comportamiento en objetos más complejos.
* Evita la rigidez de la **herencia clásica** y fomenta la **reutilización de código**.
* `Object.assign` permite fusionar varios objetos en uno, creando objetos dinámicos con capacidades específicas.
