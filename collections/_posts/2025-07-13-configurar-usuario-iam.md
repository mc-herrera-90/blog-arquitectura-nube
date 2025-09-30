---
layout: post
title: "Configurar usuario IAM"
tagline: "Guía paso a paso"
author: "Marco Contreras"
draft: true
---

Los administradores de AWS pueden confiar en políticas, en lugar de configuraciones individuales, para configurar la seguridad de las cuentas en la plataforma. También tienen la ventaja de crear y configurar usuarios mediante programación.

## __¿Por qué AWS IAM?__

Para trabajar de forma segura, lo ideal es crear un __usuario IAM__ con permisos necesarios. Este usuario puede iniciar sesión en la consola o usar la CLI para administrar recursos.

Por ejemplo, un administrador de AWS puede otorgar a un usuario acceso completo únicamente a __Amazon Simple Storage Service__ (S3) o __Amazon Elastic Compute Cloud__ (EC2). Este enfoque de seguridad es más transparente y consistente que el acceso a cuentas configuradas individualmente.

> AWS IAM es gratuito. AWS cobra por __los recursos que consumen las cuentas__.

## __Crear un usuario IAM__

### 1. __Iniciar sesión__

- Inicia sesión como root.

![iam](https://www.techtarget.com/rms/onlineimages/SCC_0821_Singh_AWSIAM_SS1.jpg)

### 2. Cambia al menú Usuarios

- En el panel de IAM, haz clic en Usuarios.

![alt text](https://www.techtarget.com/rms/onlineimages/SCC_0821_Singh_AWSIAM_SS2.jpg)


## __Configurar las credenciales de usuario en AWS en la CLI__

En este artículo se utiliza AWS CLI, disponible a través del proveedor de nube. [Con una configuración mínima](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html), AWS CLI permite al administrador usar su shell preferido para interactuar con los servicios de AWS. Puede elegir cualquier distribución de Linux.

### 1. Instalar la herramienta de línea de comandos

Primero, necesitas instalar AWS CLI en tu sistema usando el siguiente comando en la terminal:

> Recuerda que la terminal se puede abrir con <kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>T</kbd>.

```bash
sudo apt install awscli
```

Una vez ejecutada la instalación, verifica la versión:

```bash
aws --version
```

### 2. Configurar el usuario con claves

Ejecuta el comando `aws configure` en la terminal para configurar rápidamente el ID de la clave de acceso y la clave de acceso secreta que obtuviste de AWS al crear el nuevo usuario en la consola de IAM.


```plaintext
$ aws configure

AWS Access Key ID [None]: AIKEAOS...
AWS Secret Access Key [None]: onmVD...
Default region name [ap-south-1]:
Default output format [json]: json
```

Este paso guarda sus credenciales en un archivo local en la ruta: `~/.aws/credentials` y las configuraciones de región y formato en la ruta: `~/.aws/config`.

