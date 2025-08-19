## Características de una PWA

- Rapida - Cargan toda la información en menos de 5 segundos.
- Instalable - Se puede navegar o instalar en un nevegador o teléfono móvil como una aplicación nátiva.
- Soporte Offline - Pueden funcionar incluso sin conexion a internet.

## Service Workers

- Es la base de una PWA. Son scripts que están corriendo todo el tiempo detrás de escenas.
- Funcionan Offline.
- No tienen acceso al DOM.
- Cargan de forma instantanea.
- Pueden sincronizar datos detrás de escena o sin interferir en la navegación.

## Funciones No Disponibles en Services Workers

- window (utiliza self)
- document (se utiliza caches)
- localStorage (se utiliza fetch)