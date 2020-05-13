---
title: Capacidad y SKU de los análisis incrustados de Power BI
description: Comprenda que son las capacidades y SKU de los análisis incrustados de Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/11/2020
ms.openlocfilehash: 66ef36f669b5f34c19f283cf9ebc8be2b12332ec
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83148646"
---
# <a name="capacity-and-skus-in-power-bi-embedded-analytics"></a>Capacidad y SKU de los análisis incrustados de Power BI

Al pasar a producción, los análisis incrustados de Power BI requieren una capacidad dedicada (SKU *A*, *EM* o *P*) para la publicación de contenido incrustado de Power BI.

Una capacidad es un conjunto dedicado de recursos reservados para uso exclusivo. Le permite publicar paneles, informes y conjuntos de datos para los usuarios sin tener que adquirir licencias por usuario. También ofrece un rendimiento confiable y continuo de su contenido.

>[!NOTE]
>Para la publicación, necesitará una cuenta de Power BI Pro.

## <a name="what-is-embedded-analytics"></a>¿Qué son los análisis incrustados?

Los análisis incrustados de Power BI incluyen dos soluciones:
* *Power BI Embedded*: oferta de Azure
* Incrustación de Power BI como parte de *Power BI Premium*: oferta de Office

### <a name="power-bi-embedded"></a>Power BI Embedded

Power BI Embedded está pensado para aquellos ISV y desarrolladores que quieran insertar objetos visuales en sus aplicaciones.

Las aplicaciones que usan Power BI Embedded permiten a los usuarios consumir contenido almacenado en la capacidad de Power BI Embedded.

### <a name="power-bi-premium"></a>Power BI Premium

[Power BI Premium](../../admin/service-premium-what-is.md) está dirigido a empresas que quieran una solución de inteligencia empresarial completa que proporcione una vista única de su organización, asociados, clientes y proveedores.

Power BI Premium es un producto SaaS que permite que los usuarios consuman el contenido a través del portal de Power BI, una aplicación móvil y aplicaciones desarrolladas internamente (servicio Power BI). Esto permite a Power BI Premium proporcionar una solución para aplicaciones internas y externas orientadas a los clientes.

## <a name="capacity-and-skus"></a>Capacidad y SKU

Cada capacidad ofrece una selección de SKU, y cada SKU proporciona diferentes niveles de recursos para la memoria y la capacidad de computación. El tipo de SKU que necesite dependerá del tipo de solución que quiera implementar.

Para saber qué cargas de trabajo se admiten para cada nivel, consulte el artículo [Configuración de cargas de trabajo en una capacidad Premium](../../admin/service-admin-premium-workloads.md).

Para planear y probar su capacidad, use estos vínculos:
* [Planificación de capacidad](embedded-capacity-planning.md)
* [Enfoques de prueba](../../admin/service-premium-capacity-optimize.md#testing-approaches)

### <a name="power-bi-embedded-skus"></a>SKU de Power BI Embedded

Power BI Embedded se suministra con una [SKU *a*](../../admin/service-admin-premium-purchase.md#purchase-a-skus-for-testing-and-other-scenarios).

### <a name="power-bi-premium-skus"></a>SKU de Power BI Premium

Power BI Premium ofrece dos SKU: *P* y *EM*.
* [Diferencias entre los SKU *P* y *EM*](../../admin/service-premium-what-is.md#subscriptions-and-licensing)
* [Compra de un SKU Premium](../../admin/service-admin-premium-purchase.md)

### <a name="which-sku-should-i-use"></a>¿Qué SKU debo usar?

En esta tabla se proporciona un resumen de las características, la capacidad requerida y el SKU específico que se necesita para cada una de ellas. 

</br>
<table>
<col width="20%">
<col width="20%">
<col width="20%">
<col width="20%">
<col width="20%">
<tbody>
<tr>
<td style="text-align: center"; colspan="2"><p><b>Característica</b></p></td>
<td style="text-align: center">
<p><b>¿Qué es Power BI Embedded de Azure?</b></p>
</td>
<td style="text-align: center"; colspan="2">
<p><b>Power BI Premium</b></p>
</td>
</tr>
<tr>
<td><p><em>¿Qué es lo que se consume?</em><p></td>
<td><p><em>¿Qué elemento realiza tal consumo?</em><p></td>
<td style="text-align: center"><p><em>SKU A</br>(Azure)</em></p></td>
<td style="text-align: center"><p><em>SKU EM</br>(Office)</em></p></td>
<td style="text-align: center"><p><em>SKU P</br>(Office)</em></p></td>
</tr>
<tr>
<td>Inserción de artefactos desde un área de trabajo de Power BI</td>
<td>
</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td rowspan="2">Informes de Power BI</td>
<td>Aplicación insertada para la organización</br>(datos en posesión del usuario)</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>Aplicación insertada para los clientes</br>(datos en posesión de la aplicación)</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td rowspan="3">Power BI content<br>(con una licencia gratuita de Power BI)</td>
<td>Servicio Power BI</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>Power BI Mobile</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>Aplicaciones de MS Office</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
</tbody>
</table>

### <a name="capacity-considerations"></a>Consideraciones de capacidad

En la tabla siguiente se enumeran las consideraciones sobre el pago y uso por capacidad.

</br>
<table>
<tbody>
<tr>
<td></td>
<td style="text-align: center;"><p><strong>¿Qué es Power BI Embedded de Azure?</strong></p></td>
<td style="text-align: center;" colspan="2"><p><strong>Power BI Premium</strong></p></td>
</tr>
<tr>
<td><p><strong>Oferta</strong></p></td>
<td style="text-align: center;"><p>Celeste</p></td>
<td style="text-align: center;" colspan="2"><p>Office</p></td>
</tr>
<tr>
<td><p><strong>SKU</strong></p></td>
<td style="text-align: center;"><p>A</p></td>
<td style="text-align: center;"><p>EM</p></td>
<td style="text-align: center;"><p>P</p></td>
</tr>
<tr>
<td><p><strong>Facturación</strong></td>
<td style="text-align: center;">Cada hora</td>
<td style="text-align: center;">Mensual</td>
<td style="text-align: center;">Mensual</td>
</tr>
<tr>
<td><p><strong>Asignación</strong></td>
<td style="text-align: center;">ninguno</td>
<td style="text-align: center;">Anualmente</td>
<td style="text-align: center;">Mensual o anual</td>
</tr>
<tr>
<td valign="top"><p><strong>Uso</strong></td>
<td style="text-align: center;">Los recursos de Azure se pueden:</br>- <a href="azure-pbie-scale-capacity.md">Escalar vertical y horizontalmente</a></br>- <a href="azure-pbie-pause-start.md">Pausar y reanudar</a>
</td>
<td style="text-align: center;">Incrustar en aplicaciones y en</br> aplicaciones de Microsoft</td>
<td style="text-align: center;">Incrustar en aplicaciones, así como en</br> la memoria y capacidad de computación</td>
</tr>
</tbody>
</table>

### <a name="sku-memory-and-computing-power"></a>del servicio Power BI

En la tabla siguiente se describen los recursos y los límites de cada SKU.

| Nodos de capacidad | Total de núcleos virtuales | Núcleos virtuales de back-end | RAM (GB) | Núcleos virtuales de front-end | Límites de conexiones dinámicas/DirectQuery (por segundo) | Paralelismo de actualización de modelo |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0.5 | 2.5 | 0.5 | 3,75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7,5 | 2 |
| EM3/A3 | T4 | 2 | 10 | 2 | 15 | T3 |
| P1/A4 | 8 | T4 | 25 | T4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| P4 | 64 | 32 | 200 | 32 | 240 | 48 |
| P5 | 128 | 64 | 400 | 64 | 480 | 96 |
| | | | | | | |

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
>[Insertar para los clientes](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Insertar para la organización](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Insertar desde aplicaciones](embed-from-apps.md)