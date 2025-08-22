# Seguridad en JavaScript

## Buenas prácticas generales

* **No almacenes contraseñas en LocalStorage** ni en SessionStorage. Estos espacios son accesibles desde el navegador y pueden ser comprometidos.
* Usa siempre `textContent` para insertar datos en el DOM, ya que evita inyecciones de código. Utiliza `innerHTML` solo cuando la fuente de datos sea completamente confiable.
* Mantén actualizado tu código y librerías para reducir riesgos de vulnerabilidades conocidas.

## Formularios

* **Valida en el cliente** con JavaScript para mejorar la experiencia del usuario, pero recuerda que esta validación **no reemplaza la validación en el servidor**, que es la capa realmente segura.
* Para autenticación de usuarios considera mecanismos seguros como **JWT (JSON Web Tokens)** o servicios externos como **Auth0** que simplifican la gestión de sesiones y tokens.

## Dependencias y librerías

* Revisa regularmente tus dependencias con herramientas como [Snyk](https://snyk.io), `npm audit` o similares para detectar vulnerabilidades.
* Descarga librerías solo desde fuentes oficiales y evita dependencias innecesarias.

## Manejo de datos sensibles

* **Nunca guardes datos críticos en el cliente.** Maneja contraseñas, claves o tokens en el servidor.
* Para almacenamiento seguro de contraseñas utiliza algoritmos de hashing como **bcrypt** o **Argon2**.
* Considera ofuscar o minimizar tu código para dificultar la ingeniería inversa, aunque recuerda que no es un mecanismo de seguridad en sí mismo.

## Concepto clave

La seguridad en JavaScript requiere una combinación de prácticas: validar tanto en cliente como en servidor, manejar datos sensibles solo en el backend, mantener dependencias seguras y minimizar los riesgos en la manipulación del DOM.