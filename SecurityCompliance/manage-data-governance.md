---
title: Administrar el control de datos en Office 365
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 5/9/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 48064107-fed2-4db0-9e5c-aa5ddd5ccb09
description: Gobierno de datos es todos los detalles sobre mantener los datos de alrededor de cuando lo necesite y obtención de suprimirlo cuando no lo hace. Con el control de datos en Office 365, puede administrar el ciclo de vida de contenido completo, de importación y almacenamiento de datos al principio, a la creación de directivas que conservarán y, a continuación, se eliminación permanentemente el contenido al final.
ms.openlocfilehash: ca3443c3b90a067bf171ddf89be604d262a7b9a4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536714"
---
# <a name="manage-data-governance-in-office-365"></a>Administrar el control de datos en Office 365

Gobierno de datos es todos los detalles sobre mantener los datos de alrededor de cuando lo necesite y obtención de suprimirlo cuando no lo hace. Con el control de datos en Office 365, puede administrar el ciclo de vida de contenido completo, de importación y almacenamiento de datos al principio, a la creación de directivas que conservarán y, a continuación, se eliminación permanentemente el contenido al final.
  
## <a name="import"></a>Importar

Algunos de los datos pueden almacenarse en lugares fuera de la nube, al igual que los servidores locales o en aplicaciones de terceros. El servicio de importación facilita Traer su mensajería, SharePoint y OneDrive para los datos profesionales en Office 365, ya sea por cargar directamente a través de la red o de envío de una unidad cifrada para nosotros. También puede usar la característica de importación inteligente en el servicio de importación para filtrar los elementos en los archivos PST que realmente obtengan importa a los buzones de correo de destino. 
  
- [Información general de importación de archivos PST en Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)
    
- [Usar la carga en la red para importar archivos PST en Office 365](use-network-upload-to-import-pst-files.md)
    
- [Usar el envío de unidades para importar los archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- [Use la herramienta de recopilación de PST para buscar, copiar y eliminar los archivos PST en su organización](find-copy-and-delete-pst-files-in-your-organization.md)
    
- [Filtrar datos al importar archivos PST a Office 365](filter-data-when-importing-pst-files.md)
    
- [Cargar contenido local en SharePoint Online con los cmdlets de PowerShell](https://support.office.com/article/555049c6-15ef-45a6-9a1f-a1ef673b867c)
    
## <a name="govern-i-store-data"></a>Controlar los datos del almacén de I:

Después de importar datos, es posible que necesite aumentar la capacidad de almacenamiento. La característica de archivado ilimitada en Office 365 (llamado ampliación automática archivado) proporciona una cantidad ilimitada de almacenamiento en buzones de archivo.
  
- [Habilitar buzones de archivo en la seguridad de Office 365 &amp; centro de cumplimiento](enable-archive-mailboxes.md)

- [Información general sobre el archivo ilimitado en Office 365](unlimited-archiving.md)
    
- [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md)
    

    
## <a name="govern-ii-create-policies-and-labels-to-retain-content"></a>Controlar II: Crear directivas y etiquetas para conservar el contenido

Una directiva de retención le ayudará a cumplir de forma proactiva con las normativas del sector y políticas internas asegurándose de que mantenga siempre que, pero ya no es necesario que el contenido. Una sola directiva de retención puede cubrir toda la organización. Además, puede utilizar etiquetas para implementar un plan de archivos mediante la clasificación de datos en toda la organización de gobierno y, a continuación, aplicar reglas de retención basadas en dicha clasificación.
  
- [Introducción a las directivas de retención](retention-policies.md)
    
- [Introducción a las etiquetas](labels.md)
    
- [Masiva creación y publicación de etiquetas mediante el uso de PowerShell](https://support.office.com/article/8986701b-ffa1-46ec-8fd0-8f7e81d5b25f.aspx)
    
- [Introducción a las revisiones de disposición](disposition-reviews.md)
    
- [Introducción a la retención basada en eventos](event-driven-retention.md)
    
## <a name="govern-iii-retain-the-email-of-former-employees"></a>Controlar III: Conservar el correo electrónico de antiguos empleados

Cuando una persona abandona la organización, puede conservar su correo electrónico mediante la creación de un buzón de correo inactivo. Un buzón de correo se convierte en inactivo cuando un juicio, directiva de retención de Office 365, o se le aplica otro tipo de espera y, a continuación, se elimina la cuenta de usuario de Office 365 correspondiente. Se conservan los elementos de un buzón inactivo para la duración de la directiva de retención o suspensión que se realizó en el buzón de correo antes de que se ha realizado como inactiva.
  
- [Información general de buzones inactivos en Office 365](inactive-mailboxes-in-office-365.md)
    
- [Crear y administrar buzones inactivos en Office 365](create-and-manage-inactive-mailboxes.md)

- [Cambiar la duración de retención para un buzón inactivo en Office 365](change-the-hold-duration-for-an-inactive-mailbox.md)
  
- [Recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md)
 
- [Restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md)

- [Eliminar un buzón inactivo en Office 365](delete-an-inactive-mailbox.md)

## <a name="monitor"></a>Supervisar

Supervisión le permite definir directivas que capturan correo electrónico y las comunicaciones 3rd terceros en su organización, por lo que se puede examinar por revisores internos o externos. Los revisores, a continuación, pueden clasificar estos communications, asegúrese de que son compatibles con las directivas de su organización y pasar material dudoso si es necesario.
  
También puede usar los informes de gobierno de datos y el Explorador de actividad de etiqueta para supervisar que las etiquetas se aplican a contenido según lo previsto.
  
- [Configurar directivas de supervisión para su organización](configure-supervision-policies.md)
    
- [Informes de supervisión](supervision-reports.md)
    
- [Ver la actividad de etiquetas de documentos](view-label-activity-for-documents.md)
    
- [Ver los informes de gobierno de datos](view-the-data-governance-reports.md)
    
## <a name="more-information"></a>Más información

- [Ver vídeos del equipo de gobierno de datos de Microsoft](https://go.microsoft.com/fwlink/?linkid=867039)
    
- [Vea una visión general de gobierno de datos en Office 365](https://go.microsoft.com/fwlink/?linkid=852644)
    
- [Seguridad de Office 365 &amp; cmdlets de centro de cumplimiento](https://go.microsoft.com/fwlink/?linkid=852310)
    

