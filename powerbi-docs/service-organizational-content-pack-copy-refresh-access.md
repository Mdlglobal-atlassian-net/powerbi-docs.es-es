---
title: 'Paquetes de contenido organizativos: Acceso y copia'
description: Obtenga más información sobre cómo crear copias de paquetes de contenido organizativos en Power BI y cómo solucionar problemas.
author: maggiesMSFT
manager: kfile
ms.reviewer: ajayan
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/08/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: c2d7a878189542d8a477933f6c54390b2636787e
ms.sourcegitcommit: b7839f2aa68c3626f55ee7e49c8392169d1ec67e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "34852242"
---
# <a name="organizational-content-packs-copy-refresh-and-get-access"></a>Paquetes de contenido de la organización: Copia, actualización y acceso
> [!NOTE]
> ¿Todavía no ha oído hablar de las nuevas *aplicaciones*? Las aplicaciones son la nueva forma de distribuir contenido para un gran público en Power BI. Tenemos previsto dejar de usar pronto los paquetes de contenido organizativos, por lo que recomendamos que use aplicaciones. Obtenga más información [sobre las aplicaciones](service-install-use-apps.md).
> 
> 

Cuando se publica un paquete de contenido organizativo, todos los destinatarios ven el mismo panel, así como los mismos informes, libros de Excel, conjuntos de datos y datos (a menos que sea un origen de datos de SQL Server Analysis Services, también denominado SSAS).  [Solo el creador del paquete de contenido lo puede volver a editar y publicar](service-organizational-content-pack-manage-update-delete.md).  Sin embargo, todos los destinatarios pueden guardar una copia del paquete de contenido, que puede coexistir con el original.

Es distinto crear paquetes de contenido que compartir paneles o colaborar en ellos en un grupo. Lea [¿Cómo debo compartir paneles, informes e iconos?](service-how-to-collaborate-distribute-dashboards-reports.md) para decidir cuál es la mejor opción en su caso.

## <a name="create-a-copy-of-an-organizational-content-pack"></a>Crear una copia de un paquete de contenido organizativo
Puede crear su propia copia del paquete de contenido, que no será visible para el resto de usuarios.

1. Seleccione los puntos suspensivos (...) junto al panel del paquete de contenido > Crear una copia.
   
    ![](media/service-organizational-content-pack-copy-refresh-access/power-bi-create-copy-organizational-content-pack.png)
2. Seleccione **Guardar**.  

Ahora ya tiene una copia que puede modificar. Nadie verá los cambios que realice.

## <a name="help--i-can-no-longer-access-the-content-pack"></a>Ayuda  Ya no puedo acceder al paquete de contenido
Esto puede ocurrir por varios motivos:

* **Cambios de pertenencia:** los paquetes de contenido se publican en grupos de distribución de correo electrónico, grupos de seguridad y [grupos de Power BI basados en Office 365](https://support.office.com/article/Create-a-group-in-Office-365-7124dc4c-1de9-40d4-b096-e8add19209e9).  Si se le elimina de ese grupo, ya no tendrá acceso al paquete de contenido.
* **Cambios de distribución:** el creador del paquete de contenido cambia la distribución. Por ejemplo, si el paquete de contenido se publicó originalmente en toda la organización, pero el creador lo volvió a publicar para un público más reducido, es posible que ya no esté incluido.
* **Cambios de configuración de seguridad:** si el panel y los informes se conectan a orígenes de datos SSAS locales y se realizan cambios en la configuración de seguridad, es posible que se hayan revocado los permisos para ese servidor.

## <a name="how-are-organizational-content-packs-refreshed"></a>¿Cómo se actualizan los paquetes de contenido organizativos?
Cuando se crea el paquete de contenido, se hereda la configuración de actualización con el conjunto de datos.  Cuando crea una copia del paquete de contenido, la nueva versión conserva el vínculo al conjunto de datos original, así como su programación de actualización. 

Consulte [Administración, actualización y eliminación de paquetes de contenido organizativos](service-organizational-content-pack-manage-update-delete.md).

## <a name="next-steps"></a>Pasos siguientes
* [Introducción a los paquetes de contenido organizativos](service-organizational-content-pack-introduction.md)
* [Creación de un grupo en Power BI](service-create-distribute-apps.md)
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)

