---
title: Incorporación de parámetros de informe de Power BI con la URL
description: Filtre un informe con parámetros de cadena de consulta de URL, con la posibilidad incluso de filtrar más de un campo.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: aeaea6d14cf8f4fd62fbbf5098e68429fe40b96a
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34471948"
---
# <a name="filter-a-report-using-query-string-parameters-in-the-url"></a>Filtro de un informe con parámetros de cadena de consulta en la URL
Al abrir un informe en el servicio Power BI, cada página del informe tiene su propia URL única. Para filtrar esa página del informe, podría utilizar el panel Filtros del lienzo de informes.  También podría agregar parámetros de cadena de consulta a la URL para filtrar el informe. Es posible que tenga un informe que quiera prefiltrarlo para mostrarlo a sus compañeros. Una manera de hacerlo es comenzar con la URL predeterminada del informe, agregar los parámetros de filtro a la URL y, luego, enviarles por correo electrónico la URL completa.

![Informe de Power BI en el servicio](media/service-url-filters/power-bi-report2.png)

<iframe width="640" height="360" src="https://www.youtube.com/embed/WQFtN8nvM4A?list=PLv2BtOtLblH3YE_Ycas5B1GtcoFfJXavO&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="query-string-parameter-syntax-for-filtering"></a>Sintaxis de parámetro de cadena de consulta para filtrar
La sintaxis es bastante sencilla: empiece con la URL del informe, agregue un signo de interrogación y, luego, incorpore la sintaxis de filtro.

URL?filter=***Tabla***/***Campo*** eq '***valor***'

![Dirección URL con filtro](media/service-url-filters/power-bi-filter-urls7b.png)

* Los nombres de **Tabla** y **Campo** distinguen mayúsculas de minúsculas, pero **valor** no.
* Todavía se pueden seguir filtrando los campos que están ocultos en la vista de informes.
* El **valor** tiene que estar rodeado de comillas simples.
* El tipo de campo debe ser un número o una cadena
* Los nombres de tabla y campo no pueden tener espacios en blanco.

Si le sigue sin quedar claro, siga leyendo.  

## <a name="filter-on-a-field"></a>Filtrado por un campo
Supongamos que la URL del informe es la siguiente.

![Dirección URL de inicio](media/service-url-filters/power-bi-filter-urls6.png)

Y que tenemos almacenes en Carolina del Norte, tal como vemos en nuestra visualización de mapas (arriba).

>[!NOTE]
>Este artículo se basa en el ejemplo de [análisis de minoristas](sample-datasets.md).
> 

Para filtrar el informe para que solo muestre los datos de tiendas de "NC" (Carolina del Norte), anexe la URL con lo siguiente:

?filter=Tienda/Territorio eq 'NC'

![Dirección URL con filtro](media/service-url-filters/power-bi-filter-urls7.png)

>[!NOTE]
>*NC* es un valor almacenado en el campo **Territorio** de la tabla **Almacén**.
> 
> 

El informe se filtra por North Carolina; todas las visualizaciones de la página del informe solo muestran datos de Carolina del Norte.

![](media/service-url-filters/power-bi-report4.png)

## <a name="filter-on-multiple-fields"></a>Filtrado por varios campos
También puede filtrar por varios campos agregando parámetros adicionales a la dirección URL. Volvamos a nuestro parámetro de filtro original.

```
?filter=Store/Territory eq 'NC'
```

Para filtrar por campos adicionales, agregue `and` y otro campo en el mismo formato que el mostrado anteriormente. Este es un ejemplo.

```
?filter=Store/Territory eq 'NC' and Store/Chain eq 'Fashions Direct'
```

<iframe width="640" height="360" src="https://www.youtube.com/embed/0sDGKxOaC8w?showinfo=0" frameborder="0" allowfullscreen></iframe>


### <a name="using-dax-to-filter-on-multiple-values"></a>Uso de DAX para filtrar por varios valores
Otra manera de filtrar por varios campos es crear una columna calculada que concatene dos campos a un único valor. Después, puede filtrar por ese valor.

Por ejemplo, tenemos dos campos: Territorio y Cadena. En Power BI Desktop, [cree una nueva columna calculada](desktop-tutorial-create-calculated-columns.md) (Campo) denominada "TerritoryChain". Recuerde que el nombre del **campo** no puede contener espacios. Esta es la fórmula DAX para esa columna.

TerritoryChain = [Territorio] & " - " & [Cadena]

Publique el informe en el servicio Power BI y, luego, use la cadena de consulta de URL para filtrar y mostrar los datos de solo las tiendas Lindseys de Carolina del Norte.

    https://app.powerbi.com/groups/me/reports/8d6e300b-696f-498e-b611-41ae03366851/ReportSection3?filter=Store/TerritoryChain eq 'NC–Lindseys'

## <a name="pin-a-tile-from-a-filtered-report"></a>Anclaje de un icono desde un informe filtrado
Una vez que se ha filtrado el informe con parámetros de cadena de consulta, puede anclar visualizaciones de ese informe al panel. El icono del panel mostrará los datos filtrados. Al seleccionar ese icono del panel se abrirá el informe que se usó para crearlo.  Sin embargo, el filtrado que se realizó utilizando la URL no se guarda con el informe y, si se selecciona el icono del panel, el informe se abre con su estado sin filtrar.  Es decir, los datos mostrados en el icono del panel no coincidirán con los que aparecen en la visualización de informes.

Puede haber algunos casos donde esto resultarán útil cuando quiera ver resultados diferentes: filtrados en el panel y sin filtrar en el informe.

## <a name="considerations-and-troubleshooting"></a>Consideraciones y solución de problemas
Hay un par de cosas que tener en cuenta al utilizar los parámetros de cadena de consulta.

* En Power BI Report Server, puede [pasar parámetros de informes](https://docs.microsoft.com/sql/reporting-services/pass-a-report-parameter-within-a-url?view=sql-server-2017.md) incluyéndolos en una URL de informe. Estos parámetros de URL no tienen prefijo porque se pasan directamente al motor de procesamiento de informes. 
* El filtrado de cadena de consulta no funciona con [Publicar en la web](service-publish-to-web.md) ni con Power BI Embedded.   
* El tipo de campo debe ser un número o una cadena.
* Los nombres de tabla y campo no pueden tener espacios en blanco.

## <a name="next-steps"></a>Pasos siguientes
[Anclar una visualización a un informe](service-dashboard-pin-tile-from-report.md)  
[Pruébelo, es gratis](https://powerbi.com/)

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

