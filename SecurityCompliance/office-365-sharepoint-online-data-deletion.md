---
title: Eliminación de datos en línea de SharePoint de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Una explicación de eliminación de datos en SharePoint Online.
ms.openlocfilehash: 8a84859ce170a4c3ca713c751aef2b6d5b911c55
ms.sourcegitcommit: 29ba4c36af8e90ddc8d885863ef25bac2cffbe94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2018
ms.locfileid: "27411166"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a>Eliminación de datos en línea de SharePoint en Office 365

SharePoint Online almacena objetos como abstracta código dentro de las bases de datos de aplicación. Cuando un usuario carga un archivo en SharePoint Online, ese archivo se desmontar y traducir a código de la aplicación y se almacena en varias tablas a través de varias bases de datos. En SharePoint Online, todo el contenido que un cliente carga se divide en fragmentos, cifrados (potencialmente con varias claves de AES de 256 bits) y distribuido en el centro de datos. Para obtener información específica acerca del proceso de fragmentación y el cifrado, vea [cifrado en la nube de Microsoft](office-365-encryption-in-the-microsoft-cloud-overview.md). 

En SharePoint Online, los elementos se conservan para 93 días desde el momento en que eliminarlos de su ubicación original. Permanecer en la Papelera de reciclaje del sitio todo el tiempo, a menos que alguien elimina ellos desde allí o vacía la Papelera de reciclaje. En ese caso, los elementos se vaya a la colección de sitios Papelera de reciclaje, donde permanecen para el resto de los días 93. Para obtener información acerca de cómo restaurar los elementos eliminados, vea [restaurar los elementos en la Papelera de reciclaje de un sitio de SharePoint](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) y [Restaurar elementos eliminados de la Papelera de reciclaje de la colección de sitios](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). El tiempo de retención de la Papelera de reciclaje no es configurable en SharePoint Online.

Cuando se elimina una colección de sitios, también está eliminando la jerarquía de sitios en la colección y todo el contenido dentro de ellos:
- Documentos y bibliotecas de documentos
- Listas y datos de lista
- Opciones de configuración de sitio
- Información de roles y seguridad que está relacionada con el sitio o sus subsitios
- Subsitios de la información de sitio Web, su contenido y el usuario de nivel superior

Si accidentalmente elimina una colección de sitios, se puede restaurar de forma global o SharePoint admin con el centro de administración de SharePoint. 

Eliminación de disco duro se produce cuando un usuario purga los elementos eliminados de la Papelera de reciclaje de la colección de sitios cuando expiren los períodos de retención y copia de seguridad, o cuando un administrador elimina de forma permanente una colección de sitios mediante el [cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). Cuando se elimina un usuario de disco duro (elimina de forma permanente o depura) también se eliminan contenido de SharePoint Online, todas las claves de cifrado para los fragmentos eliminados. Los bloques en los discos que anteriormente se almacenan los fragmentos eliminados se marcan como no usado y están disponible para volver a usar.
