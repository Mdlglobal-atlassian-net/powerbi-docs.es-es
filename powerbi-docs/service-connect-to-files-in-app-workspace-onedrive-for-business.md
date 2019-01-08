---
title: Conéctese a los archivos en OneDrive de un área de trabajo de aplicaciones de Power BI
description: Obtenga información no solo acerca de cómo almacenar archivos de Excel, CSV y Power BI Desktop, sino también de cómo conectarse a ellos en el OneDrive de su área de trabajo de la aplicación de Power BI.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukasz
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/02/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 1b40cf858fd42e9e73a64e926fef0caf917ed064
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008911"
---
# <a name="connect-to-files-stored-in-onedrive-for-your-power-bi-app-workspace"></a>Conéctese a los archivos almacenados en OneDrive del área de trabajo de aplicaciones de Power BI
Una vez que [ha creado un área de trabajo de una aplicación en Power BI](service-create-distribute-apps.md), puede almacenar los archivos de Excel, CSV y Power BI Desktop en la instancia de OneDrive para la Empresa de dicho área. Los archivos que almacene en OneDrive se pueden seguir actualizando, y dichas actualizaciones se reflejarán automáticamente en los informes y paneles de Power BI en función de los archivos. 

> [!NOTE]
> La versión preliminar de la nueva experiencia de áreas de trabajo cambiará la relación entre las áreas de trabajo de Power BI y los grupos de Office 365. Ya no creará automáticamente un grupo de Office 365 cada vez que cree una de las nuevas áreas de trabajo. Obtenga información sobre [la creación de nuevas áreas de trabajo (versión preliminar)](service-create-the-new-workspaces.md)

La incorporación de archivos al área de trabajo de una aplicación es un proceso que consta de dos pasos: 

1. En primer lugar, [cargue archivos en OneDrive para la Empresa](service-connect-to-files-in-app-workspace-onedrive-for-business.md#1-upload-files-to-the-onedrive-for-business-for-your-app-workspace) del área de trabajo de la aplicación.
2. Después, [conéctese a esos archivos desde Power BI](service-connect-to-files-in-app-workspace-onedrive-for-business.md#2-import-excel-files-as-datasets-or-as-excel-online-workbooks).

> [!NOTE]
> Las áreas de trabajo de la aplicación solo están disponibles en [Power BI Pro](service-features-license-type.md).
> 
> 

## <a name="1-upload-files-to-the-onedrive-for-business-for-your-app-workspace"></a>1 Carga archivos en OneDrive para la Empresa del área de trabajo de la aplicación
1. En el servicio Power BI, seleccione la flecha situada junto a Áreas de trabajo y, después, el botón de puntos suspensivos (**...**) junto al nombre del área de trabajo. 
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-ellipsis.png)
2. Seleccione **Archivos** para abrir OneDrive para la Empresa del área de trabajo de la aplicación en Office 365.
   
   > [!NOTE]
   > Si no ve **Archivos** en el área de trabajo de la aplicación, seleccione **Miembros** para abrir OneDrive para la Empresa del área de trabajo de la aplicación. Una vez ahí, seleccione **Archivos**. Office 365 configura una ubicación de almacenamiento en OneDrive para los archivos del área de trabajo de su aplicación. Este proceso puede tardar algún tiempo. 
   > 
   > 
3. Aquí puede cargar los archivos en OneDrive para la Empresa del área de trabajo de la aplicación. Seleccione **Cargar**y vaya a los archivos.
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grpfilesonedrive.png)

## <a name="2-import-excel-files-as-datasets-or-as-excel-online-workbooks"></a>2 Importación de archivos de Excel como conjuntos de datos o como libros de Excel Online
Ahora que los archivos se encuentran en OneDrive para la Empresa del área de trabajo de la aplicación, tiene dos opciones. Puede: 

* [Importar los datos del libro de Excel como un conjuntos de datos](service-get-data-from-files.md) y usarlos para crear informes y paneles que se puedan ver en un explorador web y en dispositivos móviles.
* O bien, [conectarse a un libro de Excel completo en Power BI](service-excel-workbook-files.md) y mostrarlo exactamente como aparece en Excel Online.

### <a name="import-or-connect-to-the-files-in-your-app-workspace"></a>Importación o conexión a los archivos del área de trabajo de la aplicación
1. En Power BI, cambie al área de trabajo de la aplicación para que el nombre del área de trabajo de la aplicación aparezca en la esquina superior izquierda. 
2. Seleccione **Obtener datos** en la parte inferior del panel de navegación izquierdo. 
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-get-data-button.png)
3. En el cuadro **Archivos** , seleccione **Obtener**.
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_getfiles.png)
4. Seleccione **OneDrive** - *Nombre del área de la aplicación*.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grp_one_drive_shrpt.png)
5. Seleccione el archivo que quiera > **Conectar**.
   
    En este punto, debe decidir si [importar los datos desde el libro de Excel](service-get-data-from-files.md) o [conectarse a libros de Excel completos](service-excel-workbook-files.md).
6. Seleccione **Importar** o **Conectarse**.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_importexceldataorwholecrop.png)
7. Si selecciona **Importar**, el libro aparecerá en la pestaña **Conjuntos de datos**. 
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-import.png)
   
    Si selecciona **Conectar**, el libro aparecerá en la pestaña **Libros**.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-connect.png)

## <a name="next-steps"></a>Pasos siguientes
* [Creación de aplicaciones y áreas de trabajo de la aplicación de Power BI](service-create-distribute-apps.md)
* [Importar datos desde libros de Excel](service-get-data-from-files.md)
* [Conectarse a libros de Excel completos](service-excel-workbook-files.md)
* ¿Tiene más preguntas? [Pruebe la comunidad de Power BI](http://community.powerbi.com/)
* Comentarios Visite [Ideas sobre Power BI](https://ideas.powerbi.com/forums/265200-power-bi)

