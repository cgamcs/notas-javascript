# `defer` y `async` en JavaScript

## Explicación del concepto

Cuando se incluyen archivos JavaScript con `<script>` en un documento HTML, el navegador por defecto detiene la carga del HTML para descargar y ejecutar el script. Esto puede hacer que la página tarde más en mostrarse.

Los atributos **`defer`** y **`async`** controlan **cuándo** y **cómo** se cargan y ejecutan los scripts externos, optimizando el rendimiento.

## Diferencias principales

### `defer`

* El script se **descarga en paralelo** mientras se procesa el HTML.
* La **ejecución se retrasa** hasta que el HTML esté completamente cargado y parseado.
* Se ejecutan en **orden de aparición** en el documento.
* Ideal para scripts que dependen de elementos del DOM.

Ejemplo:

```html
<script src="app.js" defer></script>
```

➡️ El script `app.js` se descargará mientras se carga el HTML, pero se ejecutará solo al final.

---

### `async`

* El script también se **descarga en paralelo** al HTML.
* Pero se **ejecuta inmediatamente** cuando termina de descargarse, sin esperar a que el HTML esté listo.
* **No garantiza el orden** de ejecución entre varios scripts.
* Útil para scripts independientes (ejemplo: anuncios, analítica).

Ejemplo:

```html
<script src="analytics.js" async></script>
```

➡️ El script `analytics.js` se ejecutará en cuanto esté listo, aunque el HTML siga cargándose.

## Resumen comparativo

| Atributo | Descarga     | Ejecución             | Orden garantizado |
| -------- | ------------ | --------------------- | ----------------- |
| Normal   | Bloquea HTML | Inmediata             | Sí                |
| `defer`  | Paralela     | Tras cargar HTML      | Sí                |
| `async`  | Paralela     | En cuanto se descarga | No                |

## Concepto clave

* Usa **`defer`** para scripts principales que dependen del DOM y deben mantener un orden.
* Usa **`async`** para scripts externos independientes que pueden ejecutarse sin esperar.
