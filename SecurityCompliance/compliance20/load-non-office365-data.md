---
title: Cargar datos que no son de Office 365 a un conjunto de trabajo
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: b177fc292c748f21907621196dc28d6b8fe17959
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296793"
---
# <a name="load-non-office-365-data-into-a-working-set"></a>Cargar datos que no son de Office 365 a un conjunto de trabajo

No todos los documentos que puede que necesite analizar con Office 365 Advanced eDiscovery residirán en Office 365. Con la característica de importación de contenido no de Office 365 en eDiscovery avanzado, puede cargar documentos que no vivan en Office 365 en un conjunto de trabajo para que se analice con eDiscovery avanzado. Este procedimiento muestra cómo llevar los documentos que no son de Office 365 a eDiscovery avanzado para su análisis.

>[!Note]
>Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede registrarse para una prueba de Office 365 Enterprise E5.

## <a name="before-you-begin"></a>Antes de empezar
El uso de la característica cargar no de Office 365 tal y como se describe en este procedimiento requiere que tenga:

- Una suscripción a Office 365 E3 con Advanced Compliance Add-on o E5.

- Todos los custodios cuyo contenido que no pertenezca a Office 365 se cargarán deben tener E3 con las licencias del complemento de cumplimiento avanzado o E5.

- Un caso de eDiscovery existente.

- Todos los archivos que se van a cargar se recopilan en carpetas en las que hay una carpeta por custodio y el nombre de las carpetas se encuentra en el formato de *alias @ nombredominio* . El *alias @ domainname* debe ser users Office 365 alias y dominio. Puede recopilar todas las carpetas *alias @ domainname* en una carpeta raíz. La carpeta raíz solo puede contener las carpetas *alias @ domainname* , no debe haber archivos sueltos en la carpeta raíz.

- Una cuenta que sea un administrador de eDiscovery o un administrador de exhibición de documentos electrónicos herramientas de almacenamiento de Microsoft Azure instaladas en un equipo que tenga acceso a la estructura de carpetas de contenido no Office 365.

- Instale AzCopy, que puede hacer desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Cargar contenido no de Office 365 en eDiscovery avanzado

1. Como administrador de eDiscovery o administrador de exhibición de documentos electrónicos, abra eDiscovery avanzado y, a continuación, el caso en el que se cargarán los datos que no son de Office 365.  Haga clic en la ficha **conjuntos de trabajo** y, a continuación, seleccione el conjunto de trabajo en el que desea cargar los datos que no son de Office 365.  Si todavía no ha creado un conjunto de trabajo, puede hacerlo ahora.  Por último, haga clic en **administrar el conjunto de trabajo** y, a continuación, **Ver cargas** en la sección de datos que no son de Office 365

2. Haga clic en el botón **cargar archivos** para iniciar el Asistente para importación de datos no perteneciente a Office 365.

![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. El primer paso del asistente simplemente prepara un BLOB seguro de Azure para los archivos que se van a cargar.  Una vez que se compelted la preparación, haga clic en el botón **cargar archivos** .

![Importación no de Office 365-preparación](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. En el paso **cargar archivos** , especifique la **ruta de acceso a la ubicación de los archivos**, aquí es donde se ubican los datos que no son de Office 365 que tiene previsto importar.  La configuración de la ubicación correcta asegura que el comando AzCopy se haya actualizado correctamente.

> [!NOTE]
> Si todavía no ha instalado AzCopy, puede hacerlo desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. Copie el comando predefinido haciendo clic en el vínculo **copiar al** portapapeles. Inicie un símbolo del sistema de Windows, pegue el comando y presione Entrar.  Los archivos se cargarán en el almacenamiento de blobs seguro de Azure para el paso siguiente.

![Importación no de Office 365: cargar archivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![No Office 365 Import-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. Por último, vuelva al cumplimiento de & de seguridad y haga clic en el botón **siguiente: procesar archivos** .  Se iniciará el procesamiento, la extracción de texto y la indización de los archivos cargados.  Puede realizar un seguimiento del progreso del procesamiento aquí o en la pestaña **trabajos** .  Una vez completados, los nuevos archivos estarán disponibles en el conjunto de trabajo.  Una vez que se haya completado el procesamiento, puede descartar el asistente.

![Archivos que no son de Office 365 importación-proceso](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

