---
title: Introducción al programa de paquetes de contenido del servicio Power BI
description: Programa de certificación del paquete de contenido
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/20/2018
ms.author: maghan
ms.openlocfilehash: cfb9727a41d602ce14bfd2a403a87e82d2f0e94d
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
---
# <a name="overview-of-the-power-bi-service-content-pack-program"></a>Introducción al programa de paquetes de contenido del servicio Power BI
Un paquete de contenido es un conjunto de contenido integrado que permite a los usuarios obtener información inmediata de un origen. Un paquete de contenido se centra normalmente en un escenario de negocio específico que proporciona información para un rol, dominio o flujo de trabajo.

Los ISV pueden crear paquetes de contenido de plantillas que permiten a los clientes conectarse y crear instancias de sus propias cuentas. Como expertos de dominio, pueden desbloquear los datos de forma que sea de fácil de consumir por usuarios empresariales. Los paquetes de contenido ofrecen supervisión ad hoc y el análisis a sus clientes sin realizar fuertes inversiones en infraestructura de informes. 

Estos paquetes de contenido de plantillas creados por ISV se pueden enviar al equipo de Power BI para que estén disponibles públicamente en la galería de paquetes de contenido de Power BI (app.powerbi.com/getdata/services) y en Microsoft AppSource (appsource.microsoft.com). Puede encontrar un ejemplo de la experiencia del paquete de contenido público [aquí](template-content-pack-experience.md).

## <a name="overview"></a>Información general
El proceso general para desarrollar y enviar un paquete de contenido de plantillas implica varios pasos.

 ![Proceso](media/service-content-pack-overview/developer-content-pack-overview.png)

1. [Revisar los requisitos](#requirements) y asegurarse de cumplirlos
2. [Crear contenido](template-content-pack-authoring.md#queries) con Power BI Desktop
3. [Crear un panel](template-content-pack-authoring.md#dashboard) en PowerBI.com
4. [Probar el paquete de contenido](template-content-pack-testing.md) usted mismo dentro de su organización
5. [Enviar](template-content-pack-testing.md#submission) el contenido a Power BI para su publicación

<a name="requirements"></a>

## <a name="requirements"></a>Requisitos
Para crear y enviar un paquete de contenido para su publicación en el servicio PowerBI y AppSource, debe cumplir los siguientes requisitos:

* Tener una aplicación de SaaS utilizada por usuarios empresariales.
* La aplicación de SaaS tiene datos de usuario que se pueden visualizar en Power BI.
* La aplicación de SaaS tiene una API que es accesible a través de la red pública de Internet. Lo ideal es que la API sea una API basada en REST o una fuente OData. Los paquetes de contenido de Power BI admiten varios tipos de autenticación como autenticación básica, OAuth 2.0 y clave de API. 
* La aplicación de SaaS está aprobada para publicar un paquete de contenido. Envíe la solicitud a la dirección pbiservicesapps@microsoft.com. Analizaremos cada envío según su relevancia y el uso esperado. 
* Acuerdo de asociado firmado. Lo hará en el [paso de envío](template-content-pack-testing.md#submission).

Revise la sección [creación](template-content-pack-authoring.md) para obtener más detalles sobre los requisitos técnicos.

## <a name="business-scenario"></a>Escenario empresarial
Los paquetes de contenido proporcionan la visión y métricas centradas en un escenario de negocio concreto. La descripción de la audiencia y el beneficio que recibirán el paquete de contenido le ayudarán a asegurarse de que los usuarios están correctamente con el contenido que proporcione.

### <a name="tips"></a>Sugerencias
* Identificar la audiencia y la tarea que está intentando realizar  
* Centrarse en un período determinado (últimos 90 días) o en los últimos resultados de N  
* Importar solo las tablas o columnas relacionadas con su escenario  
* Tenga en cuenta que ofrece más de un paquete de contenido para escenarios únicos independientes  

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes
**Como tercero, ¿puedo crear un paquete de contenido del servicio Power BI para una aplicación SaaS que no es de mi propiedad?**

Se exige firmar un acuerdo entre socios con el propietario de la aplicación SaaS para poder publicar un paquete de contenido del servicio. Como tercero, debe facilitar la firma del acuerdo entre socios con el propietario de la aplicación SaaS.

**No tengo una API para desarrolladores pública para mi servicio. ¿Puedo crear un paquete de contenido del servicio Power BI que extraiga los datos directamente del almacenamiento de datos?**

No, los paquetes de contenido del servicio Power BI requieren una API para desarrolladores que sea accesible a través de la red pública de Internet.

**¿Qué tipos de API son compatibles con los paquetes de contenido del servicio y con qué tipos de autenticación funcionan?**

Los paquetes de contenido del servicio Power BI admiten cualquier API de REST o fuente OData. Power BI puede trabajar con varios tipos de autenticación como autenticación básica, OAuth2.0 y clave de la API de web. Consulte más detalles sobre los requisitos técnicos en el artículo [Creación del paquete de contenido de plantillas](template-content-pack-authoring.md#dashboard).

**Tengo un paquete de contenido publicado en Power BI. ¿Cómo puedo actualizarlo?**

Los paquetes de contenido publicados se pueden actualizar una vez al mes. Las solicitudes de actualización enviadas a [pbiservicesapps@microsoft.com](mailto:pbiservicesapps@microsoft.com) antes del último día del mes en curso se publican en la primera semana del mes siguiente.

**Tengo más preguntas acerca de los paquetes de contenido del servicio. ¿Cómo puedo ponerme en contacto con usted?**

No dude en enviarnos un mensaje de correo electrónico con sus preguntas a [pbiservicesapps@microsoft.com](mailto:pbiservicesapps@microsoft.com)

## <a name="support"></a>Soporte técnico
Para obtener soporte técnico durante el desarrollo, use [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support). Se realiza la supervisión y administración de forma activa. Los incidentes del cliente encuentran rápidamente la forma de llegar al equipo adecuado.

## <a name="next-step"></a>Paso siguiente
[Creación](template-content-pack-authoring.md)

