---
title: Muestreo de líneas de alta densidad en Power BI
description: Muestreo de líneas de alta densidad en Power BI
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/19/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 7fb3e6163d63cdf3f40d0400f246095550fc9032
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34286575"
---
# <a name="high-density-line-sampling-in-power-bi"></a>Muestreo de líneas de alta densidad en Power BI
Desde la versión de junio de 2017 de **Power BI Desktop** y las actualizaciones al **servicio Power BI**, hay disponible un nuevo algoritmo de muestreo que mejora los objetos visuales con muestreos de datos de alta densidad. Por ejemplo, puede crear un gráfico de líneas a partir de los resultados de ventas de sus tiendas, con cada tienda con más de diez mil recibos de ventas cada año. Un gráfico de líneas de dicha información de ventas realizará un muestreo de los datos (seleccionando una representación significativa de los datos para ilustrar cómo varían las ventas a través del tiempo) a partir de los datos de cada tienda, y creará un gráfico de líneas de varias series que, por lo tanto, representa datos subyacentes. Esta es una práctica habitual al visualizar datos de alta densidad. Power BI Desktop ha mejorado el muestreo de datos de alta densidad, cuyos detalles se describen en este artículo.

![](media/desktop-high-density-sampling/high-density-sampling_01.png)

> [!NOTE]
> El algoritmo de **muestreo de alta densidad** que se describe en este artículo está disponible tanto en **Power BI Desktop** como en el **servicio Power BI**.
> 
> 

## <a name="how-high-density-line-sampling-works"></a>Cómo funciona el muestreo de líneas de alta densidad
Anteriormente, **Power BI** seleccionaba una colección de puntos de datos de muestra en el intervalo completo de datos subyacentes de manera determinista. Por ejemplo, para los datos de alta densidad en un objeto visual que abarquen un año de calendario, puede haber 350 puntos de datos de muestra que aparezcan en el objeto visual, cada uno de los cuales se seleccionó para asegurarse de que el rango de datos completo (la serie completa de datos subyacentes) aparece representado en el objeto visual. Para ayudarle a entender cómo sucede esto, imagine que se va a trazar la cotización en bolsa durante un período de un año y se seleccionan 365 puntos de datos para crear un objeto visual de gráfico de líneas que, por tanto, tendrá un punto de datos para cada día.

En ese caso, dentro de cada día hay muchos valores para la cotización en bolsa. Por supuesto, hay un mínimo y un máximo diarios, pero estos pueden producirse en cualquier momento durante el día mientras la bolsa de valores esté abierta. Para el muestreo de líneas de alta densidad, si se toma la muestra de los datos subyacentes a las 10:30 a.m. y las 12:00 p.m. cada día, se obtendría una instantánea representativa de los datos subyacentes (el precio de las acciones a las 10:30 a.m. y a las 12:00 p.m.), pero esto podría no capturar el máximo y el mínimo de la cotización para ese punto de datos representativo (ese día). En esta y otras situaciones, el muestreo es representativo de los datos subyacentes, pero no siempre captura puntos importantes, que en este caso serían las cotizaciones máxima y mínima diarias.

Por definición, se muestrean los datos de alta densidad para crear visualizaciones de forma razonablemente rápida que responden a interactividad. Si hay demasiados puntos de datos en un objeto visual pueden provocar que se ralentice y disminuya la visibilidad de las tendencias. Por eso, la forma en la que se muestrean los datos es lo que impulsa la creación del algoritmo de muestreo, para proporcionar la mejor experiencia de visualización. En Power BI Desktop, se ha mejorado el algoritmo para proporcionar la mejor combinación de capacidad de respuesta, representación y conservación de los puntos importantes en cada segmento de tiempo.

## <a name="how-the-new-line-sampling-algorithm-works"></a>Cómo funciona el nuevo algoritmo de muestreo de líneas
El nuevo algoritmo para el muestreo de líneas de alta densidad está disponible para los elementos visuales de gráfico de líneas y gráfico de áreas con un eje x continuo.

Para un elemento visual de alta densidad, **Power BI** segmenta de forma inteligente los datos en fragmentos de alta resolución y, después, elige los puntos importantes para representar cada fragmento. Este proceso de segmentación de datos de alta resolución se optimiza de forma específica para asegurarse de que el gráfico resultante es visualmente indistinguible de la representación de todos los puntos de datos subyacentes, pero es mucho más rápido y más interactivo.

### <a name="minimum-and-maximum-values-for-high-density-line-visuals"></a>Valores mínimos y máximos para los objetos visuales de líneas alta densidad
Para cualquier visualización, se aplican las siguientes limitaciones visuales:

* **3500** es el número máximo de puntos de datos que se *muestran* en el objeto visual, independientemente del número de puntos de datos subyacente o de series. Por lo tanto, si tiene 10 series con 350 puntos de datos cada una, el objeto visual ha alcanzado su límite máximo de puntos de datos totales. Si tiene una serie, puede tener hasta 3.500 puntos de datos si el nuevo algoritmo considera que ese es el mejor muestreo para los datos subyacentes.
* Hay un máximo de **60 serie** para cualquier objeto visual. Si tiene más de 60 series, divida los datos y cree varios objetos visuales con 60 o menos series cada uno. Es recomendable usar una **segmentación** para mostrar solo los segmentos de los datos (solo determinadas serie). Por ejemplo, si se muestran todas las subcategorías en la leyenda, podría usar una segmentación de datos para filtrar por la categoría general en la misma página del informe.

Estos parámetros aseguran que los objetos visuales en Power BI Desktop se representan muy rápidamente y responden a la interacción con los usuarios, y que no dan lugar a una sobrecarga de procesamiento en el equipo que genera la representación del objeto visual.

### <a name="evaluating-representative-data-points-for-high-density-line-visuals"></a>Evaluación de puntos de datos representativos para objetos visuales de líneas de alta densidad
Cuando el número de puntos de datos subyacente supera el máximo de puntos de datos que se pueden representar en el objeto visual (más de 3500), se inicia un proceso llamado *discretización* que fragmenta los datos subyacentes en grupos llamados *ubicaciones* y, después, refina de forma iterativa esas ubicaciones.

El algoritmo crea tantas ubicaciones como sea posible para crear la mayor granularidad para el objeto visual. Dentro de cada ubicación, el algoritmo busca el valor de datos mínimo y máximo, para asegurarse de que los valores importantes y significativos (por ejemplo, los valores atípicos) se capturan y muestran en el objeto visual. Basándose en los resultados de la discretización y la evaluación posterior de los datos que realiza Power BI, se determina la resolución mínima para el eje x del objeto visual, con el fin de asegurar la máxima granularidad para el objeto visual.

Como se mencionó anteriormente, la granularidad mínima para cada serie es 350 puntos y la máxima 3.500.

Cada ubicación se representa mediante dos puntos de datos, que se convierten en los puntos de datos representativos de la ubicación en el objeto visual. Los puntos de datos son simplemente los valores alto y bajo para esa ubicación; la selección de los valores alto y bajo en el proceso de discretización garantiza que cualquier valor alto importante, o valor bajo significativo, se captura y aparece representado en el objeto visual.

Si todo esto suena a que se analiza mucho para asegurarse de que se captura el valor atípico ocasional y se muestra correctamente en el objeto visual, es porque se trata precisamente de eso: es la razón que se encuentra tras el nuevo algoritmo y el proceso de discretización.

## <a name="tooltips-and-high-density-line-sampling"></a>Información sobre herramientas y muestreo de líneas de alta densidad
Es importante tener en cuenta que este proceso de discretización, que da como resultado la captura y representación de los valores mínimo y máximo en una ubicación determinada, puede afectar a la forma en la que la información sobre herramientas muestra los datos cuando se mantiene el mouse sobre los puntos de datos. Para explicar cómo y por qué ocurre esto, vamos a recurrir otra vez al ejemplo sobre cotizaciones en bolsa.

Supongamos que va a crear un objeto visual basado en las cotizaciones en bolsa y que compara dos paquetes de acciones diferentes: ambos usan el **muestreo de alta densidad**. Los datos subyacentes para cada serie tienen un gran número de puntos de datos (por ejemplo, puede capturar el precio de las acciones cada segundo del día). El algoritmo de muestreo de líneas de alta densidad realiza la discretización de forma independiente para cada serie.

Ahora supongamos que el primer paquete de acciones sube de precio a las 12:02, y diez segundos más tarde, vuelve a bajar rápidamente. Este es un punto de datos importante. Cuando se produce la discretización de esas acciones, la subida de las 12:02 será un punto de datos representativo para esa ubicación.

Pero, para el segundo paquete de acciones, a las 12:02 no hubo ninguna subida o bajada en la ubicación que incluya esa hora. Quizás el alto y bajo de la ubicación que incluye 12:02 se produjo tres minutos más tarde. En este caso, cuando se crea el gráfico de líneas y se coloca el mouse sobre 12:02, se verá un valor en la información sobre herramientas para las acciones del primer paquete (porque subió a las 12:02 y ese valor se ha seleccionado como punto de datos alto de esa ubicación), pero *no* se verá ningún valor en la información sobre herramientas a las 12:02 para el segundo paquete. Esto es porque el segundo paquete de acciones no tuvo ningún valor alto ni bajo, en la ubicación que incluye 12:02. Por lo tanto, no hay ningún dato para mostrar para el segundo paquete de acciones a las 12:02. Por eso, no se muestra ningún dato en la información sobre herramientas.

Esta situación aparece con frecuencia en la información sobre herramientas. Los valores altos y bajos de una ubicación determinada pueden no coincidir exactamente con los puntos de valor que siguen la escala uniforme en el eje x, por lo tanto, en ese caso, la información sobre herramientas no mostrará ningún valor.  

## <a name="how-to-turn-on-high-density-line-sampling"></a>Cómo activar el muestreo de líneas de alta densidad
De forma predeterminada, el nuevo algoritmo está **activado**. Para cambiar este ajuste, vaya al panel **Formato**, en la tarjeta **General** y, en la parte inferior, verá un control deslizante llamado **Muestreo de alta densidad**. Para desactivar esta función, cámbiela a **Desactivar**.

![](media/desktop-high-density-sampling/high-density-sampling_02.png)

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
El nuevo algoritmo para el muestreo de líneas de alta densidad es una mejora importante en Power BI, pero hay algunas consideraciones que debe conocer a la hora de trabajar con datos y valores de alta densidad.

* Debido a una mayor granularidad y al proceso de discretización, es posible que las **informaciones sobre herramientas** solo muestren un valor si hay datos representativos que estén alineados con el cursor. Vea la sección *Información sobre herramientas y muestreo de líneas de alta densidad* de este artículo para saber más.
* Cuando el tamaño de un origen de datos global es demasiado grande, el nuevo algoritmo elimina series (elementos de leyenda) para dar cabida a la restricción máxima de importación de datos.
  
  * En esta situación, el nuevo algoritmo ordena alfabéticamente las series de leyenda y empieza por el final de la lista de elementos de leyenda en orden alfabético, hasta que alcanza el máximo y no importa más series adicionales.
* Cuando un conjunto de datos subyacentes tiene más de 60 series (es decir, el número máximo de series, como se describió anteriormente), el nuevo algoritmo ordena alfabéticamente las series y elimina aquellas que están más allá de la serie que tiene el número 60 en el orden alfabético.
* Si los valores de los datos no son del tipo *numérico* o *fecha/hora*, Power BI no usa el nuevo algoritmo y vuelve al algoritmo anterior (muestreo de densidad no alta).
* El ajuste **Mostrar elementos sin datos** no es compatible con el nuevo algoritmo.
* El nuevo algoritmo no se admite cuando se usa una conexión dinámica a un modelo que se hospeda en SQL Server Analysis Services (versión 2016 o una versión anterior). Se admite en modelos hospedados en **Power BI** o Azure Analysis Services.

## <a name="next-steps"></a>Pasos siguientes
Si quiere saber más sobre el muestreo de alta densidad en gráficos de dispersión, vea el artículo siguiente.

* [Muestreo de alta densidad en los gráficos de dispersión de Power BI](desktop-high-density-scatter-charts.md)

