---
title: Importar contenido no de Office 365 para el análisis avanzado de eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Pasos para importar contenido que no está almacenado en O365 en un BLOB de Azure para que se pueda analizar con AeD
ms.openlocfilehash: 1c971c9f95d03d05db76f80344adeb93b0a72c06
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152692"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a>Importar contenido no de Office 365 para el análisis avanzado de eDiscovery

No todos los documentos que puede que necesite analizar con Office 365 Advanced eDiscovery residirán en Office 365. Con la característica de importación de contenido no de Office 365 en eDiscovery avanzado, puede cargar documentos que no vivan en Office 365 (excepto los archivos PST) en un caso vinculado al BLOB de almacenamiento de Azure y analizarlo con la exhibición avanzada de documentos electrónicos. Este procedimiento muestra cómo llevar los documentos que no son de Office 365 a eDiscovery avanzado para su análisis.
  
> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
> [!NOTE]
> Puede adquirir una suscripción de complemento de almacenamiento de datos de eDiscovery avanzado de Office 365 para el contenido que no es de Office 365. Esto está disponible exclusivamente para el contenido que se va a analizar con la exhibición avanzada de documentos electrónicos. Siga los pasos descritos en [Buy or Edit and Add-in for office 365 for Business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) y compre el complemento de almacenamiento avanzado de exhibición de documentos electrónicos de Office 365. 
  
## <a name="before-you-begin"></a>Antes de empezar

El uso de la característica cargar no de Office 365 tal y como se describe en este procedimiento requiere que tenga:
  
- Un complemento de Office 365 E3 con Advanced Compliance o de la suscripción a E5
    
- Todos los custodios cuyo contenido que no pertenezca a Office 365 se cargarán deben tener E3 con las licencias del complemento de cumplimiento avanzado o E5.
    
- Un caso de eDiscovery existente
    
- Todos los archivos que se van a cargar se recopilan en carpetas en las que hay una carpeta por custodio y el nombre de las carpetas se encuentra en el formato de *alias @ nombredominio* . El *alias @ domainname* debe ser users Office 365 alias y dominio. Puede recopilar todas las carpetas *alias @ domainname* en una carpeta raíz. La carpeta raíz solo puede contener las carpetas *alias @ domainname* , no debe haber archivos sueltos en la carpeta raíz 
    
- Una cuenta que sea administrador de exhibición de documentos electrónicos o administrador de exhibición de documentos electrónicos
    
- [Herramientas de almacenamiento de Microsoft Azure](https://aka.ms/downloadazcopy) instaladas en un equipo que tiene acceso a la estructura de carpetas de contenido no Office 365. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Cargar contenido no de Office 365 en eDiscovery avanzado

1. Como administrador de eDiscovery o administrador de exhibición de documentos electrónicos, Abra **eDiscovery**y abra el caso en el que se cargarán los datos que no son de Office 365. Si necesita crear un caso, consulte [administrar casos de eDiscovery en el centro de seguridad &amp; y cumplimiento de Office 365](manage-ediscovery-cases.md)
    
2. Haga clic en **cambiar a exhibición avanzada de** documentos electrónicos
    
3. En **tipo de origen** , seleccione **datos que no son de Office 365**.
    
4. Haga clic en **Agregar contenedor**. Asigne un nombre al contenedor y agregue una descripción.
    
5. Seleccione el contenedor recién agregado de la lista de contenedores y copie la dirección URL que aparece en el panel de detalles del contenedor y, a continuación, cierre el panel.
    
6. Abra un símbolo del sistema como administrador y cambie el directorio a la carpeta donde está instalado AzCopy.
    
7. Construya la línea de comandos de AzCopy para cargar los archivos de la siguiente manera:
    
    AzCopy/Source: " *ruta de acceso completa a la carpeta raíz en el equipo local* "/dest: " *dirección URL del contenedor hasta el? o sin incluir el?*  "/DestSAS:" *resto de la dirección URL del contenedor del? al final* "/S. 
    
    Por ejemplo, con estos valores: 
    
  - carpeta raíz: datos de C:\Collected 
    
  - Dirección URL del https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&ampcontenedor-; Sr&amp;= c si = NonOfficeData15&amp;% 7C0 SIG = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3D
    
    la sintaxis de la línea de comandos de AzCopy sería:
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    Para obtener más información sobre la sintaxis de Azcopy, consulte [transferir datos con Azcopy en Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) . 
    
    > [!IMPORTANT]
    > Debe haber una carpeta raíz por usuario y el nombre de la carpeta debe tener el formato *alias @ nombreDeDominio* . 
  
8. Una vez que las carpetas terminen de cargarse, vuelva a la exhibición avanzada de documentos electrónicos. El contenido de las carpetas que cargó ya está listo para su procesamiento en eDiscovery avanzado. Seleccione el contenedor y haga clic en el botón procesar. Para obtener más información sobre el procesamiento avanzado de eDiscovery, vea [ejecutar el módulo de proceso y cargar datos en eDiscovery avanzado de Office 365](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
    
    > [!IMPORTANT]
    > Una vez que el contenedor se procesa correctamente en eDiscovery avanzado, ya no podrá agregar nuevo contenido al almacenamiento SAS en Azure. Si recopila contenido adicional y desea agregarlo al análisis de eDiscovery avanzado, debe crear un nuevo contenedor de **datos distinto de Office 365** y repetir este procedimiento. 
  
    > [!NOTE]
    > Si el contenedor *no se procesa correctamente debido a problemas de nombres de carpeta* y, a continuación, soluciona los problemas, deberá crear un nuevo contenedor y volver a conectar y cargar de nuevo con los procedimientos descritos en este artículo. 
  

