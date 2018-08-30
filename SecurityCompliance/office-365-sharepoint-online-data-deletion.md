---
title: Eliminación de datos en línea de SharePoint de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Una explicación de eliminación de datos en SharePoint Online.
ms.openlocfilehash: c281f6de9cd9e4978ac4a6997333d71d8835420f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535793"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a>Eliminación de datos en línea de SharePoint en Office 365

SharePoint Online almacena objetos como abstracta código dentro de las bases de datos de aplicación. Cuando un usuario carga un archivo en SharePoint Online, ese archivo se desmontar y traducir a código de la aplicación y se almacena en varias tablas a través de varias bases de datos. En SharePoint Online, todo el contenido que un cliente carga se divide en fragmentos, cifrados (potencialmente con varias claves de AES de 256 bits) y distribuido en el centro de datos. Para obtener información específica acerca del proceso de fragmentación y el cifrado, vea [cifrado en la nube de Microsoft](office-365-encryption-in-the-microsoft-cloud-overview.md). Servicios de protección de datos se proporcionan para evitar la pérdida de datos de SharePoint Online. Específicamente, las copias de seguridad se realiza cada 12 horas y conservar durante 14 días.

Cuando se elimina el contenido de un sitio de SharePoint Online, no se elimina inmediatamente. Se envía a una Papelera de reciclaje de sitio, donde se puede restaurar, si es necesario. (Vea [Restaurar elementos eliminados de la Papelera de reciclaje de la colección de sitios](https://support.office.com/article/Restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b) para los pasos de restauración). El valor predeterminado de tiempo de retención de Papelera de reciclaje del sitio es de aproximadamente 90 días. Si se elimina el contenido de una Papelera de reciclaje del sitio, se envía a la Papelera de reciclaje de colección de sitios, que tiene un tiempo de retención de 30 días. El período de tiempo para mantener las cosas en la Papelera de reciclaje se puede configurar un administrador, pero en ausencia de, el período de retención predeterminado es aproximadamente 90 días. El almacenamiento de Papelera de reciclaje de sitio cuenta frente a la cuota de almacenamiento de colección de sitios y el [Umbral de vista de lista](https://support.office.com/article/List-View-Threshold-b8588dae-9387-48c2-9248-c24122f07c59).

Cuando se elimina una colección de sitios, también está eliminando la jerarquía de sitios de la colección, incluida toda la información de usuario y de contenido:
- Documentos y bibliotecas de documentos
- Listas y datos de lista
- Opciones de configuración de sitio
- Información de roles y seguridad que está relacionada con el sitio o sus subsitios
- Subsitios de la información de sitio Web, su contenido y el usuario de nivel superior

Antes de eliminar una colección de sitios, le recomendamos que revise la descripción del servicio SharePoint Online para el plan, que describe la programación de copia de seguridad de datos mantenida por Microsoft para sitios de SharePoint Online. También tenga en cuenta que pueden restauraciones de las copias de seguridad son solo para las colecciones de sitios o subsitios, no para los archivos, listas o bibliotecas. Si necesita recuperarlos, use la Papelera de reciclaje.

Si accidentalmente elimina una colección de sitios, se puede restaurar desde la Papelera de reciclaje de la colección de sitios por un administrador de colección de sitios dentro de 30 días. Si necesita una colección de sitios Restaurar después de 30 días, se puede restaurar mediante Microsoft plazo de 14 días desde la caducidad de 30 días por ponerse en contacto con Microsoft a través de una solicitud de servicio.

Eliminación de disco duro se produce cuando un usuario purga los elementos eliminados de la Papelera de reciclaje del sitio, y la retención y períodos de copia de seguridad expiren, o cuando un administrador elimina de forma permanente una colección de sitios mediante el [cmdlet Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). Cuando se elimina un usuario de disco duro (elimina de forma permanente o depura) también se eliminan contenido de SharePoint Online, todas las claves de cifrado para los fragmentos eliminados. Los bloques en los discos que anteriormente se almacenan los fragmentos eliminados se marcan como no usado y están disponible para volver a usar.
