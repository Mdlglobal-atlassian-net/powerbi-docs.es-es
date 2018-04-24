---
title: Solución de problemas de origen de datos no admitido para la actualización
description: Solución de problemas de origen de datos no admitido para la actualización
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 802ed2f13d9965833f8862bda05796ac5b1dec5c
ms.sourcegitcommit: 312390f18b99de1123bf7a7674c6dffa8088529f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshooting-unsupported-data-source-for-refresh"></a>Solución de problemas de origen de datos no admitido para la actualización
Puede ver un error al intentar configurar un conjunto de datos para la actualización programada.

        You cannot schedule refresh for this dataset because it gets data from sources that currently don’t support refresh.

Esto sucede cuando no se admite el origen de datos que usa, en Power BI Desktop, para la actualización. Tendrá que buscar el origen de datos que está usando y compararlo con la lista de orígenes de datos compatibles en [Actualizar datos en Power BI](refresh-data.md). 

## <a name="find-the-data-source"></a>Búsqueda del origen de datos
Si no está seguro de qué origen de datos se utilizó, puede encontrarlo siguiendo los siguientes pasos en Power BI Desktop.  

1. En Power BI Desktop, asegúrese de que se encuentra en el panel **Informe** .  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-report-pane.png)
2. Seleccione **Editar consultas** en la barra de cinta.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-edit-queries.png)
3. Seleccione **Editor avanzado**.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-advanced-editor.png)
4. Tome nota del proveedor que aparece para el origen.  En este ejemplo, el proveedor es Active Directory.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-provider.png)
5. Compare el proveedor con la lista de orígenes de datos admitidos que se encuentra en [Actualizar datos en Power BI](refresh-data.md).  Encontrará que Active Directory no es un origen de datos compatible para la actualización.  

## <a name="next-steps"></a>Pasos siguientes
[Actualización de datos](refresh-data.md)  
[Power BI Gateway - Personal](personal-gateway.md)  
[On-premises Data Gateway (Puerta de enlace de datos local)](service-gateway-onprem.md)  
[Solución de problemas con la puerta de enlace de datos local](service-gateway-onprem-tshoot.md)  
[Solución de problemas de Power BI Gateway - Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

¿Tiene más preguntas? [Pruebe a preguntar a la comunidad de Power BI](http://community.powerbi.com/)

