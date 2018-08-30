---
title: Información general sobre el archivo ilimitado en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Obtenga información acerca de la expansión automática de archivado en Office 365, que proporciona almacenamiento de archivo ilimitado para buzones de Exchange Online.
ms.openlocfilehash: 4fc490871c1a0142ab0f68126cce6f2a51e0f7d0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535894"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a>Información general sobre el archivo ilimitado en Office 365

En Office 365, buzones de archivo proporcionan a los usuarios con el espacio de almacenamiento de buzones de correo adicionales. Después de habilita el buzón de archivo de un usuario, hasta 100 GB de almacenamiento de información adicional está disponible. Cuando se alcanza la cuota de almacenamiento de 100 GB, las organizaciones tenían ponerse en contacto con Microsoft para el espacio de almacenamiento adicional de la solicitud para un buzón de archivo. Ya no es el caso. La nueva característica de archivado ilimitada en Office 365 (llamado ampliación automática archivado) proporciona una cantidad ilimitada de almacenamiento en buzones de archivo. Ahora, cuando se alcanza la cuota de almacenamiento en el buzón de archivo, Office 365 automáticamente aumenta el tamaño de archivo, lo que significa que los usuarios no se ejecutan fuera del espacio de almacenamiento de buzones de correo y los administradores no deben solicitar almacenamiento adicional para buzones de archivo .
  
Para obtener instrucciones paso a paso para activar la ampliación automática de archivado, vea [Habilitar el archivado ilimitado en Office 365](enable-unlimited-archiving.md).
  
> [!NOTE]
> Ampliación automática de archivado también es compatible con los buzones compartidos. Para habilitar el archivo para un buzón compartido, se requiere una licencia de Exchange Online Plan 2 o una licencia de Exchange Online Plan 1 con una licencia de archivado de Exchange Online. 
  
## <a name="how-auto-expanding-archiving-works"></a>¿Cómo ampliación automática funciona el archivado

Como buzón de correo adicional, explicado anteriormente espacio de almacenamiento se crea cuando está habilitado el buzón de archivo de un usuario. Cuando está habilitado la expansión automática de archivado, Office 365 comprueba periódicamente si el tamaño del buzón de archivo. Cuando se obtiene un buzón de archivo próximo a su límite de almacenamiento, Office 365 crea automáticamente espacio de almacenamiento adicionales para el archivo. Si el usuario se ejecuta fuera de este espacio de almacenamiento adicional, Office 365 agrega más espacio de almacenamiento para el archivo del usuario. Este proceso se realiza automáticamente, lo que significa que los administradores no deben solicitar el almacenamiento de archivos adicionales o administrar el archivado de ampliación automática. 
  
Este es un breve resumen del proceso.
  
![Información general del proceso de archiving ampliación automática](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. El archivado está habilitado para un buzón de usuario o un buzón compartido. Se crea un buzón de archivo con 100 GB de espacio de almacenamiento. 
    
2. Un administrador habilita la ampliación automática de archivado para el buzón de correo. A continuación, cuando el buzón de archivo (incluida la carpeta elementos recuperables) alcanza 90 GB, se convierte en un archivo de ampliación automática y Office 365 agrega espacio de almacenamiento para el archivo. Tenga en cuenta que puede tardar hasta 30 días para aprovisionar el espacio de almacenamiento adicional.
    
3. Office 365 agrega automáticamente más espacio de almacenamiento para el archivo cuando sea necesario.
  
## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>¿Qué Obtiene movido al espacio de almacenamiento adicionales de archiving?

Para hacer un uso eficiente de almacenamiento de archivo de crecimiento automático, es posible que se mueven las carpetas. Office 365 determina en qué carpetas se mueven cuando se agrega almacenamiento adicional al archivo. Cuando se mueve una carpeta, se crea automáticamente una subcarpeta bajo la carpeta original en la parte de archivo de la lista de carpetas de Outlook. Esta nueva subcarpeta apunta a los elementos que se han movido. Es la convención de nomenclatura que usa Office 365 para el nombre de la carpeta ** \<nombre de la carpeta\>_yyyy (creadas en mmm dd, aaaa h_mm)**, donde: 
  
- **aaaa** es el año en que se recibieron los mensajes en la carpeta. 
    
- **mmm dd, aaaa h_m** es la fecha y hora en que se creó la subcarpeta por Office 365, en formato UTC, en función de la zona horaria del usuario y la configuración regional en Outlook. 
    
Las capturas de pantalla siguiente muestran una lista de carpetas antes y después de que los mensajes se mueven en un archivo expandido automático.
  
 **Antes de agrega almacenamiento adicional**
  
![Lista de carpetas de buzón de archivo antes de que se ha aprovisionado el archivo de ampliación automática](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 **Después de agrega almacenamiento adicional**
  
![Lista de carpetas de buzón de archivo después de que se ha aprovisionado el archivo de ampliación automática](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Requisitos de Outlook para obtener acceso a los elementos de un archivo expandido automático

Para obtener acceso a los mensajes que se almacenan en un archivo expandido automático, los usuarios tienen que usar uno de los siguientes clientes de Outlook:
  
- Outlook 2016 para Windows
    
- Outlook en la web 
    
- Outlook 2016 para Mac 
    
> [!NOTE]
> Los usuarios de Outlook 2013 pueden sólo los elementos de acceso que se almacenaron originalmente en su buzón de archivo. No podrán para acceder a elementos que se mueven al almacenamiento de archivos adicionales. 
  
A continuación presentamos algunas cosas que debe considerar cuando se utiliza Outlook o Outlook en el web para el acceso a los mensajes almacenados en un archivo expandido automático.
  
- Puede tener acceso a cualquier carpeta en su buzón de archivo, los que se han movido al área de almacenamiento expandido automático incluidos.
    
- Puede buscar los elementos que se han movido a un área de almacenamiento adicional buscando la propia carpeta. Esto significa que tiene que seleccionar la carpeta de archivos en la lista de carpetas para seleccionar la opción de la **Carpeta actual** como el ámbito de búsqueda. De forma similar, si una carpeta en un área de almacenamiento expandido automático contiene las subcarpetas, se debe buscar en cada subcarpeta por separado. 
    
- Los recuentos de elemento en Outlook y recuentos de leído/no leído (en Outlook y Outlook en el web) en un archivo expandido automático es posible que no sean precisos.
    
- Puede eliminar elementos en una subcarpeta que apunta a un área de almacenamiento expandido automático, pero no se puede eliminar la propia carpeta.
    
- No puede usar la característica recuperar elementos eliminados para recuperar un elemento que se ha eliminado de un área de almacenamiento expandido automático.
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a>Ampliación automática de archivado y otras características de cumplimiento de normas de Office 365

En esta sección se explica la funcionalidad entre la ampliación automática de archivado y otros cumplimiento de Office 365 y características de gobierno de datos.
  
- También se busca en la **exhibición de documentos electrónicos** - cuando use una herramienta de exhibición de documentos electrónicos de Office 365, como la búsqueda de contenido o en contexto exhibición de documentos electrónicos, las áreas de almacenamiento de información adicional en un archivo expandido automático.
    
- **Retención** - al poner un buzón de correo en espera mediante herramientas como juicio en Exchange Online o contiene el caso de exhibición de documentos electrónicos y las directivas de retención de la seguridad de Office 365 &amp; centro de cumplimiento, contenido que se encuentra en un archivo expandido automático también es pondrá en espera.
    
- También se eliminará de **mensajería (MRM) de administración de registros** - si usa las directivas de eliminación de MRM en Exchange Online para eliminar permanentemente los elementos del buzón que han expirado, elementos caducados que se encuentra en el archivo expandido automático.
    
- **Importación de servicio** - puede usar el servicio Office 365 importar para importar archivos PST al archivo expandido automático de un usuario. Puede importar hasta 100 GB de datos de los archivos PST al buzón de archivo del usuario. 
