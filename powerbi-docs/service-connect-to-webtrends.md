---
title: Conexión a Webtrends con Power BI
description: Webtrends para Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 1166808dc827448f94bb84cc37bf4000df178c1d
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008681"
---
# <a name="connect-to-webtrends-with-power-bi"></a>Conexión a Webtrends con Power BI
El paquete de contenido de Webtrends para Power BI incluye una variedad de métricas listas para usar como, por ejemplo, las vistas de página totales o las visitas por origen del tráfico. La visualización de los datos de Webtrends en Power BI comienza por la conexión a su cuenta de Webtrends. Puede usar el panel y los informes proporcionados, o bien personalizarlos para resaltar la información que más le interesa.  Los datos se actualizarán automáticamente una vez al día.

Conéctese al [paquete de contenido de Webtrends para Power BI](https://app.powerbi.com/getdata/services/webtrends).

## <a name="how-to-connect"></a>Cómo conectarse
1. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo.
   
   ![](media/service-connect-to-webtrends/getdata3.png)
2. En el cuadro **Servicios** , seleccione **Obtener**.
   
   ![](media/service-connect-to-webtrends/services.png)
3. Seleccione **Webtrends** \> **Obtener**.
   
   ![](media/service-connect-to-webtrends/webtrends.png)
4. El paquete de contenido se conecta a un identificador de perfil de Webtrends específico. Consulte los detalles acerca de la [búsqueda de este parámetro](#FindingParams) más adelante.
   
   ![](media/service-connect-to-webtrends/parameters.png)
5. Especifique sus credenciales de Webtrends para conectarse. Tenga en cuenta que el campo de nombre de usuario espera su cuenta y nombre de usuario. Consulte los [detalles](#FindingParams) más adelante.
   
   ![](media/service-connect-to-webtrends/creds.png)
6. Tras la aprobación, el proceso de importación se iniciará automáticamente. Cuando haya finalizado, aparecerá un nuevo panel, informes y modelo en el panel de navegación. Seleccione el panel para ver los datos importados.
   
   ![](media/service-connect-to-webtrends/dashboard.png)

**¿Qué más?**

* Pruebe a [hacer una pregunta en el cuadro de preguntas y respuestas](consumer/end-user-q-and-a.md), en la parte superior del panel.
* [Cambie los iconos](service-dashboard-edit-tile.md) en el panel.
* [Seleccione un icono](consumer/end-user-tiles.md) para abrir el informe subyacente.
* Aunque el conjunto de datos se programará para actualizarse diariamente, puede cambiar la programación de actualización o intentar actualizar a petición mediante **Actualizar ahora**

## <a name="whats-included"></a>Qué se incluye
<a name="Included"></a>

El paquete de contenido de Webtrends extrae datos de los informes siguientes:  

| Nombre del informe | Report ID (Id. de informe) |
| --- | --- |
| Métricas clave | |
| On-Site Searches (Búsquedas en el sitio) |34awBVEP0P6 |
| Exit Pages (Páginas de salida) |7FshY8eP0P6 |
| Next Pages (Páginas siguientes) |CTd5rpeP0P6 |
| Previous Pages (Páginas anteriores) |aSdOeaUgnP6 |
| Site Pages (Páginas del sitio) |oOEWQj3sUo6 |
| Onsite Ads Clickthroughs (click-throughs de anuncios en el sitio) |41df19b6d9f |
| Cities (Ciudades) |aUuHskcP0P6 |
| Países |JHWXJNcP0P6 |
| Visitors (Visitantes) |xPcmTDDP0P6 |
| Visit Duration (Duración de la visita) |U5KAyqdP0P6 |
| Search Phrases (Frases de búsqueda) |IKYEDxIP0P6 |
| Traffic Sources (Orígenes de tráfico) |JmttAoIP0P6 |
| Search Engines (Motores de búsqueda) |yGz3gAGP0P6 |
| Entry Pages (Páginas de entrada) |i6LrkNVRUo6 |

>[!NOTE]
>Para los perfiles de SharePoint, los nombres de las métricas pueden ser un poco diferentes de las que se muestran en la interfaz de usuario de Webtrends. Para mantener la coherencia entre los perfiles de SharePoint y Web se realiza la asignación siguiente:   

    - Sesiones = Visitas  
    - Nuevos usuarios = Nuevos visitantes  
    - Vistas por sesión = Vistas de páginas por visita  
    - Duración de usuario promedio diario = Promedio de tiempo en el sitio por visitante  

## <a name="system-requirements"></a>Requisitos del sistema
El paquete de contenido requiere acceso a un perfil de Webtrends con el [conjunto de informes correcto](#Included) habilitado.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Búsqueda de parámetros
El identificador de perfil de Webtrends puede encontrarse en la dirección URL después de seleccionar un perfil:

![](media/service-connect-to-webtrends/webtrendsparameters.png)

Las credenciales son las mismas que las que se especifican al iniciar sesión en Webtrends; sin embargo, esperamos su cuenta y el nombre de usuario en la misma línea separados por una barra diagonal inversa:

![](media/service-connect-to-webtrends/webtrendscreds.png)

## <a name="troubleshooting"></a>Solución de problemas
Puede abordar un problema mientras se está cargando el paquete de contenido, después de proporcionar sus credenciales. Si ve el mensaje "¡Vaya!" durante la carga, revise las sugerencias de solución de problemas siguientes. Si todavía tiene problemas, envíe una incidencia de soporte técnico a https://support.powerbi.com

1. Se utiliza el identificador de perfil correcto; consulte [Búsqueda de parámetros](#FindingParams) para más detalles.
2. El usuario tiene acceso a los informes que aparecen en la sección ["Qué se incluye"](#Included)

## <a name="next-steps"></a>Pasos siguientes
[¿Qué es Power BI?](power-bi-overview.md)

[Power BI: Conceptos básicos](consumer/end-user-basic-concepts.md)

