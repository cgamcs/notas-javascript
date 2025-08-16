### 🧠 Tema Principal: Functional JavaScript

### 📌 ¿Qué es Functional JavaScript?

---

Crear tu código utilizando funciones.

Pero hay ciertas reglas, básicamente las funciones deben tomar una entrada  y tener una salida de datos.

No se permite la modificación de datos.

Tiene una sintaxis más de matemáticas.

**Conceptos clave**

- Inmutabilidad - Los datos no deben modificarse (utilizar const siempre)
- Separar funciones de datos
- First-class functions

**1. Inmutabilidad**

Un datos no puede cambiarse, no puede tener esto:

```JS
let cleinte = "Juan"

cliente = "Pedro"
```

**2. Separar funciones de datos**

Se utilizan mucho funciones que retornan un nuevo dato o Array Methods, de esa forma tendremos funciones que entregan un resultado nuevo pero nunca modifican los datos.

**3. First-class functions**

Es poder crear funciones que parezcan cualquier variable como lo es function expression.

```JS
const suma = function(a, b) {
  return a + b
}

const resultado = suma
```