---
title: Datos de Analysis Services multidimensionales en Power BI Desktop
description: Datos de Analysis Services multidimensionales en Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 40da2a9a53cfb7a0e497f85f87bca6a133046720
ms.sourcegitcommit: 05303d3e0454f5627eccaa25721b2e0bad2cc781
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "52578713"
---
# <a name="connect-to-ssas-multidimensional-models-in-power-bi-desktop"></a>Conectarse a modelos SSAS multidimensionales en Power BI Desktop
Con Power BI Desktop, ahora puede acceder a **modelos SSAS multidimensionales**, que suelen denominarse **SSAS MD**.

Para conectarse a una base de datos **SSAS MD**, seleccione **Obtener datos &gt; Base de datos &gt; Base de datos de SQL Server Analysis Services**, como se muestra esta imagen:

![](media/desktop-ssas-multidimensional/ssas-multidimensional-2.png)

Tanto el servicio Power BI como Power BI Desktop admiten **modelos SSAS multidimensionales** en el modo de conexión dinámica. También puede publicar y cargar informes que empleen **modelos SSAS multidimensionales** en el modo de conexión dinámica en el servicio Power BI.

## <a name="capabilities-and-features-of-ssas-md"></a>Funcionalidades y características de SSAS MD
Las secciones siguientes describen las características y funcionalidades de las conexiones de Power BI y SSAS MD.

### <a name="tabular-metadata-of-multidimensional-models"></a>Metadatos tabulares de modelos multidimensionales
La siguiente tabla muestra la correspondencia entre los objetos multidimensionales y los metadatos tabulares que se devuelven a Power BI Desktop. Power BI consulta los metadatos tabulares al modelo y, según los metadatos devueltos, ejecuta las consultas DAX apropiadas en Analysis Services cuando se crea una visualización como una tabla, una matriz, un gráfico o una segmentación de datos.

| Objeto multidimensional BISM | Metadatos tabulares |
| --- | --- |
| Cubo |Modelo |
| Dimensión de cubo |Tabla |
| Atributos de dimensión (Keys), Name |columnas |
| Grupo de medida |Tabla |
| Medida |Medida |
| Medidas sin grupo de medida asociado |En la tabla llamada *Medidas* |
| Grupo de medida -> Relación de dimensión de cubo |Relación |
| Perspectiva |Perspectiva |
| KPI |KPI |
| Jerarquías de usuarios, elementos primarios y secundarios |Jerarquías |

### <a name="measures-measure-groups-and-kpis"></a>Medidas, grupos de medida y KPI
Los grupos de medida de un cubo multidimensional se exponen en Power BI como tablas con el signo ∑ junto a ellos en el panel **Campos** . La medidas calculadas que no tienen un grupo de medida asociado se agrupan en una tabla especial llamada *Medidas* en los metadatos tabulares.

En un modelo multidimensional, puede definir un conjunto de medidas o KPI en un cubo que se ubicará dentro de una *Carpeta para mostrar*, lo que puede ayudar a simplificar modelos complejos. Power BI reconoce las carpetas para mostrar en los metadatos tabulares y muestra las medidas y los KPI dentro de las carpetas para mostrar. En las bases de datos multidimensionales, los KPI admiten los atributos *Value*, *Goal*, *Status Graphic* y *Trend Graphic*.

### <a name="dimension-attribute-type"></a>Tipos de atributos de dimensión
Los modelos multidimensionales también permiten asociar atributos de dimensión con tipos de atributo de dimensión específicos. Por ejemplo, una dimensión **Geography** cuyos atributos de dimensión *City*, *State-Province*, *Country* y *Postal Code* tienen asociados los tipos de geografía adecuados, se exponen en los metadatos tabulares. Power BI reconoce los metadatos, lo que permite crear visualizaciones de mapas. Reconocerá estas asociaciones por el icono *mapa* situado junto al elemento en el panel **Campo** en Power BI.

Power BI también puede representar imágenes cuando se proporciona un campo que contiene las direcciones URL (localizador uniforme de recursos) de las imágenes. Puede especificar que el tipo de estos campos sea *ImageURL* en SQL Server Data Tools (o después en Power BI) y la información sobre el tipo se proporciona a Power BI en los metadatos tabulares. Después, Power BI puede recuperar las imágenes de la dirección URL y mostrarlos en objetos visuales.

### <a name="parent-child-hierarchies"></a>Jerarquías de elementos primarios y secundarios
Los modelos multidimensionales admiten jerarquías de elementos primarios y secundarios, que se presentan como una *jerarquía* en los metadatos tabulares. Cada nivel de la jerarquía de elementos primarios y secundarios se expone como una columna oculta en los metadatos tabulares. El atributo clave de la dimensión de elementos primarios y secundarios no se expone en los metadatos tabulares.

### <a name="dimension-calculated-members"></a>Miembros calculados de dimensión
Los modelos multidimensionales permiten crear varios tipos de *miembros calculados*. Los dos tipos de miembros calculados más comunes son los siguientes:

* Miembros calculados en jerarquías de atributos y que no sean del mismo nivel que *Todos*
* Miembros calculados en jerarquías de usuarios

Los modelos multidimensionales exponen *miembros calculados en jerarquías de atributos* como valores de una columna. Existen algunas opciones y restricciones adicionales a la hora de exponer este tipo de miembro calculado:

* El atributo de dimensión puede tener un valor de *UnknownMember* opcional
* Un atributo que contenga miembros calculados no puede ser el atributo clave de la dimensión, a menos que sea el único atributo de la dimensión
* Un atributo que contenga miembros calculados no puede ser un atributo de elementos primarios y secundarios

Los miembros calculados de las jerarquías de usuarios no se exponen en Power BI. En su lugar, podrá conectarse a un cubo que contenga miembros calculados en jerarquías de usuarios, pero no podrá ver los miembros calculados si no se cumplen las restricciones mencionadas en la lista con viñetas anterior.

### <a name="security"></a>Seguridad
Los modelos multidimensionales admiten la seguridad en el nivel de celdas y dimensiones mediante *Roles*. Cuando se conecte a un cubo con Power BI, se autenticarán y evaluarán los permisos adecuados. Cuando un usuario tiene aplicada *seguridad de dimensión* , el usuario no ve los miembros de dimensión correspondientes en Power BI. Sin embargo, cuando un usuario tiene definido un permiso de *seguridad de celda* , que restringe ciertas celdas, ese usuario no puede conectarse al cubo mediante Power BI.

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
Existen ciertas limitaciones en el uso de **SSAS MD**:

* Los servidores deben ejecutar SQL Server 2012 SP1 CU4 o versiones posteriores de Analysis Services para que el conector SSAS MD de Power BI Desktop funcione correctamente.
* Las *acciones* y los *conjuntos con nombre* no se exponen en Power BI, pero todavía puede conectarse a los cubos que, del mismo modo, contengan *acciones* o *conjuntos con nombre* y crear objetos visuales e informes.
* Puede que detecte un problema por el que Power BI muestra los metadatos de un modelo SSAS, pero no puede recuperar los datos del modelo. Esto puede ocurrir si tiene instalada en el sistema la versión de 32 bits del proveedor MSOLAP, en vez de la versión de 64 bits. El problema debería resolverse instalando la versión de 64 bits.
* No puede crear medidas de "nivel de informe" al crear un informe conectado en directo a un modelo multidimensional SSAS. Las únicas medidas que están disponibles son las que se definen en el modelo MD.

## <a name="supported-features-of-ssas-md-in-power-bi-desktop"></a>Características admitidas de SSAS MD en Power BI Desktop
Se admiten las siguientes características de SSAS MD en Power BI Desktop:

* Se admite el consumo de los elementos siguientes en esta versión de **SSAS MD** (puede obtener [más información](https://msdn.microsoft.com/library/jj969574.aspx) sobre estas características):
  * Carpetas para mostrar
  * Tendencias de KPI
  * Miembros predeterminados
  * Atributos de dimensión
  * Miembros de dimensión calculados (debe ser un único miembro real si la dimensión tiene más de un atributo, no puede ser el atributo clave de la dimensión a menos que sea el único atributo y no puede ser un atributo primario-secundario)
  * Tipos de atributos de dimensión
  * Jerarquías
  * Medidas (con o sin grupos de medida)
  * Medidas como variante
  * KPI
  * Direcciones URL de imagen
  * Seguridad de dimensión

## <a name="troubleshooting"></a>Solución de problemas 
En la lista siguiente se describen todos los problemas conocidos al conectarse a SQL Server Analysis Services (SSAS). 

* **Error: No se pudo cargar el esquema de modelo**. Este error suele producirse si el usuario que intenta conectarse a Analysis Services no tiene acceso a la base de datos o al cubo.
