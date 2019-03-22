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
ms.sourcegitcommit: cf9d9b545a7c153d314aa9c08c7fb16fcd785b3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2019
ms.locfileid: "30742518"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery-preview"></a><span data-ttu-id="21825-102">Solucionar problemas de AzCopy en eDiscovery avanzado (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="21825-102">Troubleshoot AzCopy in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="21825-103">Al cargar datos y documentos que no son de Office 365 para la corrección de errores en eDiscovery avanzado (versión preliminar), la interfaz de usuario suministra un comando AzCopy de Azure que contiene parámetros con la ubicación en la que se almacenan los archivos que desea cargar y Azure Ubicación de almacenamiento en la que se cargarán los archivos.</span><span class="sxs-lookup"><span data-stu-id="21825-103">When loading non-Office 365 data or documents for error remediation in Advanced eDiscovery (Preview), the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="21825-104">Para cargar los documentos, copie este comando y, a continuación, ejecútelo en un símbolo del sistema en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="21825-104">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="21825-105">La captura de pantalla siguiente muestra un ejemplo de un comando AzCopy:</span><span class="sxs-lookup"><span data-stu-id="21825-105">The follow screenshot shows an example of an AzCopy command:</span></span>

![Cargar archivos que no son de Office 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="21825-107">En la mayoría de los casos, el comando que se proporciona funcionará cuando lo ejecute.</span><span class="sxs-lookup"><span data-stu-id="21825-107">In most cases, the command that's provided will work when you run it.</span></span> <span data-ttu-id="21825-108">Sin embargo, puede haber casos en los que el comando que se muestra no se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="21825-108">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="21825-109">Estas son algunas de las razones posibles.</span><span class="sxs-lookup"><span data-stu-id="21825-109">Here's a few possible reasons.</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="21825-110">AzCopy no está instalado en el equipo local o no está instalado en la ubicación predeterminada</span><span class="sxs-lookup"><span data-stu-id="21825-110">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="21825-111">Si AzCopy no está instalado o está instalado en una ubicación distinta de la ubicación de instalación predeterminada (que `%ProgramFiles(x86)%`es), es posible que reciba el siguiente error al ejecutar el comando AzCopy:</span><span class="sxs-lookup"><span data-stu-id="21825-111">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

    The system cannot find the path specified.

<span data-ttu-id="21825-112">Si AzCopy no se instala en el equipo local, puede instalarlo desde aquí (Asegúrese de instalarlo en la ubicación predeterminada): [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="21825-112">If AzCopy isn't install on the local computer, you can install from here (being sure to install it in the default location): [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span>


<span data-ttu-id="21825-113">Si AzCopy está instalado, pero se instala en una ubicación distinta de la ubicación predeterminada, puede copiar el comando, pegarlo en un archivo de texto y, a continuación, cambiar la ruta de acceso a la ubicación en la que AzCopy está instalado.</span><span class="sxs-lookup"><span data-stu-id="21825-113">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is actually installed.</span></span> <span data-ttu-id="21825-114">Por ejemplo, si Azcopy se encuentra en `%ProgramFiles%`, puede cambiar la primera parte del comando de `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` a. `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`</span><span class="sxs-lookup"><span data-stu-id="21825-114">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="21825-115">Después de realizar este cambio, cópielo del archivo de texto y, a continuación, ejecútelo desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="21825-115">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="21825-116">Si AzCopy está instalado en una ubicación distinta de la ubicación de instalación predeterminada, considere la posibilidad de desinstalarlo y volver a instalarlo en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="21825-116">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="21825-117">Esto le ayudará a evitar este problema en el futuro.</span><span class="sxs-lookup"><span data-stu-id="21825-117">This will help prevent this issue in the future.</span></span>