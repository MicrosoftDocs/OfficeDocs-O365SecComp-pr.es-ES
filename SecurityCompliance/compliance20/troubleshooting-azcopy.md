---
title: Solucionar problemas de AzCopy en eDiscovery avanzado (versión preliminar)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 9711bee4ec9a61510b47568df37dfd3135e1e00c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241086"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery-preview"></a>Solucionar problemas de AzCopy en eDiscovery avanzado (versión preliminar)

Al cargar datos y documentos que no son de Office 365 para la corrección de errores en eDiscovery avanzado (versión preliminar), la interfaz de usuario suministra un comando AzCopy de Azure que contiene parámetros con la ubicación en la que se almacenan los archivos que desea cargar y Azure Ubicación de almacenamiento en la que se cargarán los archivos. Para cargar los documentos, copie este comando y, a continuación, ejecútelo en un símbolo del sistema en el equipo local.  La captura de pantalla siguiente muestra un ejemplo de un comando AzCopy:

![Cargar archivos que no son de Office 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

En la mayoría de los casos, el comando que se proporciona funcionará cuando lo ejecute. Sin embargo, puede haber casos en los que el comando que se muestra no se ejecute correctamente. Estas son algunas de las razones posibles.

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy no está instalado en el equipo local o no está instalado en la ubicación predeterminada

Si AzCopy no está instalado o está instalado en una ubicación distinta de la ubicación de instalación predeterminada (que `%ProgramFiles(x86)%`es), es posible que reciba el siguiente error al ejecutar el comando AzCopy:

    The system cannot find the path specified.

Si AzCopy no se instala en el equipo local, puede instalarlo desde aquí (Asegúrese de instalarlo en la ubicación predeterminada): [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).


Si AzCopy está instalado, pero se instala en una ubicación distinta de la ubicación predeterminada, puede copiar el comando, pegarlo en un archivo de texto y, a continuación, cambiar la ruta de acceso a la ubicación en la que AzCopy está instalado. Por ejemplo, si Azcopy se encuentra en `%ProgramFiles%`, puede cambiar la primera parte del comando de `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` a. `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` Después de realizar este cambio, cópielo del archivo de texto y, a continuación, ejecútelo desde el símbolo del sistema.

> [!TIP]
> Si AzCopy está instalado en una ubicación distinta de la ubicación de instalación predeterminada, considere la posibilidad de desinstalarlo y volver a instalarlo en la ubicación predeterminada. Esto le ayudará a evitar este problema en el futuro.