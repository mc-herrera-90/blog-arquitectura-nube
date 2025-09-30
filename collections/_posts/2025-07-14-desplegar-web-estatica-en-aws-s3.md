---
layout: post
title: "Desplegar una Web Estática en AWS S3"
tagline: "Guía paso a paso"
categories: serverless
background: "https://media2.dev.to/dynamic/image/width=1000,height=420,fit=cover,gravity=auto,format=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fxpcqcf9t8ieu9t6h8rmd.png"
author: "Marco Contreras"
---

Si tienes una página web estática (generada con HTML, CSS y JS o frameworks como Jekyll, Hugo o Astro), puedes publicarla en Internet __gratis__ usando los __servicios serverless de Amazon Web Services__ (AWS). Aquí te ayudo a cómo hacerlo paso a paso, ya sea que tengas una cuenta __Free Tier__ o una cuenta de estudiante mediante __AWS Academy__.

Para ello, usaremos:

- __Amazon S3__: Servicio de almacenamiento de archivos.

## __Entendiendo AWS Serverless__

__AWS Serverless__ en un modelo de desarrollo nativo de la nube que permite a los desarrolladores crear y ejecutar aplicaciones sin preocuparse por los servidores. Mientras los servidores sigan existiendo, AWS se encarga de su configuración, mantenimiento y escalado. Solo tienes que centrarte en el desarrollo de tu sitio web.

> __Serverless__ no significa que no haya servidores, sino que __no tienes que administrarlos__. AWS se encarga de todo y solo tienes que subir tus archivos y dejar que el servicio los sirva al mundo sin preocuparse por infraestructura.

## __Descripción de los buckets de Amazon S3__

Un bucket de Amazon S3 es un recurso de almacenamiento en la nube disponible en __Simple Storage Service__ (S3) de AWS. Este servicio de almacenamiento de objetos ofrece escalabilidad, disponibilidad de datos, seguridad y rendimiento. Ofrece alojamiento estático de sitios web donde puede alojar su aplicación sin servidor.

La estructura de tu sitio debe incluir un archivo `index.html`:

```bash
mi-sitio/
│
├── index.html
├── style.css
└── script.js
```

## __Guía Paso a Paso__

### __1. Ir a la consola de administración__

__Opción 1:__

- Registrate para acceder a tu cuenta en [https://aws.amazon.com/free/](https://aws.amazon.com/free/).

__Opción 2:__
- Desde el [__portal de AWS Academy__](https://awsacademy.instructure.com/login/canvas) inicia el AWS Learner Lab.

{:align="center"}
![Consola AWS]({{ 'assets/images/aws_lab/aws_start_lab.png' | relative_url }})
_AWS Learner Lab._

__En el panel de inicio__

- Desde la consola principal de AWS, busca "S3" en la barra de búsqueda de servicios y haz clic en el servicio S3:

![Search AWS S3]({{ 'assets/images/aws/search-s3-from-console.png' | relative_url }})

### __2. Crear un nuevo Bucket__

- En la página de inicio de S3, encontrarás una opción para crear un nuevo bucket para su sitio web. Haz clic en ella.

![Crear nuevo bucket]({{ 'assets/images/aws/new-bucket-button.png' | relative_url }})

- Puedes crear el __bucket__ con la configuración predeterminada, pero ten en cuenta que el nombre no podrá cambiarse en el futuro.

![Nombrar bucket]({{ 'assets/images/aws/name-bucket-s3.png' | relative_url }})

### __3. Sube tu sitio web al Bucket__

- Después de crear el contenedor, haz clic en él para acceder a la opción de subir archivos. Haz clic en el botón que dice __Cargar__:

![Botón cargar]({{ 'assets/images/aws/btn-change-upload-files.png' | relative_url }})

- Ahora puedes subir los archivos de diferentes maneras, arrastrando la carpeta o presionando en los botones:

{: align="center" }
![Subir archivos del sitio]({{ 'assets/images/aws/upload-files-website.png' | relative_url }})
_Carga los archivos manualmente_

{: align="center" }
![Mover directorios]({{ 'assets/images/aws/upload-files-move-website.png' | relative_url }})
_Carga tu sitio web arrastrando la carpeta del proyecto_

{:align="center"}
![Detalles de los archivos y cargarlos]({{ 'assets/images/aws/details-files-and-upload.png' | relative_url }})
_Detalles de los archivos a subir_

- Después de cargar los archivos, se muestra la carpeta de tu sitio web y allí podrás ver todos los archivos, incluido el `index.html`. Si haces clic sobre este archivo, verás un enlace en __URL del objeto__ que te llevará a la página web.

![Enlace al sitio web]({{ 'assets/images/aws/object-url-website.png' | relative_url }})

- Sin embargo, al hacer clic en él, aparecerá el siguiente error:

{:align="center"}
![Error acceso denegado]({{ 'assets/images/aws/error-access-denied.png' | relative_url }})
_Error: Permisos insuficientes para acceder al archivo en S3_

### ¿Por qué?

- Al crear el bucket, configuramos los permisos del depósito para no permitir el __acceso de lectura__ a público, lo que impide que los usuarios accedan a sus archivos.

## __5. Actualizar la configuración del Bucket__

- Para acceder a nuestro sitio web de forma pública necesitamos hacer dos cosas:

### a. Permitir el acceso público

- Para ello, debes ir al bucket y luego hacer clic sobre la pestaña __Permisos__ y editar __Bloquear acceso público (configuración del bucket)__ y desmarcar __Bloquear todo el acceso público__:

{:align="center"}
![Ir a pestaña permisos]({{ 'assets/images/aws/permissions-bucket.png' | relative_url }})
_Vista de la pestaña "Permisos" de un bucket en Amazon S3_

{:align="center"}
![Desmarcar el bloqueo a público]({{ 'assets/images/aws/uncheck-block-bucket.png' | relative_url }})
_Al desmarcar esta casilla se permite configurar el acceso público al bucket_

> Solo debes hacer esto si estás seguro de que el bucket debe estar disponible públicamente, como en el caso de un sitio web estático.

### b. Actualizar política del Bucket

En la misma pestaña de permisos, verás la opción para editar la política del bucket:

![editar políticas del bucket]({{ 'assets/images/aws/edit-policy-bucket.png' | relative_url }})

En esa política, agregue la siguiente política y guarde los cambios:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```

> Nota: Asegúrate de cambiar `your-bucket-name` por el nombre del bucket creado.

![Nueva política agregada]({{ 'assets/images/aws/new-policy-add.png' | relative_url }})

Finalmente, después de completar todos los pasos, vuelve a la carpeta del sitio web y haz clic sobre el `index.html`.

Encontrarás el enlace que revisamos anteriormente en __Objeto URL__ y, en esta ocasión, verás tu sitio:

![Show AWS]({{ 'assets/images/aws/website-s3-show.png' | relative_url }})


## __Conclusión__

Alojar un sitio web estático con AWS S3 es una solución fácil y rápida. Al crear un bucket, subir archivos y ajustar la configuración pertinente, puede implementar un sitio rápidamente sin preocuparse por la administración del servidor.

Si estás haciendo una demostración personal, proyecto de portafolio o sitio sin mucho tráfico, vas a generar costos muy bajos o hasta te salga __gratuito__ 💛.