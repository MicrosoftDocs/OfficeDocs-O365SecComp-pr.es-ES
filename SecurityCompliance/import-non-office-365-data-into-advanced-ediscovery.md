---
title: Importar contenido que no sea de Office 365 para el análisis de eDiscovery avanzado
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 5/25/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Cómo a pasos para importar el contenido que no se almacena en O365 en un Azure blob para que se puede analizar con donde
ms.openlocfilehash: ab6c7ac76a159603a34719aa8edb51de3a4fabbb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536860"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a>Importar contenido que no sea de Office 365 para el análisis de eDiscovery avanzado

No todos los documentos que necesita analizar con Office 365 avanzada eDiscovery residirá en Office 365. Con el contenido que no son Office 365 importar característica de exhibición de documentos electrónicos avanzada que puede cargar documentos que no Live Meeting en Office 365 (excepto los archivos PST) a un blob de almacenamiento vinculado, Azure mayúsculas y análisis de ellos con avanzadas exhibición de documentos electrónicos. Este procedimiento muestra cómo incorporar los documentos que no sean Office 365 en la exhibición de documentos electrónicos avanzada para el análisis.
  
> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
> [!NOTE]
> Puede adquirir una suscripción de Office 365 avanzada de exhibición de documentos electrónicos datos almacenamiento complementario para el contenido que no sean Office 365. Esto está disponible exclusivamente para el contenido que va a analizarse con avanzadas exhibición de documentos electrónicos. Siga los pasos descritos en [comprar o editar y complemento de Office 365 para profesionales](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) y el complemento Office 365 avanzada de almacenamiento de exhibición de documentos electrónicos de compra. 
  
## <a name="before-you-begin"></a>Antes de empezar

Uso de la característica de carga no Office 365 tal como se describe en este procedimiento requiere que tenga:
  
- Un equipo con Office 365 E3 con complemento de cumplimiento avanzadas o suscripción E5
    
- Todos los Custodios cuyo contenido que no sean Office 365 se cargará deben tener E3 con complemento de cumplimiento avanzadas o licencias E5
    
- Un caso de exhibición de documentos electrónicos existentes
    
- Todos los archivos para cargar se recopilan en carpetas donde hay una carpeta por custodia y es el nombre de las carpetas en este formato *alias@domainname* . El *alias@domainname* debe ser dominio y alias de los usuarios de Office 365. Puede recopilar todas las carpetas de *alias@domainname* en una carpeta raíz. La carpeta raíz sólo puede contener las carpetas *alias@domainname* , no debe haber ningún archivos separados en la carpeta raíz 
    
- Una cuenta que sea una exhibición de documentos electrónicos Manager o la exhibición de documentos electrónicos administrador
    
- [Herramientas de almacenamiento de información de Microsoft Azure](https://aka.ms/downloadazcopy) instalado en un equipo que tenga acceso a la estructura de la carpeta de contenido que no sean Office 365. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Cargar contenido que no sean Office 365 en la exhibición de documentos electrónicos avanzada

1. Como una exhibición de documentos electrónicos Manager o la exhibición de documentos electrónicos administrador, abra la **exhibición de documentos electrónicos**y abrir el caso de que los datos que no sean Office 365 se cargará en. Si necesita crear un caso, vea [administrar casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](manage-ediscovery-cases.md)
    
2. Haga clic en **cambiar para exhibición de documentos electrónicos avanzada**
    
3. En **tipo de origen** , seleccione **datos no Office 365**.
    
4. Haga clic en **Agregar contenedor**. Nombre del contenedor y agregar una descripción.
    
5. Seleccione el contenedor recién agregado en la lista de contenedor y copie la dirección URL que aparece en el panel de detalles del contenedor y, a continuación, cierre el panel
    
6. Abra un símbolo del sistema como administrador y cambie el directorio a la carpeta donde ha instalado el AzCopy..
    
7. Construir la línea de comandos AzCopy para cargar los archivos como este:
    
    ¿AzCopy /Source: " *ruta de acceso completa a la carpeta raíz en el equipo local* " / dest: " *dirección URL de contenedor hasta, pero sin incluir el?* " /DestSAS: " *resto de la dirección url de contenedor de la? al final* "/ S. 
    
    Por ejemplo, con estos valores: 
    
  - carpeta raíz - C:\Collected datos 
    
  - dirección url de contenedor - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp; sr = c&amp;si = NonOfficeData15 %7 C 0&amp;sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA % 3D
    
    la sintaxis de línea de comandos de AzCopy sería el siguiente:
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    Para obtener más información sobre Azcopy sintaxis, consulte [transferir datos con el AzCopy en Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) . 
    
    > [!IMPORTANT]
    > Debe haber una carpeta raíz por usuario y el nombre de la carpeta debe tener el formato *alias@domainname* . 
  
8. Una vez han terminado las carpetas cargar, volver a la exhibición de documentos electrónicos avanzada. El contenido de las carpetas que ha cargado ahora está listo para ser procesado en la exhibición de documentos electrónicos avanzada. Seleccione el contenedor y haga clic en el botón de proceso. Para obtener más detalles sobre la exhibición de documentos electrónicos avanzada vea procesamiento, [ejecute el módulo de proceso y carga de datos en la exhibición de documentos electrónicos avanzada de Office 365](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
    
    > [!IMPORTANT]
    > Una vez que el contenedor se procesa correctamente en la exhibición de documentos electrónicos avanzada, ya no podrá agregar nuevo contenido al almacenamiento SAS en Azure. Si recopilar contenido adicional y que desee agregar el caso para el análisis de exhibición de documentos electrónicos avanzada, debe crear un nuevo contenedor de **datos que no son de Office 365** y repita este procedimiento. 
  
    > [!NOTE]
    > Si el contenedor *no procesa correctamente debido a problemas de nomenclatura de carpeta* y, a continuación, solucionar los problemas, debe seguir crear un nuevo contenedor y volver a conectar y cargar nuevo mediante los procedimientos de este artículo. 
  

