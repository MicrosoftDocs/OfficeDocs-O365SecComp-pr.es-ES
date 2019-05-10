---
title: Cargar datos que no son de Office 365 a un conjunto de revisión
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
ms.openlocfilehash: 60775002d5ebec83aacbec350a044b9d6ffeb461
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834969"
---
# <a name="load-non-office-365-data-into-a-review-set"></a>Cargar datos que no son de Office 365 a un conjunto de revisión

No todos los documentos que puede que necesite analizar con Office 365 Advanced eDiscovery residirán en Office 365. Con la característica de importación de contenido no de Office 365 en eDiscovery avanzado, puede cargar documentos que no vivan en Office 365 en un conjunto de revisión para que se analice con eDiscovery avanzado. Este procedimiento muestra cómo llevar los documentos que no son de Office 365 a eDiscovery avanzado para su análisis.

>[!Note]
>EDiscovery avanzado requiere un Office 365 E3 con el complemento Advanced Compliance o una suscripción a e5 para su organización. Si no tiene ese plan y desea probar la exhibición avanzada de documentos electrónicos, puede registrarse para obtener una versión de prueba de Office 365 Enterprise E5.

## <a name="before-you-begin"></a>Antes de empezar

El uso de la característica cargar no de Office 365 tal y como se describe en este artículo requiere lo siguiente:

- Una suscripción de Office 365 o Microsoft 365 E5 o una suscripción a E3 con la suscripción de complemento de cumplimiento avanzado.

- Todos los custodios cuyo contenido que no pertenezca a Office 365 se cargará deben tener una licencia E3 con una licencia de complemento de cumplimiento avanzado o tener una licencia E5.

- Un caso de exhibición avanzada de documentos electrónicos existente.

- Se deben agregar custodios al caso antes de cargar los datos que no son de Office 365 asociados a ellos.

- Todos los archivos que se cargarán deben encontrarse en carpetas, donde cada carpeta está asociada a un custodio específico. Los nombres de estas carpetas deben usar el siguiente formato de nombre: *alias @ domainname*. El *alias @ domainname* debe ser el alias y el dominio de Office 365 del usuario. Puede recopilar todas las carpetas *alias @ domainname* en una carpeta raíz. La carpeta raíz solo puede contener las carpetas *alias @ domainname* ; los archivos sueltos no se permiten en la carpeta raíz.

   Por ejemplo, la estructura de carpetas para los datos que no son de Office 365 que desea cargar sería similar a la siguiente:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Donde abraham.mcmahon@contoso.com, jewell.gordon@contoso.com y staci.gonzalez@contoso.com son las direcciones SMTP de los custodios en el caso.

   ![Estructura de carpetas de carga de datos no de Office 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Una cuenta que sea administrador de exhibición de documentos electrónicos o administrador de exhibición de documentos electrónicos

- Herramientas de almacenamiento de Microsoft Azure instaladas en un equipo que tiene acceso a la estructura de carpetas de contenido no Office 365.

- Instale AzCopy, que puede hacer desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Cargar contenido no de Office 365 en eDiscovery avanzado

1. Como administrador de eDiscovery o administrador de exhibición de documentos electrónicos, abra eDiscovery avanzado y, a continuación, el caso en el que se cargarán los datos que no son de Office 365.  Haga clic en la pestaña **Review sets** y, a continuación, seleccione el conjunto de revisión en el que desea cargar los datos que no son de Office 365.  Si aún no ha creado un conjunto de revisiones, puede hacerlo ahora.  Por último, haga clic en **administrar conjunto de revisiones** y, a continuación, haga clic en **Ver cargas** en el mosaico de datos * * que no es de Office 365.

2. Haga clic en el botón **cargar archivos** para iniciar el Asistente para importación de datos no perteneciente a Office 365.

   ![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. El primer paso del asistente simplemente prepara un BLOB seguro de Azure para los archivos que se van a cargar.  Una vez completada la preparación, haga clic en el botón **cargar archivos** .

   ![Importación no de Office 365-preparación](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. En el paso **cargar archivos** , especifique la **ruta de acceso a la ubicación de los archivos**, aquí es donde se ubican los datos que no son de Office 365 que tiene previsto importar.  La configuración de la ubicación correcta asegura que el comando AzCopy se haya actualizado correctamente.

   > [!NOTE]
   > Si todavía no ha instalado AzCopy, puede hacerlo desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. Copie el comando predefinido haciendo clic en el vínculo **copiar al** portapapeles. Inicie un símbolo del sistema de Windows, pegue el comando y presione Entrar.  Los archivos se cargarán en el almacenamiento de blobs seguro de Azure para el paso siguiente.

   ![Importación no de Office 365: cargar archivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   ![No Office 365 Import-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Si se produce un error en el comando AzCopy proporcionado, consulte [solucionar problemas de azcopy en EDiscovery avanzado](troubleshooting-azcopy.md) .

6. Por último, vuelva al cumplimiento de & de seguridad y haga clic en el botón **siguiente: procesar archivos** .  Se iniciará el procesamiento, la extracción de texto y la indización de los archivos cargados.  Puede realizar un seguimiento del progreso del procesamiento aquí o en la pestaña **trabajos** .  Una vez completados, los nuevos archivos estarán disponibles en el conjunto de revisión.  Una vez que se haya completado el procesamiento, puede descartar el asistente.

   ![Archivos que no son de Office 365 importación-proceso](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

