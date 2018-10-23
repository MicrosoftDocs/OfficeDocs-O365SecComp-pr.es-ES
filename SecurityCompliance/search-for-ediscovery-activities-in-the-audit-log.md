---
title: Buscar actividades de exhibición de documentos electrónicos en el registro de auditoría de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Obtenga información sobre cómo buscar en el registro de auditoría de Office 365 para eventos que se registran cuando los administradores de cumplimiento realizar tareas de mayúsculas y minúsculas de la búsqueda de contenido y exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: f3d8e49da32de85c127d6bbf28d0b53bd6974c09
ms.sourcegitcommit: 98a418052be88137c06f5c1abe7012359a7e90ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2018
ms.locfileid: "25698036"
---
# <a name="search-for-ediscovery-activities-in-the-office-365-audit-log"></a>Buscar actividades de exhibición de documentos electrónicos en el registro de auditoría de Office 365

Contenido de búsqueda y las actividades relacionadas con la exhibición de documentos electrónicos que se realizan en Office 365 seguridad &amp; centro de cumplimiento o mediante la ejecución de la correspondiente Windows PowerShell cmdlets se registran en el registro de auditoría de Office 365. Se registran eventos cuando los administradores o administradores de cumplimiento (o cualquier usuario que está asignado exhibición de documentos electrónicos permisos) lleva a cabo la siguiente búsqueda de contenido y las tareas relacionadas con la exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento:
  
- Creación y administración de casos de exhibición de documentos electrónicos
    
- Crear, iniciar y edición de las búsquedas de contenido
    
- Realizar acciones de búsqueda de contenido, como obtener una vista previa, los resultados de búsqueda de exportación y al eliminar
    
- Configuración de permisos de filtrado para la búsqueda de contenido
    
- Administración de la función de administrador de exhibición de documentos electrónicos
    
> [!IMPORTANT]
> Las actividades descritas en este artículo son sólo el resultado de tareas de exhibición de documentos electrónicos que se realizan mediante el uso de la seguridad &amp; centro de cumplimiento. tareas de exhibición de documentos electrónicos que se realizaron con la herramienta de exhibición de documentos electrónicos en contexto en Exchange Online o el centro de exhibición de documentos electrónicos en SharePoint Online no se incluyen. 
  
Para obtener más información acerca de cómo buscar el registro de auditoría de Office 365, los permisos que son necesarios y exportar los resultados de búsqueda, vea [Buscar en el registro de auditoría de la seguridad de Office 365 &amp; centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md).
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Cómo buscar y ver las actividades de exhibición de documentos electrónicos

Actualmente, tiene que hacer algunas cosas específicas para ver las actividades de exhibición de documentos electrónicos en el registro de auditoría de Office 365. Aquí es cómo.
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo, haga clic en **búsqueda &amp; investigación**y, a continuación, haga clic en **búsqueda de registro de auditoría**.
    
4. En la lista desplegable de **actividades** , en **las actividades de exhibición de documentos electrónicos**, haga clic en una o más actividades para buscar. O bien, puede hacer clic en **las actividades de exhibición de documentos electrónicos** para buscar todas las actividades relacionadas con la exhibición de documentos electrónicos. 
    
    > [!NOTE]
    > La lista desplegable de actividades también incluye un grupo de actividades denominado **actividades de cmdlet de exhibición de documentos electrónicos** que devolverá registros desde el registro de auditoría de cmdlet. 
  
5.  Seleccione un intervalo de fecha y hora para mostrar eventos de exhibición de documentos electrónicos que se produjeron dentro de ese período. 
    
6. En el cuadro **usuarios** , seleccione uno o varios usuarios para mostrar los resultados de búsqueda para. Deje este cuadro en blanco para devolver las entradas de todos los usuarios. 
    
7. Haga clic en **Buscar** para ejecutar la búsqueda con los criterios de búsqueda. 
    
8. Después de que se muestran los resultados de búsqueda, puede hacer clic en **los resultados de filtro** para filtrar u ordenar los registros resultantes de la actividad. Desafortunadamente, no se puede utilizar el filtrado para excluir explícitamente ciertas actividades. 
    
9. Para ver detalles acerca de una actividad, haga clic en el registro de actividad en la lista de resultados de búsqueda. 
    
    Se muestra un marcha de **Detalles de** página que contiene las propiedades detalladas del registro de eventos. Para mostrar detalles adicionales, haga clic en **obtener más información**. Para obtener una descripción de estas propiedades, vea la sección de [Propiedades detalladas para actividades de exhibición de documentos electrónicos](#detailed-properties-for-ediscovery-activities) . 

  
## <a name="ediscovery-activities"></a>actividades de exhibición de documentos electrónicos

En la siguiente tabla se describe la búsqueda de contenido y las actividades relacionadas con la exhibición de documentos electrónicos que se registran cuando un administrador o un usuario realiza una actividad relacionada con la exhibición de documentos electrónicos mediante el uso de la seguridad &amp; centro de cumplimiento o ejecutando el cmdlet correspondiente en PowerShell remoto que está conectado a la seguridad de su organización &amp; centro de cumplimiento. 
  
> [!NOTE]
> Las actividades de exhibición de documentos electrónicos que se describen en esta sección proporcionan información similar a las actividades de cmdlet de exhibición de documentos electrónicos que se describen en la siguiente sección. Se recomienda que use las actividades de exhibición de documentos electrónicos que se describen en esta sección porque aparecerán en los resultados de búsqueda de registro de auditoría dentro de 30 minutos. Se tardan hasta 24 horas para la exhibición de documentos electrónicos en actividades de cmdlet que aparezca en los resultados de búsqueda de registro de auditoría. 
  
|**Nombre descriptivo**|**Operation**|**Cmdlet correspondiente**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Se ha agregado un miembro a caso de exhibición de documentos electrónicos  <br/> |CaseMemberAdded  <br/> |ComplianceCaseMember agregar  <br/> |Se agregó un usuario como un miembro de un caso de exhibición de documentos electrónicos. Como miembro de un caso, un usuario puede realizar diversas tareas relacionadas con el caso dependiendo de si se les ha asignado los permisos necesarios.  <br/> |
|Búsqueda de contenido modificada  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |Se ha cambiado una búsqueda de contenido existente. Adición o eliminación de ubicaciones de contenido o edición de la consulta de búsqueda, pueden incluir los cambios.  <br/> |
|Pertenencia al administrador de exhibición de documentos electrónicos modificados  <br/> |CaseAdminUpdated  <br/> |Actualización de eDiscoveryCaseAdmin  <br/> |Se ha cambiado la lista de exhibición de documentos electrónicos los administradores de la organización. Esta actividad se registra cuando la lista de exhibición de documentos electrónicos los administradores se ha reemplazado con un grupo de usuarios nuevos. Si se agrega o se quita un único usuario, se registra la operación CaseAdminAdded.  <br/> |
|Caso de exhibición de documentos electrónicos modificados  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |Se ha cambiado un caso de exhibición de documentos electrónicos. Los cambios incluyen cerrar un caso abierto o volver a abrir un caso cerrado.  <br/> |
|Pertenencia a casos de exhibición de documentos electrónicos modificados  <br/> |CaseMemberUpdated  <br/> |Actualización de ComplianceCaseMember  <br/> |Se ha cambiado la lista de pertenencia de un caso de exhibición de documentos electrónicos. Esta actividad se registra cuando todos los miembros se han reemplazado con un grupo de usuarios nuevos. Si se agrega o se quita un miembro único, se registra la operación CaseMemberAdded o CaseMemberRemoved.  <br/> |
|Cambiar el filtro de búsqueda de permisos  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |Se ha cambiado un filtro de búsqueda de permisos.  <br/> |
|Consulta de búsqueda modificada para suspensión casos de exhibición de documentos electrónicos  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |Se ha cambiado una suspensión basada en consultas asociada con un caso de exhibición de documentos electrónicos. Las modificaciones posibles incluyen la edición de la consulta o suspensión de intervalo de fechas para basada en una consulta.  <br/> |
|Descargar elemento de vista previa de la búsqueda de contenido  <br/> |PreviewItemDownloaded  <br/> |N/D  <br/> |Un usuario descarga un elemento en su equipo local (haciendo clic en el vínculo **Descargar elemento original** ) al obtener una vista previa de los resultados de búsqueda.  <br/> |
|Aparece el elemento de la vista previa de la búsqueda de contenido  <br/> |PreviewItemListed  <br/> |N/D  <br/> |Un usuario hace clic en **vista previa de resultados de búsqueda** para mostrar la página de resultados de búsqueda de vista previa, que enumera los elementos hasta 1.000 desde los resultados de una búsqueda de contenido.  <br/> |
|Ve elemento de vista previa de la búsqueda de contenido  <br/> |PreviewItemRendered  <br/> |N/D  <br/> |Un administrador de exhibición de documentos electrónicos ve un elemento haciendo clic en ella durante la vista previa de los resultados de búsqueda.  <br/> |
|Búsqueda de contenido creada  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |Se ha creado una nueva búsqueda de contenido.  <br/> |
|Administrador de exhibición de documentos electrónicos creada  <br/> |CaseAdminAdded  <br/> |EDiscoveryCaseAdmin agregar  <br/> |Se agregó un usuario como un administrador de exhibición de documentos en la organización.  <br/> |
|Caso de exhibición de documentos electrónicos creada  <br/> |CaseAdded  <br/> |Nueva ComplianceCase  <br/> |Se creó un caso de exhibición de documentos electrónicos. Cuando se crea un caso, sólo debe asignarle un nombre. Otras tareas relacionadas con el caso, como agregar a miembros, crear suspensiones y creación de búsquedas de contenido asociadas con el resultado de mayúsculas y minúsculas en eventos adicionales que se está registrando.  <br/> |
|Creado el filtro de búsqueda de permisos  <br/> |SearchPermissionCreated  <br/> |Nueva ComplianceSecurityFilter  <br/> |Se ha creado un filtro de búsqueda de permisos.  <br/> |
|Consulta de búsqueda creada para suspensión casos de exhibición de documentos electrónicos  <br/> |HoldCreated  <br/> |Nueva CaseHoldRule  <br/> |Se ha creado una suspensión basada en consultas asociada con un caso de exhibición de documentos electrónicos.  <br/> |
|Búsqueda de contenido eliminada  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |Se eliminó una búsqueda de contenido existente.  <br/> |
|Administrador de exhibición de documentos electrónicos eliminados  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Un administrador de exhibición de documentos electrónicos se eliminó de la organización.  <br/> |
|Caso de exhibición de documentos electrónicos eliminados  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Se eliminó un caso de exhibición de documentos electrónicos. Tenga en cuenta que cualquier suspensión asociado con el caso debe quitarse antes de que se pueden eliminar las mayúsculas y minúsculas.  <br/> |
|Filtro de permisos de búsqueda eliminados  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |Se eliminó un filtro de búsqueda de permisos.  <br/> |
|Consulta de búsqueda eliminados suspensión casos de exhibición de documentos electrónicos  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Se eliminó una suspensión basada en consultas asociada con un caso de exhibición de documentos electrónicos. Eliminación de la consulta de la suspensión a menudo es el resultado de la eliminación de una suspensión. Cuando se elimina una suspensión o una consulta de suspensión, se liberan las ubicaciones de contenido que estaban en espera.  <br/> |
|Exportación descargado de búsqueda de contenido  <br/> |SearchExportDownloaded  <br/> |N/D  <br/> |Un usuario descarga los resultados de una búsqueda de contenido en su equipo local. Tenga en cuenta que una actividad **iniciado exportar de búsqueda de contenido** debe iniciarse antes de que se pueden descargar los resultados de búsqueda.<br/> |
|La vista previa de los resultados de búsqueda de contenido  <br/> |SearchPreviewed  <br/> |N/D  <br/> |Un usuario obtener vista previa de los resultados de una búsqueda de contenido.  <br/> |
|Purgado de los resultados de búsqueda de contenido  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Un usuario purga los resultados de una búsqueda de contenido mediante la ejecución de la **New-ComplianceSearchAction-purgar** comando.  <br/> |
|Se ha quitado el análisis de búsqueda de contenido  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Una búsqueda de contenido Preparar acción (para preparar los resultados de búsqueda de exhibición de documentos electrónicos avanzada de Office 365) se ha eliminado. Si la acción de preparación fue inferior a dos semanas de antigüedad, los resultados de búsqueda que se han preparado para exhibición de documentos electrónicos avanzada se eliminaron desde el área de almacenamiento de información de Microsoft Azure. Si la acción de preparación fue más de 2 semanas, este evento indica que se ha eliminado únicamente la acción de preparación correspondiente.  <br/> |
|Exportación se ha quitado de la búsqueda de contenido  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de exportación de la búsqueda de contenido. Si la acción de exportación fue menos de dos semanas, se han eliminado los resultados de búsqueda que se han cargado en el área de almacenamiento de información de Microsoft Azure. Si la acción de exportación fue más de 2 semanas, este evento indica que se ha eliminado únicamente la acción de exportación correspondiente.  <br/> |
|Miembro se ha quitado de caso de exhibición de documentos electrónicos  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Se quitó un usuario como un miembro de un caso de exhibición de documentos electrónicos.  <br/> |
|Quita de la vista previa de resultados de búsqueda de contenido  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de vista previa de la búsqueda de contenido.  <br/> |
|Acción que se ha quitado purgar se realiza en búsqueda de contenido  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de purga de búsqueda de contenido.  <br/> |
|Quita el informe de búsqueda  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Una búsqueda de contenido Exportar informe de acción se ha eliminado.  <br/> |
|Iniciado análisis de búsqueda de contenido  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |Los resultados de una búsqueda de contenido se han preparado para el análisis de exhibición de documentos electrónicos avanzada.  <br/> |
|Inicia la búsqueda de contenido  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |Se ha iniciado una búsqueda de contenido. Al crear o cambiar una búsqueda de contenido mediante el uso de la seguridad &amp; GUI del centro de cumplimiento, la búsqueda se inicia automáticamente. Si crear o cambiar una búsqueda mediante el **Nuevo ComplianceSearch** o el cmdlet **Set-ComplianceSearch** , se debe ejecutar el cmdlet **Start-ComplianceSearch** para iniciar la búsqueda.<br/> |
|Exportación de introducción de búsqueda de contenido  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Un usuario exporta los resultados de una búsqueda de contenido.  <br/> |
|Informe de exportación de introducción  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Un usuario exporta un informe de búsqueda de contenido.  <br/> |
|Detiene la búsqueda de contenido  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Un usuario detiene una búsqueda de contenido.  <br/> |
  
## <a name="ediscovery-cmdlet-activities"></a>actividades de cmdlet de exhibición de documentos electrónicos

En la siguiente tabla se enumera los registros de registro de auditoría de cmdlet que se registran cuando un administrador o un usuario realiza una actividad relacionada con la exhibición de documentos electrónicos mediante el uso de la seguridad &amp; centro de cumplimiento o ejecutando el cmdlet correspondiente en PowerShell remoto que del conectado a la seguridad de su organización &amp; centro de cumplimiento. Tenga en cuenta que la información detallada en el registro de auditoría es diferente para las actividades de cmdlet enumeradas en esta tabla y las actividades de exhibición de documentos electrónicos que se describen en la sección anterior. 
  
Como se ha indicado anteriormente, se tardan hasta 24 horas de exhibición de documentos electrónicos actividades de cmdlet que aparezca en los resultados de búsqueda de registro de auditoría.
  
> [!TIP]
> Los cmdlets en la columna de la **operación** en la siguiente tabla se vinculan al tema de Ayuda del cmdlet correspondiente en TechNet. Vaya al tema de ayuda para obtener una descripción de los parámetros disponibles para cada cmdlet de cmdlet. El parámetro y el valor del parámetro que se usaron con un cmdlet se incluyen en la entrada de registro de auditoría para cada actividad de cmdlet de exhibición de documentos electrónicos que se registra. 
  
|**Nombre descriptivo**|**Operación (cmdlet)**|**Descripción**|
|:-----|:-----|:-----|
|Suspensión creada en caso de exhibición de documentos electrónicos  <br/> |[Nueva CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |Se creó una suspensión para un caso de exhibición de documentos electrónicos. Una suspensión se puede crear con o sin especificar un origen de contenido. Si se especifican los orígenes de contenido, podrá identificar en la entrada de registro de auditoría.  <br/> |
|Suspensión eliminada de caso de exhibición de documentos electrónicos  <br/> |[Remove-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |Se eliminó una suspensión a la que está asociada con un caso de exhibición de documentos electrónicos. Eliminación de una suspensión libera todas las ubicaciones de contenido de la suspensión. Eliminar la suspensión también da como resultado la eliminación de las reglas de mayúsculas y minúsculas espera asociadas con la suspensión (vea **Remove-CaseHoldRule** ).<br/> |
|Espera modificada en caso de exhibición de documentos electrónicos  <br/> |[Set-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |Se ha cambiado una suspensión a la que está asociada con una exhibición de documentos electrónicos. Las modificaciones posibles incluyen agregando o quitando ubicaciones de contenido o desactivar (deshabilitar) la suspensión.  <br/> |
|Consulta de búsqueda creada para suspensión casos de exhibición de documentos electrónicos  <br/> |[Nueva CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |Se ha creado una suspensión basada en consultas asociada con un caso de exhibición de documentos electrónicos.  <br/> |
|Consulta de búsqueda eliminados suspensión casos de exhibición de documentos electrónicos  <br/> |[Remove-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |Se eliminó una suspensión basada en consultas asociada con un caso de exhibición de documentos electrónicos. Eliminación de la consulta de la suspensión a menudo es el resultado de la eliminación de una suspensión. Cuando se elimina una suspensión o una consulta de suspensión, se liberan las ubicaciones de contenido que estaban en espera.  <br/> |
|Consulta de búsqueda modificada para suspensión casos de exhibición de documentos electrónicos  <br/> |[Set-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |Se ha cambiado una suspensión basada en consultas asociada con un caso de exhibición de documentos electrónicos. Las modificaciones posibles incluyen la edición de la consulta o suspensión de intervalo de fechas para basada en una consulta.  <br/> |
|Caso de exhibición de documentos electrónicos creada  <br/> |[Nueva ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |Se creó un caso de exhibición de documentos electrónicos. Cuando se crea un caso, sólo debe asignarle un nombre. Otras tareas relacionadas con el caso, como agregar a miembros, crear suspensiones y creación de búsquedas de contenido asociadas con el resultado de mayúsculas y minúsculas en eventos adicionales que se está registrando.  <br/> |
|Caso de exhibición de documentos electrónicos eliminados  <br/> |[Remove-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |Se eliminó un caso de exhibición de documentos electrónicos. Tenga en cuenta que cualquier suspensión asociado con el caso debe quitarse antes de que se pueden eliminar las mayúsculas y minúsculas.  <br/> |
|Caso de exhibición de documentos electrónicos modificados  <br/> |[Set-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |Se ha cambiado un caso de exhibición de documentos electrónicos. Los cambios incluyen cerrar un caso abierto o volver a abrir un caso cerrado.  <br/> |
|Se ha agregado un miembro a caso de exhibición de documentos electrónicos  <br/> |[ComplianceCaseMember agregar](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |Se agregó un usuario como un miembro de un caso de exhibición de documentos electrónicos. Como miembro de un caso, un usuario puede realizar diversas tareas relacionadas con el caso dependiendo de si se les ha asignado los permisos necesarios.  <br/> |
|Miembro se ha quitado de caso de exhibición de documentos electrónicos  <br/> |[Remove-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |Se quitó un usuario como un miembro de un caso de exhibición de documentos electrónicos.  <br/> |
|Pertenencia a casos de exhibición de documentos electrónicos modificados  <br/> |[Actualización de ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |Se ha cambiado la lista de pertenencia de un caso de exhibición de documentos electrónicos. Esta actividad se registra cuando todos los miembros se han reemplazado con un grupo de usuarios nuevos. Si se agrega o se quita un miembro único, se registra la operación de **Agregar ComplianceCaseMember** o **Remove-ComplianceCaseMember** .<br/> |
|Búsqueda de contenido creada  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |Se ha creado una nueva búsqueda de contenido.  <br/> |
|Búsqueda de contenido eliminada  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |Se eliminó una búsqueda de contenido existente.  <br/> |
|Búsqueda de contenido modificada  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |Se ha cambiado una búsqueda de contenido existente. Agregar o quitar ubicaciones de contenido que se buscan y modificar la consulta de búsqueda, pueden incluir los cambios.  <br/> |
|Inicia la búsqueda de contenido  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |Se ha iniciado una búsqueda de contenido. Al crear o cambiar una búsqueda de contenido mediante el uso de la seguridad &amp; GUI del centro de cumplimiento, la búsqueda se inicia automáticamente. Si crear o cambiar una búsqueda mediante el **Nuevo ComplianceSearch** o el cmdlet **Set-ComplianceSearch** , se debe ejecutar el cmdlet **Start-ComplianceSearch** para iniciar la búsqueda.<br/> |
|Detiene la búsqueda de contenido  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |Se ha detenido una búsqueda de contenido que se encontraba en ejecución.  <br/> |
|Crear la acción de búsqueda de contenido  <br/> |[New-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |Se creó una acción de búsqueda de contenido. Acciones de búsqueda de contenido incluyen obtener una vista previa de los resultados de búsqueda, exportar los resultados de búsqueda, preparación de los resultados de búsqueda para el análisis de exhibición de documentos electrónicos avanzada de Office 365 y eliminar permanentemente los elementos que coinciden con los criterios de búsqueda de una búsqueda de contenido.  <br/> |
|Acción de búsqueda de contenido eliminado  <br/> |[Remove-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |Se eliminó una acción de búsqueda de contenido.  <br/> |
|Creado el filtro de búsqueda de permisos  <br/> |[Nueva ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |Se ha creado un filtro de búsqueda de permisos.  <br/> |
|Filtro de permisos de búsqueda eliminados  <br/> |[Remove-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |Se eliminó un filtro de búsqueda de permisos.  <br/> |
|Cambiar el filtro de búsqueda de permisos  <br/> |[Set-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |Se ha cambiado un filtro de búsqueda de permisos.  <br/> |
|Administrador de exhibición de documentos electrónicos creada  <br/> |[EDiscoveryCaseAdmin agregar](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |Se agregó un usuario como un administrador de exhibición de documentos en su organización.  <br/> |
|Administrador de exhibición de documentos electrónicos eliminados  <br/> |[Remove-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |Un administrador de exhibición de documentos electrónicos se eliminó de la organización.  <br/> |
|Pertenencia al administrador de exhibición de documentos electrónicos modificados  <br/> |[Actualización de eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |Se ha cambiado la lista de exhibición de documentos electrónicos los administradores de la organización. Esta actividad se registra cuando la lista de exhibición de documentos electrónicos los administradores se ha reemplazado con un grupo de usuarios nuevos. Si se agrega o se quita un único usuario, se registra la operación de **Agregar eDiscoveryCaseAdmin** o **Remove-eDiscoveryCaseAdmin** .<br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>Propiedades detalladas para actividades de exhibición de documentos electrónicos

En la siguiente tabla se describe las propiedades que se incluyen al hacer clic en **obtener más información** en la página de **Detalles** de una actividad de exhibición de documentos electrónicos que aparecen en los resultados de búsqueda. Estas propiedades también se incluyen en el archivo CSV al exportar los resultados de búsqueda de registro de auditoría. Tenga en cuenta que un registro de registro de auditoría para una actividad de exhibición de documentos electrónicos no incluir cada propiedad detallada enumerado a continuación. 
  
> [!TIP]
> Al exportar los resultados de búsqueda, el archivo CSV contiene una columna denominada **Detalles**, que contiene las propiedades detalladas que se describen en la siguiente tabla en una propiedad de varios valor. Puede usar la característica de consulta de alimentación en Excel para dividir esta columna en varias columnas para que cada propiedad tendrá su propia columna. Esto le permitirá ordenar y filtrar en una o varias de estas propiedades. Para obtener más información, vea la sección "Exportar los resultados de búsqueda a un archivo" en [el registro de auditoría en el centro de cumplimiento de seguridad de Office 365 y de búsqueda ](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file). 
  
|**Propiedad**|**Descripción**|
|:-----|:-----|
|Caso  <br/> |La identidad (GUID) de la caja de exhibición de documentos electrónicos que se ha creado, modificado o eliminado.  <br/> |
|ClientApplication  <br/> |actividades de exhibición de documentos electrónicos cmdlet tienen un valor de **EMC** para esta propiedad. Esto indica que la actividad se llevó a cabo mediante el uso de la seguridad &amp; interfaz gráfica de usuario del centro de cumplimiento de normas o ejecutando el cmdlet de PowerShell.<br/> |
|IPCliente  <br/> |La dirección IP del dispositivo que se usó cuando se registró la actividad. La dirección IP se muestra en formato de dirección de un IPv4 o IPv6.  <br/> |
|ClientRequestId  <br/> | Para las actividades de exhibición de documentos electrónicos, esta propiedad es normalmente en blanco.  <br/> |
|CmdletVersion  <br/> |El número de compilación de la versión de la seguridad &amp; centro de cumplimiento de normas que se ejecuta en su organización.  <br/> |
|CreationTime  <br/> |La fecha y hora en hora Universal coordinada (UTC) cuando se ha completado la actividad de exhibición de documentos electrónicos.  <br/> |
|EffectiveOrganization  <br/> |El nombre de la organización de Office 365.  <br/> |
|ExchangeLocations  <br/> |Los buzones de Exchange Online que se incluyen en una búsqueda de contenido o se colocan en espera en un caso de exhibición de documentos electrónicos.  <br/> |
|Exclusiones de  <br/> |Ubicaciones de buzón de correo o sitio que se excluyen de la búsqueda de contenido o una suspensión en un caso de exhibición de documentos electrónicos.  <br/> |
|ExtendedProperties  <br/> |Propiedades adicionales de un contenido de búsqueda, una acción de búsqueda de contenido, o mantienen en un caso de exhibición de documentos electrónicos, por ejemplo, el GUID del objeto y el cmdlet correspondiente y los parámetros de cmdlet que se usaron cuando se realizó la actividad.  <br/> |
|Id  <br/> |El identificador de la entrada del informe. El identificador identifica la entrada de registro de auditoría.  <br/> |
|NonPIIParameters  <br/> |Una lista de los parámetros (sin cualquiera de los valores) que se usaron con el cmdlet identificado en la propiedad de la operación. Los parámetros que aparecen en esta propiedad son los mismos que los que aparecen en la propiedad Parameters.  <br/> |
|ObjectId  <br/> |El GUID o el nombre del objeto (por ejemplo, una búsqueda de contenido o un caso de exhibición de documentos electrónicos) que se ha creado, modificado o eliminado por la actividad que aparecen en la propiedad de la operación. Este objeto también se identifica en la columna de elemento en los resultados de búsqueda de registro de auditoría.  <br/> |
|ObjectType  <br/> |El tipo de objeto de exhibición de documentos electrónicos que el usuario crea, eliminado o modificado; Por ejemplo, una acción de búsqueda de contenido (vista previa, exportar o purgar), un caso de exhibición de documentos electrónicos o una búsqueda de contenido.  <br/> |
|Operation  <br/> |El nombre de la operación que corresponde a la actividad de exhibición de documentos electrónicos que se llevó a cabo.  <br/> |
|OrganizationId  <br/> |El GUID de la organización de Office 365.  <br/> |
|Parámetros  <br/> |El nombre y el valor de los parámetros que se usaron con el cmdlet correspondiente.  <br/> |
|PublicFolderLocations  <br/> |Las ubicaciones de carpetas públicas en Exchange Online que se incluyen en una búsqueda de contenido o se colocan en espera en un caso de exhibición de documentos electrónicos.  <br/> |
|Consulta  <br/> |La consulta de búsqueda asociada con la actividad, como una búsqueda de contenido o una suspensión basada en consultas.  <br/> |
|RecordType  <br/> |El tipo de operación indicado en el registro. El valor de **18** indica un evento relacionado con una actividad que aparecen en la sección [actividades de cmdlet de exhibición de documentos electrónicos](#ediscovery-cmdlet-activities) . Un valor de **24** indica un evento relacionado con una actividad que aparecen en la sección [cómo buscar y ver las actividades de exhibición de documentos electrónicos](#how-to-search-for-and-view-ediscovery-activities) .<br/> |
|ResultStatus  <br/> |Indica si la acción (especificada en la propiedad Operation) se realizó correctamente o no.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Indica que la actividad era una seguridad &amp; (evento) Centro de cumplimiento. Todas las actividades de exhibición de documentos electrónicos tendrá un valor de **0** para esta propiedad.<br/> |
|SharepointLocations  <br/> |Los sitios de SharePoint Online que se incluyen en una búsqueda de contenido o se colocan en espera en un caso de exhibición de documentos electrónicos.  <br/> |
|StartTime  <br/> |La fecha y hora en hora Universal coordinada (UTC) cuando se inició la actividad de exhibición de documentos electrónicos.  <br/> |
|UserId  <br/> |El usuario que realizó la actividad (especificada en la propiedad Operation) que se esperó en el registro que se está registrando. Tenga en cuenta que los registros de actividad de exhibición de documentos electrónicos de cuentas del sistema (como NT AUTHORITY\SYSTEM) también se encuentran en el registro de auditoría.  <br/> |
|UserKey  <br/> |Un identificador alternativo para el usuario identificado en la propiedad UserId. Para las actividades de exhibición de documentos electrónicos, el valor de esta propiedad es normalmente el mismo que la propiedad UserId.  <br/> |
|UserServicePlan  <br/> |La suscripción de Office 365 usada por su organización. Para las actividades de exhibición de documentos electrónicos, esta propiedad es normalmente en blanco.  <br/> |
|UserType  <br/> |El tipo de usuario que realizó la operación. Los siguientes valores indican el tipo de usuario.  <br/> Usuario habitual de 0 A. 2 un administrador de la organización de Office 365. 3 un centro de datos Administrador o centro de datos del sistema cuenta de Microsoft. 4 una cuenta del sistema. 5 una aplicación. 6 una entidad de seguridad del servicio. |
|Versión  <br/> |Indica el número de versión de la actividad (identificado por la propiedad Operation) que se registra.  <br/> |
|Carga de trabajo  <br/> |El servicio Office 365 donde se produjo la actividad. Para las actividades de exhibición de documentos electrónicos, el valor es **SecurityComplianceCenter**.<br/> |
