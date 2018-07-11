---
title: Conectarse a una base de datos de Impala en Power BI Desktop
description: Conectarse fácilmente a una base de datos de Impala y usarla en Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 7feb562c5d2d96c4d726b93393a0b4a26c658415
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37134763"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Conectarse a una base de datos de Impala en Power BI Desktop
En Power BI Desktop, puede conectarse a una base de datos de **Impala** y usar los datos subyacentes como cualquier otro origen de datos en Power BI Desktop.

## <a name="connect-to-an-impala-database"></a>Conectarse a una base de datos de Impala
Para conectarse a una base de datos de **Impala**, seleccione **Obtener datos** en la cinta **Inicio** de Power BI Desktop. Seleccione **Base de datos** en las categorías de la izquierda para que se muestre **Impala**.

![](media/desktop-connect-impala/connect_impala_2.png)

En la ventana **Impala** que aparece, escriba o pegue en el cuadro el nombre de su servidor Impala y seleccione **Aceptar**. Tenga en cuenta que puede elegir **Importar** datos directamente a Power BI o puede usar **DirectQuery**. Puede obtener más información acerca de cómo [usar DirectQuery](desktop-use-directquery.md).

![](media/desktop-connect-impala/connect_impala_3a.png)

Cuando se le pida, escriba sus credenciales o conéctese de forma anónima. El conector de Impala admite Anonymous, Basic (nombre de usuario + contraseña) y la autenticación de Windows.

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> Una vez que haya escrito su nombre de usuario y contraseña para un servidor **Impala** determinado, Power BI Desktop usa esas mismas credenciales en los intentos de conexión posteriores. Si quiere modificar dichas credenciales, vaya a **Archivo > Opciones y configuración > Configuración de origen de datos**.
> 
> 

Una vez que se haya conectado correctamente, aparece la ventana **Navegador**, en la que se muestran los datos disponibles en el servidor, desde donde puede seleccionar uno o varios elementos para importar y usar en **Power BI Desktop**.

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
Hay algunos límites y consideraciones que se deben tener en cuenta con el conector de **Impala**:

* El conector de Impala se admite en la puerta de enlace de datos local, con cualquiera de los tres mecanismos de autenticación admitidos.

## <a name="next-steps"></a>Pasos siguientes
Hay todo tipo de datos a los que puede conectarse con Power BI Desktop. Para obtener más información sobre orígenes de datos, consulte los siguientes recursos:

* [¿Qué es Power BI Desktop?](desktop-what-is-desktop.md)
* [Orígenes de datos en Power BI Desktop](desktop-data-sources.md)
* [Combinar datos y darles forma con Power BI Desktop](desktop-shape-and-combine-data.md)
* [Connect to Excel workbooks in Power BI Desktop (Conectarse a libros de Excel en Power BI Desktop)](desktop-connect-excel.md)   
* [Especificar datos directamente en Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

