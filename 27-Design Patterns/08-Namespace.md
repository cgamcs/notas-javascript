# Patrón Namespace en JavaScript

## Explicación del concepto

El **patrón Namespace** se usa para **organizar y agrupar código** dentro de un solo objeto global, evitando la contaminación del espacio de nombres y posibles conflictos entre variables o funciones con el mismo nombre. Sirve para mantener el código modular y más legible.

## Ejemplo explicado

En el código:

1. Se crea un objeto vacío `restaurantApp`, que actuará como **namespace** para almacenar todo lo relacionado con la aplicación.

2. Dentro del namespace:

   * `platillos` es un arreglo de objetos, donde cada objeto representa un platillo con su nombre y precio.
   * `funciones` contiene métodos que manipulan los platillos:

     * `mostrarMenu`: recorre el arreglo y muestra cada platillo con su precio.
     * `ordernar`: recibe un `id` y muestra un mensaje indicando qué platillo se está preparando.
     * `agregarPaltillo`: recibe un platillo y precio, y lo añade al arreglo.

3. Se agrega un nuevo platillo `"Taco"` usando `agregarPaltillo`.

4. Con `mostrarMenu`, se listan todos los platillos disponibles.

5. Con `ordernar(1)`, se selecciona el segundo platillo (`Hamburguesa`) y se simula su preparación.

## Salida

```txt
0: Pizza $25
1: Hamburguesa $20
2: Hot Dog $20
3: Taco $25
Tu platillo: Hamburguesa se esta preparando
```

## Concepto clave

* El patrón Namespace encapsula datos y funciones en un solo objeto global.
* Evita colisiones de nombres en aplicaciones grandes.
* Facilita la organización del código en módulos más claros y reutilizables.
