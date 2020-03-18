---
title: Creación de un certificado SSL
description: Instrucciones de la solución alternativa para crear certificados manualmente en el servidor para desarrolladores
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: fab40863d7beae4892a56975aa5e92c4fe5486ac
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79380281"
---
# <a name="create-an-ssl-certificate"></a>Creación de un certificado SSL

En este artículo se describe cómo crear un certificado SSL.

Para generar el certificado mediante el cmdlet `New-SelfSignedCertificate` de PowerShell en Windows 8 o versiones posteriores, ejecute el siguiente comando:

```cmd
pbiviz --install-cert
```

La herramienta requiere una instalación de OpenSSL para Windows 7. La utilidad OpenSSL debe estar disponible desde la línea de comandos.

Para instalar OpenSSL, vaya al sitio de [OpenSSL](https://www.openssl.org) o de [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries).

## <a name="create-a-certificate-mac-os-x"></a>Creación de un certificado (Mac OS X)

Normalmente, la utilidad OpenSSL está disponible en el sistema operativo Linux o Mac OS X.

También puede instalar la utilidad si ejecuta alguno de los siguientes comandos:

* En el administrador de paquetes *Brew*:

    ```cmd
    brew install openssl
    brew link openssl --force
    ```

* Mediante *MacPorts*:

    ```cmd
    sudo port install openssl
    ```

Después de instalar la utilidad OpenSSL para generar un nuevo certificado, ejecute el siguiente comando:

```cmd
pbiviz --install-cert
```

## <a name="create-a-certificate-linux"></a>Creación de un certificado (Linux)

La utilidad OpenSSL no está disponible en el sistema operativo Linux, pero puede instalarla con uno de los siguientes comandos:

* Para el administrador de paquetes *APT*:

    ```cmd
    sudo apt-get install openssl
    ```

* Para *Yellowdog Updater*:

    ```cmd
    yum install openssl
    ```

* Para *Redhat Package Manager*:

    ```cmd
    rpm install openssl
    ```

Si la utilidad OpenSSL ya está disponible en el sistema operativo, ejecute el siguiente comando para generar un nuevo certificado:

```cmd
pbiviz --install-cert
```

También puede obtener la utilidad OpenSSL en el sitio de [OpenSSL](https://www.openssl.org) u [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries).

## <a name="generate-the-certificate-manually"></a>Generación manual del certificado

Puede especificar que los certificados se generen mediante cualquier herramienta.

Si la utilidad OpenSSL ya está instalada en el sistema, ejecute los siguientes comandos para generar un nuevo certificado:

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBICustomVisualTest_private.key -out PowerBICustomVisualTest_public.crt -days 365
```

Normalmente, puede encontrar los certificados de servidor web correspondientes a PowerBI-visuals-tools si ejecuta uno de los siguientes comandos:

* Para la instancia global de las herramientas:

    ```cmd
    %appdata%\npm\node_modules\PowerBI-visuals-tools\certs
    ```

* Para la instancia local de las herramientas:

    ```cmd
    <custom visual project root>\node_modules\PowerBI-visuals-tools\certs
    ```

Si usa el formato PEM, guarde el archivo de certificado como *PowerBICustomVisualTest_public.crt* y guarde el archivo privateKey como *PowerBICustomVisualTest_public.key*.

Si usa el formato PFX, guarde el archivo de certificado como *PowerBICustomVisualTest_public.pfx*.

Si el archivo de certificado PFX requiere una frase de contraseña, haga lo siguiente:
1. En el archivo de configuración, especifique:

    ```cmd
    \PowerBI-visuals-tools\config.json
    ```

1. En la sección `server`, especifique la frase de contraseña; para ello, reemplace el marcador de posición "*YOUR PASSPHRASE*":

    ```cmd
    "server":{
        "root":"webRoot",
        "assetsRoute":"/assets",
        "privateKey":"certs/PowerBICustomVisualTest_private.key",
        "certificate":"certs/PowerBICustomVisualTest_public.crt",
        "pfx":"certs/PowerBICustomVisualTest_public.pfx",
        "port":"8080",
        "passphrase":"YOUR PASSPHRASE"
    }
    ```