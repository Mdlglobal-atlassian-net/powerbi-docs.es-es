---
title: Accesibilidad a informes de Power BI Desktop
description: Características y sugerencias para crear informes accesibles de Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/05/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 6147f41ea99ad4a0416f6aa9c01288102f792771
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "34812937"
---
# <a name="accessibility-in-power-bi-desktop-reports"></a>Accesibilidad a informes de Power BI Desktop
**Power BI Desktop** presenta características que permiten a las personas con discapacidades utilizar los informes de **Power BI Desktop** e interactuar con ellos con más facilidad. Estas características incluyen la capacidad de interactuar con el informe mediante el teclado o un lector de pantalla, la tabulación para centrar la atención en varios objetos de una página y el uso apropiado de marcadores en las visualizaciones.

![Uso de marcadores diferentes para gráficos de líneas y de áreas para mejorar la accesibilidad](media/desktop-accessibility/accessibility_01.png)

> [!NOTE]
> Estas características de accesibilidad están disponibles con la versión de **Power BI Desktop** de junio de 2017 y posteriores. También se prevé una funcionalidad de accesibilidad adicional en futuras versiones.
> 
> 

## <a name="consuming-a-power-bi-desktop-report-with-a-keyboard-or-screen-reader"></a>Interactuación con un informe de Power BI Desktop mediante un teclado o un lector de pantalla
A partir de la versión de septiembre de 2017 de **Power BI Desktop**, puede presionar la tecla **?** para mostrar una ventana que describe los métodos abreviados de teclado de accesibilidad disponibles en **Power BI Desktop**.

![Presione la tecla ? en Power BI Desktop para mostrar los métodos abreviados de teclado de accesibilidad](media/desktop-accessibility/accessibility_03.png)

Con las mejoras de accesibilidad, puede interactuar con un informe de **Power BI Desktop** mediante un teclado o un lector de pantalla utilizando las siguientes técnicas:

Puede cambiar el enfoque entre las pestañas de las páginas del informe o los objetos de la página de un informe determinada con las teclas **Ctrl+F6**.

* Cuando el enfoque recae en las *pestañas de páginas de informes*, use el *tabulador* o las teclas de *dirección* para cambiar el enfoque de la página de un informe a la siguiente. El lector de pantalla lee el título de la página del informe e identifica si dicha página está seleccionada actualmente. Para cargar la página del informe en la que recae el enfoque actualmente, use la tecla *ENTRAR* o la *barra espaciadora*.
* Si el enfoque recae en una *página del informe* cargada, use el *tabulador* para cambiar el enfoque a cada objeto de la página, que incluye todos los cuadros de texto, imágenes, formas y gráficos. El lector de pantalla lee el tipo de objeto y una descripción de dicho objeto facilitada por su autor. 

Puede presionar **Alt + Mayús + F10** para cambiar el centro de atención al menú de un objeto visual.

Puede presionar **Alt + Mayús + F11** para presentar una versión de la ventana *Ver datos* a la que se puede acceder.

![Presione Alt + Mayús + F11 en Power BI Desktop para mostrar una ventana accesible Ver datos en un objeto visual](media/desktop-accessibility/accessibility_04.png)

Estas incorporaciones a las opciones de accesibilidad se han creado para que los usuarios consuman totalmente los informes de **Power BI Desktop** informes mediante un lector de pantalla y la navegación mediante teclado.

## <a name="tips-for-creating-accessible-reports"></a>Sugerencias para la creación de informes accesibles
Las siguientes sugerencias pueden ayudarlo a crear informes de **Power BI Desktop** que sean más accesibles.

* Para los objetos visuales de **línea**, **área** y **combinados**, al igual que para **Dispersión** y **Burbuja** active los marcadores y use una *forma de marcador* distinta para cada línea.
  
  * Para activar los *marcadores*, seleccione la sección **Formato** en el panel **Visualizaciones** y expanda la sección **Formas**; a continuación, desplácese hacia abajo para encontrar la opción de activación/desactivación de **Marcadores** y *actívela*.
  * A continuación, seleccione el nombre de cada línea (o de área, si usa un gráfico de **área**) en el cuadro de lista desplegable de la sección **Formas**. Debajo de la lista desplegable, puede ajustar muchos aspectos del marcador utilizado para la línea seleccionada, entre otros, su forma, color y tamaño.
  
  ![Uso de marcadores diferentes para gráficos de líneas y de áreas para mejorar la accesibilidad](media/desktop-accessibility/accessibility_01.png)
  
  * La utilización de una *forma de marcador* distinta para cada línea permite que los lectores del informe puedan diferenciar cada una de las líneas o áreas con más facilidad.
* Como continuación del punto anterior, no se base en el color para transmitir información. El uso de formas en líneas (marcadores, como se ha descrito en los puntos anteriores) resulta de utilidad.
* Seleccione un *tema* en la galería de temas con un alto contraste y un color apropiado para invidentes y, después, impórtelo en la [característica de versión preliminar **Temas**](desktop-report-themes.md).
* Proporcione *texto alternativo* para cada objeto de un informe. De esta forma, se asegura de que los usuarios del informe entienden lo que trata de comunicar con un objeto visual, incluso aunque ellos no puedan ver el objeto visual, la imagen, la forma o el cuadro de texto. Para proporcionar *texto alternativo* para cualquier objeto de un informe de **Power BI Desktop**, seleccione el objeto (como un objeto visual, una forma, etc.) y, en el panel **Visualizaciones**, seleccione la sección **Formato**, expanda **General**, desplácese hacia abajo y rellene el cuadro de texto **Texto alternativo**.
  
  ![El texto alternativo para cualquier objeto de un informe se puede agregar en Visualizaciones > Formato > General > cuadro Texto alternativo.](media/desktop-accessibility/accessibility_02.png)
* Asegúrese de que los informes tengan suficiente contraste entre el texto y los colores de fondo.
* Use tamaños de texto y fuentes que sean fácilmente legibles. El texto o las fuentes de pequeño tamaño podrían ser difíciles de leer y poco prácticos de cara a la accesibilidad.
* Incluya un título, etiquetas de eje y etiquetas de datos en todos los objetos visuales.

## <a name="high-contrast-support-for-reports"></a>Compatibilidad con el contraste alto en los informes

Al usar los modos de contraste alto en Windows, esta configuración y la paleta que seleccione también se aplicarán a los informes de **Power BI Desktop**. 

![Configuración de Windows de contraste alto](media/desktop-accessibility/accessibility_05.png)

**Power BI Desktop** detecta automáticamente el tema de contraste alto que se usa en Windows y aplica esta configuración a los informes. Los colores de contraste alto seguirán al informe a la hora de publicarlo en el servicio Power BI o en otro lugar.

![Configuración de Windows de contraste alto](media/desktop-accessibility/accessibility_05b.png)

El servicio Power BI también intenta detectar la configuración de contraste alto seleccionada para Windows, pero el grado de eficacia y de precisión de esa detección dependerá del explorador usado en el servicio Power BI. Si quiere establecer el tema manualmente en el servicio Power BI, puede seleccionar **Vista > Colores de alto contraste** y, después, seleccionar el tema que quiere aplicar al informe.

![Configuración del contraste alto en el servicio Power BI](media/desktop-accessibility/accessibility_06.png)

Cuando esté en **Power BI Desktop** se percatará de que algunas áreas, como los campos **Visualizaciones** y **Campos**, no reflejan la selección de combinaciones de colores de contraste alto de Windows.


## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones
Hay algunos problemas conocidos y limitaciones con las características de accesibilidad, que se describen en la lista siguiente:

* JAWS solo se admite en los informes que se ven en el **servicio Power BI**, incluidos los informes insertados. JAWS también se admite en **Power BI Desktop**; sin embargo, debe abrir el lector de pantalla antes de abrir cualquier archivo de **Power BI Desktop** para que la pantalla de lectura funcione correctamente.

## <a name="next-steps"></a>Pasos siguientes
* [Uso de los temas para los informes en Power BI Desktop (versión preliminar)](desktop-report-themes.md)

