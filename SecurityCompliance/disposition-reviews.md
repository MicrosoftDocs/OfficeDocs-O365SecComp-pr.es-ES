---
title: Introducción a las revisiones de disposición
ms.author: stephow
author: stephow-MSFT
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
ms.assetid: d0c6095b-bfee-4906-a2c7-89c2d7f411c1
description: Cuando se crea una etiqueta que se conserva el contenido en Office 365, puede desencadenar una revisión de disposición al final del período de retención.
ms.openlocfilehash: c0a2933f597c9b314ac4ce2e72de9619fac90082
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013724"
---
# <a name="overview-of-disposition-reviews"></a>Introducción a las revisiones de disposición

Cuando el contenido llega al final de su período de retención, existen varias razones por qué es posible que desee revisar dicho contenido para decidir si se puede eliminar sin ningún riesgo ("eliminado"). Por ejemplo, es posible que necesite:
  
- Suspender la eliminación ("disposición") de contenido relevante en caso de litigio o una auditoría.
    
- Quitar el contenido de la lista de disposición para almacenar en un archivo, si dicho contenido tiene investigación o valor histórico.
    
- Asignar un período de retención diferente para el contenido, si la directiva original era una solución temporal o provisional.
    
- Devolver el contenido a los clientes o transferir a otra organización.
    
Cuando se crea una etiqueta que se conserva el contenido en Office 365, puede desencadenar una revisión de disposición al final del período de retención. En una revisión de disposición:
  
- Las personas que elija reciben una notificación de correo electrónico que tienen contenido para revisar. Estos revisores pueden ser usuarios individuales, distribución o grupos de seguridad o grupos de Office 365. Tenga en cuenta que las notificaciones se envían de forma semanal.
    
- Los revisores vaya a la página de **disposición** en la seguridad &amp; centro de cumplimiento para revisar el contenido. 
    
- Para cada documento, el revisor puede:
    
  - Aplicar una etiqueta diferente.
    
  - Ampliar su período de retención.
    
  - Eliminarlo de forma permanente.
    
- Los revisores pueden ver disposiciones pendientes o históricas y exportar esa lista como un archivo .csv.
    
Tenga en cuenta que disposición revisiones requieren una suscripción a Office 365 Enterprise E5.
  
Una revisión de disposición puede incluir contenido en los buzones de Exchange, los sitios de SharePoint, OneDrive cuentas y grupos de Office 365. En espera de una revisión de disposición en esas ubicaciones de contenido se elimina después de que un revisor elige eliminar permanentemente el contenido.
  
![Página de disposición](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a>Configuración de la revisión de disposición mediante la creación de una etiqueta

Este es el flujo de trabajo básico para la configuración de una revisión de disposición. Tenga en cuenta que este flujo de muestra una etiqueta que se va a publicar y, a continuación, se aplica manualmente por un usuario; como alternativa, una etiqueta que desencadena una revisión de disposición puede ser automático aplicada al contenido.
  
![Gráfico que muestra el flujo del funcionamiento de disposición](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
Una revisión de disposición es una opción cuando se crea una etiqueta en Office 365. Tenga en cuenta que esta opción no está disponible en una directiva de retención, pero solo en una etiqueta con la configuración de retención.
  
Para obtener más información acerca de las etiquetas, vea [información general de las etiquetas](labels.md).
  
![Configuración de retención de una etiqueta](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a>Eliminación de contenido

Cuando un revisor recibe una notificación por correo electrónico que el contenido está listo para revisar, pueden ir a la página de **disposición** en la seguridad &amp; centro de cumplimiento y seleccionados uno o varios elementos. El revisor puede, a continuación: 
  
- Aplicar una etiqueta diferente.
    
- Ampliar el período de retención.
    
- Eliminar permanentemente el elemento.
    
Un revisor puede usar el vínculo para ver el documento en su ubicación original, si el revisor tiene permisos para esa ubicación. Durante una revisión de disposición, el contenido nunca se mueve desde su ubicación original y no se eliminen nunca hasta que el revisor elige hacerlo.
  
Tenga en cuenta que las notificaciones de correo electrónico se envían automáticamente a los revisores de forma semanal. Por lo tanto, cuando el contenido llega al final de su período de retención, puede tardar hasta siete días para los revisores reciben la notificación de correo electrónico que el contenido está esperando su disposición.
  
Tenga en cuenta también que todas las acciones de disposición se auditan. Para asegurarse de esto, debe activar la auditoría de al menos un día antes de la primera acción de disposición - para obtener más información, vea [Buscar en el registro de auditoría de la seguridad de Office 365 &amp; centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md). 
  
![Opciones de eliminación de un documento](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a>Permisos para la disposición

Para obtener acceso a la página de **disposición** , los revisores deben ser miembros de la **Administración de la eliminación** y el rol de **Los registros de auditoría con permiso de vista** . Se recomienda crear un nuevo grupo de rol denominado revisores de disposición, adición de estas dos funciones a ese grupo de roles y, a continuación, agregar miembros al grupo de funciones. 
  
Para obtener más información, vea [dar a los usuarios acceso a la seguridad de Office 365 &amp; centro de cumplimiento](grant-access-to-the-security-and-compliance-center.md)
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>¿Cuánto tiempo hasta que el contenido eliminado se elimina de manera permanente

En espera de una revisión de disposición de contenido se elimina después de que un revisor elige eliminar permanentemente el contenido. Cuando el revisor elige esta opción, el contenido en el sitio de SharePoint o la cuenta de OneDrive, pasa a ser candidato para el proceso de limpieza estándar que se describen en esta sección: [funcionamiento con contenido en lugar de una directiva de retención](retention-policies.md#how-a-retention-policy-works-with-content-in-place).
  
Esto significa:
  
- El contenido en una biblioteca de documentos estará mueve a la primera etapa Papelera de reciclaje **dentro de 7 días** de disposición y, a continuación, elimina permanentemente **93 días** después de que. La Papelera de reciclaje no se indiza por la búsqueda y, por tanto, su contenido no está disponible para una exhibición de documentos electrónicos. 
    
- El contenido de la suspensión de conservación biblioteca quedará permanentemente eliminado **dentro de 7 días** de disposición. 
    
## <a name="view-pending-and-completed-dispositions"></a>Ver pendientes y disposiciones completados

En la página de **eliminación** de la seguridad &amp; centro de cumplimiento, puede ver disposiciones pendientes y completadas: 
  
- Disposiciones **pendiente** han alcanzado el final de su período de retención y requieren una revisión de disposición. Después de revisar cada elemento, decidir si desea aplicar una etiqueta diferente a ella, ampliar su período de retención o eliminarlo de forma permanente. 
    
- Disposiciones **completado** se han aprobado para su eliminación durante una revisión de disposición y ahora están en el proceso que se va a eliminar de forma permanente. Elementos que han tenido una etiqueta diferente aplicado o su período de retención extendido como parte de una revisión no aparecerá aquí. 
    
### <a name="filter-the-disposition-views"></a>Filtrar las vistas de disposición

Puede filtrar estas vistas por intervalo de tiempo o de etiqueta. Para pendientes disposiciones, el intervalo de tiempo se basa en la fecha de caducidad. Para disposiciones históricas, el intervalo de tiempo se basa en la fecha de eliminación.
  
![Opciones de filtro en la página de disposición](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a>Exportar los elementos de disposición

Además, puede exportar los elementos en la vista como un archivo .csv que se puede abrir en Excel.
  
![Datos de disposición exportado en Excel](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

