---
title: Interactuación con un mapa de ArcGIS compartido con usted
description: Uso del mapa de ArcGis en la vista de lectura como consumidor de informes de Power BI
author: mihart
manager: kvivek
ms.reviewer: willt
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/10/2019
ms.author: mihart
ms.openlocfilehash: 7fef2c96afadad6fe39d731038f74249a4ccbf6d
ms.sourcegitcommit: 8cc2b7510aae76c0334df6f495752e143a5851c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73432306"
---
# <a name="interacting-with-arcgis-maps-in-power-bi"></a>Interactuación con mapas de ArcGIS en Power BI
Este tema se escribe desde el punto de vista de una persona que *consume* un mapa de ArcGIS en el servicio Power BI, Desktop o para dispositivos móviles. Si un creador comparte un mapa de ArcGIS con usted, existen numerosas maneras de interactuar con el mapa.  Para más información acerca de cómo crear un mapa de ArcGIS, consulte el [tutorial de mapas ArcGIS de Esri](../visuals/power-bi-visualization-arcgis.md).

Con la combinación de ArcGIS Maps y Power BI, los mapas no se limitan a ser una representación de puntos, sino que alcanzan un nivel completamente nuevo. Las opciones disponibles para mapas base, tipos de ubicación, temas, estilos de símbolos y capas de referencia crean magníficas visualizaciones informativas de mapas. La combinación de capas de datos relevantes (como datos del censo) en un mapa con el análisis espacial transmite una comprensión más profunda de los datos en la visualización.

> [!TIP]
> GIS son las siglas en inglés para sistema de información geográfica.
> 

En el ejemplo que se usa, se examinan las ventas del año pasado por ciudad y se utiliza un mapa base de calles, símbolos de burbujas para representar el tamaño y una capa de referencia para los ingresos medios por hogar. El mapa contiene 3 marcas y un radio de tiempo de conducción (en púrpura).

![](media/power-bi-visualizations-arcgis/power-bi-arcgis-esri-new.png)

> [!TIP]
> Visite la [página de Esri en Power BI](https://www.esri.com/powerbi) para ver numerosos ejemplos y leer recomendaciones. Y después consulte la [página de introducción a ArcGIS Maps para Power BI](https://doc.arcgis.com/en/maps-for-powerbi/get-started/about-maps-for-power-bi.htm) de Esri.
> 
> 

<br/>

## <a name="user-consent"></a>Consentimiento del usuario
La primera vez que un compañero comparta un mapa de ArcGIS con usted, Power BI mostrará un aviso. Esri (www.esri.com) proporciona ArcGIS Maps for Power BI y su uso está sujeto a los términos y a la directiva de privacidad de Esri. Los usuarios de Power BI que quieran usar objetos visuales de ArcGIS Maps para Power BI tienen que aceptar el cuadro de diálogo de consentimiento.

## <a name="selection-tools"></a>Herramientas de selección
ArcGIS Maps para Power BI permite tres modos de selección. Se puede seleccionar un máximo de 250 puntos de datos a la vez.

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-tools2.png)

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-single2.png) Seleccione puntos de datos individuales.

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-marquee2.png) Dibuja un rectángulo en el mapa y selecciona los puntos de datos contenidos. Use CTRL para seleccionar más de un área rectangular.

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-reference-layer2.png) Permite usar los límites o polígonos en las capas de referencia para seleccionar puntos de datos contenidos.

<br/>

## <a name="interacting-with-an-arcgis-map"></a>Interactuación con un mapa de ArcGIS
Las características disponibles dependen de si es el *creador* (persona que realizó el mapa) o el *consumidor* (alguien ha compartido un mapa de ArcGIS con usted). Si interactúa con un mapa de ArcGIS como consumidor (también conocido como [Vista de lectura](../consumer/end-user-reading-view.md)), estas son las acciones disponibles.

* Si es un consumidor Premium con permisos de *vista*, podrá [ver los datos utilizados para crear la visualización](../consumer/end-user-show-data.md), [suscribirse](../consumer/end-user-subscribe.md), ver el mapa en [modo de enfoque y modo de pantalla completa](../consumer/end-user-focus.md), [visualizar el contenido relacionado](../consumer/end-user-related.md), [interactuar con los filtros](../consumer/end-user-report-filter.md) establecidos por el *creador del informe*, [compartir el informe](../service-share-reports.md) y mucho más.

* Al igual que con otros tipos de visualización, los consumidores **Pro** de Power BI pueden hacer todo lo que el consumidor Premium puede hacer, además de [exportar los datos subyacentes](../visuals/power-bi-visualization-export-data.md), [obtener métricas de uso](../service-usage-metrics.md), guardar una copia, [publicar en la web](../service-publish-to-web.md) y mucho más.

    
* Expanda el panel **Filters** (Filtros) para explorar el mapa mediante filtros.   
    ![](media/power-bi-visualizations-arcgis/power-bi-filter-newer.png)  
* Si el mapa tiene una capa de referencia, seleccione ubicaciones para mostrar los detalles en una información sobre herramientas. Aquí hemos seleccionado el condado de Adams y vemos los datos de la capa de referencia de los ingresos medios por hogar que el creador ha agregado al mapa.
  
    ![](media/power-bi-visualizations-arcgis/power-bi-reference-layer.png)  
  
    En este caso, también tenemos un gráfico. Seleccione una barra en el gráfico para profundizar en los datos. Aquí vemos que 79 hogares del condado de Adams disfrutan de unos ingresos de 200.000 $ o más.
  
    ![](media/power-bi-visualizations-arcgis/power-bi-tooltip-chart.png)
  
    Seleccione la flecha para mostrar gráficos adicionales.
* Mantenga el puntero sobre los símbolos de ubicación del mapa base para ver los detalles en una información sobre herramientas.     
  ![](media/power-bi-visualizations-arcgis/power-bi-arcgis-hover.png)
  
  > [!TIP]
  > Tendrá que usar la ampliación para seleccionar una ubicación específica.  En caso contrario, si existen ubicaciones superpuestas, Power BI puede presentar más de una información sobre herramientas a la vez. Seleccione las flechas para moverse entre las distintas informaciones sobre herramientas
  > 
  > ![](media/power-bi-visualizations-arcgis/power-bi-3-screens.png)
  > 
  > 
* Si el creador ha agregado una capa de infografías al mapa de ArcGIS, podrá ver datos adicionales que aparecen en la esquina superior derecha del mapa.  Por ejemplo, aquí el creador del mapa ha agregado "Children under 14" ("Hijos menores de 14").
  
    ![](media/power-bi-visualizations-arcgis/power-bi-demographics.png)

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
ArcGIS Maps para Power BI está disponible en los siguientes servicios y aplicaciones:

<table>
<tr><th>Servicio/aplicación</th><th>Disponibilidad</th></tr>
<tr>
<td>Power BI Desktop</td>
<td>Sí</td>
</tr>
<tr>
<td>Servicio Power BI (app.powerbi.com)</td>
<td>Sí</td>
</tr>
<tr>
<td>Aplicaciones móviles de Power BI</td>
<td>Sí</td>
</tr>
<tr>
<td>Publicar en Web de Power BI</td>
<td>No</td>
</tr>
<tr>
<td>Power BI Embedded</td>
<td>No</td>
</tr>
<tr>
<td>Inserción del servicio Power BI (PowerBI.com)</td>
<td>No</td>
</tr>
</table>

**¿Cómo funciona ArcGIS Maps for Power BI?**
Esri (www.esri.com) proporciona ArcGIS Maps for Power BI. Su uso de ArcGIS Maps for Power BI está sujeto a los [términos](https://go.microsoft.com/fwlink/?LinkID=8263222) y a la [directiva de privacidad](https://go.microsoft.com/fwlink/?LinkID=826323) de Esri. Los usuarios de Power BI que quieran usar objetos visuales de ArcGIS Maps for Power BI tienen que aceptar el cuadro de diálogo de consentimiento (vea Consentimiento del usuario para más detalles).  El uso de ArcGIS Maps for Power BI de Esri está sujeto a los términos y a la directiva de privacidad de Esri, a los que puede acceder desde el vínculo del cuadro de diálogo de consentimiento. Cada usuario debe dar su consentimiento antes de usar ArcGIS Maps for Power BI por primera vez. Una vez que el usuario acepta el consentimiento, los datos enlazados al objeto visual se envían a los servicios de Esri al menos para su geocodificación, lo que implica transformar la información de ubicación en información de latitud y longitud que se pueda representar en un mapa. Debe tener en cuenta que los datos enlazados a la visualización de datos pueden enviarse a los servicios de Esri. Esri proporciona servicios como mapas base, análisis espacial, geocodificación, etc. El objeto visual de ArcGIS Maps for Power BI interactúa con estos servicios mediante una conexión SSL protegida por un certificado proporcionado y mantenido por Esri. Puede obtener más información sobre ArcGIS Maps for Power BI en la [Página del producto ArcGIS Maps for Power BI](https://www.esri.com/powerbi) de Esri.

**Power BI Plus**    
![Selección del icono Más para registrarse o iniciar sesión](media/power-bi-visualizations-arcgis/power-bi-plus.png)

Cuando un usuario se suscribe a una suscripción Plus ofrecida por Esri a través de ArcGIS Maps for Power BI, está entablando una relación directa con Esri. Power BI no envía información personal sobre el usuario a Esri. El usuario inicia sesión en una aplicación AAD proporcionada por Esri, y confía en ella, mediante su propia identidad AAD. Al hacerlo, el usuario comparte su información personal directamente con Esri. Una vez que el usuario agrega contenido Plus a un objeto visual de ArcGIS Maps for Power BI, otros usuarios de Power BI también necesitan una suscripción Plus de Esri para ver o editar ese contenido. 

Para realizar preguntas técnicas detalladas sobre el funcionamiento de ArcGIS Maps for Power BI de Esri, póngase en contacto con Esri a través de su sitio de soporte técnico.

**El mapa de ArcGIS no aparece**    
En los servicios o aplicaciones donde ArcGIS Maps para Power BI no está disponible, la visualización mostrará un objeto visual vacío con el logotipo de Power BI.

**No veo toda mi información en el mapa**    
Cuando se geocodifica la latitud o longitud en el mapa, se muestran hasta 30 000 puntos de datos. Cuando se geocodifican puntos de datos como códigos postales o direcciones, solo se geocodifican los primeros 15 000 puntos de datos. La geocodificación de nombres de lugares o países no está sujeto al límite de 1500 direcciones.

**¿Hay algún cargo por usar ArcGIS Maps para Power BI?**

ArcGIS Maps para Power está disponible para todos los usuarios de Power BI sin costo adicional. Es un componente que proporciona **Esri** y su uso está sujeto a los términos y a la directiva de privacidad que proporciona **Esri**, como se ha indicado anteriormente en este artículo. Si se suscribe a ArcGIS **Plus**, hay un cargo.

**Recibo un mensaje de error sobre el hecho de que la caché está llena**

Se trata de un error que están solucionando.  Mientras tanto, seleccione el vínculo que aparece en el mensaje de error para ver instrucciones sobre cómo borrar la caché de Power BI.

**¿Puedo ver mi mapas de ArcGIS sin conexión?**

No, Power BI necesita conectividad de red para mostrar los mapas.

## <a name="next-steps"></a>Pasos siguientes
Obtener ayuda: **Esri** ofrece [documentación exhaustiva](https://go.microsoft.com/fwlink/?LinkID=828772) sobre el conjunto de características de **ArcGIS Maps para Power BI**.

Puede formular preguntas, buscar la información más reciente, notificar problemas y encontrar respuestas en el [hilo de la comunidad de Power BI relacionado con **ArcGIS Maps para Power BI**](https://go.microsoft.com/fwlink/?LinkID=828771).


[Página del producto ArcGIS Maps para Power BI](https://www.esri.com/powerbi)
