---
title: 'Ejemplo de análisis de gasto en TI para Power BI: un paseo'
description: 'Ejemplo de análisis de gasto en TI para Power BI: un paseo'
author: maggiesMSFT
manager: kfile
ms.reviewer: amac
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/23/2018
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 66a1999637f31083681a6984d4698d78815dc1c1
ms.sourcegitcommit: 1e4fee6d1f4b7803ea285eb879c8d5a4f7ea8b85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2018
ms.locfileid: "51717479"
---
# <a name="it-spend-analysis-sample-for-power-bi-take-a-tour"></a>Ejemplo de análisis de gasto en TI para Power BI: un paseo

## <a name="overview-of-the-it-spend-analysis-sample"></a>Introducción al Ejemplo de análisis de gastos de TI
El [paquete de contenido](service-organizational-content-pack-introduction.md) del análisis de gastos de TI (panel, informe y conjunto de datos) analiza los costos planeados frente a los costos reales de un departamento de TI. Esta comparación nos ayuda a comprender la calidad del planeamiento anual y de la investigación de las áreas con enormes desviaciones del planeamiento que ha realizado la empresa. La empresa de este ejemplo pasa por un ciclo de planeamiento anual y produce trimestralmente un nuevo último cálculo que ayude a analizar los cambios del gasto en TI durante el año fiscal.

![](media/sample-it-spend/it1.png)

Este ejemplo forma parte de una serie en la que se muestra cómo puede usar Power BI con datos, informes y paneles empresariales. Estos son datos reales de obviEnce (<http://obvience.com/>) que son anónimos.

## <a name="prerequisites"></a>Requisitos previos

 Para poder usar el ejemplo, primero debe descargarlo como un [paquete de contenido](https://docs.microsoft.com/power-bi/sample-it-spend#get-the-content-pack-for-this-sample), un [archivo .pbix](http://download.microsoft.com/download/E/9/8/E98CEB6D-CEBB-41CF-BA2B-1A1D61B27D87/IT%20Spend%20Analysis%20Sample%20PBIX.pbix) o un [libro de Excel](http://go.microsoft.com/fwlink/?LinkId=529783).

### <a name="get-the-content-pack-for-this-sample"></a>Obtención del paquete de contenido de este ejemplo

1. Abra el servicio Power BI (app.powerbi.com) e inicie sesión.
2. En la esquina inferior izquierda, seleccione **Obtener datos**.
   
    ![](media/sample-datasets/power-bi-get-data.png)
3. En la página que aparece, seleccione el icono **Ejemplos**.
   
   ![](media/sample-datasets/power-bi-samples-icon.png)
4. Seleccione el **Ejemplo de análisis de gastos de TI** y elija **Conectar**.  
  
   ![Obtener datos](media/sample-it-spend/it-connect.png)
   
5. Power BI importa el paquete de contenido y agrega un nuevo panel, informe y conjunto de datos en el área de trabajo actual. El contenido nuevo viene indicado con un asterisco amarillo. 
   
   ![Asterisco](media/sample-it-spend/it-asterisk.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Obtención del archivo .pbix de este ejemplo

Como alternativa, puede descargar el ejemplo como un archivo .pbix, que está diseñado para su uso con Power BI Desktop. 

 * [Ejemplo de análisis de gastos de TI](http://download.microsoft.com/download/E/9/8/E98CEB6D-CEBB-41CF-BA2B-1A1D61B27D87/IT%20Spend%20Analysis%20Sample%20PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>Obtención del libro de Excel de este ejemplo
También puede [descargar únicamente el conjunto de datos (libro de Excel)](http://go.microsoft.com/fwlink/?LinkId=529783) para este ejemplo. El libro contiene hojas de Power View que puede ver y modificar. Para ver los datos sin procesar seleccione **Power Pivot > Administrar**.


## <a name="the-it-spend-analysis-sample-dashboard"></a>El panel de ejemplo de análisis de gasto en TI
Los dos iconos de números del panel, el **% de desviación del planeamiento** y el **% de desviación del último cálculo del tercer trimestre**nos aportan una visión general de la calidad de nuestro trabajo con respecto al planeamiento y el cálculo del último trimestre (LE3 = último cálculo del tercer trimestre). En términos generales, tenemos una desviación del 6 % del planeamiento. Exploremos la causa de esta desviación: cuándo, dónde y qué categoría.

## <a name="ytd-it-spend-trend-analysis-page"></a>Página de "Análisis de tendencia de gasto en TI hasta la fecha" 
Al seleccionar el icono del panel **% de desviación del planeamiento por región de venta**, irá a la página "Análisis de tendencias de gasto en TI" del informe de ejemplo de análisis de gastos de TI. Vemos de un vistazo que tenemos una desviación positiva en Estados Unidos y Europa y una desviación negativa en Canadá, Latinoamérica y Australia. EE. UU. tenía alrededor de un 6 % de desviación positiva en el último cálculo, mientras que Australia tiene alrededor de un 7 % de desviación negativa en el último cálculo.

![](media/sample-it-spend/it2.png)

Pero si solo miramos este gráfico y sacamos conclusiones podemos equivocarnos. Tenemos que analizar los importes reales para poner las cosas en perspectiva.

1. Seleccione **Australia y Nueva Zelanda** en el gráfico de % de desviación del planeamiento según la región de ventas y observe el gráfico de áreas de la desviación del planeamiento por TI.

   ![](media/sample-it-spend/it3.png)
2. Ahora seleccione **EE. UU.** Para hacerse una idea, Australia supone una parte muy reducida de nuestro gasto general en comparación con EE. UU.

    Por este motivo, lo restringimos a EE. UU. ¿Y ahora qué? Veamos qué categoría en EE. UU. está causando la desviación.

## <a name="ask-questions-of-the-data"></a>Pregunte sobre los datos
1. Seleccione **Ejemplo de análisis de gasto de TI** en la barra de navegación superior para volver a los paneles.
2. Escriba en el cuadro de pregunta "mostrar gráfico de barras de las áreas de TI, % de desviación del planeamiento y % de desviación del último cálculo del tercer trimestre".

   ![](media/sample-it-spend/it4.png)

   En la primera área de TI, **Infraestructura**, el porcentaje cambió radicalmente entre la desviación del planeamiento inicial y el último cálculo de la desviación del planeamiento.

## <a name="ytd-spend-by-cost-elements-page"></a>Página "gasto hasta la fecha por elementos de costo"
Vuelva al panel y observe el icono del panel **% de desviación del planeamiento, % de desviación del último cálculo del tercer trimestre** .

![](media/sample-it-spend/it5.png)

La infraestructura destaca con una gran desviación positiva del planeamiento.

1. Haga clic en este icono para ir a la página "gastos hasta la fecha por elementos de costo" del informe de ejemplo de análisis de gasto en TI.
2. Haga clic en la barra **Infraestructura** del gráfico "% de desviación del planeamiento y % de desviación del último cálculo del tercer trimestre por área de TI" en la parte inferior izquierda y observe la desviación del planeamiento en "% de desviación del planeamiento por región de ventas" a la izquierda.

    ![](media/sample-it-spend/it6.png)
3. Haga clic en el nombre de cada Grupo de elementos de costo en la segmentación para encontrar el elemento de costo con una gran desviación.
4. Tras seleccionar **Otros** , haga clic en **Infraestructura** en el Área de TI y haga clic en las subáreas en la segmentación de Subárea de TI para encontrar la subárea con la mayor desviación.  

   Vemos una gran desviación en **Redes**.

   Aparentemente, la empresa decidió proporcionar a sus empleados servicios telefónicos como beneficio, pero este movimiento no estaba planeado.

## <a name="plan-variance-analysis-page"></a>Página "Análisis de desviación del planeamiento"
En el informe, haga clic en la pestaña "Análisis de la desviación del planeamiento" en la parte inferior del informe para ir a la página 3 del informe.

En el gráfico combinado "desviación del planeamiento y % de desviación del planeamiento por área de negocio" de la izquierda, haga clic en la columna Infraestructura para resaltar los valores de la infraestructura en el resto de la página.

![](media/sample-it-spend/it7.png)

Observe que en el gráfico de "% de desviación del planeamiento por mes y área de negocio" la infraestructura empezó a experimentar una desviación positiva en febrero que luego continuó aumentando. Además, observe cómo la varianza para planear el valor de la infraestructura varía según el país, en comparación con el valor de todas las áreas de negocios. Use las segmentaciones "Área de TI" y "Subáreas de TI" a la derecha para filtrar los valores del resto de la página en lugar de resaltarlos. Haga clic en las diferentes Áreas de TI de la derecha para explorar los datos de otra forma. También puede hacer clic en Subáreas de TI y ver la desviación en ese nivel.

## <a name="edit-the-report"></a>Editar el informe
Haga clic en **Editar informe** en la esquina superior izquierda y explore la Vista de edición.

* Vea cómo se realizan las páginas: los campos de cada gráfico y los filtros de las páginas.
* Agregue páginas y gráficos basados en los mismos datos.
* Cambie el tipo de visualización de cada gráfico.
* Ánclelos al panel.

Se trata de un entorno seguro en el que experimentar. Siempre puede elegir no guardar los cambios. Pero si los guarda, siempre puede ir a Obtener datos para obtener una copia nueva de este ejemplo.

## <a name="next-steps-connect-to-your-data"></a>Pasos siguientes: conectarse a sus propios datos
Esperamos que este paseo le haya mostrado cómo los paneles de Power BI, Preguntas y respuestas y los informes pueden ofrecer recomendaciones sobre los datos de gasto en TI. Ahora es su turno: conéctese a sus propios datos Con Power BI puede conectarse a una gran variedad de orígenes de datos. Más información sobre [cómo empezar a usar Power BI](service-get-started.md).
