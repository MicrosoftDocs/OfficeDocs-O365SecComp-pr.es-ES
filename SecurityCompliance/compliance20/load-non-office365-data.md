---
title: Cargar datos que no son de Office 365 a un conjunto de trabajo
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 1dad52075303450673e7f48b87e2952e35629a5e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706091"
---
# <a name="load-non-office-365-data-into-a-working-set"></a>Cargar datos que no son de Office 365 a un conjunto de trabajo

No todos los documentos que necesita analizar con Office 365 avanzada eDiscovery residirá en Office 365. Con el contenido que no son Office 365 importar característica de exhibición de documentos electrónicos avanzada que puede cargar documentos que no live en Office 365 en un conjunto de trabajo, por lo que se analiza con avanzadas exhibición de documentos electrónicos. Este procedimiento muestra cómo incorporar los documentos que no sean Office 365 en la exhibición de documentos electrónicos avanzada para el análisis.

>[!Note]
>Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede registrarse para una prueba de Office 365 Enterprise E5.

## <a name="before-you-begin"></a>Antes de empezar
Uso de la característica de carga no Office 365 tal como se describe en este procedimiento requiere que tenga:

- Un Office 365 E3 con complemento de cumplimiento avanzadas o suscripción E5.

- Todos los Custodios cuyo contenido que no sean Office 365 se cargará deben tener E3 con complemento de cumplimiento avanzadas o licencias E5.

- Un caso de exhibición de documentos electrónicos existentes.

- Todos los archivos para cargar se recopilan en carpetas donde hay una carpeta por custodia y es el nombre de las carpetas en este formato *alias@domainname* . El *alias@domainname* debe ser dominio y alias de los usuarios de Office 365. Puede recopilar todas las carpetas de *alias@domainname* en una carpeta raíz. La carpeta raíz sólo puede contener las carpetas *alias@domainname* , no debe haber ningún archivos separados en la carpeta raíz.

- Una cuenta que es un administrador de exhibición de documentos electrónicos o exhibición de documentos electrónicos Administrador Microsoft Azure almacenamiento herramientas instalado en un equipo que tenga acceso a la estructura de la carpeta de contenido que no sean Office 365.

- Instalar AzCopy, que se puede realizar desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Cargar contenido que no sean Office 365 en la exhibición de documentos electrónicos avanzada

1. Como una exhibición de documentos electrónicos Manager o la exhibición de documentos electrónicos administrador, abra la exhibición de documentos electrónicos avanzada, a continuación, en el caso de que los datos que no sean Office 365 se cargará en.  Haga clic en la ficha **conjuntos de trabajo** y, a continuación, seleccione el conjunto de trabajo que desea cargar los datos que no son de Office 365 para.  Si aún no ha creado un conjunto de trabajo, puede hacerlo ahora.  Por último, haga clic en **establece el funcionamiento de administrar** **cargas de vista** en la sección de datos que no son de Office 365

2. Haga clic en el botón **cargar archivos** para iniciar el Asistente para importación de datos que no son de Office 365.

![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. El primer paso en el Asistente para simplemente prepara un blob de Azure seguro para los archivos que se va a cargar.  Una vez que la preparación del es compelted, haga clic en el **siguiente: cargar archivos** botón.

![No son de Office 365-importar: preparar](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. En el paso **cargar archivos** , especifique la **ruta de acceso a la ubicación de archivos**, esto es donde se encuentran los datos no Office 365 que piensa acerca de la importación.  Establecer la ubicación correcta, asegura la AzCopy comando se actualiza correctamente.

> [!NOTE]
> Si no tiene instalado AzCopy, puede hacerlo desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. Copie el comando predefinido, haga clic en el vínculo **Copiar al Portapapeles** . Inicie un símbolo del sistema de windows, pegue el comando y presione ENTRAR.  Los archivos se cargarán en el almacenamiento de blobs de Azure seguro para el paso siguiente.

![Importación de no-Office 365 - cargar archivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Importación de no son de Office 365 - AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. Por último, volver a la & cumplimiento de seguridad y haga clic en el **siguiente: procesar archivos** botón.  Se iniciará el procesamiento, extracción de texto e indización de los archivos cargados.  Puede realizar un seguimiento del progreso de procesamiento aquí o en la ficha **trabajos** .  Una vez completado, los nuevos archivos estará disponibles en el conjunto de trabajo.  Una vez finalizado el procesamiento, puede pasar por alto al asistente.

![Importación de no-Office 365 - proceso de archivos](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

