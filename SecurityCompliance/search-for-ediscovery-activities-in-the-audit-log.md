---
title: Buscar actividades de eDiscovery en el registro de auditoría de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Obtenga información sobre cómo buscar en el registro de auditoría de Office 365 eventos que se registran cuando los administradores de cumplimiento realizan tareas de caso de exhibición de documentos electrónicos y de búsqueda de contenido en el centro de seguridad & cumplimiento.
ms.openlocfilehash: 62c58d123367fd5ee6778034716bc1deb5afc1e2
ms.sourcegitcommit: 6c9340e4eb221bf81472ff3f1ae25ae21aaf5297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "31814101"
---
# <a name="search-for-ediscovery-activities-in-the-office-365-audit-log"></a>Buscar actividades de eDiscovery en el registro de auditoría de Office 365

La búsqueda de contenido y las actividades relacionadas con la exhibición de documentos electrónicos que se realizan en el centro de seguridad & cumplimiento o mediante la ejecución de los cmdlets de Windows PowerShell correspondientes se registran en el registro de auditoría de Office 365. Los eventos se registran cuando los administradores o los administradores de cumplimiento (o cualquier usuario que tenga asignados permisos de exhibición de documentos electrónicos) realizan las siguientes tareas relacionadas con la exhibición de documentos electrónicos y la búsqueda de contenido en el centro de seguridad & cumplimiento:
  
- Creación y administración de casos de eDiscovery
    
- Creación, Inicio y edición de búsquedas de contenido
    
- Realización de acciones de búsqueda de contenido, como vista previa, exportación y eliminación de resultados de búsqueda
    
- Configuración del filtrado de permisos para búsqueda de contenido
    
- Administración del rol de administrador de eDiscovery
    
> [!IMPORTANT]
> Las actividades descritas en este artículo solo son el resultado de las tareas de eDiscovery realizadas mediante el centro de seguridad & cumplimiento. las tareas de eDiscovery que se realizaron con la herramienta de exhibición de documentos electrónicos local en Exchange online o el centro de exhibición de documentos electrónicos en SharePoint Online no se incluyen. 
  
Para obtener más información acerca de la búsqueda en el registro de auditoría de Office 365, los permisos necesarios y los resultados de la búsqueda, vea [Buscar en el registro de auditoría del centro de seguridad _AMP_ cumplimiento](search-the-audit-log-in-security-and-compliance.md).
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Cómo buscar y ver actividades de eDiscovery

Actualmente, tiene que hacer algunas cosas específicas para ver las actividades de eDiscovery en el registro de auditoría de Office 365. Aquí se muestra cómo hacerlo.
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el panel izquierdo, haga clic en **Buscar**y, a continuación, haga clic en **búsqueda de registros de auditoría**.
    
4. En la lista desplegable **actividades** , en **actividades de exhibición**de documentos electrónicos, haga clic en una o más actividades para buscar. O puede hacer clic en **actividades de exhibición** de documentos electrónicos para buscar todas las actividades relacionadas con la exhibición de documentos electrónicos. 
    
    > [!NOTE]
    > La lista desplegable actividades también incluye un grupo de actividades que se denominan **actividades del cmdlet eDiscovery** y que devolverán registros del registro de auditoría del cmdlet. 
  
5.  Seleccione un intervalo de fecha y hora para mostrar los eventos de eDiscovery que se produjeron dentro de ese período. 
    
6. En el cuadro **usuarios** , seleccione uno o más usuarios para los que desea mostrar los resultados de la búsqueda. Deje este cuadro en blanco para devolver las entradas de todos los usuarios. 
    
7. Haga clic en **Buscar** para ejecutar la búsqueda con los criterios de búsqueda. 
    
8. Una vez que se muestran los resultados de la búsqueda, puede hacer clic en **filtrar resultados** para filtrar u ordenar los registros de actividad resultantes. Desafortunadamente, no se puede usar el filtrado para excluir explícitamente ciertas actividades. 
    
9. Para ver los detalles de una actividad, haga clic en el registro de actividad en la lista de resultados de la búsqueda. 
    
    Se muestra una página **detalles** de la marcha que contiene las propiedades detalladas del registro del evento. Para mostrar información adicional, haga clic en **más información**. Para obtener una descripción de estas propiedades, consulte la sección [propiedades detalladas para actividades de eDiscovery](#detailed-properties-for-ediscovery-activities) . 

  
## <a name="ediscovery-activities"></a>actividades de eDiscovery

En la tabla siguiente se describen las actividades relacionadas con la exhibición de documentos electrónicos y la búsqueda de contenido que se registran cuando un administrador o un usuario realiza una actividad relacionada con eDiscovery mediante el centro de seguridad & cumplimiento o mediante la ejecución del cmdlet correspondiente en PowerShell remoto que está conectado al centro de seguridad & de cumplimiento de la organización. 
  
> [!NOTE]
> Las actividades de eDiscovery descritas en esta sección proporcionan información similar a las actividades del cmdlet de exhibición de documentos electrónicos que se describen en la siguiente sección. Le recomendamos que use las actividades de eDiscovery descritas en esta sección, ya que aparecerán en los resultados de la búsqueda del registro de auditoría en 30 minutos. Las actividades del cmdlet eDiscovery tardan hasta 24 horas en aparecer en los resultados de la búsqueda de registros de auditoría. 
  
|**Nombre descriptivo**|**Operación**|**Cmdlet correspondiente**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Se agregó un miembro al caso de eDiscovery  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |Se ha agregado un usuario como miembro de un caso de exhibición de documentos electrónicos. Como miembro de un caso, un usuario puede realizar varias tareas relacionadas con casos en función de si se les han asignado los permisos necesarios.  <br/> |
|Búsqueda de contenido modificada  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |Se ha cambiado una búsqueda de contenido existente. Los cambios pueden incluir la adición o eliminación de ubicaciones de contenido o la edición de la consulta de búsqueda.  <br/> |
|Pertenencia del administrador de eDiscovery modificada  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |Se cambió la lista de administradores de exhibición de documentos electrónicos de la organización. Esta actividad se registra cuando la lista de administradores de eDiscovery se reemplaza por un grupo de nuevos usuarios. Si se agrega o se quita un solo usuario, se registra la operación CaseAdminAdded.  <br/> |
|Caso de exhibición de documentos electrónicos cambiado  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |Se cambió un caso de exhibición de documentos electrónicos. Los cambios incluyen cerrar un caso abierto o volver a abrir un caso cerrado.  <br/> |
|Pertenencia al caso de eDiscovery cambiado  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |Se cambió la lista de miembros de un caso de exhibición de documentos electrónicos. Esta actividad se registra cuando todos los miembros se reemplazan por un grupo de nuevos usuarios. Si se agrega o se quita un solo miembro, se registra la operación CaseMemberAdded o CaseMemberRemoved.  <br/> |
|Filtro de permisos de búsqueda cambiados  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |Se ha cambiado un filtro de permisos de búsqueda.  <br/> |
|Consulta de búsqueda modificada para suspensión de casos de exhibición de documentos electrónicos  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |Se cambió una retención basada en consulta asociada a un caso de exhibición de documentos electrónicos. Los posibles cambios incluyen editar la consulta o el intervalo de fechas de una suspensión basada en consulta.  <br/> |
|Elemento de vista previa de búsqueda de contenido descargado  <br/> |PreviewItemDownloaded  <br/> |N/D  <br/> |Un usuario descargó un elemento en su equipo local (haciendo clic en el vínculo **Descargar elemento original** ) al obtener la vista previa de los resultados de búsqueda.  <br/> |
|Elemento de vista previa de búsqueda de contenido  <br/> |PreviewItemListed  <br/> |N/D  <br/> |Un usuario hizo clic en **vista previa de resultados de búsqueda** para mostrar la página de resultados de la búsqueda en vista previa, que enumera hasta 1000 elementos a partir de los resultados de una búsqueda de contenido.  <br/> |
|Elemento vista previa de búsqueda de contenido visto  <br/> |PreviewItemRendered  <br/> |N/D  <br/> |Un administrador de exhibición de documentos electrónicos ha visto un elemento haciendo clic en él para obtener una vista previa de los resultados de búsqueda.  <br/> |
|Búsqueda de contenido creada  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |Se ha creado una nueva búsqueda de contenido.  <br/> |
|Administrador de exhibición de documentos electrónicos creado  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |Se ha agregado un usuario como administrador de exhibición de documentos electrónicos en la organización.  <br/> |
|Caso de exhibición de documentos electrónicos creado  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |Se ha creado un caso de exhibición de documentos electrónicos. Cuando se crea un caso, solo tiene que asignarle un nombre. Otras tareas relacionadas con el caso, como la adición de miembros, la creación de suspensiones y la creación de búsquedas de contenido asociadas con el caso del resultado se registran eventos adicionales.  <br/> |
|Filtro de permisos de búsqueda creados  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |Se ha creado un filtro de permisos de búsqueda.  <br/> |
|Consulta de búsqueda creada para la suspensión de casos de eDiscovery  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |Se ha creado una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos.  <br/> |
|Búsqueda de contenido eliminada  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |Se eliminó una búsqueda de contenido existente.  <br/> |
|Administrador de eDiscovery eliminado  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Se eliminó un administrador de exhibición de documentos electrónicos de su organización.  <br/> |
|Caso de exhibición de documentos electrónicos eliminado  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Se eliminó un caso de exhibición de documentos electrónicos. Tenga en cuenta que cualquier retención asociada con el caso debe quitarse antes de que se pueda eliminar el caso.  <br/> |
|Filtro de permisos de búsqueda eliminados  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |Se eliminó un filtro de permisos de búsqueda.  <br/> |
|Consulta de búsqueda eliminada para la suspensión de casos de eDiscovery  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Se ha eliminado una retención basada en consulta asociada a un caso de exhibición de documentos electrónicos. La eliminación de la consulta de la retención suele ser el resultado de eliminar una suspensión. Cuando se elimina una consulta de suspensión o de retención, se sueltan las ubicaciones de contenido en suspensión.  <br/> |
|Exportación de la búsqueda de contenido desCargada  <br/> |SearchExportDownloaded  <br/> |N/D  <br/> |Un usuario ha descargado los resultados de una búsqueda de contenido en su equipo local. Tenga en cuenta que es necesario iniciar una **exportación iniciada de la actividad de búsqueda de contenido** para poder descargar los resultados de la búsqueda.  <br/> |
|Vista previa de los resultados de la búsqueda de contenido  <br/> |SearchPreviewed  <br/> |N/D  <br/> |Un usuario ha dado la vista previa de los resultados de una búsqueda de contenido.  <br/> |
|Resultados dePurados de la búsqueda de contenido  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Un usuario purgó los resultados de una búsqueda de contenido mediante la ejecución del comando **New-ComplianceSearchAction-Purge** .  <br/> |
|Análisis quitado de la búsqueda de contenido  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de preparación de búsqueda de contenido (para preparar los resultados de búsqueda para Office 365 Advanced eDiscovery). Si la acción de preparación fue de menos de dos semanas de antigüedad, los resultados de la búsqueda que se prepararon para eDiscovery avanzado se eliminaron del área de almacenamiento de Microsoft Azure. Si la acción de preparación era anterior a dos semanas, este evento indica que solo se eliminó la acción de preparación correspondiente.  <br/> |
|Se ha quitado la búsqueda de exportación de contenido  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de exportación de búsqueda de contenido. Si la acción de exportación era anterior a dos semanas, los resultados de la búsqueda que se cargaron en el área de almacenamiento de Microsoft Azure se eliminaron. Si la acción de exportación era anterior a dos semanas, este evento indica que solo se eliminó la acción de exportación correspondiente.  <br/> |
|Miembro quitado del caso de eDiscovery  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Un usuario se quitó como miembro de un caso de exhibición de documentos electrónicos.  <br/> |
|Se quitaron los resultados de vista previa de búsqueda de contenido  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de vista previa de búsqueda de contenido.  <br/> |
|Se quita la acción de purga realizada en la búsqueda de contenido  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de purga de búsqueda de contenido.  <br/> |
|Informe de búsqueda quitado  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de informe de exportación de búsqueda de contenido.  <br/> |
|Se inició el análisis de búsqueda de contenido  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |Los resultados de una búsqueda de contenido se han preparado para el análisis en la exhibición avanzada de documentos electrónicos.  <br/> |
|Búsqueda de contenido iniciada  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |Se ha iniciado una búsqueda de contenido. Al crear o cambiar una búsqueda de contenido mediante la interfaz gráfica de usuario del centro de cumplimiento de & de seguridad, la búsqueda se inicia automáticamente. Si crea o cambia una búsqueda con el cmdlet **New-compliancesearch** o **set-compliancesearch** , tiene que ejecutar el cmdlet **Start-compliancesearch** para iniciar la búsqueda.  <br/> |
|Se inició la exportación de búsqueda de contenido  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Un usuario exportó los resultados de una búsqueda de contenido.  <br/> |
|Informe de exportación iniciado  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Un usuario exportó un informe de búsqueda de contenido.  <br/> |
|Búsqueda de contenido detenido  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Un usuario ha detenido una búsqueda de contenido.  <br/> |
  
## <a name="ediscovery-cmdlet-activities"></a>actividades del cmdlet eDiscovery

En la tabla siguiente se enumeran los registros de auditoría de cmdlet que se registran cuando un administrador o un usuario realiza una actividad relacionada con eDiscovery mediante el centro de seguridad & cumplimiento o mediante la ejecución del cmdlet correspondiente en PowerShell remoto que está conectado al centro de seguridad & cumplimiento de la organización. Tenga en cuenta que la información detallada en el registro de auditoría es diferente para las actividades de cmdlet que se enumeran en esta tabla y las actividades de eDiscovery descritas en la sección anterior. 
  
Como se mencionó anteriormente, las actividades de cmdlet de eDiscovery tardan hasta 24 horas en aparecer en los resultados de búsqueda de registros de auditoría.
  
> [!TIP]
> Los cmdlets de la columna **Operation** de la tabla siguiente están vinculados al tema de la ayuda de cmdlet correspondiente en TechNet. Vaya al tema de ayuda del cmdlet para obtener una descripción de los parámetros disponibles para cada cmdlet. El parámetro y el valor de parámetro que se usaron con un cmdlet se incluyen en la entrada del registro de auditoría para cada actividad de cmdlet de eDiscovery que se registra. 
  
|**Nombre descriptivo**|**Operación (cmdlet)**|**Descripción**|
|:-----|:-----|:-----|
|Suspensión creada en caso de exhibición de documentos electrónicos  <br/> |[New-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |Se ha creado una suspensión para un caso de exhibición de documentos electrónicos. Una suspensión se puede crear con o sin especificar un origen de contenido. Si se especifican los orígenes de contenido, se identificarán en la entrada del registro de auditoría.  <br/> |
|Eliminación de la retención del caso de eDiscovery  <br/> |[Remove-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |Se eliminó una suspensión asociada a un caso de exhibición de documentos electrónicos. Al eliminar una retención, se liberan todas las ubicaciones de contenido de la suspensión. Eliminar la retención también da como resultado la eliminación de las reglas de suspensión de casos asociadas con la retención (consulte **Remove-CaseHoldRule** a continuación).  <br/> |
|Cambio en la retención en el caso de eDiscovery  <br/> |[Set-CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |Se cambió una suspensión asociada a una exhibición de documentos electrónicos. Los posibles cambios incluyen agregar o quitar ubicaciones de contenido o desactivar (deshabilitar) la retención.  <br/> |
|Consulta de búsqueda creada para la suspensión de casos de eDiscovery  <br/> |[New-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |Se ha creado una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos.  <br/> |
|Consulta de búsqueda eliminada para la suspensión de casos de eDiscovery  <br/> |[Remove-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |Se ha eliminado una retención basada en consulta asociada a un caso de exhibición de documentos electrónicos. La eliminación de la consulta de la retención suele ser el resultado de eliminar una suspensión. Cuando se elimina una consulta de suspensión o de retención, se sueltan las ubicaciones de contenido en suspensión.  <br/> |
|Consulta de búsqueda modificada para suspensión de casos de exhibición de documentos electrónicos  <br/> |[Set-CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |Se cambió una retención basada en consulta asociada a un caso de exhibición de documentos electrónicos. Los posibles cambios incluyen editar la consulta o el intervalo de fechas de una suspensión basada en consulta.  <br/> |
|Caso de exhibición de documentos electrónicos creado  <br/> |[New-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |Se ha creado un caso de exhibición de documentos electrónicos. Cuando se crea un caso, solo tiene que asignarle un nombre. Otras tareas relacionadas con el caso, como la adición de miembros, la creación de suspensiones y la creación de búsquedas de contenido asociadas con el caso del resultado se registran eventos adicionales.  <br/> |
|Caso de exhibición de documentos electrónicos eliminado  <br/> |[Remove-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |Se eliminó un caso de exhibición de documentos electrónicos. Tenga en cuenta que cualquier retención asociada con el caso debe quitarse antes de que se pueda eliminar el caso.  <br/> |
|Caso de exhibición de documentos electrónicos cambiado  <br/> |[Set-ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |Se cambió un caso de exhibición de documentos electrónicos. Los cambios incluyen cerrar un caso abierto o volver a abrir un caso cerrado.  <br/> |
|Se agregó un miembro al caso de eDiscovery  <br/> |[Add-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |Se ha agregado un usuario como miembro de un caso de exhibición de documentos electrónicos. Como miembro de un caso, un usuario puede realizar varias tareas relacionadas con casos en función de si se les han asignado los permisos necesarios.  <br/> |
|Miembro quitado del caso de eDiscovery  <br/> |[Remove-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |Un usuario se quitó como miembro de un caso de exhibición de documentos electrónicos.  <br/> |
|Pertenencia al caso de eDiscovery cambiado  <br/> |[Update-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |Se cambió la lista de miembros de un caso de exhibición de documentos electrónicos. Esta actividad se registra cuando todos los miembros se reemplazan por un grupo de nuevos usuarios. Si se agrega o se quita un solo miembro, se registra la operación **Add-ComplianceCaseMember** o **Remove-ComplianceCaseMember** .  <br/> |
|Búsqueda de contenido creada  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |Se ha creado una nueva búsqueda de contenido.  <br/> |
|Búsqueda de contenido eliminada  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |Se eliminó una búsqueda de contenido existente.  <br/> |
|Búsqueda de contenido modificada  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |Se ha cambiado una búsqueda de contenido existente. Los cambios pueden incluir la adición o eliminación de ubicaciones de contenido en las que se realiza la búsqueda y la edición de la consulta de búsqueda.  <br/> |
|Búsqueda de contenido iniciada  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |Se ha iniciado una búsqueda de contenido. Al crear o cambiar una búsqueda de contenido mediante la interfaz gráfica de usuario del centro de cumplimiento de & de seguridad, la búsqueda se inicia automáticamente. Si crea o cambia una búsqueda con el cmdlet **New-compliancesearch** o **set-compliancesearch** , tiene que ejecutar el cmdlet **Start-compliancesearch** para iniciar la búsqueda.  <br/> |
|Búsqueda de contenido detenido  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |Se detuvo una búsqueda de contenido que se estaba ejecutando.  <br/> |
|Acción de búsqueda de contenido creada  <br/> |[New-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |Se ha creado una acción de búsqueda de contenido. Las acciones de búsqueda de contenido incluyen la vista previa de los resultados de búsqueda, la exportación de resultados de búsqueda, la preparación de los resultados de búsqueda para el análisis en eDiscovery avanzado de Office 365 y la eliminación permanente de elementos que coinciden con los criterios de búsqueda de una búsqueda de contenido.  <br/> |
|Acción de búsqueda de contenido eliminada  <br/> |[Remove-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |Se eliminó una acción de búsqueda de contenido.  <br/> |
|Filtro de permisos de búsqueda creados  <br/> |[New-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |Se ha creado un filtro de permisos de búsqueda.  <br/> |
|Filtro de permisos de búsqueda eliminados  <br/> |[Remove-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |Se eliminó un filtro de permisos de búsqueda.  <br/> |
|Filtro de permisos de búsqueda cambiados  <br/> |[Set-ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |Se ha cambiado un filtro de permisos de búsqueda.  <br/> |
|Administrador de exhibición de documentos electrónicos creado  <br/> |[Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |Se ha agregado un usuario como administrador de exhibición de documentos electrónicos en su organización.  <br/> |
|Administrador de eDiscovery eliminado  <br/> |[Remove-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |Se eliminó un administrador de exhibición de documentos electrónicos de su organización.  <br/> |
|Pertenencia del administrador de eDiscovery modificada  <br/> |[Update-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |Se cambió la lista de administradores de exhibición de documentos electrónicos de la organización. Esta actividad se registra cuando la lista de administradores de eDiscovery se reemplaza por un grupo de nuevos usuarios. Si se agrega o se quita un solo usuario, se registra la operación **Add-eDiscoveryCaseAdmin** o **Remove-eDiscoveryCaseAdmin** .  <br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>Propiedades detalladas para actividades de eDiscovery

En la tabla siguiente se describen las propiedades que se incluyen al hacer clic en **más información** en la página de **detalles** de una actividad de exhibición de documentos electrónicos que aparece en los resultados de búsqueda. Estas propiedades también se incluyen en el archivo CSV cuando se exportan los resultados de la búsqueda de registros de auditoría. Tenga en cuenta que un registro de auditoría para una actividad de eDiscovery no incluirá todas las propiedades detalladas que se enumeran a continuación. 
  
> [!TIP]
> Cuando se exportan los resultados de la búsqueda, el archivo CSV contiene una columna denominada **detail**, que contiene las propiedades detalladas que se describen en la siguiente tabla en una propiedad de varios valores. Puede usar la característica Power Query en Excel para dividir esta columna en varias columnas para que cada propiedad tenga su propia columna. Esto le permitirá ordenar y filtrar por una o varias de estas propiedades. Para obtener más información, consulte la sección "exportar los resultados de la búsqueda a un archivo" en [Buscar el registro de auditoría](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file). 
  
|**Propiedad**|**Descripción**|
|:-----|:-----|
|Case  <br/> |La identidad (GUID) del caso de exhibición de documentos electrónicos que se creó, modificó o eliminó.  <br/> |
|ClientApplication  <br/> |las actividades del cmdlet de eDiscovery tienen un valor de **EMC** para esta propiedad. Esto indica que la actividad se llevó a cabo mediante la interfaz gráfica de usuario del centro de cumplimiento de & de seguridad o al ejecutar el cmdlet en PowerShell.  <br/> |
|ClientIP  <br/> |La dirección IP del dispositivo que se ha usado cuando la actividad se ha registrado. La dirección IP se muestra en el formato de dirección IPv4 o IPv6.  <br/> |
|ClientRequestId  <br/> | Para actividades de eDiscovery, esta propiedad suele estar en blanco.  <br/> |
|CmdletVersion  <br/> |El número de compilación de la versión del centro de seguridad & cumplimiento que se ejecuta en su organización.  <br/> |
|CreationTime  <br/> |La fecha y la hora en la hora universal coordinada (UTC) cuando se completó la actividad de eDiscovery.  <br/> |
|EffectiveOrganization  <br/> |El nombre de la organización de Office 365.  <br/> |
|ExchangeLocations  <br/> |Los buzones de correo de Exchange online que se incluyen en una búsqueda de contenido o se colocan en suspensión en un caso de exhibición de documentos electrónicos.  <br/> |
|Exclusiones  <br/> |Ubicaciones de buzones o sitios que se excluyen de una búsqueda de contenido o una retención en un caso de exhibición de documentos electrónicos.  <br/> |
|ExtendedProperties  <br/> |Propiedades adicionales de una búsqueda de contenido, una acción de búsqueda de contenido o una retención en un caso de exhibición de documentos electrónicos, como el GUID del objeto y el cmdlet correspondiente y los parámetros del cmdlet que se usaron cuando se realizó la actividad.  <br/> |
|Id  <br/> |IDENTIFICADOR de la entrada de informe. El identificador identifica de forma única la entrada del registro de auditoría.  <br/> |
|NonPIIParameters  <br/> |Una lista de los parámetros (sin valores) que se usaron con el cmdlet identificado en la propiedad Operation. Los parámetros que aparecen en esta propiedad son los mismos que los que aparecen en la propiedad paraMeters.  <br/> |
|ObjectId  <br/> |GUID o nombre del objeto (por ejemplo, una búsqueda de contenido o un caso de exhibición de documentos electrónicos) que ha creado, cambiado o eliminado la actividad enumerada en la propiedad Operation. Este objeto también se identifica en la columna elemento de los resultados de la búsqueda de registros de auditoría.  <br/> |
|ObjectType  <br/> |El tipo de objeto de exhibición de documentos electrónicos que el usuario ha creado, eliminado o modificado; por ejemplo, una acción de búsqueda de contenido (vista previa, exportación o purga), un caso de exhibición de documentos electrónicos o una búsqueda de contenido.  <br/> |
|Operación  <br/> |El nombre de la operación que corresponde a la actividad de exhibición de documentos electrónicos que se realizó.  <br/> |
|OrganizationId  <br/> |El GUID de la organización de Office 365.  <br/> |
|Parámetros  <br/> |El nombre y el valor de los parámetros que se usaron con el cmdlet correspondiente.  <br/> |
|PublicFolderLocations  <br/> |Las ubicaciones de carpetas públicas en Exchange online que se incluyen en una búsqueda de contenido o se colocan en suspensión en un caso de exhibición de documentos electrónicos.  <br/> |
|Consulta  <br/> |La consulta de búsqueda asociada a la actividad, como una búsqueda de contenido o una suspensión basada en consulta.  <br/> |
|RecordType  <br/> |El tipo de operación indicado por el registro. El valor **18** indica un evento relacionado con una actividad enumerada en la sección [actividades del cmdlet de exhibición](#ediscovery-cmdlet-activities) de documentos electrónicos. Un valor de **24** indica un evento relacionado con una actividad enumerada en la sección [Cómo buscar y ver actividades de eDiscovery](#how-to-search-for-and-view-ediscovery-activities) .  <br/> |
|ResultStatus  <br/> |Indica si la acción (especificada en la propiedad Operation) se completó correctamente o no.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Indica que la actividad fue un evento del centro de cumplimiento de & de seguridad. Todas las actividades de eDiscovery tendrán un valor de **0** para esta propiedad.  <br/> |
|SharepointLocations  <br/> |Los sitios de SharePoint Online que se incluyen en una búsqueda de contenido o que se colocan en retención en un caso de exhibición de documentos electrónicos.  <br/> |
|StartTime  <br/> |La fecha y la hora en la hora universal coordinada (UTC) cuando se inició la actividad de eDiscovery.  <br/> |
|UserId  <br/> |El usuario que realizó la actividad (especificado en la propiedad Operation) que resultó en el registro que se está registrando. Tenga en cuenta que los registros de la actividad de eDiscovery que realizan las cuentas del sistema (como NT AUTHORITY\SYSTEM) también se incluyen en el registro de auditoría.  <br/> |
|UserKey  <br/> |Un id. alternativo para el usuario identificado en la propiedad id. de usuario. Para las actividades de eDiscovery, el valor de esta propiedad suele ser el mismo que el de la propiedad UserId.  <br/> |
|UserServicePlan  <br/> |La suscripción de Office 365 usada por su organización. Para actividades de eDiscovery, esta propiedad suele estar en blanco.  <br/> |
|UserType  <br/> |El tipo de usuario que llevó a cabo la operación. Los siguientes valores indican el tipo de usuario.  <br/> 0 un usuario normal. 2 un administrador de la organización de Office 365. 3 una cuenta de Microsoft Datacenter Administrator o Datacenter System. 4 una cuenta del sistema. 5 una aplicación. 6 una entidad de servicio. |
|Versión  <br/> |Indica el número de versión de la actividad (identificado por la propiedad Operation) que se registra.  <br/> |
|Carga de trabajo  <br/> |El servicio de Office 365 donde se produjo la actividad. Para las actividades de eDiscovery, el valor es **SecurityComplianceCenter**.  <br/> |
