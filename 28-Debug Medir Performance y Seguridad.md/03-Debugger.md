
# Uso de `debugger` en JavaScript

```js
function mostrarCotizacionHTML(cotizacion) {

    limpiarHTML();

    console.log(cotizacion);
    const  { PRICE, HIGHDAY, LOWDAY, CHANGEPCT24HOUR, LASTUPDATE } = cotizacion;


    debugger

    const precio = document.createElement('p');
    precio.classList.add('precio');
    precio.innerHTML = `El Precio es: <span> ${PRICE} </span>`;

    const precioAlto = document.createElement('p');
    precioAlto.innerHTML = `<p>Precio más alto del día: <span>${HIGHDAY}</span> </p>`;

    const precioBajo = document.createElement('p');
    precioBajo.innerHTML = `<p>Precio más bajo del día: <span>${LOWDAY}</span> </p>`;

    const ultimasHoras = document.createElement('p');
    ultimasHoras.innerHTML = `<p>Variación últimas 24 horas: <span>${CHANGEPCT24HOUR}%</span></p>`;

    const ultimaActualizacion = document.createElement('p');
    ultimaActualizacion.innerHTML = `<p>Última Actualización: <span>${LASTUPDATE}</span></p>`;

    debugger

    resultado.appendChild(precio);
    resultado.appendChild(precioAlto);
    resultado.appendChild(precioBajo);
    resultado.appendChild(ultimasHoras);
    resultado.appendChild(ultimaActualizacion);

    formulario.appendChild(resultado);
}
```

## Explicación del concepto

La palabra clave **`debugger`** en JavaScript detiene la ejecución del programa y abre las herramientas de depuración del navegador (DevTools). Sirve para inspeccionar variables, el flujo del programa y el estado del DOM en un punto específico del código.

## Ejemplo explicado

La función `mostrarCotizacionHTML` recibe un objeto `cotizacion` con datos de una criptomoneda y construye dinámicamente el HTML para mostrarlo.

1. `limpiarHTML();`
   Limpia el contenido previo del contenedor de resultados.

2. `console.log(cotizacion);`
   Imprime el objeto completo en consola para ver sus valores.

3. **Desestructuración del objeto:**
   Se extraen las propiedades `PRICE`, `HIGHDAY`, `LOWDAY`, `CHANGEPCT24HOUR` y `LASTUPDATE`.

4. `debugger`
   Pausa la ejecución en este punto. El desarrollador puede revisar en DevTools cómo están los valores antes de continuar.

5. Se crean nodos `<p>` para mostrar:

   * Precio actual.
   * Precio más alto y más bajo del día.
   * Variación en las últimas 24 horas.
   * Última actualización.

6. `debugger`
   Nueva pausa de ejecución justo antes de insertar el contenido en el DOM.

7. Finalmente, los elementos se agregan al contenedor `resultado`, y luego se adjuntan al `formulario`.

## Salida

El resultado en la página será una lista de párrafos con la cotización. Ejemplo:

```
El Precio es:  $25000
Precio más alto del día: $25500
Precio más bajo del día: $24500
Variación últimas 24 horas: 2.5%
Última Actualización: 15:30:22
```

En DevTools, la ejecución se detendrá en cada `debugger`, mostrando el estado de las variables.

## Concepto clave

* `debugger` es una herramienta de depuración integrada en JavaScript.
* Se activa solo si las DevTools están abiertas.
* Permite inspeccionar valores en tiempo real y seguir el flujo del programa paso a paso.
* Es más potente que `console.log` para entender errores o comportamientos inesperados.
