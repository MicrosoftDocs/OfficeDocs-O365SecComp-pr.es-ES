---
title: exhibición de documentos electrónicos solución serie datos pérdidas escenario - búsqueda y depuración
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: Usar herramientas de exhibición de documentos electrónicos y búsqueda de Office 365 para administrar y responder a un incidente de pérdidas de datos en su organización.
ms.openlocfilehash: 2bf17923408bd5cf8325d27a38595331d169906f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535704"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>serie de soluciones de exhibición de documentos electrónicos: escenario de pérdidas de datos - búsqueda y depuración

 **¿Qué es pérdidas de datos y por qué debería interesarle?** Pérdidas de datos es cuando se libera un documento confidencial en un entorno que no se confía. Cuando se detecta un incidente de pérdidas de datos, es importante evaluar rápidamente el tamaño y las ubicaciones de las pérdidas, se examinan las actividades del usuario alrededor de él y, a continuación, permanentemente purgar los datos derramados desde el sistema. 
  
## <a name="data-spillage-scenario"></a>Escenario de pérdidas de datos

Eres un responsable de seguridad de la información de cliente potencial de Contoso. Se le informa de una situación de pérdidas de datos donde un empleado sin darse cuenta comparte un documento altamente confidencial con varias personas a través de correo electrónico. Desea evaluar rápidamente que recibió este documento interna y externamente. Una vez identificado, que le gustaría compartir casos conclusiones con otros investigadores para revisar y, a continuación, quitar permanentemente los datos de Office 365. Una vez finalizada la investigación, que desea generar un informe con la prueba de eliminación permanente y otros detalles del caso para cualquier futuras referencias.
  
### <a name="scope-of-this-article"></a>Ámbito de este artículo

Este documento proporciona una lista de instrucciones acerca de cómo quitar permanentemente un mensaje de Office 365 para que no se puede tener acceso o recuperables. Para eliminar un mensaje y realizar recuperables hasta que expire el período de retención de elementos eliminados, consulte [Buscar y eliminar mensajes de correo electrónico en la organización de Office 365](search-for-and-delete-messages-in-your-organization.md).
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>Flujo de trabajo para la administración de incidentes de pérdidas de datos

Este es un procedimiento para administrar un incidente de pérdidas de datos:

![El flujo de trabajo de 8-paso para la administración de incidentes de pérdidas de datos](media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[(Opcional) Paso 1: Administrar quién puede tener acceso a las mayúsculas y minúsculas y establecer los límites de cumplimiento](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[Paso 2: Crear un caso de exhibición de documentos electrónicos](#step-2-create-an-ediscovery-case)<br/>
[Paso 3: Búsqueda de los datos derramados](#step-3-search-for-the-spilled-data)<br/>
[Paso 4: Revisar y validar las conclusiones mayúsculas y minúsculas](#step-4-review-and-validate-case-findings)<br/>
[Paso 5: Usar el mensaje de registro de seguimiento para comprobar los datos derramados cómo se ha compartido](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[Paso 6: Preparar los buzones de correo](#step-6-prepare-the-mailboxes)<br/>
[Paso 7: Eliminar permanentemente los datos derramados](#step-7-permanently-delete-the-spilled-data)<br/>
[Paso 8: Comprobar, proporcionar una prueba de eliminación y de auditoría](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>Cosas que debe saber antes de empezar

- Cuando un buzón se encuentra en suspensión, un mensaje eliminado permanece en la carpeta elementos recuperables hasta que expire el período de retención o se libera la suspensión. [Paso 6](#step-6-prepare-the-mailboxes) se describe cómo quitar la suspensión de los buzones de correo. Compruebe con la administración de registros o departamentos legales antes de quitar la suspensión. Su organización puede tener una directiva que define si un buzón de correo en espera o un incidente de pérdidas de datos tiene prioridad. 
    
- Para controlar qué buzones de usuario una investigación de pérdidas de datos puede buscar y administrar quién puede tener acceso a las mayúsculas y minúsculas, puede establecer los límites de cumplimiento de normas y crear un grupo de funciones personalizado, que se describe en el [paso 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries). Para ello, tiene que ser un miembro del grupo de roles de administración de la organización o tener asignado el rol de administración de roles. Si se o en el Administrador de la organización ya tiene los límites de cumplimiento del conjunto, puede omitir el paso 1.
    
- Para crear un caso, debe ser miembro del grupo de roles de administrador de exhibición de documentos electrónicos o ser miembro de un grupo de funciones personalizado que ha asignado el rol de administración de casos. Si no es un miembro, pida a un administrador de Office 365 para [Agregar para el grupo de roles de administrador de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).
    
- Para eliminar los datos que se vuelcan en su organización, debe usar el comando [Search-Mailbox-DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps) en Exchange Online PowerShell. Además, para usar el parámetro *DeleteContent* , también tiene que ser un miembro de un grupo de roles en Exchange Online que ha asignado la función de exportación de importación de buzón de correo. Vea la sección "Adición de una función a un grupo de roles" en [Administrar grupos de roles](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx).
    
- Para buscar las actividades de exhibición de documentos electrónicos de registro de auditoría de Office 365 en el paso 8, auditoría debe estar activada para su organización. Puede buscar las actividades que se realizaron en los últimos 90 días. Para obtener más información acerca de cómo habilitar y usar la auditoría, consulte la sección [auditoría el proceso de investigación de pérdidas de datos](#auditing-the-data-spillage-investigation-process) en el paso 8. 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>(Opcional) Paso 1: Administrar quién puede tener acceso a las mayúsculas y minúsculas y establecer los límites de cumplimiento

En función de su organización práctica, deberá controlar quién puede tener acceso el caso de exhibición de documentos electrónicos que se usa para investigar un incidente de pérdidas de datos y establecer los límites de cumplimiento. La forma más sencilla de hacerlo es agregar investigadores como miembros del grupo de roles existentes en el centro de cumplimiento y seguridad de Office 365 y, a continuación, agregue el grupo de roles como un miembro de la caja de exhibición de documentos electrónicos. Para obtener información acerca de los grupos de funciones de exhibición de documentos electrónicos integrados y cómo agregar miembros a un caso de exhibición de documentos electrónicos, consulte [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).
  
También puede crear un nuevo grupo de funciones que se alinea con las necesidades de su organización. Por ejemplo, quizás desee un grupo de investigadores de pérdidas de datos en la organización para obtener acceso y colaborar en todos los casos de pérdidas de datos. Puede hacerlo mediante la creación de un grupo de roles "Investigación de pérdidas de datos", la asignación de las funciones adecuadas (exportación, RMS descifrar, revisión, vista previa, búsqueda de cumplimiento y administración de casos), agregar los investigadores de pérdidas de datos para el grupo de roles y, a continuación, agregar el grupo de funciones como un miembro de la caja de exhibición de documentos electrónicos de pérdidas de datos. Para obtener instrucciones detalladas acerca de cómo hacer esto, vea [establecer los límites de cumplimiento para investigaciones de exhibición de documentos electrónicos en Office 365](set-up-compliance-boundaries.md) . 
  
## <a name="step-2-create-an-ediscovery-case"></a>Paso 2: Crear un caso de exhibición de documentos electrónicos

Un caso de exhibición de documentos electrónicos proporciona una forma eficaz para administrar su investigación de pérdidas de datos. Puede agregar a miembros al grupo de funciones que creó en el paso 1, agregue el grupo de roles como un miembro de nuevo un caso de exhibición de documentos electrónicos, realizar búsquedas de iterativas para buscar los datos derramados, exportar un informe para compartir, realizar un seguimiento del estado de las mayúsculas y minúsculas y, a continuación, hacer referencia a los detalles de la c ase si es necesario. Considere la posibilidad de establecer una convención de nomenclatura para los casos de exhibición de documentos electrónicos usados para incidentes de pérdidas de datos y proporcione tanta información como lo haría en el nombre del caso y la descripción para que pueda buscar y hacer referencia a en el futuro si es necesario.
  
Para crear un nuevo caso, puede usar la exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento. Vea "Crear un nuevo caso" en [los casos de exhibición de documentos electrónicos en el centro de cumplimiento y seguridad de Office 365](ediscovery-cases.md#step-2-create-a-new-case).
  
## <a name="step-3-search-for-the-spilled-data"></a>Paso 3: Búsqueda de los datos derramados

Ahora que ha creado un caso y acceso administrado, puede usar las mayúsculas y minúsculas para buscar de forma iterativa para encontrar los datos derramados e identificar los buzones de correo que contienen los datos derramados. Va a usar la misma consulta de búsqueda que usa para buscar los mensajes de correo electrónico para eliminar esos mismos mensajes en el [paso 7](#step-7-permanently-delete-the-spilled-data).
  
Para crear un contenido búsquedas asociada a un caso de exhibición de documentos electrónicos, consulte "Crear y ejecutar que una búsqueda de contenido asociada con un caso" en [los casos de exhibición de documentos electrónicos en el centro de cumplimiento y seguridad de Office 365](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case).
  
 **Importante:** Las palabras clave que usar en la consulta de búsqueda pueden contener los datos derramados real que se va a buscar. Por ejemplo, si busca documentos que contienen un número de la seguridad social y usa la TI como palabra clave de búsqueda, debe eliminar la consulta posteriormente para evitar pérdidas de otros. Vea la [eliminación de la consulta de búsqueda](#deleting-the-search-query) en el paso 8. 
  
## <a name="step-4-review-and-validate-case-findings"></a>Paso 4: Revisar y validar las conclusiones mayúsculas y minúsculas

Después de crear una búsqueda de contenido, debe revisar y validar que la búsqueda de resultados y compruebe que constan sólo de los mensajes de correo electrónico que se deben eliminar. En una búsqueda de contenido, puede obtener una vista previa de un muestreo aleatorio de 1.000 mensajes de correo electrónico sin necesidad de exportar los resultados de búsqueda para evitar aún más pérdidas de datos. Puede leer más información sobre las limitaciones de vista previa en [límites para la búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento](limits-for-content-search.md).
  
Si tiene más de 1.000 buzones de correo o de más de 100 mensajes de correo electrónico por buzón de correo para revisar, puede dividir la búsqueda inicial en varias búsquedas mediante el uso de palabras clave adicionales o condiciones como remitente o destinatario o intervalo de fechas y revisar los resultados de cada búsqueda de forma individual. Asegúrese de que tenga en cuenta hacia abajo todas las consultas de búsqueda que se utilizarán al eliminar los mensajes en el [paso 7](#step-7-permanently-delete-the-spilled-data).

Si se asigna una licencia de Office 36 E5 de una custodia o el usuario final, puede examinar hasta 10.000 resultados de búsqueda a la vez mediante Office 365 avanzada exhibición de documentos electrónicos. Si hay más de 10.000 mensajes de correo electrónico para revisar, puede dividir la consulta de búsqueda por intervalo de fechas y revise cada resultado individualmente como búsqueda, los resultados se ordenan por fecha. En Avanzadas exhibición de documentos electrónicos, puede marcar los resultados de búsqueda mediante la característica de **etiqueta como** en el panel de vista previa y filtrar los resultados de búsqueda mediante la etiqueta que con la etiqueta. Esto es útil cuando colaborar con un revisor secundario. Mediante las herramientas de análisis adicionales en Avanzadas exhibición de documentos electrónicos, como el reconocimiento óptico de caracteres, los subprocesos de correo electrónico y codificación predictivo, rápidamente puede procesar y revise miles de mensajes y etiqueta de otra revisión. Consulte [el programa de instalación rápida de documentos electrónicos avanzada de Office 365](quick-setup-for-advanced-ediscovery.md).

Cuando encuentre un mensaje de correo electrónico que contiene datos derramados, compruebe a los destinatarios del mensaje para determinar si se ha compartido externamente. Para realizar un seguimiento más un mensaje, se pueden recopilar información del remitente y el intervalo de fechas por lo que puede usar los registros de seguimiento de mensajes, que se describe en el [paso 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared).

Una vez haya comprobado que los resultados de búsqueda, es posible que desee compartir sus conclusiones con otros usuarios para una revisión secundaria. Las personas que asigna el caso en el paso 1 pueden revisar el contenido de casos de exhibición de documentos electrónicos y exhibición de documentos electrónicos avanzada y aprobar conclusiones mayúsculas y minúsculas. También puede generar un informe sin exportar el contenido real. También puede utilizar este mismo informe como una prueba de eliminación, que se describe en el [paso 8](#step-8-verify-provide-a-proof-of-deletion-and-audit).
  
 **Para generar un informe de estadístico:**
  
1. Vaya a la página de **búsqueda** en el caso de exhibición de documentos electrónicos y haga clic en la búsqueda que se desea generar un informe para. 
    
2. En la página emergente, haga clic en **más > Exportar informe**.
 
      Se abrirá la página de informe de exportación.

    ![Seleccione la búsqueda y, a continuación, haga clic en más > Exportar el informe en la página emergente](media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. Seleccione **todos los elementos, los que tienen formato no reconocido, incluidos se cifran, o no estaban indizados por otros motivos** y, a continuación, haga clic en **Generar informe**.

4. En el caso de exhibición de documentos electrónicos, haga clic en **Exportar** para mostrar la lista de trabajos de exportación. Puede que tenga que hacer clic en **Actualizar** para actualizar la lista para mostrar el trabajo de exportación que acaba de crear.

5. Haga clic en el trabajo de exportación y, a continuación, haga clic en **Descargar** informe en la página emergente.
 
    ![En la página Exportar, haga clic en la exportación y, a continuación, haga clic en "Descargar informe"](media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

El informe de **Resumen de exportación** contiene el número de ubicaciones que se encuentra con los resultados y el tamaño de los resultados de búsqueda. Puede usar esto en comparación con el informe generado después de la eliminación y proporcionar como una prueba de eliminación. El informe de **resultados** contiene un resumen más detallado de los resultados de búsqueda, incluidos el asunto, remitente, los destinatarios, si se ha leído el correo electrónico, las fechas y tamaño de cada mensaje. Si cualquiera de los detalles de este informe contiene los datos derramados real, asegúrese de eliminar permanentemente el archivo Results.csv cuando se termine la investigación.

Para obtener más información acerca de la exportación de informes, consulte [exportar un informe de búsqueda de contenido](export-a-content-search-report.md).
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>Paso 5: Usar el mensaje de registro de seguimiento para comprobar los datos derramados cómo se ha compartido

Para investigar si se ha compartido el correo electrónico con datos derramados, opcionalmente, puede consultar los registros de seguimiento de mensaje con la información del remitente y la información de intervalo de fecha que recopiló en el paso 4. Tenga en cuenta que el período de retención para el seguimiento de mensajes es de 30 días de datos en tiempo real y de 90 días para los datos históricos.
  
Puede usar el seguimiento de mensajes en el centro de cumplimiento y seguridad o use los cmdlets correspondientes en Exchange Online PowerShell. Es importante tener en cuenta que el seguimiento de mensajes no ofrece garantías completas en la integridad de los datos devueltos. Para obtener más información acerca del uso de seguimiento de mensajes, consulte: 
  
- [Mensaje de seguimiento en la seguridad de Office 365 &amp; centro de cumplimiento](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [Nuevo seguimiento de mensajes de seguridad de Office 365 &amp; centro de cumplimiento](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>Paso 6: Preparar los buzones de correo

Después de revisar y validar que los resultados de búsqueda contiene sólo los mensajes que se deben eliminar, debe recopilar una lista de las direcciones de correo electrónico de los buzones afectados a usar en el paso 7 cuando se ejecuta el comando **Search-Mailbox-DeleteContent** . También debe preparar los buzones de correo antes de que puede eliminar permanentemente los mensajes de correo electrónico dependiendo de si está habilitada la recuperación de elemento único en los buzones de correo que contienen los datos derramados o si cualquiera de los buzones de correo están en espera.
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>Obtener una lista de direcciones de los buzones de correo con datos derramados

Hay dos formas para recopilar una lista de direcciones de correo electrónico de buzones de correo con datos derramados.

**Opción 1: Obtener una lista de direcciones de los buzones de correo con datos derramados**

1. Abra el caso de exhibición de documentos electrónicos, vaya a la página de **búsqueda** y seleccione la búsqueda de contenido apropiada. 
    
2. En la página emergente, haga clic en **los resultados de la vista**.
    
3. En la lista desplegable **resultados individuales** , haga clic en **estadísticas de búsqueda**.
    
4. En la lista desplegable **tipo** , haga clic en **ubicaciones principales**.
    
    ![Obtener una lista de buzones de correo que contienen resultados de búsqueda en la página ubicaciones principales en las estadísticas de búsqueda](media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    Se muestra una lista de buzones de correo que contienen resultados de búsqueda. También se muestra el número de elementos en cada buzón de correo que coinciden con la consulta de búsqueda.
    
5. Copiar la información de la lista y guardar en un archivo o haga clic en **Descargar** para descargar la información a un archivo CSV. 
    
**Opción 2: Obtener las ubicaciones de buzón de correo desde el informe de exportación**

Abra el informe de resumen de exportación que ha descargado en el [paso 4](#step-4-review-and-validate-case-findings). En la primera columna en el informe, aparece la dirección de correo electrónico de cada buzón de correo en **ubicaciones**.
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>Preparar los buzones de correo, por lo que puede eliminar los datos derramados

Si se habilita la recuperación de un solo elemento o un buzón de correo se pondrá en espera, un mensaje permanentemente eliminado (depurado) se conservan en la carpeta elementos recuperables. Por lo que antes de que se puede purgar datos derramados, necesita comprobar las configuraciones de buzón de correo existentes y deshabilitar la recuperación de un solo elemento y eliminar cualquier suspensión o la directiva de retención de Office 365. Tenga en cuenta que puede preparar un buzón de correo a la vez y, a continuación, ejecute el mismo comando en los buzones de correo diferentes o crear un script de PowerShell para preparar varios buzones al mismo tiempo.

- Vea "paso 1: recopilar información acerca del buzón" en [Eliminar elementos en la carpeta de buzones de correo basados en la nube en retención de elementos recuperables](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) para obtener instrucciones sobre cómo comprobar si está habilitada la recuperación de elemento único o si el buzón de correo se pondrá en espera o se asigna a un Directiva de retención. 
    
- Vea "paso 2: preparar el buzón de correo" en [Eliminar elementos en la carpeta de buzones de correo basados en la nube en retención de elementos recuperables](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) para obtener instrucciones acerca de cómo deshabilitar la recuperación de elemento único. 
    
- Vea "paso 3: quitar todas las suspensiones desde el buzón de correo" en [Eliminar elementos en la carpeta de buzones de correo basados en la nube en retención de elementos recuperables](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) para obtener instrucciones sobre cómo quitar una directiva de retención o suspensión de un buzón de correo. 
    
 **Importante:** Compruebe con la administración de registros o departamentos legales antes de quitar una directiva de retención o suspensión. Su organización puede tener una directiva que define si un buzón de correo en espera o un incidente de pérdidas de datos tiene prioridad. 
  
No olvide revertir el buzón de correo a las configuraciones anteriores después de comprobar que los datos derramados se ha eliminado de forma permanente. Vea los detalles en el [paso 7](#step-7-permanently-delete-the-spilled-data).

## <a name="step-7-permanently-delete-the-spilled-data"></a>Paso 7: Eliminar permanentemente los datos derramados

Uso de las ubicaciones de buzón de correo que se recopilan y preparado en el paso 6 y la consulta de búsqueda que se creó y refinada en el paso 3 para buscar los mensajes de correo electrónico que contienen los datos derramados, ahora puede permanentemente eliminar los datos derramados. Como se explica anteriormente, se debe asignar el rol de buzón de correo importar exportar en Exchange Online para eliminar los mensajes mediante el siguiente procedimiento.
  
1. [Conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
2. Ejecute el comando siguiente:
    
    ```
    Search-Mailbox -Identity <mailbox identity> -SearchDumpster -DeleteContent $true -SearchQuery <search query>
    ```
  
3. Vuelva a ejecutar el comando anterior para cada buzón de correo que contiene los datos derramados, reemplazando el valor para el parámetro Identity; Por ejemplo:

    ```
    Search-Mailbox -Identity sarad@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

    ```
    Search-Mailbox -Identity janets@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

   ```
   Search-Mailbox -Identity pilarp@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
   ```
  
Como se señaló anteriormente, también puede crear un [script de powershell](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) y ejecutarla en una lista de buzones de correo para que la secuencia de comandos elimina los datos derramados en cada buzón de correo.
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>Paso 8: Comprobar, proporcionar una prueba de eliminación y de auditoría

Es el último paso en el flujo de trabajo para administrar un incidente de pérdidas de datos comprobar que los datos derramados permanentemente se ha quitado del buzón de correo en el caso de exhibición de documentos electrónicos y volver a ejecutar la misma consulta de búsqueda que se usó para eliminar esos datos para confirmar que no hay ar de los resultados de la e devuelto. Después de confirmar que los datos derramados se ha quitado de forma permanente, puede exportar un informe e incluir (junto con el informe original) como una prueba de eliminación. A continuación, se puede [Cerrar el caso](ediscovery-cases.md#optional-step-9-close-a-case), que le permitirá volver a abrirlo si ha referirse a ella en el futuro. Además, también puede revertir los buzones de correo a su estado anterior, eliminar la consulta de búsqueda que se utiliza para encontrar los datos derramados y para los registros de las tareas de auditoría realiza al administrar la incidencia de pérdidas de datos de búsqueda. 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>Revertir los buzones de correo a su estado anterior

Si cambia cualquier configuración de buzón de correo en el paso 6 para preparar los buzones de correo antes de que se ha eliminado los datos derramados, necesita, vuelva a su estado anterior. Vea "paso 5: revertir el buzón de correo a su estado anterior" en [Eliminar elementos en la carpeta de buzones de correo basados en la nube en retención de elementos recuperables](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-5-revert-the-mailbox-to-its-previous-state).
  
### <a name="deleting-the-search-query"></a>Eliminación de la consulta de búsqueda

Si las palabras clave en la consulta de búsqueda que crea y se usa en el paso 3 contiene algunos o todos los datos reales derramados, debe eliminar la consulta de búsqueda para evitar aún más las pérdidas de datos.
  
1. En el centro de cumplimiento y seguridad, abra el caso de exhibición de documentos electrónicos, vaya a la página de **búsqueda** y seleccione la búsqueda de contenido apropiada.
    
2. En la página emergente, haga clic en **Eliminar**.

    ![Seleccione la búsqueda y, a continuación, haga clic en Eliminar en la página emergente](media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a>El proceso de investigación de pérdidas de datos de auditoría

Puede buscar el registro de auditoría de Office 365 para las actividades de exhibición de documentos electrónicos que se realizaron durante la investigación. También puede buscar el registro de auditoría para devolver los registros de auditoría que se crearon cuando ejecutó el comando **Search-Mailbox-DeleteContent** para eliminar los datos derramados. Para obtener más información, vea:

- [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md)

- [Buscar actividades de exhibición de documentos electrónicos en el registro de auditoría de Office 365](search-for-ediscovery-activities-in-the-audit-log.md)

- Vea la sección "Auditar actividades - registro de auditoría de administración de Exchange" en [el registro de auditoría en el centro de cumplimiento de seguridad de Office 365 y de búsqueda](search-the-audit-log-in-security-and-compliance.md#audited-activities) para obtener instrucciones acerca de cómo buscar registros de auditoría relacionados con la ejecución de cmdlets en Exchange Online.
  

