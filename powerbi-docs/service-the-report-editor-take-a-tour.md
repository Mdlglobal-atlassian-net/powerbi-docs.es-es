---
title: Un paseo por el editor de informes...
description: Un paseo por el editor de informes.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/11/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 3c6ae5351908bd71888040c3bc900323837935c2
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46546082"
---
# <a name="the-report-editortake-a-tour"></a>Un paseo por el editor de informes...
## <a name="editing-reports-in-power-bi-service-and-power-bi-desktop"></a>Edición de informes en el servicio Power BI y en Power BI Desktop
El editor de informes del servicio Power BI y el editor de informes de Power BI Desktop son muy similares. En el vídeo se muestra el editor de informes en Power BI Desktop y, en este artículo, se muestra el editor de informes en el servicio Power BI. 

## <a name="the-difference-between-report-creators-and-report-consumers"></a>Diferencia entre *creadores* y *consumidores* de informes
La capacidad de crear y editar un informe está restringida a los propietarios de los informes (es decir, los *creadores*). Si está *consumiendo* un informe que se ha compartido con usted, aún podrá abrirlo e interactuar con el informe en el servicio Power BI [solo en la vista de lectura](consumer/end-user-reading-view.md), pero no dispondrá de las sólidas y amplias características disponibles al creador del informe.  

Para más información sobre la vista de lectura del informe, consulte [Vista de lectura y vista de edición de informes del servicio Power BI](consumer/end-user-reading-view.md). 

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

En el servicio Power BI, el *editor de informes* solo está disponible en la [vista de edición](consumer/end-user-reading-view.md). Para abrir un informe en la vista de edición, debe ser el propietario o el creador del informe.

El editor de informes de Power BI se compone de tres secciones:  

1. los paneles **Campos**, **Visualizaciones** y **Filtros**
2. las barras de navegación superior    
3. el lienzo del informe     

![](media/service-the-report-editor-take-a-tour/power-bi-report-canvas.png)

## <a name="1-the-report-editor-panes"></a>1. Paneles del editor de informes
![Editor de informes de Power BI](media/service-the-report-editor-take-a-tour/power-bi-report-panes.png)

Hay tres paneles visibles al abrir un informe: Visualizaciones, Filtros y Campos. Los paneles del lado izquierdo, las Visualizaciones y los Filtros controlan la apariencia de las visualizaciones, como el tipo, los colores, el filtrado y el formato.  Y el panel de la derecha, Campos, administra los datos subyacentes que se usan en las visualizaciones. 

El contenido mostrado en el editor de informes varía según las opciones seleccionadas en el lienzo de informe.  Por ejemplo, al seleccionar un objeto visual individual, 

|  |  |
| --- | --- |
| ![](media/service-the-report-editor-take-a-tour/power-bi-panes.png) |<ul><li>La parte superior del panel Visualización identifica el tipo de objeto visual en uso; en este ejemplo, un gráfico de columnas agrupadas.<br><br></li> <li>La parte inferior del panel Visualización (es posible que tenga que desplazarse hacia abajo) muestra los campos que se están utilizando en el objeto visual. Este gráfico está usando FiscalMonth, DistrictManager y Total Sales Variance. <br><br></li><li>El panel Filtros (es posible que tenga que desplazarse hacia abajo) muestra los filtros que se han aplicado. <br><br></li><li>El panel Campos muestra las tablas disponibles y, si se expande el nombre de la tabla, los campos que forman la tabla. La fuente amarilla le indica que se está utilizando al menos un campo de dicha tabla en la visualización.<br><br></li><li>![Icono de rodillo de pintar](media/service-the-report-editor-take-a-tour/power-bi-paint-roller-icon.png) Para mostrar el panel de formato, en la visualización seleccionada, seleccione el icono de rodillo de pintar.<br><br></li><li>![Icono de lupa](media/service-the-report-editor-take-a-tour/power-bi-magnifying-icon.png) Para mostrar el panel de análisis, seleccione el icono de lupa.</ul> |

## <a name="the-visualizations-pane-from-top-to-bottom"></a>El panel Visualizaciones (de arriba a abajo)
![Parte superior del panel Visualizaciones](media/service-the-report-editor-take-a-tour/selectviz.png)

Aquí es donde se selecciona un tipo de visualización. Las imágenes pequeñas se denominan *plantillas*. En la imagen anterior, se selecciona el gráfico de barras agrupadas. Si no selecciona primero un tipo de visualización, sino que empieza a crear una visualización mediante la selección de campos, Power BI seleccionará el tipo de visualización por usted. Puede mantener la selección de Power BI o cambiar el tipo seleccionando otra plantilla. Cambie tantas veces como necesite para buscar el tipo de visualización que mejor represente los datos.

### <a name="manage-the-fields-used-in-your-visual"></a>Administre los campos utilizados en el objeto visual.
![Parte intermedia del panel Visualizaciones](media/service-the-report-editor-take-a-tour/power-bi-field-list.png)

Los cubos (a veces llamados *áreas*) que se muestran en este panel varían dependiendo del tipo de visualización seleccionada.  Por ejemplo, si seleccionó un gráfico de barras, verá cubos para: Valores, Ejes y Leyenda. Al seleccionar un campo o arrastrarlo hasta el lienzo, Power BI agrega ese campo a uno de los cubos.  También puede arrastrar campos desde la lista de Campos directamente a los cubos.  Algunos cubos están limitados a determinados tipos de datos.  Por ejemplo, **Valores** no aceptará campos no numéricos. Por tanto, si se arrastra un campo **nombredeempleado** al cubo **Valores** , Power BI lo cambia a **recuento de nombredeempleado**.

### <a name="remove-a-field"></a>Quitar un campo
Para quitar un campo de la visualización, seleccione la **X** de la derecha del nombre de campo.

![Eliminación de StoreType de la leyenda](media/service-the-report-editor-take-a-tour/deletefield.png)

Para más información, consulte [Agregar visualizaciones a un informe de Power BI](visuals/power-bi-report-add-visualizations-i.md).

### <a name="format-your-visuals"></a>Dar formato a los objetos visuales
Seleccione el icono del rodillo de pintura para mostrar la pestaña Formato. La opción disponible depende del tipo de visualización seleccionada.

![Panel de formato](media/service-the-report-editor-take-a-tour/power-bi-formatting.png)

Las posibilidades de formato son prácticamente ilimitadas.  Para más información, explore por su cuenta o consulte estos artículos:

* [Personalización del título, el fondo y la leyenda de una visualización](visuals/power-bi-visualization-customize-title-background-and-legend.md)
* [Formato de color](visuals/service-getting-started-with-color-formatting-and-axis-properties.md)
* [Personalizar las propiedades de los ejes X e Y](visuals/power-bi-visualization-customize-x-axis-and-y-axis.md)

### <a name="add-analytics-to-your-visualizations"></a>Agregar análisis a las visualizaciones
Seleccione el icono de lupa para mostrar el panel de análisis. La opción disponible depende del tipo de visualización seleccionada.

![](media/service-the-report-editor-take-a-tour/power-bi-analytics.png)    
Con el panel de análisis del servicio Power BI, puede agregar líneas de referencia dinámicas a visualizaciones y destacar las tendencias o información importantes. Para más información, consulte [Panel de análisis del servicio Power BI](service-analytics-pane.md) o [Panel de análisis en Power BI Desktop](desktop-analytics-pane.md).

- - -
## <a name="the-filters-pane"></a>El panel Filtros
Utilice el panel Filtros para ver, establecer y modificar filtros persistentes en los informes en el nivel de página, informe, obtención de detalles y objetos visuales. Sí, se puede hacer el filtrado ad-hoc en las páginas de informe y en los objetos visuales mediante la selección de elementos de los objetos visuales o con herramientas como las segmentaciones, pero con el panel Filtros se guarda el estado de los filtros con el informe. 

El panel Filtros cuenta con otra eficaz función: la capacidad de filtrar mediante un campo ***que no se esté utilizando en uno de los objetos visuales del informe***. Vamos a explicarlo. Cuando se crea una página del informe, Power BI agrega automáticamente todos los campos que se usan en las visualizaciones al área de filtros de nivel de objetos visuales del panel Filtros.  Sin embargo, si desea establecer un filtro de objeto visual, de página, de obtención de detalles o de informe mediante un campo que no se está utilizando en ninguna visualización, solo hay que arrastrarlo a uno de los cubos de filtros.   

![Panel Filtros](media/service-the-report-editor-take-a-tour/power-bi-formatting-pane.png)

Para más información, consulte [Agregar un filtro a un informe](power-bi-report-add-filter.md).

- - -
## <a name="the-fields-pane"></a>El panel Campos
El panel Campos muestra las tablas y campos que existen en los datos y están disponibles para su uso para crear visualizaciones.

|  |  |
| --- | --- |
| ![Panel Campos](media/service-the-report-editor-take-a-tour/reportfields.png) |<ul><li>Arrastre un campo a la página para iniciar una nueva visualización.  También puede arrastrar un campo a una visualización existente para agregar el campo a esa visualización.<br><br></li> <li>Cuando se agrega una marca de verificación junto a un campo, Power BI agrega ese campo a la visualización activa (o nueva). Y también decide en qué cubo se va a colocar ese campo.  Por ejemplo, ¿debe el campo utilizarse como leyenda, eje o valor? Power BI realiza una mejor estimación y podrá moverlo desde ese cubo a otro si es necesario. <br><br></li><li>En cualquier caso, cada campo seleccionado se agrega al panel Visualizaciones en el editor de informes.</li></ul> |

**NOTA**: si usa Power BI Desktop, también podrá acceder a las opciones para mostrar/ocultar campos, agregar cálculos, etc.

### <a name="what-do-the-field-icons-mean"></a>¿Qué significan los iconos de campo?
* **∑ Agregados** Un agregado es un valor numérico que se suma o cuyo promedio se calcula, por ejemplo. Los agregados se importan con los datos (definidos en el modelo de datos en el que se basa su informe).
  Para más información, consulte [Agregados en los informes de Power BI](service-aggregates.md).
* ![icono de calculadora](media/service-the-report-editor-take-a-tour/pbi_calculated_icon.png) **Medidas calculadas (también denominadas campos calculados)**  
   Cada campo calculado tiene su propia fórmula codificada de forma rígida. No se puede cambiar el cálculo, por ejemplo, si es una suma, solo podrá ser una suma. Para obtener más información, [lea la descripción de las medidas](desktop-measures.md)
* ![Icono de campo único](media/service-the-report-editor-take-a-tour/icon.png) **Campos únicos**  
   Los campos con este icono se importaron desde Excel y están configurados para mostrar todos los valores, incluso si tienen duplicados. Por ejemplo, los datos pueden tener dos registros para las personas llamadas "John Smith" y cada una se tratará de forma única: no se sumarán.  
* **![Icono de geografía](media/service-the-report-editor-take-a-tour/pbi_geo_icon.png) Campos de geografía**  
   Los campos de ubicación se pueden usar para crear visualizaciones de mapas. 
* **![Icono de jerarquía](media/service-the-report-editor-take-a-tour/power-bi-hierarchy-icon.png) Jerarquía**  
   Seleccione la flecha para mostrar los campos que componen la jerarquía. 

- - -
## <a name="2-the-top-navigation-bar"></a>2. Barra de navegación superior
Las acciones disponibles de la barra de navegación superior son numerosas; con nuevas acciones que se agregan todo el tiempo. Para obtener información sobre una acción concreta, use la tabla de contenido de documentación de Power BI o el cuadro de búsqueda.

## <a name="3-the-report-canvas"></a>3. El lienzo del informe
El lienzo del informe es donde se muestra el trabajo. Al utilizar los paneles Visualizaciones, Filtros y Campos para crear objetos visuales, estos se compilan y se muestran en el lienzo del informe. Cada pestaña de la parte inferior del lienzo representa una página del informe. Seleccione una pestaña para abrir esa página. 

## <a name="next-steps"></a>Pasos siguientes:
[Crear un informe](service-report-create-new.md)

Lea más sobre los informes del [servicio Power BI](consumer/end-user-reports.md), [Power BI Desktop](desktop-report-view.md) y [Power BI Mobile](consumer/mobile/mobile-apps-view-phone-report.md).

[Power BI: Conceptos básicos](consumer/end-user-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

