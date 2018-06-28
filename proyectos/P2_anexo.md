# Documentación del servicio Awesome Profile Cards

## API del back-end

La URL base del servicio es

`https://us-central1-awesome-cards-cf6f0.cloudfunctions.net/`

El API sigue una convención tipo REST para la gestión de tarjetas: creación y acceso a las mismas. Las acciones impementadas por este API son las siguientes:

- *CREATE*: una petición 'POST' a la URL `/card` con los datos necesarios en formato JSON (especificados más abajo) creará una nueva tarjeta 
- *GET*: una petición 'GET' a la URL `/card/:id:/` devueleve una página web en HTML donde se muestran los datos de la tarjeta con el identificador 'id'

En el proyecto 2 de Adalab vamos a acceder al servicio para crear una tarjeta. Esta acción nos devuelve una URL que usa la segunda acción (GET) para acceder a una versión web de la tarjeta que crea este servicio.

## Datos necesarios para crear una tarjeta

Todos los campos son obligatorios, excepto las habilidades (skills).

- **Paleta colores**
  - Nombre del campo: `colors`
  - Descripción: número que representa la paleta elegida, de 1 a 3
  - Ejemplo: 1
- **Tipografía**
  - Nombre del campo: `typography`
  - Descripción: número que representa la tipografía elegida, de 1 a 3
  - Ejemplo: 1
- **Nombre**
  - Nombre del campo: `name`
  - Descripción: nombre completo
  - Ejemplo: María García
- **Profesión**
  - Nombre del campo: `job`
  - Descripción: profesión
  - Ejemplo: Programadora front-end
- **Teléfono**
  - Nombre del campo: `phone`
  - Descripción: teléfono
  - Ejemplo: +34 666666666
- **Teléfono**
  - Nombre del campo: `email`
  - Descripción: email
  - Ejemplo: maria.garcia@example.com
- **LinkedIn**
  - Nombre del campo: `linkedin`
  - Descripción: nombre de usuario de LinkedIn
  - Ejemplo: mariagar
- **GitHub**
  - Nombre del campo: `github`
  - Descripción: nombre de usuario de GitHub
  - Ejemplo: mariagar
- **Foto**
  - Nombre del campo: `photo`
  - Descripción: foto en codificación base64 (la que obtenemos al hacer `FileReader.readAsDataURL`)
- **Habilidades**
  - Nombre del campo: `skills`
  - Descripción: listado de habilidades
  - Ejemplo: `['HTML', 'Sass']`


## Formato de respuestas

La respuesta que da el API tiene el siguiente formato si todo ha ido bien:

```json
{
  "success": true,
  "cardURL": "https://us-central1-awesome-cards-cf6f0.cloudfunctions.net/card/${cardId}"
}
```

Si hay algún error, la respuesta tiene esta pinta:

```json
{
  "success": false,
  "error": "Error description"
}
```

## Ejemplo de uso

Proporcionamos un [ejemplo de uso del servicio en este codepen](https://codepen.io/adalab/pen/yERXZE?editors=1010).
