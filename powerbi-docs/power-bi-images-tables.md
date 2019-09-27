---
title: Visualización de imágenes en una tabla o una matriz de un informe
description: En Power BI Desktop, cree una columna con hipervínculos a imágenes. A continuación, en Power BI Desktop o en el servicio Power BI, agregue esos hipervínculos a una tabla de informe, una matriz, una segmentación o una tarjeta de varias filas para mostrar la imagen.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/11/2019
ms.author: maggies
LocalizationGroup: Visualizations
ms.openlocfilehash: 2ebbc277f2a269ebaf2d1bdb99f1aa800576b466
ms.sourcegitcommit: ba085b248c54e8fb1fd8eb2bb23a814e3fdd7ff6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2019
ms.locfileid: "70936502"
---
# <a name="display-images-in-a-table-matrix-or-slicer-in-a-report"></a>Visualización de imágenes en una tabla, una matriz o una segmentación de un informe

Una buena manera de mejorar los informes es agregarles imágenes. Las imágenes estáticas de la página son adecuadas para algunos fines. Pero, en ocasiones, querrá que las imágenes se relacionen con los datos del informe. En este tema se enseña cómo mostrar imágenes en una tabla, una matriz, una segmentación o una tarjeta de varias filas. 

![Imágenes de dirección URL en una tabla](media/power-bi-images-tables/power-bi-url-images-table.png)

## <a name="add-images-to-your-report"></a>Adición de imágenes a un informe

1. Cree una columna con las direcciones URL de las imágenes. Consulte más adelante la sección de [Consideraciones](#considerations) en este artículo para conocer los requisitos.

1. Seleccione esa columna. En la cinta **Modelado**, en **Registro de datos**, seleccione **Dirección URL de la imagen**.

    ![Establecimiento de la categoría de los datos para la dirección URL de la imagen](media/power-bi-images-tables/power-bi-set-url-image.png)

1. Agregue la columna a una tabla, una matriz, una segmentación o una tarjeta de varias filas.

    ![Segmentación con imágenes](media/power-bi-images-tables/power-bi-url-images-slicer.png)

## <a name="considerations"></a>Consideraciones

- La imagen debe estar en uno de estos formatos de archivo: .bmp, .jpg, .jpeg, .gif, .png o .svg
- La dirección URL debe ser accesible de forma anónima, no en un sitio que requiera inicio de sesión, como SharePoint. Sin embargo, si las imágenes están hospedadas en SharePoint o OneDrive, es posible que pueda obtener un código para insertar que apunte directamente a ellas. 


## <a name="next-steps"></a>Pasos siguientes

[Adición de formas estáticas, cuadros de texto e imágenes a un informe](https://docs.microsoft.com/power-bi/guided-learning/visualizations?tutorial-step=11)

[Conceptos básicos para los diseñadores en el servicio Power BI](service-basic-concepts.md)

¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
