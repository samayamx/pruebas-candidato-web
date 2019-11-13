# pruebas-candidato(a)-web
Propuestas de ejercicios de prueba a candidatos web para aplicar a Samaya Companion

## Frontend

### Webapp (React) para Listar contenidos de API Pública

Requerimientos:

- Obtener contenidos de una API Pública (Goodreads, Spotify, Youtube, etc.)
- Mostrar títulos, imágenes, etc.
- Permitir guardar "favoritos" por usuario (en localStorage para evitar backend).
- No utilizar librerías aparte de React y ReactRouter en caso de tomar las sugerencias.
- Se puede utilizar un framework de CSS, sin widgets de JS.

Sugerencia
- Hacer login propio en pantalla aparte para permitir a diferentes "usuarios" guardar sus propios favs y búsquedas.
- Utilizar ReactRouter y Context para guardar/recuperar datos de cada "usuario".
- Utilizar la menor cantidad de CSS posible requerido, en caso de framework solo lo requerido o el más ligero posible.


## Backend

### CRUD de un modelo con Lumen y Twig

Requerimientos:

- Capturar listas de libros por leer/leídos.
- Soportar una lista por usuario.
- Se puede cambiar de usuario al cambiar de URL.
- Permite marcar los libros ya leídos y asignarles calificación en la misma lista.
- Permite archivar los libros ya leídos con un botón, y recuperarlos.
- Las vistas se requieren con Twig porque es más portable que Blade.

Sugerido:
- Poner el servicio de vista en un ServiceProvider propio del framework usado (Laravel o Lumen)
- No llevar a otra vista para capturar o hacer cambios a una entrada, hacerlo por AJAX.
