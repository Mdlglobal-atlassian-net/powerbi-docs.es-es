---
title: Gráficos de anillos en Power BI
description: Gráficos de anillos en Power BI
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/23/2017
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 5d8be3d160e8ea37ba9814c7bd78c3ad5a751d3b
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34294205"
---
# <a name="doughnut-charts-in-power-bi"></a>Gráficos de anillos en Power BI
Un gráfico de anillos es similar a un gráfico circular porque muestra la relación de las partes con el todo. La única diferencia es que el centro está en blanco y deja espacio para un icono o una etiqueta.

## <a name="create-a-doughnut-chart"></a>Crear un gráfico de anillos
Estas instrucciones usan el ejemplo de análisis de venta directa para crear un gráfico de anillos que muestra las ventas de este año por categorías. Para poder continuar, [descargue el ejemplo](sample-datasets.md) del servicio Power BI (app.powerbi.com) o Power BI Desktop.

1. Comience en una [página de informe en blanco](power-bi-report-add-page.md) y seleccione el campo **SalesStage** \> **Sales Stage**. Si está utilizando el servicio Power BI, asegúrese de que abre el informe en [Vista de edición](service-interact-with-a-report-in-editing-view.md).

2. En el panel Campos, seleccione **Ventas** \> **Ventas del último año**.  
   
3. En el panel Visualizaciones, seleccione el icono del gráfico de anillos ![icono del gráfico de anillos]() para convertir el gráfico de barras en un gráfico de anillos. Si **Ventas del último año** no está en el área **Valores**, arrástrelo aquí.
     
   ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. Seleccione **Elemento** \> **Categoría** para agregarlo al área **Leyenda**. 
     
    ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. Si lo desea, [ajuste el tamaño y el color del texto del gráfico](power-bi-visualization-customize-title-background-and-legend.md). 

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
* La suma de los valores del gráfico de anillos debe ser el 100%.
* Demasiadas categorías dificultan la lectura y la interpretación.
* Los gráficos de anillos son útiles para comparar una sección determinada con el total, en lugar de comparar secciones individuales entre sí. 

## <a name="next-steps"></a>Pasos siguientes
[Informes en Power BI](service-reports.md)

[Tipos de visualización en Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Visualizaciones en informes de Power BI](power-bi-report-visualizations.md)

[Power BI: Conceptos básicos](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

