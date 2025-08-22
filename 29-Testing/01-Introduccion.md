# Testing en JavaScript

## Ventajas de hacer Testing

* Mejora la calidad del software al reducir la aparición de bugs.
* Probar manualmente todos los escenarios es costoso; las herramientas de testing automatizan este proceso.
* Permite liberar nuevas versiones con mayor confianza en la estabilidad del proyecto.

## Consideraciones con el Testing

* Al agregar nuevas funciones en un proyecto existente, las pruebas ayudan a confirmar que lo anterior sigue funcionando correctamente.
* Facilita el trabajo de nuevos desarrolladores, ya que las pruebas documentan el comportamiento esperado de cada parte.
* No es necesario probar absolutamente todo, lo importante es verificar cómo se integran las diferentes partes de la aplicación.

## Diferentes tipos de Testing

* **End to End (E2E):** Simula la interacción del usuario, como clicks y formularios, para verificar que la interfaz muestre lo esperado.
* **Integración:** Comprueba que varios módulos funcionen correctamente al combinarse.
* **Unit (Unitarias):** Verifica que cada componente individual funcione de forma aislada.
* **Static:** Detecta errores en el código mientras se escribe (ejemplo: análisis estático).

## Herramientas para Testing

* **Jest:** Popular en múltiples entornos (Vue.js, Angular, TypeScript, Node.js, React). Requiere Node.js instalado.
* **Cypress:** Especializada en pruebas End to End.
