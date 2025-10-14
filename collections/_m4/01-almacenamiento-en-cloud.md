---
title: "Almacenamiento<br/> en Cloud"
layout: page
---

En el mundo actual, el almacenamiento en la nube se ha convertido en un componente esencial para casi todas las organizaciones, independientemente de su tamaño o sector. Con la expansión de los volúmenes de datos y la necesidad de accesibilidad global, la nube ofrece una serie de ventajas que superan, en muchos casos, al almacenamiento tradicional o "on-premise". En este artículo profundizaremos en los conceptos fundamentales del almacenamiento en la nube, revisaremos sus ventajas y desventajas, y exploraremos los tipos de nube, revisaremos sus ventajas y desventajas, y exploraremos los tipos de almacenamiento más comunes, junto con sus propósitos y costos asociados.

## Almacenamiento en Cloud

### Conceptos fundamentales del almacenamiento cloud

El almacenamiento en la nube es un modelo de servicio en el cual los datos se almacenan en servidores remotos a los que se accede a través de Internet. En lugar de mantener el hardware físico en las instalaciones de la organización, un proveedor de nube ofrece la infraestructura necesaria para guardar los datos en sus centros de datos.

#### Elementos clave del almacenamiento en la nube

- __Infraestructura gestionada por terceros__: No es necesario que la empresa adquiera y mantenga servidores físicos.
- __Acceso remoto__: Los usuarios pueden acceder a la información desde cualquier ubicación y dispositivos con conexión a internet.
- __Seguridad y escalabilidad__: Los proveedores cloud ofrecen mecanismos robustos de seguridad y la capacidad de escalar hacia arriba o hacia abajo en función de las necesidades.
- __Pago por uso__: Generalmente, se paga únicamente por la cantidad de almacenamiento y los recursos efectivamente utilizados.

## 2. Conceptos básicos del almacenamiento en la nube

- __Disponibilidad__: Se refiere a la capacidad de acceder a los datos en cualquier momento. La mayoría de los proveedores de nube ofrecen SLA (Acuerdos de Nivel de Servicio) que garantizan altos niveles de disponibilidad (por ejemplo, 99.9% o superior).
- __Durabilidad__: Es la probabilidad de que tus datos permanezcan intacto y sin pérdida a lo largo del tiempo. El almacenamiento en la nube suele replicar los datos en múltiples ubicaciones físicas.
- __Elasticidad__: Permite aumentar o disminuir la capacidad de almacenamiento de forma rápida, según la demanda.
- __Seguridad__: Implica cifrado en tránsito (cuando los datos viajan a través de la red) y en reposo (cuando los datos se almacenan en los servidores), junto con controles de acceso y auditoría.

## 3. Ventajas y desventajas de almacenamiento en la nube versus on-premise

A continuación, se presenta una __tabla comparativa__ que sintetiza las principales ventajas y desventajas del almacenamiento en la nube frente al almacenamiento on-premise:

|Criterio|Cloud|On-Premise|
|:-------|:----|:---------|
|__Costos iniciales__|Bajo a casi nulos (pago por uso).|Altos (compra de hardware, licencia, instalación).|
|__Mantenimiento__|A cargo del proveedor (actualizaciones, parches).|Requiere personal interno, recursos y costos de soporte y mantenimiento.|
|__Escalabilidad__|Inmediata, elástica y prácticamente ilimitada.|Limitada por la infraestructura física disponible.|
|__Disponibilidad__|Alto SLA ofrecido por el proveedor.|Depende de las capacidades internas y redundancia propia.|
|__Seguridad__|Cifrado, auditorías, cumplimiento normativo avanzado.|Control total (físico) del hardware, se depende de los recursos y experiencia local.|
|__Flexibilidad__|Fácil integración con otros servicios cloud.|Díficil integración con nuevas tecnologías si no se cuenta con la infraestructura.|
|__Ubicación de datos__|Almacenamiento en centros de datos remotos.|Almacenamiento en servidores de la organización, control físico total.|
|__Desventajas__|Dependencia de internet, costos crecientes a largo plazo si no se gestiona bien.|Requiere graninversión inicial díficil escalabilidad, actualización constante.|

## 4. Tipos de almacenamiento y sus própositos

En la nube, encontramos diversos servicios de almacenamiento diseñados para cumplir con diferentes requisitos de rendimiento, durabilidad, disponibilidad y costos. Nos enfocaremos específicamente en los servicios más destacados:

### Almacenamiento simple de objetos (S3)

- __¿Qué es?__: Un servicio orientado al almacenamiento de objetos que se accede mediante una API REST. Está diseñada para almacenar y recuperar cualquier volumen de datos desde cualquier parte del mundo.
- __Características__:
    - Almacena datos en "buckets" y cada objeto recibe un "key" único.
    - Alta durabilidad (generalmente 99.99999999%).
    - Diferentes clases de almacenamiento (Standar, Infrequent Access, Intelligent-Tiering, etc) para optimizar costos.
    - Ideal para contenido estático de sitios web, copias de seguridad y archivos multimedia.
- __Ventajas__: Muy escalable, integración sencilla con otros servicios (como servicios de Machine Learning, CDN, etc.), pago por uso.
- __Desventajas__: Latencia más alta si se compara con almacenamiento de bloque (no es ideal para bases de datos transaccionales en tiempo real).

### Almacenamiento de largo plazo (Glacier)

- __¿Qué es?__: Servicio diseñado específicamente para archivado de datos y copias de seguridad a largo plazo con costos muy bajos.
- __Características__:
    - Las operaciones de recuperación de datos pueden tardar entre minutos y horas, según la opción de recuperación elegida.
    - Está pensado para datos a los que se accede con muy poca frecuencia.
    - Costos de almacenamiento extremadamente bajos comparados con otros servicios.
- __Ventajas__: Ideal para archivado y cumplimiento de regulaciones que exigen retener datos durante largos periodos.
- __Desventajas__: No es apto para uso frecuente; las recuperaciones pueden ser lentas y con un costo mayor.

### Almacenamiento de alto rendimiento (Elastic Block Store - EBS)

- __¿Qué es?__: Un servicio de almacenamiento de bloques que se utiliza principalmente para instancias de cómputo (máquinas virtuales en la nube).
- __Características__:
    - Funciona como un disco virtual para servidores en la nube.
    - Permite alcanzar bajas latencias y alto rendimiento para operaciones de lectura/escritura.
    - Ideal para bases de datos, aplicaciones que requieren alto rendimiento de IOPS (Input/Output Operations Per Second).
- __Ventajas__: Consistencia en la latencia, escalabilidad de tamaño y rendimiento, integración con instancias de cómputo.
- __Desventaja__: No es la opción más económica si solo se necesita almacenar datos "fríos" o poco utilizados.

### Sistemas de archivos escalables (Elastic File System - EFS)

- __¿Qué es?__: Un sistema de archivos elástico para cargas de trabajo que requieren un sistema compartido, accesible por múltiples instancias a la vez.
- __Características__:
    - Permite acceso simultáneo desde varias instancias, ideal para entornos de servidores que comparten archivos.
    - Escalabilidad automática de almacenamiento.
    - Compatible con protocolos NFS (Network File System).
- __Ventajas__: Facilidad de uso, manejo de archivos a nivel de sistema de archivos.
- __Desventajas__: Costos pueden ser más alto que opciones de objeto si se almacena gran cantidad de datos que no requieren un sistema de archivos compartido.

### Storage Gateway

- __¿Qué es?__: Un servicio que permite integrar los datos on-premise con la nube, sirviendo como un "puente" para sincronizar y respaldar información.
- __Características__:
    - Ofrece caché local para el acceso rápido a datos frecuentemente utilizados y almacenamiento remoto en la nube.
    - Útil para migraciones graduales a la nube o para entornos híbridos.
- __Ventajas__: Permite aprovechar recursos on-premise existentes, facilita la transición a la nube, reduce latencia de acceso a datos críticos.
- __Desventajas__: Añade cierta complejidad a la infraestructura (se necesita mantener una puerta de enlace local).

## 5. Beneficios de utilizar almacenamientos diferenciados

Cada tipo de almacenamiento cumple un próposito específico, por lo que una estrategia que combine varios de ellos puede maximizar la eficiencia y optimizar costos. Por ejemplo:

- __Usar S3__ para datos semi-frecuentes (logs, contenido estático de sitios web).
- __Migrar a Glacier__ para datos históricos que solo se requieren en auditorías o archivado legal.
- __EBS__ para bases de datos y aplicaciones que demandan rápido acceso.
- __EFS__ para entornos en donde múltiples máquinas necesitan acceso simultáneo a un sistema de archivos.
- __Storage Gateway__ para mantener un entorno híbrido, con datos relevantes en on-premise y en la nube para respaldos o alta disponibilidad.

## 6. Costos asociados a los diferentes tipos de almacenamiento

A grandes rasgos, los proveedores de nube manejan una estructura de costos basada en:

- __Capacidad de almacenamiento (GB/mes)__: cada servicio cobra por GB almacenado por mes.
- __Operaciones__: Lecturas, escrituras, listados de objetos, solicitudes de recuperación, etc.
- __Salida de datos (Data transfer out)__: Se cobran los datos que salen de la nube, pero usualmente no los que entran.
- __Clases de almacenamiento__: Dentro de S3 y Glacier hay múltiples niveles (Standard, Infrequent Access, Deep Archive, etc.) que varían en costo según la frecuencia de acceso y la durabilidad requerida.

En __Glacier__, por ejemplo, el almacenamiento puede ser muy económico, pero las recuperaciones pueden tener un costo adicional y tardar más tiempo. En __EBS__, el costo por GB/mes es más alto, pero entrega el rendimiento que aplicaciones críticas necesitan. __EFS__ puede cobrar tanto por capacidad como por la cantidad de operaciones, especialmente si se usa el modo "Provisioned Throughput".

> __Consejo__: Es recomendable realizar una estimación de costos teniendo en cuenta el volumen de datos, la frecuencia de acceso y la proyección de crecimiento a largo plazo. Además, muchos proveedores ofrecen calculadoras de precios para estimar gastos.

## 7. Estrategias de uso de diferentes tecnologías

Para optimizar la inversión y el rendimiento, las organizaciones suelen adoptar estrategias híbridad o multinube. Algunas recomendaciones:

1. __Clasificar los datos según su freciencia de acceso__:
    - Datos críticos y de acceso constante (producción) en EBS o EFS.
    - Datos semi-frecuentes en S3.
    - Datos inactivos y de archivo en Glacier.
2. __Implementar ciclos de vida de objetos__ (en caso de S3).
    - Mover automáticamente los objetos a una clase de almacenamiento más barata después de un tiempo establecido (por ejemplo, a S3 Glacier o S3 Glacier Deep Archive).
3. __Integrar on-premise con la nube__:
    - A través de Storage Gateway, mantener lo más usado en caché local y respaldar o archivar en la nube.
4. __Supervisar y optimizar costos__:
    - Utilizar herramientas de monitoreo de facturación y uso para detectar patrones de acceso y mover datos a soluciones de menor costo cuando sea posible.
5. __Pruebas de rendimiento__:
    - Verificar que el almacenamiento elegido soporte el volumen de transacciones y la latencia requerida.

Estas estrategias permiten equilibrar el costo, el rendimiento, la seguridad y la disponibilidad, de acuerdo con las necesidades específicas de la organización.