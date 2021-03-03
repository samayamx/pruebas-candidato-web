## Introducción.

*Elige **uno** de los proyectos que te proponemos de [backend](#Backend) o [frontend](#Frontend)*, de acuerdo a tus aptitudes e intereses.

**¡Presume tus puntos fuertes!**

#### Objetivo
Conocer el estilo de trabajo autónomo de el/la candidato(a), se recomienda realizar un ejercicio que involucra una serie de componentes y conocimientos del lenguaje y framework elegido: 
-	enfocados en una tarea específica
-	pero integrando servicios de terceros (nuestro principal requerimiento)
-	y opciones de autenticación de usuarios
-	permite validar:
  -	la integración de componentes o librerías propias o de terceros para evitar desarrollar funcionalidad desde cero
  -	estilo de documentación de API
  - documentación de instrucciones para implementación (en lugar de README genérico del framework elegido, instrucciones específicas para este proyecto)
  - preferible pero no requerido, deployment de demostración público con el código fuente de candidat@
  - atomicidad de los commits y/o Pull/Merge Request e información incluida en los mensajes de commit y PR/MR
  - uso de pruebas unitarias y/o integración
  - uso de CI/CD para el deployment de su código fuente.

¿Dudas? Escribe al reclutador que te contactó para proponerte la prueba de inducción.

## Frontend

### Webapp (React) para Listar contenidos de API Pública

#### Requerimientos:

- Obtener contenidos de una API Pública (Goodreads, Spotify, Youtube, etc.)
- Mostrar títulos, imágenes, etc.
- Permitir guardar "favoritos" por usuario (en localStorage por simplicidad).
- Utiliza hooks, no clases salvo para cachar errores.
- No utilizar librerías aparte de React y ReactRouter en caso de tomar las sugerencias.
- Se puede utilizar un framework de CSS, sin widgets de JS.
- Documentación del uso básico de la aplicación mediante README. 
- Utiliza un linter, al menos, standard.

#### Sugerencias para puntos extra.

***Puedes implementarlo diferente, pero utiliza las sugerencias para mostrar tus aptitudes***.

- Utiliza el create-react-app con el template de **TypeScript**, y si necesitas *any*, que sea el mínimo posible.
- Hacer login con Firebase o Auth0, mediante redes sociales y/o usuario y contraseña. 
- Guardar Favoritos del usuario en Firebase (u otra base remota) en lugar de localStorage. 
- Pruebas unitarias y/o integración. 

### Webapp (React o Angular) para conversión de archivos 

#### Requerimientos
- Login con Firebase o Auth0, mediante redes sociales y/o usuario y contraseña. 
- Permitir al usuario subir archivos mediante una dropzone o URL del asset. 
- Convertir assets mediante el uso de una API de conversión de archivos (CloudConvert u otra afín). 
  - Documentos Word e imágenes se convierten a PDF
  - Videos se convierten a MP4 
  - Enviar un correo al usuario con la URL de descarga del asset convertido. 
- Dar feedback visual al usuario sobre el estatus de conversión del asset y envío del correo. 
- Se puede utilizar un framework de CSS, sin widgets de JS. 
- Documentación del uso básico de la aplicación mediante README.
- Utiliza un linter, standard si solo usas JS, si usas TypeScript el incluido con Angular o uno apropiado para React.

#### Sugerencias 

- Genera tu aplicación con create-react-app con la opción de TypeScript o si usas la CLI de Angular, puedes generar el build optimizado pero sin excluir sourcemaps.
- Pruebas unitarias y/o integración.
- Si usas React escribe tu código con TypeScript con Hooks y evita el uso de any.
- Guardar en Firebase los eventos de conversión por usuario. 
- Mostrar bitácora de eventos del usuario.

## Backend

*Recuerda que te recomendamos elegir **uno** de los proyectos propuestos*.

### Uso de base de datos e integración con servicios de terceros

*Te sugerimos apoyarte en un ORM de la plataforma que utilizarás*, por ejemplo si es Laravel usa Eloquent, Symfony usa Doctrine, Node.js tienes muuuchas opciones, Ruby usa lo que te convenga con Sinatra o Rails. Usamos lenguajes dinámicos en backend.

#### A.	Aplicación para programar retweets a nombre del usuario. 
- Login con Twitter para obtener su token para operar con la API con su usuario. 
- Buscar cuentas y listar sus últimos tweets. 
- Retuitear de inmediato o en una fecha futura sin que el usuario tenga abierta la página. 

#### B.	Aplicación para dar/quitar Stars a repositorios de Github. 
- Login con Github. 
- Buscar cuentas y listar sus repositorios más recientes/con más estrellas/recién actualizados. 
- Dar o quitar estrella a nombre de este usuario a los repositorios listados. 
- Difundir en un perfil de twitter de la aplicación (no a nombre del usuario), que el usuario logueado con github, le dio Star al repo de otro usuario. 

#### C.	Carga de archivos en “proyectos” (colección de documentos) del usuario, opción de compartir públicamente. Servicio sobre patrón de diseño MVC. 
- Permite indicar una lista de emails a los cuáles enviar la notificación de que el archivo ya está disponible para su descarga al terminar el procesamiento. 
- El archivo en sí (asset) se hospeda en blobs de Azure o bucket S3 de AWS. 
- El asset se etiqueta con título y descripción para su previsualización en la URL pública que permite acceder al archivo en twitter, Facebook, whatsapp, etc. 
- Al quitar el permiso de compartir del asset, o eliminar el asset, la URL de compartir muestra un mensaje de que el contenido ya no es público o ha expirado, según corresponda. 
- Al eliminar el asset se va a una papelera de donde se puede recupera o eliminar tanto el archivo cargado automáticamente y su registro en base de datos. 
- Documentos de Word e imágenes se convierten a PDF para su descarga. 
- Vídeos se convierten a MP4 optimizado para visualización en twitter Card. 
- Si es muy pesado, se puede proporcionar a través de una URL para su descarga. 
- La respuesta de que el archivo fue recibido y será procesado debe ser inmediata, una vez recibiendo el backend los datos del formulario. 
- El procesamiento y envío de notificaciones del archivo deben ocurrir en Jobs diferidos para evitar “cuelgues” del servicio web. 
- No hay restricciones de como implementar la cola de trabajos, pero se recomienda utilizar las facilidades que ya incluya el framework elegido. 

### Proyecto de funciones serverless reutilizables por backend o frontend. 
- Todas las funciones deben estar implementadas en el mismo repositorio. 
- Las funciones requeridas son: 
  - Recuperar tweets (con opción a indicar un usuario de twitter consumiendo su API) 
  - Retuitear un estatus de cuenta de tercero, el usuario que hace el retweet debe ser configurable. 
  - Enviar archivos a conversión / optimización. 
  - Recibir respuesta de API de conversión / optimización y descarga de archivo en bucket/blob o envío de notificación a usuario. 
  - Enviar email mediante API de terceros. 
  - Enviar notificación *web* con firebase. 
