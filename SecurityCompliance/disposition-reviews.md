---
title: Introducción a las revisiones de disposición
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d0c6095b-bfee-4906-a2c7-89c2d7f411c1
description: Cuando se crea una etiqueta que conserva el contenido en Office 365, se puede optar por desencadenar una revisión de disposición al final del período de retención.
ms.openlocfilehash: 0948d61131595d4111f656c385c58258c5cce99c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215010"
---
# <a name="overview-of-disposition-reviews"></a>Introducción a las revisiones de disposición

Cuando el contenido alcanza el final de su período de retención, existen varios motivos por los que puede que desee revisar el contenido para decidir si se puede eliminar de forma segura ("eliminado"). Por ejemplo, es posible que deba:
  
- Suspender la eliminación ("disposición") del contenido relevante en caso de litigio o una auditoría.
    
- Quitar contenido de la lista de disposición para almacenarla en un archivo, si el contenido tiene un valor histórico o de investigación.
    
- Asigne un período de retención diferente al contenido, si la directiva original era una solución temporal o provisional.
    
- Devolver el contenido a los clientes o transferirlo a otra organización.
    
Cuando se crea una etiqueta que conserva el contenido en Office 365, se puede optar por desencadenar una revisión de disposición al final del período de retención. En una revisión de disposición:
  
- Las personas que elija reciben una notificación por correo electrónico de que tienen contenido que revisar. Estos revisores pueden ser usuarios individuales, grupos de seguridad o de distribución o grupos de Office 365. Tenga en cuenta que las notificaciones se envían cada semana.
    
- Los revisores van a la página de **disposición** en el &amp; centro de seguridad y cumplimiento para revisar el contenido. 
    
- Para cada documento, el revisor puede:
    
  - Aplique una etiqueta diferente.
    
  - Ampliar su período de retención.
    
  - Eliminarlo de forma permanente.
    
- Los revisores pueden ver las disposiciones pendientes o históricas y exportar dicha lista como un archivo. csv.
    
Tenga en cuenta que las revisiones de disposición requieren una suscripción a Office 365 Enterprise E5.
  
Una revisión de disposición puede incluir contenido en buzones de Exchange, sitios de SharePoint, cuentas de OneDrive y grupos de Office 365. El contenido que espera una revisión de disposición en esas ubicaciones se elimina solo después de que un revisor elige eliminar el contenido de forma permanente.
  
![Página de disposición](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a>Configuración de la revisión de disposición mediante la creación de una etiqueta

Este es el flujo de trabajo básico para configurar una revisión de disposición. Tenga en cuenta que este flujo muestra una etiqueta que se publica y que un usuario aplica manualmente; como alternativa, se puede aplicar automáticamente una etiqueta que desencadene una revisión de disposición al contenido.
  
![Gráfico que muestra el flujo de trabajo de disposición](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
Una revisión de disposición es una opción cuando se crea una etiqueta en Office 365. Tenga en cuenta que esta opción no está disponible en una directiva de retención, sino solo en una etiqueta con la configuración de retención.
  
Para obtener más información sobre las etiquetas, vea [Información general sobre etiquetas](labels.md).
  
![Configuración de retención de una etiqueta](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a>Eliminación de contenido

Cuando se notifica a un revisor por correo electrónico que el contenido está listo para su revisión, puede ir a la página de **disposición** en &amp; el centro de seguridad y cumplimiento y seleccionar uno o más elementos. A continuación, el revisor puede: 
  
- Aplique una etiqueta diferente.
    
- Ampliar el período de retención.
    
- Eliminar permanentemente el elemento.
    
Un revisor puede usar el vínculo para ver el documento en su ubicación original, si el revisor tiene permisos para dicha ubicación. Durante una revisión de disposición, el contenido nunca se mueve desde su ubicación original, y nunca se elimina hasta que el revisor elige hacerlo.
  
Tenga en cuenta que las notificaciones por correo electrónico se envían de forma automática a los revisores cada semana. Por lo tanto, cuando el contenido alcanza el final de su período de retención, los revisores pueden tardar hasta siete días en recibir la notificación por correo electrónico de que el contenido espera la disposición.
  
Además, tenga en cuenta que se auditan todas las acciones de disposición. Para garantizar esto, debe activar la auditoría al menos un día antes de la primera acción de disposición (para obtener más información, vea [Buscar en el registro de auditoría del centro de &amp; seguridad y cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md)). 
  
![Opciones de disposición para un documento](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a>Permisos para disposición

Para obtener acceso a la página de **disposición** , los revisores deben ser miembros de la función de **Administración de disposición** y el rol **registros de auditoría con permiso de vista** . Se recomienda crear un nuevo grupo de roles denominado revisores de disposición, agregar estos dos roles a ese grupo de roles y, a continuación, agregar miembros al grupo de roles. 
  
Para obtener más información, vea [conceder acceso a los usuarios al &amp; centro de seguridad y cumplimiento de Office 365](grant-access-to-the-security-and-compliance-center.md)
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>Cuánto tiempo se eliminará permanentemente el contenido desechado

El contenido que espera una revisión de disposición se elimina solo después de que un revisor elige eliminar el contenido de forma permanente. Cuando el revisor elige esta opción, el contenido en el sitio de SharePoint o la cuenta de OneDrive pasa a ser elegible para el proceso de limpieza estándar descrito en esta sección: [Cómo funciona una directiva de retención con el contenido en su lugar](retention-policies.md#how-a-retention-policy-works-with-content-in-place).
  
Esto significa que:
  
- El contenido de una biblioteca de documentos se mueve a la papelera de reciclaje de primera etapa **en un plazo de 7 días** después de la disposición y, a continuación, se elimina de forma permanente **93 días** después de eso. La papelera de reciclaje no está indizada por búsqueda y, por lo tanto, su contenido no está disponible para la conservación de la exhibición de documentos electrónicos. 
    
- El contenido de la biblioteca de conservación de contenido se eliminará permanentemente **en 7 días después** de la disposición. 
    
## <a name="view-pending-and-completed-dispositions"></a>Ver las disposiciones pendientes y completadas

En la página de **disposición** del centro &amp; de seguridad y cumplimiento, puede ver las disposiciones pendientes y completadas: 
  
- Las desposiciones **pendientes** han llegado al final de su período de retención y requieren una revisión de disposición. Después de revisar cada elemento, decida si desea aplicar una etiqueta distinta, ampliar su período de retención o eliminarlo de forma permanente. 
    
- **** Las desposiciones completadas se aprobaron para su eliminación durante una revisión de disposición y ahora están en proceso de eliminación permanente. Los elementos a los que se ha aplicado una etiqueta diferente o cuyo período de retención se ha ampliado como parte de una revisión no aparecerán aquí. 
    
### <a name="filter-the-disposition-views"></a>Filtrar las vistas de disposición

Puede filtrar estas vistas por etiqueta o intervalo de tiempo. Para las disposiciones pendientes, el intervalo de tiempo se basa en la fecha de expiración. Para las disposiciones históricas, el intervalo de tiempo se basa en la fecha de eliminación.
  
![Opciones de filtro en la página de disposición](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a>Exportar los elementos de disposición

Además, puede exportar los elementos en cualquiera de las vistas como un archivo. csv que se puede abrir en Excel.
  
![Datos de disposición exPortados en Excel](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

