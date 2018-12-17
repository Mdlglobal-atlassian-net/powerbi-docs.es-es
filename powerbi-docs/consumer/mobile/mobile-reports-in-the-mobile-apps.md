---
title: Exploración de informes en las aplicaciones móviles de Power BI
description: Aprenda a ver informes e interactuar con ellos en las aplicaciones móviles de Power BI del teléfono o la tableta. Cree informes en el servicio Power BI o en Power BI Desktop y, luego, interactúe con ellos en las aplicaciones móviles.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 08/17/2018
ms.author: maggies
ms.openlocfilehash: 694ae2cd6f77fbcf898a984b135fb65b9163a43b
ms.sourcegitcommit: f25464d5cae46691130eb7b02c33f42404011357
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53180999"
---
# <a name="explore-reports-in-the-power-bi-mobile-apps"></a>Exploración de informes en las aplicaciones móviles de Power BI
Se aplica a:

| ![iPhone](././media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![iPad](././media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![Teléfono Android](././media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Tableta Android](././media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Dispositivos de Windows 10](./media/mobile-reports-in-the-mobile-apps/win-10-logo-40-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone |iPad |Teléfonos Android |Tabletas Android |Dispositivos de Windows 10 |

Un informe de Power BI es una vista interactiva de los datos, con objetos visuales que describen distintas conclusiones e información a partir de esos datos. Ver informes en las aplicaciones móviles de Power BI es el tercer paso de un proceso de tres pasos.

1. [Crear informes en Power BI Desktop](../../desktop-report-view.md). Puede incluso [optimizar un informe para teléfonos](mobile-apps-view-phone-report.md) en Power BI Desktop. 
2. Publique esos informes en el servicio Power BI [(https://powerbi.com)](https://powerbi.com) o [Power BI Report Server](../../report-server/get-started.md).  
3. Interactuar luego con estos informes en las aplicaciones móviles de Power BI.

## <a name="open-a-power-bi-report-in-the-mobile-app"></a>Apertura de un informe de Power BI en la aplicación móvil
Los informes de Power BI se almacenan en distintos lugares de la aplicación móvil, en función de su procedencia. Pueden estar en Aplicaciones, Compartido conmigo, Áreas de trabajo (incluidos Mi área de trabajo) o en un servidor de informes. A veces se desplaza por un panel relacionado para llegar a un informe y a veces aparecen en una lista.

* En el panel, pulse el botón de puntos suspensivos (...) en la esquina superior derecha de un icono > **Abrir informe**.
  
  ![Abrir informe](./media/mobile-reports-in-the-mobile-apps/power-bi-android-open-report-tile.png)
  
  No todos los iconos tienen la opción de abrirse en un informe. Por ejemplo, los iconos que ha creado cuando hace una pregunta en el cuadro de preguntas y respuestas no abren informes al pulsar en ellos. 
  
  En un teléfono, el informe se abre en modo horizontal, a menos que esté [optimizado para visualizarse en un teléfono](mobile-reports-in-the-mobile-apps.md#view-reports-optimized-for-phones).
  
  ![Informe de teléfono en modo horizontal](./media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-landscape.png)

## <a name="view-reports-optimized-for-phones"></a>Visualización de informes optimizados para teléfonos
Los autores de informes de Power BI pueden crear un diseño de informe optimizado especialmente para teléfonos. Se ha agregado funcionalidad a las páginas de informes optimizadas para teléfonos; por ejemplo, puede explorar en profundidad y ordenar los objetos visuales y puede tener acceso a los [filtros que el autor del informe ha agregado a la página del informe](mobile-apps-view-phone-report.md#filter-the-report-page-on-a-phone). El informe se abre en el teléfono filtrado según los valores que se filtran en el informe en la Web, además de un mensaje que indica que hay filtros activos en la página. Puede cambiar los filtros en el teléfono.Puede cambiar los filtros en el teléfono.

En una lista de informes, un informe optimizado tiene un icono especial ![Icono de informe de teléfono](./media/mobile-reports-in-the-mobile-apps/power-bi-phone-report-icon.png):

![Abrir informe de teléfono](./media/mobile-reports-in-the-mobile-apps/power-bi-android-phone-report.png)

Al ver el informe en un teléfono, se abre en la vista vertical.

![Informe en vista vertical](./media/mobile-reports-in-the-mobile-apps/07-power-bi-phone-report-portrait.png)

 Un informe puede tener una combinación de páginas optimizadas y no optimizadas para teléfonos. Por lo tanto, al desplazarse por el informe, la vista cambiará de vertical a horizontal para cada página.

Más información sobre los [informes optimizados para la vista de teléfono](mobile-apps-view-phone-report.md).

## <a name="use-slicers-to-filter-a-report"></a>Uso de segmentaciones de datos para filtrar un informe
Al diseñar un informe en el servicio Power BI Desktop o Power BI, considere la posibilidad de [agregar segmentaciones a una página del informe](../../visuals/power-bi-visualization-slicers.md). Usted y sus compañeros pueden usar segmentaciones para filtrar la página en un explorador y en las aplicaciones móviles. Cuando ve el informe en un teléfono, puede ver e interactuar con las segmentaciones en modo horizontal y en una página optimizada para el modo vertical del teléfono. Si selecciona un valor en una segmentación o un filtro del explorador, el valor también se seleccionará cuando vea la página en la aplicación móvil. Verá un mensaje que indica que hay filtros activos en la página.  

* Al seleccionar un valor en una segmentación de datos de la página de informe, se filtran los demás objetos visuales de la página.
  
  ![Segmentación de informe](./media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-slicer.png)
  
  En esta ilustración, la segmentación de datos filtra el gráfico de columnas para mostrar solo los valores de julio.

## <a name="cross-filter-and-highlight-a-report"></a>Aplicar un filtro cruzado a un informe y resaltarlo
Cuando selecciona un valor en un objeto visual, lo no filtra los otros objetos visuales. Resalta los valores relacionados en los otros objetos visuales.

* Pulse un valor en un objeto visual.
  
  ![Aplicar un filtro cruzado a una página](./media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-highlight.png)
  
  Al pulsar en la columna Large (Grande) en un objeto visual, se resaltan los valores relacionados en los demás objetos visuales. 

## <a name="sort-a-visual-on-an-ipad-or-a-tablet"></a>Ordenación de un objeto visual en un iPad o una tableta
* Pulse el gráfico y el botón de puntos suspensivos (**...**) y, después, el nombre del campo.
  
   ![Ordenar un objeto visual](./media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-sort.png)
* Para invertir el criterio de ordenación, pulse de nuevo el botón de puntos suspensivos (**...**) y otra vez el mismo nombre de campo.

## <a name="drill-down-and-up-in-a-visual"></a>Explorar en profundidad y rastrear agrupando datos de un objeto visual
Si el autor de un informe ha agregado la funcionalidad de exploración en profundidad a un objeto visual, puede explorar en profundidad un objeto visual para ver los valores que constituyen una parte de él. Puede [agregar una exploración en profundidad a un objeto visual](../end-user-drill.md) tanto en Power BI Desktop como en el servicio Power BI. 

* Mantenga pulsada una barra determinada o un punto de un objeto visual para mostrar la información en pantalla. Si admite la exploración desagrupando los datos, se mostrarán flechas que podrá pulsar en la parte inferior de la información sobre herramientas. 
  
  ![Exploración en profundidad en un objeto visual](./media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-down-tooltip.png)

* Para volver a agrupar los datos, pulse la flecha hacia arriba en la información sobre herramientas.
  
  ![Explorar agrupando datos](./media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up-tooltip.png)

* También puede explorar desagrupando los datos todos los puntos de datos de un objeto visual. Ábralo en el modo de enfoque, pulse el icono de Explorar y elija mostrar todo el siguiente nivel, o bien amplíe para que se muestren el nivel actual y el próximo.

   ![Explorar desagrupando los datos en Power BI](./media/mobile-reports-in-the-mobile-apps/power-bi-drill-down-all.png)

## <a name="drill-through-from-one-page-to-another"></a>Explorar varias páginas al mismo tiempo

Con la *obtención de detalles*, al pulsar una parte específica de un objeto visual, Power BI le mostrará otra página del informe y la filtrará según el valor que haya pulsado. El autor de un informe puede definir una o más opciones de exploración de varias páginas, de modo que cada opción dirija a una página diferente. En ese caso, podrá elegir en qué página quiere obtener detalles. En el ejemplo siguiente, al pulsar el valor en el medidor, puede elegir entre obtener detalles **por el gasto de cada área de negocio** o **por la planificación de cada área de negocio**.

![Informe detallado de obtención de detalles de Power BI Mobile](./media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-through-it-spent-report.png)

Al obtener detalles, el botón Atrás lo dirigirá de vuelta a la página de informe anterior.

Obtenga información sobre cómo [agregar la obtención de detalles a Power BI Desktop](../../desktop-drillthrough.md).

## <a name="show-data-and-copy-values"></a>Mostrar datos y copiar valores

Para ver los datos subyacentes a una visualización, seleccione los puntos suspensivos en las opciones del menú (**...**) en la esquina superior derecha de una visualización en un informe para móviles y, luego, seleccione **Mostrar datos**.

![Opción de menú Mostrar datos para móviles en Power BI](./media/mobile-reports-in-the-mobile-apps/copy-data-visual.png)

Al realizar una pulsación larga en una celda de la tabla presentada se mostrará el menú nativo de selección y copia, donde podrá elegir los datos de copia de la tabla (o la tabla entera).

![Informe detallado de obtención de detalles de Power BI Mobile](./media/mobile-reports-in-the-mobile-apps/copy-data-table.png)

## <a name="next-steps"></a>Pasos siguientes
* [Ver e interactuar con informes de Power BI optimizados para el teléfono](mobile-apps-view-phone-report.md)
* [Creación de versiones de informes optimizadas para teléfonos](../../desktop-create-phone-report.md)
* ¿Tiene alguna pregunta? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

