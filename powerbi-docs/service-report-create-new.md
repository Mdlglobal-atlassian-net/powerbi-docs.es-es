---
title: 'Creación de un nuevo informe a partir de un conjunto de datos '
description: Creación de un informe de Power BI nuevo a partir de un conjunto de datos
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/24/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 377ea4acc1a6fb41101571ac3ed0be2f3e50889b
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "34246166"
---
# <a name="create-a-new-report-in-power-bi-service-by-importing-a-dataset"></a>Creación de un informe en el servicio Power BI mediante la importación de un conjunto de datos
Ha leído [Informes en Power BI](service-reports.md) y ahora desea crear los suyos propios. Hay muchas formas distintas de crear un informe y en este artículo comenzaremos por crear un informe muy básico de un conjunto de datos de Excel mediante el servicio Power BI. Una vez que conozca los fundamentos de la creación de informes, la sección **Pasos siguientes** de la parte inferior le dirigirá a temas de informes más avanzados.  

> **Sugerencia**: para crear un informe mediante la copia de un informe existente, consulte [Copia de un informe](power-bi-report-copy.md)
> 
### <a name="prerequisites"></a>Requisitos previos
- Servicio Power BI (para la creación de informes con Power BI Desktop, consulte [Vista de informes en Power BI Desktop](desktop-report-view.md))  
- Conjunto de datos de ejemplo Retail Analysis

## <a name="import-the-dataset"></a>Importación del conjunto de datos
Este método de creación de informes comienza con un conjunto de datos y un lienzo de informe en blanco. Para seguir el tutorial, [descargue el conjunto de datos de Excel Retail Analysis Sample](http://go.microsoft.com/fwlink/?LinkId=529778) y guárdelo en OneDrive para la Empresa (opción preferida) o localmente.

1. El informe lo crearemos en un área de trabajo de un servicio Power BI, así que seleccione un área de trabajo existente o cree una nueva.
   
   ![Lista de áreas de trabajo de la aplicación](media/service-report-create-new/power-bi-workspaces2.png)
2. En la parte inferior del panel de navegación izquierdo, seleccione **Obtener datos**.
   
   ![Obtener datos](media/service-report-create-new/power-bi-get-data3.png)
3. Seleccione **Archivos** y navegue hasta la ubicación en que guardó el archivo 
Retail Analysis Sample.
   
    ![Selección de Archivos](media/service-report-create-new/power-bi-select-files.png)
4. Para este ejercicio, seleccione **Importar**.
   
   ![Selección de Importar](media/service-report-create-new/power-bi-import.png)
5. Una vez importado el conjunto de datos, seleccione **Ver conjunto de datos**.
   
   ![Selección de Ver conjunto de datos](media/service-report-create-new/power-bi-view-dataset.png)
6. Al visualizar un conjunto de datos, en realidad se abre el editor de informes.  Verá un lienzo en blanco y las herramientas de edición del informe.
   
   ![Editor de informes](media/service-report-create-new/power-bi-blank-report.png)

> **Sugerencia**: si nunca ha usado el lienzo de edición de informes o necesita que le recuerden cómo funciona, [realice un recorrido por el editor de informes ](service-the-report-editor-take-a-tour.md) antes de continuar.
> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Adición de un medidor radial al informe
Una vez que ha importado el conjunto de datos, ha llegado el momento de responder algunas preguntas.  Nuestro director de marketing (CMO) desea saber lo cerca que estamos de cumplir los objetivos de ventas de este año. Un medidor es una [buena opción de visualización](power-bi-report-visualizations.md) para mostrar este tipo de información.

1. En el panel Campos, seleccione **Ventas** > **Ventas de este año** > **Valor**.
   
    ![Gráfico de barras en el editor de informes](media/service-report-create-new/power-bi-report-step1.png)
2. Convierta el objeto visual en un medidor al seleccionar la plantilla Medidor ![icono de medidor](media/service-report-create-new/powerbi-gauge-icon.png) en el panel **Visualizaciones**.
   
    ![Objeto visual de medidor en el editor de informes](media/service-report-create-new/power-bi-report-step2.png)
3. Arrastre **Ventas** > **Ventas de este año** > **Objetivo** al área **Valor del objetivo**. Parece que estamos muy cerca de nuestro objetivo.
   
    ![Objeto visual de medidor con Objetivo como Valor del objetivo](media/service-report-create-new/power-bi-report-step3.png)
4. Este sería un buen momento para [guardar el informe](service-report-save.md).
   
   ![Menú Abrir](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Adición de un gráfico de áreas y segmentación de datos al informe
Nuestro director de marketing quiere que respondamos a varias preguntas más. Quiere ver la comparación de las ventas de este con las del anterior. Y también quiere ver los resultados por distrito.

1. En primer lugar, vamos a hacer algo de espacio en el lienzo. Seleccione el medidor y muévalo a la esquina superior derecha. Después, arrastre una de las esquinas para hacerlo menor.
2. Anule la selección del medidor. En el panel Campos, seleccione **Ventas** > **Ventas de este año** > **Valor** y seleccione **Ventas** > **Ventas del año anterior**.
   
    ![Editor de informes con medidor y gráfico de barras](media/service-report-create-new/power-bi-report-step4.png)
3. Para convertir el objeto visual en un gráfico de áreas, seleccione la plantilla Gráfico de áreas ![icono de gráfico](media/service-report-create-new/power-bi-areachart-icon.png) en el panel **Visualizaciones**.
4. Seleccione **Tiempo** > **Período** para agregarlo al área **Ejes**.
   
    ![Editor de informes con gráfico de áreas activo](media/service-report-create-new/power-bi-report-step5.png)
5. Para ordenar la visualización por período de tiempo, seleccione los puntos suspensivos y elija **Sort by Period**.
6. Ahora vamos a agregar la segmentación de datos. Seleccione un área vacía en el lienzo y elija la plantilla ![icono de segmentación](media/service-report-create-new/power-bi-slicer-icon.png)    Segmentación. Así se agrega una segmentación de datos vacía al lienzo.
   
    ![el lienzo del informe](media/service-report-create-new/power-bi-report-step6.png)    
7. En el panel Campos, seleccione **Distrito**  >  **Distrito**. Mueva la segmentación de datos y cámbiela de tamaño.
   
    ![Editor de informes, adición de Distrito](media/service-report-create-new/power-bi-report-step7.png)  
8. Use la segmentación de datos para buscar patrones e información por distrito.
   
   ![Vídeo de uso de la segmentación](media/service-report-create-new/power-bi-slicer-video2.gif)  

Continúe explorando los datos y agregando visualizaciones. Cuando encuentre una información especialmente interesante, [ánclela a un panel](service-dashboard-pin-tile-from-report.md).

## <a name="next-steps"></a>Pasos siguientes
* [Incorpore una página al informe](power-bi-report-add-page.md)  
* Aprenda a [anclar visualizaciones a un panel](service-dashboard-pin-tile-from-report.md)   
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

