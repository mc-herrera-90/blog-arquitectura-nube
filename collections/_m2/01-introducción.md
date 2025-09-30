---
title: "Evolución de los modelos<br/> de distribución de software"
layout: page
---

## Introducción

La evolución de los modelos de distribución de software ha cambiado significativamente la forma en que las empresas y los usuarios acceden y utilizan las aplicaciones. Durante muchos años, el software se adquiría e instalaba de forma local en los dispositivos de los usuarios, pero con el avance de la tecnología (especialmente de internet) los modelos de distribución se han transformado. Esta transformación se aceleró gracias al desarrollo de la virtualización a principios de los años 2000, el aumento de la disponibilidad de la banda ancha, y la aparición de servicios claves Amazon Web Services (AWS) en 2006, Google Apps en 2006 y Office 365 en 2011. En este artículo, exploraremos la transición desde el software on-premise hasta el auge de los servicios de software en la nube, conocidos como SaaS (_Software as a Service_) y la infraestructura de Cloud Computing.

## Software On-Premise

El software on-premise es aquel que se instala y ejecuta localmente en los equipos y servidores de la organización. A diferencia del software en la nube, el software on-premise ofrece un alto grado de control y personalización, ya que se puede adaptar a las necesidades específicas de la empresa y garantizar el manejo local de la información.

{% include illustrations/dialog.svg %}

Una de las principales ventajas del software on-premise es la seguridad, ya que permite a las empresas tener un mayor control sobre sus datos. Sin embargo, __esta modalidad implica costos significativos en infraestructura y mantenimiento__, además de una dependencia del equipo técnico interno para resolver problemas y realizar actualizaciones.

A medida que el modelo SaaS ha ganado popularidad, el software on-premise ha visto una disminución en su adopción. Sin embargo, sigue siendo relevante para empresas que requieren una infraestructura robusta y personalizable, así como para aquellas que operan en entornos con restricciones regulatorias severas.

## Ventajas y Desventajas del modelo On-Premise

|Ventajas|Desventajas|
|:-------|:----------|
|Mayor control sobre los datos y la infraestructura|Altos costos iniciales (CAPEX)|
|Alta personalización del software|Costos de mantenimiento y actualizaciones (OPEX)|
|Alineación con políticas internas de seguridad|Escalabilidad limitada|
|Recomendado para entornos regulados|Requiere personal técnico especializado|
|Independencia de proveedores externos|Implementación y despliegue más lentos|

## Software como Servicio (SaaS)

{% include illustrations/realtime.svg %}

__Qué és__: El modelo de Software como Servicio (SaaS) permite a los usuarios acceder a aplicaciones alojadas en servidores remotos a través de internet. En lugar de instalar y mantener el software localmente, los usuarios simplemente acceden a él mediante sus navegadores web. Este modelo es ampliamente utilizado debido a su flexibilidad y facilidad de acceso.

__Ventajas y Desventajas__: Entre sus principales ventajas, SaaS ofrece una reducción significativa en costos de infraestructura y mantenimiento, ya que el proveedor se encarga de gestionar los servidores, las actualizaciones y el soporte técnico. Además, permite una escalabilidad rápida, lo que significa que las empresas pueden aumentar o disminuir el uso del software según sus necesidades. Sin embargo, SaaS también presenta desventajas, como la dependencia de la conexión a internet y el riesgo de problemas de seguridad en los datos que se almacenan en servidores externos.

__Tipos y Ejemplos__: Existen diversos tipos de SaaS que van desde soluciones empresariales como CRM (Salesforce) hasta herramientas de productividad como Office 365. Cada tipo de SaaS está diseñado para cumplir con necesidades específicas del usuario, y su adopción depende de factores como el costo, la funcionalidad y la facilidad de integración con otros sistemas.

## Cloud Computing

{% include illustrations/cloud.svg %}

Cloud Computing o computación en la nube es una tecnología que permite el acceso remoto a los servicios de cómputo a través de internet. Este modelo ha transformado la forma en que las empresas gestionan sus recursos tecnológicos, permitiéndoles prescindir de la infraestructura física tradicional y acceder a una gama completa de servicios informáticos sin necesidad de realizar inversiones iniciales considerables. En lugar de adquirir y mantener servidores propios, las organizaciones pueden ahora optar por utilizar recursos en la nube, pagando únicamente por el uso real de estos, lo cual reduce significativamente los costos operativos. Un ejemplo común es el servicio de almacenamiento en la nube de __Amazon Web Services__ (AWS), ampliamente utilizado por empresas de todos los tamaños.

La flexibilidad es una de las características clave de Cloud Computing, ya que permite a las empresas escalar sus recursos de acuerdo con la demanda. Por ejemplo, durante períodos de alta actividad, como temporadas de ventas, una organización puede aumentar temporalmente su capacidad de procesamiento y almacenamiento sin tener que adquirir hardware adicional.

## Arquitectura elástica

{% include illustrations/investigacion.svg %}

La arquitectura elástica es una característica clave de la computación en la nube que permite que los recursos se ajusten automáticamente a la carga de trabajo. Esto significa que una aplicación puede ampliar su capacidad en momentos de alta demanda y reducirla cuando el tráfico disminuye, optimizando así los recursos y los costos. Esta elasticidad es fundamental para aplicaciones que experimentan fluctuaciones en el tráfico.

Una arquitectura elástica no solo permite gestionar los recursos de manera eficiente, sino que también asegura la disponibilidad y el rendimiento de las aplicaciones, incluso en situaciones de alta demanda. Las empresas que adoptan una arquitectura elástica pueden responder mejor a los cambios y reducir el tiempo de inactividad.

Para implementar esta elasticidad, los proveedores de servicios en la nube ofrecen mecanismos específicos. Uno de ellos es __Auto Scaling__, una funcionalidad que permite agregar o eliminar instancias de cómputo automáticamente en función de métricas como el uso de CPU, la latencia o el número de peticiones. Gracias a Auto Scaling, la infraestructura se adapta de forma dinámica sin necesidad de intervención manual.

Otro mecanismo crucial es el __Balanceador de Carga (Load Balancer)__. Este componente distribuye el tráfico de red entre varias instancias activas, evitando la sobrecarga de un solo servidor y asegurando que las solicitudes se atiendan de forma eficiente. Además, trabaja en conjunto con Auto Scaling para dirigir el tráfico a las nuevas instancias cuando se expanden recursos.

Los principales proveedores de nube, como __AWS (con EC2 Auto Scaling y Elastic Load Balancer)__, __Microsoft Azure (con Virtual Machine Scale Sets y Azure Load Balancer)__ y __Google Cloud (con Instance Groups y Cloud Load Balancing)__, ofrecen herramientas avanzadas que facilitan la implementación de estos mecanismos en tiempo real.