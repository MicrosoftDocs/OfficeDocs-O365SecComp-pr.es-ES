---
title: Cargar datos que no son de Office 365 a un conjunto de revisión
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Importar datos que no son de Office 365 a un conjunto de revisión en un caso de exhibición avanzada de documentos electrónicos.
ms.openlocfilehash: d7609c774e7c8a42e24b22a87fbed271a12a97f5
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048112"
---
# <a name="load-non-office-365-data-into-a-review-set"></a>Cargar datos que no son de Office 365 a un conjunto de revisión

No todos los documentos que debe analizar en la exhibición avanzada de documentos electrónicos se encuentran en Office 365. Con la característica de importación de datos no de Office 365 en eDiscovery avanzado, puede cargar documentos que no se encuentran en Office 365 a un conjunto de revisión. En este artículo se muestra cómo llevar los documentos que no son de Office 365 a eDiscovery avanzado para su análisis.

>[!Note]
>EDiscovery avanzado requiere una suscripción a Microsoft 365 o a Office 365 E5 para su organización o una suscripción a E3 con la suscripción de complemento de cumplimiento avanzado. Si no tiene ese plan y desea probar la exhibición avanzada de documentos electrónicos, puede registrarse para obtener una versión de prueba de Office 365 Enterprise E5.

## <a name="before-you-begin"></a>Antes de empezar

El uso de la característica de carga que no es de Office 365 que se describe en este artículo requiere lo siguiente:

- Todos los custodios que desee asociar a contenido que no pertenece a Office 365 deben tener asignada una licencia E5 o una licencia E3 con una licencia de complemento de cumplimiento avanzada.

- Un caso de exhibición avanzada de documentos electrónicos existente.

- Los custodios deben agregarse al caso antes de que pueda cargar y asociar los datos que no son de Office 365.

- Los datos que no son de Office 365 deben ser un tipo de archivo compatible con la exhibición avanzada de documentos electrónicos. Para obtener más información, consulte [tipos de archivo admitidos en EDiscovery avanzado](supported-filetypes-ediscovery20.md).

- Todos los archivos que se cargan en un conjunto de revisión deben estar ubicados en carpetas, donde cada carpeta está asociada a un custodio específico. Los nombres de estas carpetas deben usar el siguiente formato de nombre: *alias @ domainname*. El alias @ domainname debe ser el alias y el dominio de Office 365 del usuario. Puede recopilar todas las carpetas alias @ domainname en una carpeta raíz. La carpeta raíz solo puede contener las carpetas alias @ domainname. No se admiten los archivos separados en la carpeta raíz.

   La estructura de carpetas para los datos que no son de Office 365 que desea cargar sería similar al ejemplo siguiente:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Donde abraham.mcmahon@contoso.com, jewell.gordon@contoso.com y staci.gonzalez@contoso.com son las direcciones SMTP de los custodios en el caso.

   ![Estructura de carpetas de carga de datos no de Office 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Una cuenta asignada al grupo de roles eDiscovery Manager (y agregada como administrador de exhibición de documentos electrónicos).

- La herramienta AzCopy v 8.1 instalada en un equipo que tiene acceso a la estructura de carpetas de contenido no perteneciente a Office 365. Para instalar AzCopy, consulte [transferir datos con azcopy v 8.1 en Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy). Asegúrese de instalar AzCopy en la ubicación predeterminada, que es **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**. Debe usar AzCopy v 8.1. Es posible que otras versiones de AzCopy no funcionen al cargar datos que no son de Office 365 en eDiscovery avanzado.


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Cargar contenido no de Office 365 en eDiscovery avanzado

1. Como administrador de eDiscovery o administrador de exhibición de documentos electrónicos, abra eDiscovery avanzado y, a continuación, el caso en el que se cargarán los datos que no son de Office 365.  

2. Haga clic en **revisar conjuntos**y, a continuación, seleccione el conjunto de revisiones para cargar los datos que no son de Office 365.  Si no tiene un conjunto de revisión, puede crear uno. 
 
3. En el conjunto de revisiones, haga clic en **administrar conjunto de revisiones**y, a continuación, haga clic en **Ver cargas** en el mosaico de **datos que no son de Office 365** .

4. Haga clic en **cargar archivos** para iniciar el Asistente para importación de datos no perteneciente a Office 365.

   ![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   El primer paso del asistente prepara una ubicación de almacenamiento de Azure segura proporcionada por Microsoft para cargar los archivos en.  Una vez completada la preparación, el botón **cargar archivos** se activa.

   ![Importación no de Office 365: preparar](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. Haga clic en **siguiente: cargar archivos**.

6. En la página **cargar archivos** , haga lo siguiente:

   ![No Office 365 Import: upload files](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. En el cuadro **ruta de acceso a la ubicación de los archivos** , compruebe o escriba la ubicación de la carpeta raíz donde almacenó los datos que no son de Office 365 que desea cargar. Por ejemplo, para la ubicación de los archivos de ejemplo que se muestran en la **sección antes de comenzar**, debe escribir **%USERPROFILE\Downloads\nonO365**. Si se proporciona la ubicación correcta, se asegurará de que el comando AzCopy que se muestra en Box en la ruta se haya actualizado correctamente.

   b. Haga clic en **copiar al** portapapeles para copiar el comando que se muestra en el cuadro.

7. Inicie un símbolo del sistema de Windows, pegue el comando que copió en el paso anterior y, a continuación, presione **entrar** para iniciar el comando AzCopy.  Después de iniciar el comando, los archivos que no son de Office 365 se cargarán en la ubicación de almacenamiento de Azure que se preparó en el paso 4.

   ![Importación no de Office 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Como se indicó anteriormente, debe usar AzCopy v 8.1 para usar correctamente el comando que se proporciona en la página **cargar archivos** . Si el comando AzCopy proporcionado no se produce, consulte [solucionar problemas de azcopy en EDiscovery avanzado](troubleshooting-azcopy.md).

8. Vuelva al centro de cumplimiento de & de seguridad y haga clic en **siguiente: procesar archivos** en el asistente.  Esto inicia el procesamiento, la extracción de texto y la indización de los archivos que no son de Office 365 que se cargaron en la ubicación de almacenamiento de Azure.  

9. Realice un seguimiento del progreso del procesamiento de los archivos que no son de Office 365 en la página **procesar archivos** o en la ficha **trabajos** mediante la visualización de un trabajo denominado **adición de datos que no son de Office 365 a un conjunto de revisión**.  Una vez finalizado el trabajo, los nuevos archivos estarán disponibles en el conjunto de revisión.

   ![Importación no de Office 365: procesar archivos](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. Una vez finalizado el procesamiento, puede cerrar el asistente.