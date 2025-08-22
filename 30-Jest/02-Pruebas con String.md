# Pruebas de Strings con Jest

```js
const password = "123456"

describe('Valida que el password no este vacio y tenga una extensión de 6 caracteres', () => {
    test('Password con 6 caracteres', () => {
        expect(password).toHaveLength(6)
    })

    test('Password no esta vacio', () => {
        expect(password).not.toHaveLength(0)
    })
})
```

## Explicación del concepto

Jest permite verificar propiedades de cadenas de texto (strings) mediante **matchers** como `toHaveLength`. Esto se usa para comprobar que una cadena tenga la longitud esperada o que no esté vacía.

## Ejemplo explicado

```js
// Probando Strings
const password = "123456"

describe('Valida que el password no este vacio y tenga una extensión de 6 caracteres', () => {
    test('Password con 6 caracteres', () => {
        expect(password).toHaveLength(6)
    })

    test('Password no esta vacio', () => {
        expect(password).not.toHaveLength(0)
    })
})
```

* Se define la constante `password` con el valor `"123456"`.
* `describe` agrupa las pruebas bajo la misma descripción.
* Primer test: `expect(password).toHaveLength(6)` verifica que la cadena tenga 6 caracteres.
* Segundo test: `expect(password).not.toHaveLength(0)` asegura que la cadena no esté vacía.

## Salida

Si se ejecuta con `npm test`, Jest mostrará que ambos tests pasan correctamente:

```
 PASS  __tests__/password.test.js
  Valida que el password no este vacio y tenga una extensión de 6 caracteres
    ✓ Password con 6 caracteres (5 ms)
    ✓ Password no esta vacio (1 ms)
```

## Concepto clave

* `toHaveLength(n)`: comprueba la longitud de un string o array.
* `.not`: invierte la condición de la expectativa.
* Los tests permiten asegurar reglas de negocio como validación de contraseñas.
