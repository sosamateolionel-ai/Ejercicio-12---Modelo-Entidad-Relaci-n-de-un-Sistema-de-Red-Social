# Ejercicio 12 - Modelo Entidad-Relación de un Sistema de Red Social

## Descripción
Este ejercicio consiste en diseñar un modelo Entidad-Relación (DER) para un sistema de red social. El modelo permite administrar usuarios, publicaciones, relaciones de seguimiento, reacciones, comentarios y etiquetas de contenido.

## Entidades y atributos

### 1. Usuario
Representa a los miembros registrados en la red social.
- **id_usuario**: identificador único del usuario.
- **mail**: correo electrónico de la cuenta.
- **contraseña**: credencial de acceso.
- **fecha creacion**: marca temporal de registro.
- **biografia**: descripción de perfil del usuario.

### 2. Publicacion
Representa los contenidos multimedia o posteos compartidos por los usuarios.
- **id_publicacion**: identificador único de la publicación.
- **id_usuario**: identificador del usuario creador.
- **tipo imagen**: formato o tipo de archivo multimedia.
- **fecha**: fecha de publicación.
- **publicacion**: contenido o enlace principal del post.
- **descripcion**: texto o epígrafe acompañado en la publicación.

### 3. Seguimiento
Representa la relación de amistad o suscripción entre usuarios (quién sigue a quién).
- **id_seguidor**: identificador del usuario que realiza el seguimiento.
- **id_seguido**: identificador del usuario que recibe el seguimiento.
- **fecha seguimiento**: marca temporal de cuándo se estableció el vínculo.

### 4. Reaccion
Representa las interacciones o "likes" realizados por los usuarios sobre las publicaciones.
- **id_usuario**: identificador del usuario que reacciona.
- **id_publicacion**: identificador de la publicación receptora.
- **tipo reaccion**: clasificación de la reacción (ej. me gusta, me encanta, etc.).
- **fecha hora**: momento en el que se efectuó la reacción.

### 5. Comentario
Representa los mensajes o opiniones dejados por los usuarios en las publicaciones.
- **id_comentario**: identificador único del comentario.
- **id_publicacion**: identificador de la publicación comentada.
- **id_usuario**: identificador del autor del comentario.
- **texto**: contenido textual del comentario.
- **fecha hora**: fecha y hora de emisión del mensaje.

### 6. Etiqueta
Representa las palabras clave o hashtags utilizados para categorizar contenido.
- **id_etiqueta**: identificador único de la etiqueta.
- **nombre**: nombre de la etiqueta o hashtag.

### 7. Publicacion_etiqueta
Entidad asociativa que vincula las publicaciones con sus respectivas etiquetas.
- **id_publicacion**: identificador de la publicación.
- **id_etiqueta**: identificador de la etiqueta asignada.

## Relaciones y cardinalidades
- **Usuario – Publicacion (Sube / 1:N)**: un usuario puede realizar múltiples publicaciones en la plataforma.
- **Usuario – Seguimiento (Realiza / Consigue / 1:N)**: gestiona la red de seguidores y seguidos entre los diferentes usuarios.
- **Usuario – Reaccion (Genera / 1:N)**: un usuario puede reaccionar a diversas publicaciones.
- **Publicacion – Reaccion (Esta / 1:N)**: una publicación acumula múltiples reacciones de los usuarios.
- **Publicacion – Comentario (Contiene / 1:N)**: una publicación puede recibir varios comentarios por parte de la comunidad.
- **Publicacion – Publicacion_etiqueta (Tiene / 1:N)** e **Etiqueta – Publicacion_etiqueta (Tiene / 1:N)**: relaciona las publicaciones con una o varias etiquetas de clasificación.

## Objetivo
Diseñar una base de datos escalable para una red social que permita administrar los perfiles de usuario y su red de contactos (seguimientos), almacenar la creación de publicaciones multimedia, gestionar interacciones activas como reacciones y comentarios, y clasificar el contenido mediante etiquetas.
