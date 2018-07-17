---
title: Procedimiento para insertar paneles, informes e iconos de Power BI
description: Obtenga información sobre los pasos necesarios para insertar contenido de Power BI en su aplicación.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: maghan
ms.openlocfilehash: 8a912791777c631208ee40d37c5eaad56806ccf9
ms.sourcegitcommit: 001ea0ef95fdd4382602bfdae74c686de7dc3bd8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2018
ms.locfileid: "38924722"
---
# <a name="embed-your-power-bi-dashboards-reports-and-tiles"></a>Inserción de paneles, informes e iconos de Power BI

Obtenga información sobre los pasos necesarios para insertar contenido de Power BI en su aplicación.

Microsoft [presentó Power BI Premium](https://powerbi.microsoft.com/blog/microsoft-accelerates-modern-bi-adoption-with-power-bi-premium/), un nuevo modelo de licencias basado en la capacidad que aumenta la flexibilidad con la que los usuarios acceden al contenido, lo comparten y lo distribuyen. La oferta también incluye mayor rendimiento y escalabilidad para el servicio Power BI. También se presentó Power BI Embedded que permite la creación de capacidad en Microsoft Azure. Power BI Embedded se centra en sus aplicaciones y clientes. 

En este artículo se explica cómo insertar contenido de Power BI para la organización y los usuarios. Los pasos son similares en ambos casos. Se resaltará el texto cuando un paso de inserción sea específico para el cliente.

Hay que realizar algunos pasos con la aplicación para hacer esto posible. Revisaremos los pasos necesarios para poder crear y usar contenido insertado en la aplicación.

> [!NOTE]
> Las API de Power BI siguen haciendo referencia a las áreas de trabajo de la aplicación como grupos. Todas las referencias a grupos significan que está trabajando con áreas de trabajo de la aplicación.

## <a name="step-1-setup-your-embedded-analytics-development-environment"></a>Paso 1: Configurar el entorno de desarrollo de análisis insertados

Antes de empezar a insertar paneles e informes en la aplicación, debe asegurarse de que su entorno está configurado para permitir la inserción. Como parte de la configuración debe hacer lo siguiente.

* [Asegúrese de que tiene un inquilino de Azure Active Directory](embedding-content.md#azureadtenant)
* [Crear una cuenta de Power BI Pro](embedding-content.md#proaccount)
* [Registro y permisos de la aplicación](embedding-content.md#appreg)
* [Creación de las áreas de trabajo de la aplicación](embedding-content.md#appws)
* [Creación y carga de los informes](embedding-content.md#createreports)

Puede seguir los pasos de la [herramienta para incorporar la inserción](https://aka.ms/embedsetup) para empezar a trabajar rápidamente y descargar una aplicación de ejemplo.

Elija la solución que más le convenga:
* La [inserción para los clientes](embedding.md#embedding-for-your-customers) permite insertar paneles e informes para los usuarios que no tienen una cuenta de Power BI. Ejecute la solución de [inserción para los clientes](https://aka.ms/embedsetup/AppOwnsData).
* La [inserción para la organización](embedding.md#embedding-for-your-organization) permite ampliar el servicio Power BI. Ejecute la solución de [inserción para la organización](https://aka.ms/embedsetup/UserOwnsData).

Si prefiere configurar el entorno manualmente, siga los pasos que se indican más adelante. 

> [!NOTE]
> La capacidad dedicada no es necesaria para el desarrollo de la aplicación. Los desarrolladores de la aplicación deben disponer de una licencia de Power BI Pro.

### <a name="azureadtenant"></a>Inquilino de Azure Active Directory

Necesita un inquilino de Azure Active Directory (Azure AD) para insertar elementos de Power BI. Este inquilino debe tener al menos un usuario de Power BI Pro. También debe definir una aplicación de Azure AD en el inquilino. Puede hacer uso de un inquilino de Azure AD existente o crear uno nuevo específicamente para fines de inserción.

Debe determinar qué configuración de inquilino usará si va a insertar contenido para los clientes.

* ¿Se usa el inquilino de Power BI corporativo actual?
* ¿Se usa un inquilino independiente para la aplicación?
* ¿Se usa un inquilino independiente para cada cliente?

Si no desea usar un inquilino existente, puede decidir crear uno nuevo para la aplicación o uno para cada cliente, consulte [Crear un inquilino de Azure Active Directory](create-an-azure-active-directory-tenant.md) u [Obtención de un inquilino de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant).

### <a name="proaccount"></a>Crear una cuenta de usuario de Power BI Pro

Solo necesita una única cuenta de Power BI Pro para insertar contenido. No obstante, puede que desee tener algunos usuarios diferentes con acceso específico a los elementos. Aquí se indican los posibles usuarios que debe tener en cuenta en el inquilino.

Las siguientes cuentas deben estar presentes en el inquilino y debe disponer de una licencia de Power BI asignada. Se requiere una licencia de Power BI Pro para trabajar con áreas de trabajo de la aplicación dentro de Power BI.

#### <a name="an-organizationtenant-admin-user"></a>Un usuario administrador de la organización o el inquilino.

Se recomienda no utilizar el usuario administrador global de la organización o el inquilino como la cuenta que utiliza la aplicación si inserta contenido para los clientes. Con esto se pretende minimizar el acceso que la cuenta de la aplicación tiene dentro del inquilino. El usuario administrador debe ser administrador en todas las áreas de trabajo de la aplicación que se han creado para la inserción.

#### <a name="accounts-for-analysts-that-create-content"></a>Cuentas para los analistas que crean contenido

Puede tener varios usuarios que crean contenido para Power BI. Necesita una cuenta de Power BI Pro para cada analista que cree e implemente contenido en Power BI.

#### <a name="an-application-master-user-account-for-embedding-for-your-customers"></a>Una cuenta de usuario *maestro* de aplicación para insertar contenido para los clientes

Se trata de la cuenta maestra que usa la aplicación para insertar contenido para los clientes. Este escenario se usa habitualmente para las aplicaciones de ISV. La cuenta maestra es la única cuenta necesaria en la organización. También se puede utilizar como cuenta de administrador o de analista, pero no se recomienda. El back-end de la aplicación almacena las credenciales para esta cuenta y las usa para adquirir un token de autenticación de Azure AD para usarlo con las API de Power BI. Esta cuenta genera un token de inserción para que la aplicación lo use para los clientes.

La cuenta maestra es solo un usuario normal con una licencia de Power BI Pro que usa con su aplicación. Debe tratarse de la cuenta de un administrador del área de trabajo de la aplicación que se va a usar para la inserción.

### <a name="appreg"></a> Registro y permisos de la aplicación

Para realizar llamadas a la API de REST es necesario registrar la aplicación en Azure AD. Para más información, consulte [Registro de una aplicación de Azure AD para insertar contenido de Power BI](register-app.md).

### <a name="appws"></a>Creación de las áreas de trabajo de la aplicación

Si va a insertar paneles e informes para los clientes, estos deben haberse colocado en un área de trabajo de la aplicación. La cuenta *maestra*, mencionada anteriormente, debe corresponder a un administrador del área de trabajo de la aplicación.

[!INCLUDE [powerbi-service-create-app-workspace](../includes/powerbi-service-create-app-workspace.md)]

> [!NOTE]
> Un usuario que no sea administrador solo puede crear hasta 250 áreas de trabajo de aplicación. Para crear más áreas de trabajo de aplicación, debe usar una cuenta de administrador de inquilinos.
>

### <a name="createreports"></a>Creación y carga de los informes

Puede crear sus propios informes y conjuntos de datos mediante Power BI Desktop y publicar esos informes en un área de trabajo de la aplicación. El usuario final que publique los informes deberá tener una licencia de Power BI Pro para publicar en un área de trabajo de la aplicación.

## <a name="step-2-embed-your-content"></a>Paso 2: Insertar el contenido

Dentro de la aplicación, debe autenticarse con Power BI. Si va a insertar contenido para los clientes, debe almacenar las credenciales de la cuenta *maestra* en la aplicación.

> [!NOTE]
> Para más información sobre cómo autenticar usuarios al insertar contenido para sus clientes, consulte [Autenticación de usuarios y obtención de un token de acceso de Azure AD para la aplicación de Power BI](get-azuread-access-token.md).
>

Una vez autenticado, en la aplicación, utilice las API de REST de Power BI y JavaScript para insertar paneles e informes en la aplicación. 

Para **insertar contenido para su organización**, consulte los siguientes tutoriales:

* [Integrar un panel en una aplicación](integrate-dashboard.md)
* [Integrar un icono en una aplicación](integrate-tile.md)
* [Integrar un informe en una aplicación](integrate-report.md)

Para **insertar contenido para sus clientes**, lo cual es habitual con aplicaciones de ISV, consulte lo siguiente:

* [Integración de un panel, icono o informe en la aplicación](embed-sample-for-customers.md)

Se necesitará un token de inserción en el caso de que las inserciones sean para los clientes. Para obtener más información, vea [Embed Token](https://docs.microsoft.com/rest/api/power-bi/embedtoken) (Token de inserción).

## <a name="step-3-promote-your-solution-to-production"></a>Paso 3: Promover la solución a producción

Pasar a producción requiere algunos pasos adicionales.

### <a name="embedding-for-your-organization"></a>Inserción de contenido para la organización

Si va a realizar inserciones para la organización, solo necesita que los demás sepan cómo acceder a la aplicación. 

Todos los usuarios, sea cual sea la licencia que tengan asignada, pueden consumir contenido insertado desde un área de trabajo de la aplicación (grupo) si esa área de trabajo está respaldada por una capacidad dedicada. Dicho esto, deberá agregar expresamente al área de trabajo de la aplicación aquellos usuarios que carezcan de una licencia de Power BI Pro. En caso contrario, recibirá un error 401 de no autorización. En la tabla siguiente se enumeran las SKU disponibles de Power BI Premium en Office 365.

| Nodo de capacidad | Núcleos totales<br/>*(Back-end y front-end)* | Núcleos de back-end | Núcleos de front-end | Límites de conexiones dinámicas/DirectQuery | Representaciones de páginas máximas en horas punta |
| --- | --- | --- | --- | --- | --- |
| EM3 |4 núcleos V |2 núcleos, 10 GB de RAM |2 núcleos | |601-1200 |
| P1 |8 núcleos V |4 núcleos, 25 GB de RAM |4 núcleos |30 por segundo |1201-2400 |
| P2 |16 núcleos V |8 núcleos, 50 GB de RAM |8 núcleos |60 por segundo |2401-4800 |
| P3 |32 núcleos V |16 núcleos, 100 GB de RAM |16 núcleos |120 por segundo |4,801-9600 |

> [!NOTE]
> Debe ser un administrador global o de facturación dentro del inquilino para poder comprar Power BI Premium. Para más información sobre cómo adquirir Power BI Premium, consulte [Adquisición de Power BI Premium](../service-admin-premium-purchase.md).

>[!Note]
>[Configure el entorno de análisis integrado para su organización.](#step-1-setup-your-embedded-analytics-development-environment)
>

### <a name="embedding-for-your-customers"></a>Inserción de contenido para los clientes

Si las inserciones están destinadas para los clientes, debe hacer lo siguiente.

* Si usa un inquilino independiente para el desarrollo, tendrá que asegurarse de que las áreas de trabajo de la aplicación, junto con los paneles e informes, estén disponibles en el entorno de producción. Asegúrese de que creó la aplicación en Azure AD para el inquilino de producción y de que se le asignaron los permisos de aplicación adecuados, tal como se indica en el paso 1.
* Adquiera la capacidad que se adapte a sus necesidades. Puede usar la tabla siguiente para saber qué SKU de la capacidad de Power BI Embedded puede necesitar. Para obtener más información, vea [Embedded analytics capacity planning whitepaper](https://aka.ms/pbiewhitepaper) (Notas del producto sobre el planeamiento de la capacidad de análisis de inserción). Cuando esté listo para comprar, vaya a [Microsoft Azure Portal](https://portal.azure.com). Para más información acerca de cómo crear la capacidad de Power BI Embedded, consulte [Create Power BI Embedded capacity in the Azure portal](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity) (Creación de capacidad de Power BI Embedded en Azure Portal).

> [!IMPORTANT]
> Dado que la inserción de tokens está pensada solo para que los desarrolladores efectúen pruebas, el número de tokens que puede generar una cuenta maestra de Power BI es limitado. Debe [adquirirse capacidad](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical) para escenarios de inserción para producción. No hay ningún límite en la generación de tokens de inserción cuando se compra una capacidad dedicada. Vaya a [Available Features](https://docs.microsoft.com/rest/api/power-bi/availablefeatures) (Características disponibles) para comprobar para cuántos tokens de inserción gratuitos se han usado.

| Nodo de capacidad | Núcleos totales<br/>*(Back-end y front-end)* | Núcleos de back-end | Núcleos de front-end | Límites de conexiones dinámicas/DirectQuery | Representaciones de páginas máximas en horas punta |
| --- | --- | --- | --- | --- | --- |
| A1 |1 núcleo V |.5 núcleos, 3 GB de RAM |5 núcleos | 5 por segundo |1-300 |
| A2 |2 núcleos V |1 núcleo, 5 GB de RAM |1 núcleo | 10 por segundo |301-600 |
| A3 |4 núcleos V |2 núcleos, 10 GB de RAM |2 núcleos | 15 por segundo |601-1200 |
| A4 |8 núcleos V |4 núcleos, 25 GB de RAM |4 núcleos |30 por segundo |1201-2400 |
| A5 |16 núcleos V |8 núcleos, 50 GB de RAM |8 núcleos |60 por segundo |2401-4800 |
| A6 |32 núcleos V |16 núcleos, 100 GB de RAM |16 núcleos |120 por segundo |4,801-9600 |

* Edite el área de trabajo de la aplicación y asígnele una capacidad dedicada en las opciones avanzadas.

    ![Asignación de un área de trabajo de la aplicación a una capacidad](media/embedding-content/powerbi-embedded-premium-capacity.png)

* Implemente la aplicación actualizada en producción y empiece a insertar paneles e informes de Power BI.

>[!Note]
>[Configure el entorno de análisis integrado para sus clientes.](#step-1-setup-your-embedded-analytics-development-environment) 
>

## <a name="admin-settings"></a>Configuración de administración

Los administradores globales, o los administradores de servicios de Power BI, pueden activar o desactivar la capacidad para usar las API de REST de un inquilino. Los administradores de Power BI pueden establecer esta opción de configuración para toda la organización o para grupos de seguridad individuales. De forma predeterminada, está habilitada para toda la organización. Esto se hace mediante el [portal de administración de Power BI](../service-admin-portal.md).

## <a name="next-steps"></a>Pasos siguientes

[Inserción con Power BI](embedding.md)  
[Migración de contenido de la colección de áreas de trabajo de Power BI Embedded a Power BI](migrate-from-powerbi-embedded.md)  
[¿Qué es Power BI Premium?](../service-premium.md)  
[Adquisición de Power BI Premium](../service-admin-premium-purchase.md)  
[Repositorio Git de la API de JavaScript](https://github.com/Microsoft/PowerBI-JavaScript)  
[Repositorio Git de C# de Power BI](https://github.com/Microsoft/PowerBI-CSharp)  
[Ejemplo de inserción de JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Notas del producto sobre el planeamiento de la capacidad de análisis de inserción](https://aka.ms/pbiewhitepaper)  
[Notas del producto de Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)