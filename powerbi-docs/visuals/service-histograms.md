---
title: Histogramas
description: Histogramas
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: d5e4148af774dc542ef5730c0d8a5fa0245698f7
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2019
ms.locfileid: "54274959"
---
# <a name="histograms"></a>Histogramas
Hay varias maneras de crear histogramas en Power BI. Comenzaremos por lo más sencillo y continuaremos a partir de ahí.

## <a name="simple-histograms"></a>Histogramas sencillos
Para empezar, determine qué consulta tiene el campo a partir del cual desea crear un histograma.  Use la opción *Referencia* para que la consulta cree una nueva consulta y asígnele el nombre *FieldName Histogram*. Use la opción **Agrupar por** de la cinta de opciones **Transformar** y seleccione el agregado **recuento de filas** . Asegúrese de que el tipo de datos es un número para la columna agregada resultante. A continuación, visualice estos datos en la página de informes. La creación de este histograma resultará rápida y sencilla, pero no funcionará bien si tiene muchos puntos de datos; además, no permite resaltar diferentes objetos visuales.

## <a name="defining-buckets-to-build-a-histogram"></a>Definición de cubos para crear un histograma
Determine qué consulta tiene el campo a partir del cual desea crear un histograma. Use la opción *Referencia* crear una nueva consulta y asígnele el nombre *FieldName*.  Defina los cubos con una regla. Use la opción **Agregar columnas personalizadas** de la cinta de opciones **Agregar columna** y cree una regla personalizada.

![](media/service-histograms/powerbi-service-histograms_1.png)

Asegúrese de que el tipo de datos es un número para la columna agregada resultante. Ahora puede usar la agrupación por técnica descrita en la sección **Histogramas más sencillos** (más arriba en este artículo) para lograr el histograma. Esta opción controla más puntos de datos, pero todavía no ayuda con los gráficos.

## <a name="defining-a-histogram-that-supports-brushing"></a>Definición de histogramas que permitan el resaltado
El resaltado se produce cuando los objetos visuales están vinculados entre sí de manera que cuando un usuario selecciona un punto de datos de un objeto visual, otros objetos visuales de la página del informe se resaltan, o se filtran puntos de datos relacionados con el punto de datos seleccionado.  Puesto que vamos a manipular los datos en tiempo de consulta, necesitamos crear una relación entre las tablas y asegurarse de que sabemos qué elemento de detalle está relacionado con el cubo del histograma y viceversa.

Inicie el proceso con la opción *Referencia* de la consulta que tiene el campo a partir del cual desea generar un histograma.  Asigne a la nueva consulta el nombre *Cubos*.  En este ejemplo, llamaremos a la consulta original *Detalles*.  A continuación, quite todas las columnas excepto la columna que se va a usar como cubo del histograma.  Ahora use la característica *Quitar duplicados* en la consulta que se encuentra en el menú contextual que aparece al seleccionar la columna. De este modo, los demás valores serán los únicos valores de la columna. Si tiene números decimales, puede usar la primera sugerencia para definir cubos para crear un histograma que permita obtener un conjunto de cubos fáciles de administrar.  Ahora, compruebe los datos que se muestran en la vista previa de la consulta. Si ve valores en blanco o nulos deberá corregirlos antes de crear una relación. Consulte "Creación de una relación si mis datos tienen valores nulos o en blanco". El uso de este enfoque puede ser problemático debido a la necesidad de ordenar. Para obtener los cubos ordenados correctamente, vea "Ordenación: conseguir que las categorías aparezcan en el orden deseado". 

> [!NOTE]
> Conviene pensar en el criterio de ordenación antes de crear los objetos visuales.   
> 
> 

El siguiente paso del proceso es definir una relación entre las consultas de *Cubos* y *Detalles* en la columna de cubos.  En *Power BI Desktop*, seleccione *Administrar relaciones* en la cinta de opciones.  Cree una relación según la cual los *Cubos* están en la tabla izquierda y los *Detalles* en la tabla derecha. A continuación, seleccione el campo que va a usar para el histograma. 

El último paso es crear el histograma. Arrastre el campo Cubo desde la tabla *Cubos* . Quite el campo predeterminado del gráfico de columnas resultante.  Ahora, en la tabla *Detalles* , arrastre el campo de histograma al mismo objeto visual. En el conjunto de campos, cambie el agregado predeterminado a Recuento. Obtendrá como resultado un histograma. Si crea otro objeto visual como, por ejemplo, un gráfico de rectángulos de la tabla Detalles, seleccione un punto de datos en el gráfico de rectángulos para ver el histograma resaltado y mostrar el histograma del punto de datos seleccionado en relación con la tendencia de todo el conjunto de datos.

