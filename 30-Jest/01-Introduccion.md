Aquí tienes una versión mejorada y más clara de la documentación:

# Introducción a Jest en JavaScript

## Instalación

```powershell
npm i -D jest
```

Este comando instala **Jest** como dependencia de desarrollo en tu proyecto.

## Configuración

```json
// package.json
"scripts": {
  "test": "jest"
}
```

Con esto puedes ejecutar pruebas usando el comando `npm test`.

## Ejecución de pruebas

```powershell
npm test
```

Esto iniciará Jest y buscará automáticamente los archivos de prueba en tu proyecto.

## Ejemplo de prueba básica

```js
// __tests__/holamundo.js

describe('Grupo de pruebas', () => {
  test('Hola Mundo', () => {})

  test('Otro hola Mundo', () => {})
})
```

En este ejemplo:

* `describe` agrupa un conjunto de pruebas relacionadas.
* `test` define un caso de prueba individual.