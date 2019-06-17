---
title: Anclaje de un icono a un panel de Power BI desde un informe
description: Anclaje de un icono a un panel de Power BI desde un informe.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: lJKgWnvl6bQ
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: a8acb5ab382c541b330d3448da8187238c42a3f5
ms.sourcegitcommit: 762857c8ca09ce222cc3f8b006fa1b65d11e4ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "66720296"
---
# <a name="pin-a-tile-to-a-power-bi-dashboard-from-a-report"></a>Anclaje de un icono a un panel de Power BI desde un informe
## <a name="pinning-tiles-from-a-report"></a>Anclar iconos desde un informe
Una manera de agregar un nuevo [icono del panel](consumer/end-user-tiles.md) es desde un [informe de Power BI](consumer/end-user-reports.md). De hecho, puede agregar muchos nuevos iconos desde un informe.  Cada uno de estos iconos es un vínculo que vuelve al informe.

Además, pueden anclarse páginas de informe completas a un panel.  Esto también se denomina anclar un *icono* dinámico.  *Dinámico* porque puede interactuar con el icono en el panel y porque, a diferencia de los iconos de visualización individual, los cambios del informe se sincronizan con el panel. Obtenga más información a continuación.

No puede anclar iconos desde informes que han compartido con usted ni desde Power BI Desktop. 

> **SUGERENCIA**: Algunas visualizaciones utilizan imágenes de fondo. El anclaje puede no funcionar si la imagen de fondo es demasiado grande.  Intente reducir el tamaño de la imagen o utilice la compresión de imágenes.  
> 
> 

## <a name="pin-a-tile-from-a-report"></a>Anclar un icono desde un informe
Vea cómo Amanda crea un panel con objetos visuales e imágenes anclados desde un informe de Power BI.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

Ahora cree su propio panel con uno de los informes de ejemplo de Power BI.

1. Mantenga el puntero sobre la visualización que desea anclar y seleccione el icono de anclaje ![](media/service-dashboard-pin-tile-from-report/pbi_pintile_small.png). Power BI abre la pantalla **Anclar en el panel** .
   
     ![Ventana Anclar al panel](media/service-dashboard-pin-tile-from-report/pbi_themes2.png)
2. Decida si va a anclar el icono a un panel existente o a uno nuevo.
   
   * Panel existente: seleccione el nombre del panel en la lista desplegable. Los paneles compartidos con usted no aparecerán en la lista desplegable.
   * Nuevo panel: escriba el nombre del nuevo panel.
3. En algunos casos, puede que el elemento que esté anclando ya tenga un *tema* aplicado.  Por ejemplo, objetos visuales anclados desde un libro de Excel. Si es así, seleccione el tema que se debe aplicar al icono.
4. Seleccione **Anclar**.
   
   Un mensaje de confirmación (cerca de la esquina superior derecha) le permitirá saber que se ha agregado la visualización al panel como un icono.
   
   ![Mensaje de proceso correcto](media/service-dashboard-pin-tile-from-report/pinsuccess.png)
5. En el panel de navegación, seleccione el panel con el nuevo icono. Seleccione el icono para volver al informe. O bien, [edite la presentación y el comportamiento del icono](service-dashboard-edit-tile.md).

## <a name="pin-an-entire-report-page"></a>Anclar una página de informe completa
Otra opción es anclar una página de informe completa a un panel. Se trata de una manera fácil de anclar más de una visualización a la vez.  Además, al anclar una página completa, los iconos son *dinámicos* y puede interactuar con ellos desde el panel. Los cambios realizados en cualquiera de las visualizaciones del editor de informes, como agregar un filtro o cambiar los campos utilizados en el gráfico, se reflejan también en el icono del panel.  

Para más información, consulte [Anclar una página de informe completa](service-dashboard-pin-live-tile-from-report.md).

## <a name="next-steps"></a>Pasos siguientes
[Paneles en Power BI](consumer/end-user-dashboards.md)

[Iconos de paneles en Power BI](consumer/end-user-tiles.md)

[Informes en Power BI](consumer/end-user-reports.md)

[Actualizar datos en Power BI](refresh-data.md)

[Conceptos básicos para los diseñadores en el servicio Power BI](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

