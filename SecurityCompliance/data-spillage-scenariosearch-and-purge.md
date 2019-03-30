---
title: 'escenario de derrame de datos de series de soluciones de eDiscovery: búsqueda y depuración'
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: Use las herramientas de búsqueda y la exhibición de documentos electrónicos de Office 365 para administrar y responder a un incidente de derrame de datos en su organización.
ms.openlocfilehash: 50078e3f22ede8a1af2a252a7a6f75710534c062
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000153"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>serie de soluciones de eDiscovery: escenario de derrame de datos: búsqueda y depuración

 **¿Qué es el derrame de datos y por qué debería interesarle?** La derramación de datos es cuando se publica un documento confidencial en un entorno que no es de confianza. Cuando se detecta un incidente de derrame de datos, es importante evaluar rápidamente el tamaño y las ubicaciones del derrame, examinar las actividades de los usuarios en torno a él y, a continuación, purgar de forma permanente los datos derramados del sistema. 
  
## <a name="data-spillage-scenario"></a>Escenario de derrame de datos

Es responsable de seguridad de la información de responsables de contoso. Se le informa de una situación de derrame de datos en la que un empleado ha compartido sin saberlo un documento altamente confidencial con varias personas a través del correo electrónico. Desea evaluar rápidamente quién recibió este documento de forma interna y externa. Una vez que se haya identificado, desea compartir los resultados de las comprobaciones de casos con otros investigadores para revisarlos y, después, eliminar de forma permanente los datos de Office 365. Una vez completada la investigación, desea generar un informe con la evidencia de eliminación permanente y otros detalles de casos para cualquier referencia futura.
  
### <a name="scope-of-this-article"></a>Ámbito de este artículo

Este documento proporciona una lista de instrucciones sobre cómo quitar de forma permanente un mensaje de Office 365 para que no sea accesible o recuperable. Para eliminar un mensaje y que sea recuperable hasta que expire el período de retención de elementos eliminados, vea [Buscar y eliminar mensajes de correo electrónico en la organización de Office 365](search-for-and-delete-messages-in-your-organization.md).
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>Flujo de trabajo para administrar incidentes de derrame de datos

A continuación se describe cómo administrar un incidente de derrame de datos:

![El flujo de trabajo de 8 pasos para administrar los incidentes de derrame de datos](media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[Opcional Paso 1: administrar quién puede tener acceso al caso y establecer los límites de cumplimiento](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[Paso 2: crear un caso de exhibición de documentos electrónicos](#step-2-create-an-ediscovery-case)<br/>
[Paso 3: buscar los datos derramados](#step-3-search-for-the-spilled-data)<br/>
[Paso 4: revisar y validar las conclusiones de casos](#step-4-review-and-validate-case-findings)<br/>
[Paso 5: usar el registro de seguimiento de mensajes para comprobar cómo se compartían los datos derramados](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[Paso 6: preparar los buzones](#step-6-prepare-the-mailboxes)<br/>
[Paso 7: eliminar permanentemente los datos derramados](#step-7-permanently-delete-the-spilled-data)<br/>
[Paso 8: comprobar, proporcionar una prueba de eliminación y auditoría](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>Cosas que debe saber antes de empezar

- Cuando un buzón está en suspensión, un mensaje eliminado permanece en la carpeta elementos recuperables hasta que expira el período de retención o se libere la retención. En el [paso 6](#step-6-prepare-the-mailboxes) se describe cómo quitar la retención de los buzones. Compruebe con la administración de registros o los departamentos jurídicos antes de quitar la retención. Es posible que su organización tenga una directiva que defina si un buzón de correo en espera o un incidente de derrame de datos tiene prioridad. 
    
- Para controlar qué buzones de usuario puede buscar y administrar los buzones de usuario que pueden administrar los usuarios que tienen acceso al caso, puede configurar los límites de cumplimiento y crear un grupo de roles personalizado, que se describe en el [paso 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries). Para ello, debe ser miembro del grupo de roles de administración de la organización o tener asignado el rol de administración de roles. Si usted o en el administrador de su organización ya ha establecido límites de cumplimiento, puede omitir el paso 1.
    
- Para crear un caso, debe ser miembro del grupo de roles de administrador de eDiscovery o ser miembro de un grupo de roles personalizado que tenga asignado el rol de administración de casos. Si no es miembro, solicite a un administrador de 365 de Office que [le agregue al grupo de roles eDiscovery Manager](assign-ediscovery-permissions.md).
    
- Para eliminar datos que se han derramado en la organización, debe usar el comando [Search-Mailbox-DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps) en Exchange Online PowerShell. Además, para usar el parámetro *DeleteContent* , también debe ser miembro de un grupo de roles en Exchange online que tenga asignada la función de importación y exportación de buzoNes de correo. Consulte la sección "agregar un rol a un grupo de roles" en [Manage role Groups](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx).
    
- Para buscar las actividades de eDiscovery del registro de auditoría de Office 365 en el paso 8, la auditoría debe estar activada para su organización. Puede buscar actividades que se han realizado en los últimos 90 días. Para obtener más información acerca de cómo habilitar y usar la auditoría, vea la sección [auditar el proceso de investigación del derrame de datos](#auditing-the-data-spillage-investigation-process) en el paso 8. 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>Opcional Paso 1: administrar quién puede tener acceso al caso y establecer los límites de cumplimiento

En función de su práctica organizativa, necesita controlar quién puede tener acceso al caso de eDiscovery usado para investigar un incidente de derrame de datos y configurar los límites de conformidad. La forma más sencilla de hacerlo es agregar investigadores como miembros de un grupo de roles existente en el centro de cumplimiento de & de seguridad y, a continuación, agregar el grupo de roles como miembro del caso de exhibición de documentos electrónicos. Para obtener información sobre los grupos de roles integrados de eDiscovery y cómo agregar miembros a un caso de exhibición de documentos electrónicos, consulte [asignar permisos de exhibición](assign-ediscovery-permissions.md)de documentos electrónicos.
  
También puede crear un nuevo grupo de roles que se alinee con las necesidades de su organización. Por ejemplo, es posible que desee que un grupo de investigadores de derrames de datos de la organización obtenga acceso y colabore en todos los casos de derrame de datos. Para ello, cree un grupo de funciones "investigación de derramamiento de datos", asignando los roles apropiados (exportar, desCifrado RMS, revisión, vista previa, búsqueda de cumplimiento y administración de casos), agregando los investigadores del derrame de datos al grupo de roles y, a continuación, agregando el Grupo de roles como miembro del caso de la exhibición de documentos electrónicos de datos. Para obtener instrucciones detalladas sobre cómo hacerlo, consulte [configurar límites de cumplimiento para investigaciones de eDiscovery en Office 365](set-up-compliance-boundaries.md) . 
  
## <a name="step-2-create-an-ediscovery-case"></a>Paso 2: crear un caso de exhibición de documentos electrónicos

Un caso de exhibición de documentos electrónicos proporciona una forma efectiva de administrar la investigación de derrame de datos. Puede Agregar miembros al grupo de roles que ha creado en el paso 1, agregar el grupo de roles como miembro del nuevo caso de exhibición de documentos electrónicos, realizar búsquedas iterativas para buscar los datos derramados, exportar un informe para compartir, realizar un seguimiento del estado del caso y, a continuación, volver a consultar los detalles de la c ase si es necesario. Considere la posibilidad de establecer una Convención de nomenclatura para los casos de eDiscovery que se usa para los incidentes de derrame de datos y proporcionar toda la información que pueda con el nombre y la descripción del caso, de modo que pueda ubicar y hacer referencia a ella en el futuro si es necesario.
  
Para crear un nuevo caso, puede usar la exhibición de documentos electrónicos en el centro de seguridad y cumplimiento. Vea "crear un nuevo caso" en [casos de exhibición](ediscovery-cases.md#step-2-create-a-new-case)de documentos electrónicos.
  
## <a name="step-3-search-for-the-spilled-data"></a>Paso 3: buscar los datos derramados

Ahora que ha creado un caso y un acceso administrado, puede usar el caso para buscar de forma iterativa los datos derramados e identificar los buzones que contienen los datos derramados. Usará la misma consulta de búsqueda que usó para buscar los mensajes de correo electrónico para eliminar los mismos mensajes en el [paso 7](#step-7-permanently-delete-the-spilled-data).
  
Para crear una búsqueda de contenido asociada a un caso de exhibición de documentos electrónicos, vea "crear y ejecutar una búsqueda de contenido asociada a un caso" en [casos de exhibición](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case)de documentos electrónicos.
  
 **Importante:** Las palabras clave que se usan en la consulta de búsqueda pueden contener los datos que se han derramado reales que se están buscando. Por ejemplo, si busca documentos que contengan un número de la seguridad social y usa la palabra clave it as Search, debe eliminar la consulta posteriormente para evitar más derrames. Consulte [eliminar la consulta de búsqueda en el](#deleting-the-search-query) paso 8. 
  
## <a name="step-4-review-and-validate-case-findings"></a>Paso 4: revisar y validar las conclusiones de casos

Después de crear una búsqueda de contenido, debe revisar y validar que los resultados de la búsqueda y comprobar que solo constan de los mensajes de correo electrónico que se deben eliminar. En una búsqueda de contenido, puede obtener una vista previa de un muestreo aleatorio de mensajes de correo electrónico de 1.000 sin exportar los resultados de la búsqueda para evitar una mayor derramación de datos. Puede obtener más información acerca de las limitaciones de la vista previa en [limits for Content Search](limits-for-content-search.md).
  
Si tiene más de 1.000 buzones o más de 100 mensajes de correo electrónico por buzón de correo para revisar, puede dividir la búsqueda inicial en varias búsquedas mediante palabras clave o condiciones adicionales, como el intervalo de fechas o el remitente o el destinatario, y revisar los resultados de cada búsqueda. individualmente. Asegúrese de anotar todas las consultas de búsqueda que debe usar cuando elimine mensajes en el [paso 7](#step-7-permanently-delete-the-spilled-data).

Si se asigna una licencia de Office 36 E5 a un custodio o un usuario final, puede examinar hasta 10.000 resultados de búsqueda a la vez con Office 365 Advanced eDiscovery. Si hay más de 10.000 mensajes de correo electrónico para revisar, puede dividir la consulta de búsqueda por intervalo de fechas y revisar cada resultado individualmente, ya que los resultados de la búsqueda se ordenan por fecha. En la exhibición avanzada de documentos electrónicos, puede marcar los resultados de la búsqueda con la **etiqueta como** característica en el panel de vista previa y filtrar los resultados de búsqueda por la etiqueta que ha etiquetado. Esto es útil cuando se colabora con un revisor secundario. Mediante el uso de herramientas de análisis adicionales en eDiscovery avanzado, como el reconocimiento óptico de caracteres, el subprocesamiento de correo electrónico y la codificación predictiva, puede procesar y revisar rápidamente miles de mensajes y etiquetarlos para revisión posterior. Consulte [Quick Setup for Office 365 Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md).

Cuando encuentre un mensaje de correo electrónico que contenga datos derramados, compruebe los destinatarios del mensaje para determinar si se ha compartido de forma externa. Para seguir trazando un mensaje, puede recopilar información del remitente y un intervalo de fechas para poder usar los registros de seguimiento de mensajes, que se describen en el [paso 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared).

Afer ha comprobado los resultados de la búsqueda, es posible que desee compartir sus hallazgos con otras personas para una revisión secundaria. Las personas que asignó al caso en el paso 1 pueden revisar el contenido del caso tanto en eDiscovery como en eDiscovery avanzado y aprobar los descubrimientos de casos. También puede generar un informe sin exportar el contenido real. También puede usar este mismo informe como prueba de eliminación, que se describe en el [paso 8](#step-8-verify-provide-a-proof-of-deletion-and-audit).
  
 **Para generar un informe estadístico:**
  
1. Vaya a la página de **búsqueda** en el caso de eDiscovery y haga clic en la búsqueda para la que desea generar un informe. 
    
2. En la página de control flotante, haga clic en **más _GT_ exportar Informe**.
 
      Se muestra la página exportar informe.

    ![Seleccione la búsqueda y, a continuación, haga clic en más > informe de exportación en la página de flotante](media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. Seleccione **todos los elementos, incluidos los que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos** y, a continuación, haga clic en **generar informe**.

4. En el caso de exhibición de documentos electrónicos, haga clic en **exportar** para mostrar la lista de trabajos de exportación. Es posible que deba hacer clic en **Actualizar** para actualizar la lista y mostrar el trabajo de exportación que acaba de crear.

5. Haga clic en el trabajo de exportación y, a continuación, haga clic en **Descargar** informe en la página de control flotante.
 
    ![En la página exportar, haga clic en exportar y, a continuación, en "descargar informe"](media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

El informe de **Resumen de exportación** contiene el número de ubicaciones que se han encontrado con los resultados y el tamaño de los resultados de la búsqueda. Puede usarlo para comparar con el informe generado tras la eliminación y proporcionar como prueba de eliminación. El informe de **resultados** contiene un resumen más detallado de los resultados de la búsqueda, incluidos el asunto, el remitente, los destinatarios, si el correo electrónico se leyó, fechas y tamaño de cada mensaje. Si alguno de los detalles de este informe contiene los datos reales derramados, asegúrese de eliminar permanentemente el archivo Results. csv cuando se complete la investigación.

Para obtener más información acerca de la exportación de informes, vea [exportar un informe de búsqueda de contenido](export-a-content-search-report.md).
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>Paso 5: usar el registro de seguimiento de mensajes para comprobar cómo se compartían los datos derramados

Para investigar más a última vez que se ha compartido el correo electrónico con datos derramados, puede consultar los registros de seguimiento de mensajes con la información del remitente y la información del intervalo de fechas recopilada en el paso 4. Tenga en cuenta que el período de retención para el seguimiento de mensajes es de 30 días para los datos en tiempo real y de 90 días para los datos históricos.
  
Puede usar el seguimiento de mensajes en el centro de seguridad y cumplimiento o usar los cmdlets correspondientes en Exchange Online PowerShell. Es importante tener en cuenta que el seguimiento de mensajes no ofrece ninguna garantía completa en cuanto a la integridad de los datos devueltos. Para obtener más información acerca del uso del seguimiento de mensajes, consulte: 
  
- [Seguimiento de mensajes en el Centro de seguridad y cumplimiento](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [Nuevo seguimiento de mensajes en el centro de seguridad & cumplimiento](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>Paso 6: preparar los buzones

Después de revisar y validar que los resultados de la búsqueda solo contengan los mensajes que deben eliminarse, debe recopilar una lista de las direcciones de correo electrónico de los buzones afectados que se usarán en el paso 7 cuando ejecute el comando **Search-Mailbox-DeleteContent** . También es posible que tenga que preparar los buzones para poder eliminar permanentemente los mensajes de correo electrónico en función de si la recuperación de un único elemento está habilitada en los buzones que contienen los datos derramados o si alguno de esos buzones de correo está en suspensión.
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>Obtener una lista de direcciones de buzones de correo con datos revertidos

Hay dos formas de recopilar una lista de direcciones de correo electrónico de buzones de correo con datos derramados.

**Opción 1: obtener una lista de direcciones de buzones de correo con datos revertidos**

1. Abra el caso de exhibición de documentos electrónicos, vaya a la página de **búsqueda** y seleccione la búsqueda de contenido adecuada. 
    
2. En la página flotante, haga clic en **ver resultados**.
    
3. En la lista desplegable **resultados individuales** , haga clic en **estadísticas de búsqueda**.
    
4. En la lista desplegable **tipo** , haga clic en **ubicaciones superiores**.
    
    ![Obtener una lista de buzones de correo que contienen resultados de búsqueda en la página ubicaciones superiores en las estadísticas de búsqueda](media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    Se muestra una lista de buzones de correo que contienen los resultados de la búsqueda. También se muestra el número de elementos de cada buzón de correo que coinciden con la consulta de búsqueda.
    
5. Copie la información de la lista y guárdela en un archivo o haga clic en **Descargar** para descargar la información en un archivo CSV. 
    
**Opción 2: obtener ubicaciones de buzón de correo del informe de exportación**

Abra el informe de Resumen de exportación que ha descargado en el [paso 4](#step-4-review-and-validate-case-findings). En la primera columna del informe, la dirección de correo electrónico de cada buzón de correo aparece en **ubicaciones**.
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>Preparar los buzones para que pueda eliminar los datos derramados

Si se habilita la recuperación de un único elemento o si un buzón de correo se coloca en suspensión, un mensaje eliminado (purgado) de forma permanente se conservará en la carpeta elementos recuperables. Por lo tanto, antes de purgar los datos derramados, debe comprobar las configuraciones de los buzones existentes y deshabilitar la recuperación de un único elemento y quitar cualquier retención o Directiva de retención de Office 365. Tenga en cuenta que puede preparar un buzón a la vez y, a continuación, ejecutar el mismo comando en buzones de correo diferentes o crear un script de PowerShell para preparar varios buzones al mismo tiempo.

- Consulte "paso 1: recopilar información sobre el buzón" en [eliminar elementos de la carpeta elementos recuperables de buzones de correo basados en la nube en espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) para obtener instrucciones sobre cómo comprobar si la recuperación de un único elemento está habilitada o si el buzón se coloca en retención o está asignado a un Directiva de retención. 
    
- Consulte "paso 2: preparar el buzón" en [eliminar elementos de la carpeta elementos recuperables de los buzones basados en la nube en espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) para obtener instrucciones sobre cómo deshabilitar la recuperación de un único elemento. 
    
- Consulte "paso 3: quitar todas las suspensiones del buzón" en [eliminar elementos de la carpeta elementos recuperables de los buzones basados en la nube en espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) para obtener instrucciones sobre cómo quitar una directiva de retención o retención de un buzón. 

- Consulte "paso 4: quitar la retención retrasada del buzón" en [eliminar elementos de la carpeta elementos recuperables de buzones de correo basados en la nube en espera](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox) para obtener instrucciones sobre cómo quitar la retención retrasada que se coloca en el buzón de correo después de que se quite cualquier tipo de suspensión.
    
 **Importante:** Compruebe con la administración de registros o los departamentos jurídicos antes de quitar una retención o Directiva de retención. Es posible que su organización tenga una directiva que defina si un buzón de correo en espera o un incidente de derrame de datos tiene prioridad. 
  
Asegúrese de revertir el buzón a configuraciones previas después de comprobar que los datos derramados se han eliminado permanentemente. Vea los detalles en el [paso 7](#step-7-permanently-delete-the-spilled-data).

## <a name="step-7-permanently-delete-the-spilled-data"></a>Paso 7: eliminar permanentemente los datos derramados

Con las ubicaciones de buzón que recopiló y preparó en el paso 6 y la consulta de búsqueda que se creó y perfeccionó en el paso 3 para buscar mensajes de correo electrónico que contengan los datos derramados, ahora puede eliminar de forma permanente los datos derramados. Como se ha explicado anteriormente, debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online para eliminar mensajes mediante el siguiente procedimiento.
  
1. [Conexión a PowerShell de Exchange Online](https://go.microsoft.com/fwlink/?linkid=396554).
    
2. Ejecute el siguiente comando:
    
    ```
    Search-Mailbox -Identity <mailbox identity> -SearchDumpster -DeleteContent $true -SearchQuery <search query>
    ```
  
3. Vuelva a ejecutar el comando anterior para cada buzón de correo que contenga los datos derramados; para ello, reemplace el valor del parámetro Identity; por ejemplo:

    ```
    Search-Mailbox -Identity sarad@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

    ```
    Search-Mailbox -Identity janets@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

   ```
   Search-Mailbox -Identity pilarp@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
   ```
  
Como se mencionó anteriormente, también puede crear un [script de PowerShell](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) y ejecutarlo en una lista de buzones para que el script elimine los datos derramados en cada buzón.
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>Paso 8: comprobar, proporcionar una prueba de eliminación y auditoría

El último paso del flujo de trabajo para administrar un incidente de derramamiento de datos es comprobar que los datos derramados se quitaron permanentemente del buzón yendo al caso de eDiscovery y volviendo a ejecutar la misma consulta de búsqueda que se usó para eliminar los datos para confirmar que no hay resultados ar e devuelto. Después de confirmar que los datos derramados se han quitado permanentemente, puede exportar un informe e incluirlo (junto con el informe original) como una prueba de eliminación. A continuación, puede [cerrar el caso](ediscovery-cases.md#optional-step-9-close-a-case), lo que le permitirá volver a abrirlo si es que hace referencia a él en el futuro. Además, también puede revertir los buzones a su estado anterior, eliminar la consulta de búsqueda usada para encontrar los datos derramados y buscar registros de auditoría de las tareas realizadas al administrar el incidente de derrame de datos. 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>Revertir los buzones a su estado anterior

Si ha cambiado la configuración de algún buzón en el paso 6 para preparar los buzones antes de que se eliminaran los datos derramados, tendrá que revertirlos a su estado anterior. Consulte "paso 6: revertir el buzón a su estado anterior" en [eliminar elementos de la carpeta elementos recuperables de los buzones basados en la nube en suspensión](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state).
  
### <a name="deleting-the-search-query"></a>Eliminación de la consulta de búsqueda

Si las palabras clave de la consulta de búsqueda que ha creado y usado en el paso 3 contienen parte de todos los datos que se han derramado, debe eliminar la consulta de búsqueda para evitar una mayor derrame de datos.
  
1. En el centro de seguridad y cumplimiento, abra el caso de exhibición de documentos electrónicos, vaya a la página de **búsqueda** y seleccione la búsqueda de contenido adecuada.
    
2. En la página flotante, haga clic en **eliminar**.

    ![Seleccione la búsqueda y, a continuación, haga clic en eliminar en la página de control flotante.](media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a>Auditoría del proceso de investigación del derrame de datos

Puede buscar en el registro de auditoría de Office 365 las actividades de eDiscovery que se llevaron a cabo durante la investigación. También puede buscar en el registro de auditoría para devolver los registros de auditoría que se crearon cuando ejecutó el comando **Search-Mailbox-DeleteContent** para eliminar los datos derramados. Para más información, visite:

- [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md)

- [Buscar actividades de eDiscovery en el registro de auditoría](search-for-ediscovery-activities-in-the-audit-log.md)

- Consulte la sección "actividades auditadas-registro de auditoría de administración de Exchange" en [Buscar el registro de auditoría](search-the-audit-log-in-security-and-compliance.md#audited-activities) para obtener instrucciones sobre cómo buscar registros de auditoría relacionados con los cmdlets en Exchange Online.
  

