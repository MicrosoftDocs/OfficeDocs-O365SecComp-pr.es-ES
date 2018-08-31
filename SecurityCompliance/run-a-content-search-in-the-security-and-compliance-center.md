---
title: Ejecutar una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ComplianceSearch
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 61852fd9-fe8a-4880-a339-cb19ed3bff4a
description: 'Usar búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento para buscar buzones, sitios de SharePoint Online y OneDrive para las ubicaciones de negocio. '
ms.openlocfilehash: 61c6c3933a75567acb04f793cb6815322fb3fada
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536039"
---
# <a name="run-a-content-search-in-the-office-365-security-amp-compliance-center"></a>Ejecutar una búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento

Puede usar la herramienta de exhibición de documentos electrónicos de búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento para buscar elementos como correo electrónico, documentos y las conversaciones de la organización de Office 365 de mensajería instantánea. Use esta herramienta para buscar elementos en estos servicios de Office 365:
  
- Carpetas públicas y buzones de Exchange Online
    
- SharePoint Online y OneDrive para sitios profesionales
    
- Skype para conversaciones de negocios
    
- Microsoft Teams 
    
- Grupos de Office 365
    
Búsqueda de contenido es una nueva herramienta de búsqueda de exhibición de documentos electrónicos con nuevas y mejores capacidades de escalabilidad y el rendimiento. Usar búsqueda de contenido para realizar búsquedas de exhibición de documentos electrónicos muy grande. Puede buscar todos los buzones, todas las carpetas públicas de Exchange y todos los sitios de SharePoint Online y OneDrive para las cuentas de negocio en una sola búsqueda de contenido. No hay ningún límite en el número de ubicaciones de contenido que se pueden buscar. No existen límites en el número de búsquedas que se pueden ejecutar al mismo tiempo. Después de ejecutar una búsqueda de contenido, el número de ubicaciones de contenido y un número estimado de resultados de búsqueda se muestra en el panel de detalles en la página de **búsqueda de contenido** . Después de ejecutar una búsqueda puede obtener una vista previa de los resultados, obtener estadísticas de palabras clave para uno o más búsquedas, editar de forma masiva las búsquedas de contenido y exportar los resultados a un equipo local. 
  
 **Contenido**
  
[Crear una búsqueda](run-a-content-search-in-the-security-and-compliance-center.md#create)
  
[Exportar resultados de la búsqueda](run-a-content-search-in-the-security-and-compliance-center.md#export)
  
[Vista previa de los resultados de búsqueda](run-a-content-search-in-the-security-and-compliance-center.md#preview)
  
[Actualizar los resultados de búsqueda](run-a-content-search-in-the-security-and-compliance-center.md#restart)
  
[Editar una búsqueda](run-a-content-search-in-the-security-and-compliance-center.md#edit)
  
[Reintentar una búsqueda](run-a-content-search-in-the-security-and-compliance-center.md#retry)
  

  
## <a name="before-you-begin"></a>Antes de empezar

- Para información e instrucciones acerca de la creación, las consultas de búsqueda y el uso de operadores de búsqueda de tipo booleano, vea [consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md). En este artículo también contiene información acerca de la búsqueda de tipos de información confidencial y búsqueda de contenido que se comparte con personas dentro y fuera de la organización.
    
- Para tener acceso a la página de **búsqueda de contenido** para realizar búsquedas y vista previa y exportar los resultados de búsqueda, un administrador, el agente de cumplimiento o el Administrador de exhibición de documentos electrónicos debe ser miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad &amp; cumplimiento Centro. No es necesario asignar permisos de búsqueda adicionales en Exchange Online, SharePoint Online, o para OneDrive para sitios de negocio. Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).
    
- Hay algunos límites que se aplican a la búsqueda de contenido para mantener la salud y la calidad de los servicios que proporciona a las organizaciones de Office 365. En la mayoría de los casos, no se puede modificar estos límites, pero debe tener en cuenta de ellos para que estos límites se pueden tener en cuenta al planear, ejecución y solución de problemas de las búsquedas. Para obtener más información, vea [límites para la búsqueda en la seguridad de Office 365 &amp; centro de cumplimiento](limits-for-content-search.md).
    
- Vea la sección para tiempos de búsqueda estimado en función del número de buzones que se buscan en una sola búsqueda de contenido. 
    
- Como se ha indicado anteriormente, puede usar la búsqueda de contenido para buscar contenido en los grupos de Office 365 y Microsoft Teams. Esto significa que puede buscar en el buzón de correo de grupo, calendario compartido y los sitios de SharePoint asociados a un grupo de Office 365 y un Microsoft Team. Además, puede buscar las conversaciones de canal en un Microsoft Team. Para obtener información acerca de los grupos de Office 365 y Microsoft Teams, consulte:
    
  - [Obtenga información acerca de los grupos de Office 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
    
  - [Ayuda de Microsoft Teams](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
    Vea la sección para obtener sugerencias sobre la búsqueda de contenido en grupos de Office 365 y Microsoft Teams. 
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="create-a-search"></a>Crear una búsqueda
<a name="create"> </a>

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta de trabajo o escuela.
    
3. En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **Búsqueda de contenido**.
    
4. Haga clic en **Nueva**![Icono Agregar](media/O365-MDM-CreatePolicy-AddIcon.gif).
    
5. En la página **Búsqueda nueva**, escriba un nombre para la búsqueda de contenido. Este nombre debe ser único en la organización. 
    
6. Elija las ubicaciones de contenido que se va a buscar. Puede buscar los buzones de correo, sitios y las carpetas públicas en la misma búsqueda.
    
    ![Elija las ubicaciones de contenido que se va a buscar](media/da32e3f9-6cd6-4a26-8217-e97a5a7071e4.png)
  
1. **Búsqueda en todos los lugares** Seleccione esta opción para buscar todas las ubicaciones de contenido de la organización. Cuando se selecciona esta opción, puede elegir buscar todos los buzones (incluidos buzones inactivos y los buzones de correo para todos los grupos de Office 365 y Microsoft Teams), todos los SharePoint y OneDrive para sitios profesionales (que incluye los sitios para todos los grupos de Office 365 y Los equipos de Microsoft) y todas las carpetas públicas.
    
    ![Haga clic en la búsqueda en todos los lugares opción para buscar todas las ubicaciones de contenido](media/86f132f1-0a2a-4048-900c-9f219d909ef2.png)
  
2. **Selección de ubicación personalizada** Seleccione esta opción para seleccionar los buzones y los sitios que desea buscar. Si elige esta opción, tiene flexibilidad para buscar todas las ubicaciones de contenido para un servicio específico (por ejemplo, para buscar todos los buzones de Exchange) o puede buscar las ubicaciones de contenido específicas para un servicio de Office 365.
    
    Al agregar ubicaciones de contenido para buscar, tenga en cuenta lo siguiente:
    
    **Buzones**
    
  - Cuando haga clic en **Agregar**![icono Agregar](media/ITPro-EAC-AddIcon.gif) para especificar los buzones de correo de búsqueda, el selector de buzón de correo que se muestra está vacío. Este comportamiento está diseñado para mejorar el rendimiento. Para agregar destinatarios a esta lista, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda y haga clic en **búsqueda**![icono de búsqueda](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif).
    
  - Puede agregar buzones inactivos y grupos de distribución a la lista de buzones de correo a buscar. Para los grupos de distribución, se buscan los buzones de correo de los miembros del grupo. Tenga en cuenta que no se admiten grupos de distribución dinámica.
    
  - Para obtener una lista de los buzones inactivos en la organización, ejecute el comando `Get-Mailbox -InactiveMailboxOnly` en Exchange Online PowerShell. Como alternativa, puede ir a la **gobernanza de datos** \> de **retención** en la seguridad &amp; centro de cumplimiento y, a continuación, haga clic en **más**![puntos suspensivos de la barra de navegación](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **buzones inactivos**.
    
  - También puede agregar el buzón de correo que está asociado con un grupo de Office 365 o un Microsoft Team. En este caso, se busca en el buzón del equipo o grupo; no se buscan en los buzones de correo de los miembros del equipo o de grupo. Para buscar en ellos, debe agregarlos específicamente para la búsqueda.
    
  - Si no desea incluir todos los buzones a la búsqueda, seleccione **elegir buzones específicos para buscar**, pero no agregar un buzón de correo a la lista.
    
    **Sitios**
    
  - Haga clic en **Agregar**![icono Agregar](media/ITPro-EAC-AddIcon.gif) para agregar sitios a la búsqueda. Escriba la dirección URL para cada sitio que se va a buscar. La herramienta de búsqueda de contenido se valida la dirección URL y, a continuación, agregarlo a la lista de sitios que se va a buscar. 
    
  - Puede agregar la de SharePoint que está asociado con un grupo de Office 365 o un Microsoft Team. Vea la sección para obtener instrucciones sobre cómo encontrar la dirección URL para el grupo o equipo. 
    
  - Si no desea incluir todos los sitios en una búsqueda, seleccione **Elegir sitios específicos para buscar**, pero no agregar un sitio a la lista.
    
    **Carpetas públicas**
    
    Para las carpetas públicas, puede elegir buscar en todas las carpetas públicas en la organización de Exchange Online o no todas las carpetas públicas.
    
7. Haga clic en **Siguiente**.
    
8. En la página **Nueva búsqueda**, puede agregar palabras clave y condiciones para crear la consulta de búsqueda. 
    
    ![Crear una consulta de búsqueda con palabras clave y condiciones](media/1b7cf7b5-f1e1-471a-ad5c-48aad8435b00.png)
  
1. En el cuadro en **¿Qué desea nos para buscar?**, escriba una consulta de búsqueda en el cuadro. Puede especificar las palabras clave, mensaje propiedades como envían y reciben fechas, o las propiedades de documento, como los nombres de archivo o la fecha en que se modificó por última vez un documento. Puede usar una de las consultas más complejas que usan un operador booleano, como **AND**, **o**, **no**, **NEAR**o **ONEAR**. También puede buscar información confidencial (como números de la seguridad social) en los documentos o buscar documentos que se han compartido externamente. Si deja vacío el cuadro de palabra clave, todo el contenido que se encuentra en las ubicaciones de contenido especificadas se incluirán en los resultados de búsqueda. 
    
2. Puede hacer clic en la casilla de verificación **Mostrar la lista de palabras clave** y el tipo de una palabra clave en cada fila. Si lo hace, las palabras clave en cada fila están conectadas por el operador **o** en la consulta de búsqueda que se crea. 
    
    ![Puede escribir una palabra clave o la fase de palabra clave en una fila en la lista de palabras clave](media/aea1a361-639d-4a82-8c3c-48645ef3fc05.png)
  
    ¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave. Esto puede ayudarle a identificar rápidamente las palabras clave son los más (y menos) eficaces. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para obtener más información acerca de las estadísticas de búsqueda, vea [Ver las estadísticas de palabra clave para los resultados de la búsqueda de contenido](view-keyword-statistics-for-content-search.md).
    
    Vea la sección para obtener instrucciones sobre el uso de la lista de palabras clave. 
    
3. Haga clic en **Comprobar consulta si hay errores ortográficos** para comprobar su consulta para caracteres no admitidos y operadores booleanos que es posible que no se puso en mayúsculas. Caracteres no admitidos a menudo están ocultos y normalmente un error de búsqueda o devuelvan resultados inesperados. Para obtener más información acerca de los caracteres no admitidos que se deben comprobar, vea [comprobar la consulta de búsqueda de contenido para errores](check-your-content-search-query-for-errors.md).
    
4. En **condiciones**, agregar condiciones a una consulta de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda de palabras clave que se crean y ejecutan cuando se inicia la búsqueda. Una condición lógicamente está conectada a la consulta de palabras clave (especificada en el cuadro de palabra clave) por el operador **y** . Esto significa que los elementos tengan que satisfacer la consulta de palabra clave y la condición que se deben incluir en los resultados. Se trata de cómo ayudar a condiciones para limitar los resultados. 
    
||
|:-----|
|Para obtener más información sobre cómo crear una consulta de búsqueda y las condiciones de uso, vea [consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido ](keyword-queries-and-search-conditions.md). |
   
9. Haga clic en **Búsqueda** para guardar la configuración de la búsqueda e iniciar la búsqueda. 
    
    Se inicia la búsqueda. Una vez completada la búsqueda, se muestra la siguiente información en el panel de detalles.
    
    ![Estadísticas de búsqueda se muestran en el panel de detalles de la búsqueda de contenido seleccionado](media/2046bb5e-f4cb-4ba7-b7fc-8e5e53dae567.png)
  
1. La fecha y hora en que se ejecutó por última vez la búsqueda.
    
2. El número (y tamaño total) de los elementos que se han encontrado que coincide con la consulta de búsqueda. Algunos ejemplos de tipos de elemento son mensajes de correo electrónico, los elementos de calendario y documentos. Si un elemento contiene varias instancias de una palabra clave que se busca, se sólo cuenta una vez en el número total de elementos. Por ejemplo, si está buscando las palabras "stock" o "sugerencia" y un mensaje de correo electrónico contiene tres instancias de la palabra "stock", se sólo cuenta una vez en el campo de **los elementos** . 
    
3. El número y el tamaño total de los elementos no indizados en las ubicaciones de contenido que se desea buscar. El número de elementos sin indizar que no cumplen con los criterios de búsqueda se incluirá en las estadísticas de búsqueda que se muestran en el panel de detalles. Si un elemento sin indizar las coincidencias de la búsqueda de consulta (debido a que otras propiedades de mensaje o el documento cumple con los criterios de búsqueda), no se incluirán en el número estimado de elementos sin indizar. Sin embargo, si se excluye un elemento sin indizar por los criterios de búsqueda, no se incluirán en la estimación de los elementos sin indizar.
    
4. El número de cada tipo de ubicación de contenido que se realizó la búsqueda. Para los buzones de correo, tenga en cuenta que los buzones de archivo se incluyen en el número total de buzones que se desea buscar. En el ejemplo anterior, se han buscado cuatro buzones de usuario y el buzón de archivo para cada uno de estos usuarios está habilitado. Por este motivo ocho buzones se citan en las estadísticas de búsqueda.
    
5. Vínculos para obtener una vista previa de la búsqueda de resultados o ejecutan la búsqueda de nuevo para actualizar las estadísticas de búsqueda.
    
    Si es necesario, haga clic en **Actualizar**![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif) para actualizar la información en el panel de detalles para la búsqueda seleccionada. 
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="export-search-results"></a>Exportar resultados de búsqueda
<a name="export"> </a>

Después de ejecuta correctamente una búsqueda, puede exportar los resultados de búsqueda a un equipo local. Al exportar los resultados de correo electrónico, se descargan en el equipo como archivos PST. Al exportar contenido de SharePoint y OneDrive para sitios de negocio, se exportan copias de los documentos de Office nativos. También existen otros documentos e informes que se incluyen con los resultados de búsqueda exportado. Para obtener más información, vea [resultados de búsqueda de exportación de la seguridad de Office 365 &amp; centro de cumplimiento](export-search-results.md).
  
## <a name="preview-search-results"></a>Obtener una vista previa de los resultados de la búsqueda
<a name="preview"> </a>

Después de una búsqueda se completa correctamente, puede obtener una vista previa de los resultados de búsqueda. Hay un número de límites de relacionadas con la vista previa de los resultados de la búsqueda de contenido. Para obtener más información, vea [límites para la búsqueda en la seguridad de Office 365 &amp; centro de cumplimiento](limits-for-content-search.md). Tenga en cuenta que los elementos no indizados no están disponibles para obtener una vista previa.
  
1. En la página de **búsqueda de contenido** , seleccione una búsqueda. 
    
2. En el panel de detalles, en **Resultados**, haga clic en **Vista previa de los resultados de la búsqueda**. Se abre la página **Vista previa de los resultados de la búsqueda**, que contiene una lista de los elementos de resultados de la búsqueda. 
    
    Puede hacer clic en un encabezado de columna para ordenar los resultados en función del asunto, tipo, remitente o la fecha en que se recibió un elemento en el buzón de origen.
    
3. Haga clic en un elemento para obtener una vista previa.
    
    El elemento se abre en el panel de vista previa.
    
4. Si no se admite un tipo de archivo de vista previa o para descargar una copia de un documento, haga clic en **descargar el archivo original** para descargar a su equipo local. Para .aspx páginas Web, la dirección URL de la página se incluye, aunque puede que no tenga permisos para tener acceso a la página. 
    
> [!NOTE]
> Si obtener una vista previa de los resultados de búsqueda para una búsqueda que se ejecutó por última vez hace más de 7 días, se le pedirá que se debe actualizar los resultados de búsqueda. Se vuelve a ejecutar la búsqueda para obtener los resultados más recientes que cumplen la consulta de búsqueda. 
  
### <a name="file-types-that-can-be-previewed"></a>Tipos de archivo que se pueden obtener una vista previa

Puede obtener una vista previa de tipos de archivo admitidos en el panel de vista previa. Si no se admite un tipo de archivo, debe descargar una copia del archivo en el equipo local para verlo. Los siguientes tipos de archivo son compatibles y se pueden obtener una vista previa en la página de **vista previa de resultados de búsqueda** . 
  
- .txt, .html, .mhtml
    
- EML
    
- .doc, .docx, .docm
    
- .pptm, .pptx
    
- .pdf
    
Además, se admiten los siguientes tipos de archivo contenedor. Puede ver la lista de archivos en el contenedor en el panel de vista previa.
  
- .zip
    
- .gzip
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="update-search-results"></a>Actualizar los resultados de búsqueda
<a name="restart"> </a>

Al actualizar los resultados de una búsqueda de contenido existente, se vuelve a ejecutar la consulta de búsqueda en todas las ubicaciones de contenido especificadas. Es el motivo obvio para actualizar los resultados de búsqueda obtener los datos más recientes.
  
1. En la página **Búsqueda de contenido**, seleccione la búsqueda cuyos resultados quiere actualizar. 
    
2. En el panel de detalles, en **Resultados**, haga clic en **Actualizar resultados de la búsqueda**.
    
    Se muestra un mensajes de estado que indica que se están recuperando los resultados. Cuando finalice la búsqueda, se actualizó la información se muestra en **los resultados** en el panel de detalles. Tenga en cuenta que la fecha en el campo **Buscar en** el panel de detalles se actualiza a la fecha y hora actuales. Para actualizar la información de la lista de búsquedas de contenido, haga clic en **Actualizar**![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif).
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="edit-a-search"></a>Editar una búsqueda
<a name="edit"> </a>

Puede cambiar los buzones de origen y la consulta de búsqueda para una búsqueda de contenido existente.
  
1. En la página de **búsqueda de contenido** , seleccione una búsqueda. 
    
2. En el panel de detalles, en **Consulta**, haga clic en **Editar búsqueda**.
    
3. En la página **ubicaciones** , puede cambiar qué buzones de correo, grupos, sitios de SharePoint o OneDrive para sitios profesionales para buscar. También puede seleccionar (o desactive) para buscar todas las carpetas públicas en Exchange. 
    
4. En la página de **consulta** , puede editar la consulta de búsqueda. 
    
5. Para iniciar la búsqueda revisada, haga clic en **búsqueda** en las **fuentes** o el **ubicaciones de** página. 
    
    Se inicia la búsqueda revisada. Cuando finalice la búsqueda, se muestran en el panel de detalles los resultados estimados para la búsqueda revisada.
    
## <a name="retry-a-search"></a>Reintentar una búsqueda
<a name="retry"> </a>

Si una búsqueda devuelve algún error, no es necesario volver a buscar en todas las ubicaciones de contenido. Puede volver a ejecutar la búsqueda para que sólo las ubicaciones de contenido que no se pudo son búsqueda nuevamente. Para volver a buscar todas las ubicaciones de contenido, puede actualizar los resultados de búsqueda.
  
1. En la página de **contenido de búsqueda** , seleccione la búsqueda que contiene las ubicaciones de contenido que desea volver a buscar. 
    
2. En el panel de detalles, en **Error**, haga clic en **Reintentar la búsqueda**.
    
    Se muestra un mensajes de estado que indica que se están recuperando los resultados. Una vez finalizada la búsqueda, se actualizó la información se muestra en **los resultados** en el panel de detalles. Tenga en cuenta que la fecha en el campo **Buscar en** el panel de detalles se actualiza a la fecha y hora actuales. Para actualizar la información de la lista de búsquedas, haga clic en **Actualizar**![icono de actualización](media/O365-MDM-Policy-RefreshIcon.gif).
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="more-information"></a>Más información
<a name="moreinfo"> </a>

Aquí es obtener más información acerca de las búsquedas de contenido.
  
[Límites y rendimiento](run-a-content-search-in-the-security-and-compliance-center.md#limits)
  
[Elementos sin indizar](run-a-content-search-in-the-security-and-compliance-center.md#unindexeditems)
  
[Los equipos de Microsoft y los grupos de Office 365](run-a-content-search-in-the-security-and-compliance-center.md#teams)
  
[OneDrive para la Empresa](run-a-content-search-in-the-security-and-compliance-center.md#onedrive)
  
[Consultas de búsqueda](run-a-content-search-in-the-security-and-compliance-center.md#queries)
  
[Buscar buzones inactivos](run-a-content-search-in-the-security-and-compliance-center.md#inactivemailboxes)
  
[Varios](run-a-content-search-in-the-security-and-compliance-center.md#misc)
  
[(Volver al principio)](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
 **Límites y rendimiento**
  
- Para obtener una descripción de los límites que se aplican a la característica de búsqueda de contenido, vea [límites para la búsqueda en la seguridad de Office 365 &amp; centro de cumplimiento](limits-for-content-search.md).
    
- Microsoft recopila información de rendimiento para las búsquedas de contenido ejecutar por todas las organizaciones de Office 365. Mientras la complejidad de la consulta de búsqueda puede afectar a los tiempos de búsqueda, busca en el factor más importante que afecta a cuánto tomar las búsquedas es el número de buzones de correo. Aunque Microsoft no proporciona un contrato de nivel de servicio para los tiempos de búsqueda, en la siguiente tabla se enumera los tiempos de búsqueda promedio para una búsqueda de contenido en función del número de buzones que se incluyen en la búsqueda.
    
|**Número de buzones de correo**|**Tiempo medio de búsqueda**|
|:-----|:-----|
|100  <br/> |30 segundos  <br/> |
|1,000  <br/> |45 segundos  <br/> |
|10,000  <br/> |4 minutos  <br/> |
|25.000  <br/> |10 minutos  <br/> |
|50.000  <br/> |20 minutos  <br/> |
|100,000  <br/> |25 minutos  <br/> |
   

  
 **Elementos sin indizar**
  
- Como elementos sin indizar, explicados anteriormente en ubicaciones de contenido que se buscan se incluyen en los resultados de búsqueda estimado. Si un elemento sin indizar las coincidencias de la búsqueda de consulta (debido a que otras propiedades de mensaje o el documento cumple con los criterios de búsqueda), no se incluirán en el número estimado de elementos sin indizar. Si se excluye un elemento sin indizar por los criterios de búsqueda, también no se incluirán en el número estimado de elementos sin indizar. Para obtener más información, vea [elementos sin indizar en búsqueda de contenido](https://go.microsoft.com/fwlink/p/?LinkId=780739).
    

  
 **Los equipos de Microsoft y los grupos de Office 365**
  
- Microsoft Teams se basan en grupos de Office 365. Por lo tanto, la búsqueda de ellos es muy similar. Tenga en cuenta lo siguiente al buscar contenido en Microsoft Teams y grupos de Office 365.
    
  - Para buscar contenido que se encuentra en Microsoft Teams y grupos de Office 365, tendrá que especificar el buzón de correo y el sitio de SharePoint que están asociados con un equipo o grupo.
    
  - Ejecute el cmdlet **Get-UnifiedGroup** en Exchange Online para ver las propiedades de un Team Microsoft o un grupo de Office 365. Esto es una buena forma de obtener la dirección URL para el sitio que está asociado con un equipo o un grupo. Por ejemplo, el siguiente comando muestra las propiedades seleccionadas de un grupo de Office 365 con nombre de equipo directivo superior: 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroup** , tiene que tener asignado el rol de los destinatarios con permiso de vista de Exchange Online o ser miembro de un grupo de roles ha asignado el rol de los destinatarios con permiso de vista. 
  
  - Cuando se busca en el buzón de un usuario, cualquier Team Microsoft Office 365 grupo que el usuario es un miembro de no ser buscar en o. De forma similar, cuando se busca un Team Microsoft o un grupo de Office 365, sólo el buzón de correo de grupo y sitios de grupo que especifique se busca; no se buscan en los buzones y OneDrive para las cuentas de negocio de miembros del grupo a menos que los agregue explícitamente a la búsqueda.
    
  - Para obtener una lista de los miembros de un Team Microsoft o un grupo de Office 365, puede ver las propiedades en el **principal \> grupos** página en el centro de administración de Office 365. Como alternativa, puede ejecutar el siguiente comando en Exchange Online PowerShell: 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroupLinks** , tiene que tener asignado el rol de los destinatarios con permiso de vista de Exchange Online o ser miembro de un grupo de roles ha asignado el rol de los destinatarios con permiso de vista. 
  
  - Las conversaciones que forman parte de un canal de Microsoft Teams se almacenan en el buzón de correo que está asociado con el Team de Microsoft. De forma similar, los archivos que comparten los miembros del equipo en un canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, se debe agregar el buzón de correo de Microsoft Team y el sitio de SharePoint como una ubicación de contenido para buscar archivos y las conversaciones en un canal.
    
  - 
    
    Como alternativa, las conversaciones que forman parte de la lista de Chat en Microsoft Teams se almacenan en el buzón de Exchange Online de los usuarios que participan en la conversación. Y los archivos que un usuario comparte en las conversaciones de Chat se almacenan en la OneDrive para la cuenta de la empresa del usuario que comparte el archivo. Por lo tanto, se debe agregar los buzones de usuario individual y OneDrive para las cuentas de negocio como ubicaciones de contenido para buscar las conversaciones y archivos en la lista de Chat.
    
    > [!NOTE]
    > Los usuarios que participan en las conversaciones que forman parte de la lista de Chat en Microsoft Teams deben tener un buzón de Exchange Online (basada en la nube) en orden para buscar las conversaciones de chat. Eso es porque las conversaciones que forman parte de la lista de Chat se almacenan en los buzones de correo basados en la nube de los participantes de chat. Si un participante de chat no tiene un buzón de Exchange Online, no podrá buscar las conversaciones de chat. Por ejemplo, en una implementación híbrida de Exchange, los usuarios con un buzón de correo local podrían ser capaz de participar en conversaciones que forman parte de la lista de Chat en Microsoft Teams. En este caso, sin embargo el contenido de estos conversación no que admite búsquedas debido a que los usuarios no dispongan de buzones de correo basados en la nube. 
  
  - Todos los canales Microsoft Team o equipo contiene un sitio Wiki para colaboración y toma de notas. El contenido de Wiki se guarda automáticamente en un archivo con un formato .mht. Este archivo se almacena en la biblioteca de documentos de datos de Wiki de los equipos en el sitio de SharePoint del equipo. Puede usar la herramienta de búsqueda de contenido para buscar el sitio Wiki mediante la especificación de sitio de SharePoint del equipo como para buscar la ubicación del contenido. 
    
    > [!NOTE]
    > La capacidad de buscar el sitio Wiki para un canal o Microsoft Team (al buscar en sitios de SharePoint del grupo) se lanzó en 22 de junio de 2017. Páginas wiki que se han guardado o actualizado en que la fecha o después están disponibles que se desea buscar. Las páginas Wiki guardado por última vez o actualizado antes de dicha fecha no están disponibles para la búsqueda. 
  

  
 **OneDrive para la Empresa **
  
- Para recopilar una lista de las direcciones URL para el OneDrive para sitios de profesionales de la organización, vea [crear una lista de todas las ubicaciones de OneDrive en la organización](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). La secuencia de comandos en este artículo, crea un archivo de texto que contiene una lista de todos los OneDrive para sitios de negocio. Para ejecutar este script, debe instalar y usar el Shell de administración de SharePoint Online. Asegúrese de que se anexará la dirección URL de dominio de Mi sitio de la organización a cada OneDrive para el sitio de negocio que se va a buscar. Éste es el dominio que contiene todos los su OneDrive para la empresa; Por ejemplo, `https://contoso-my.sharepoint.com`. Este es un ejemplo de una dirección URL para OneDrive un usuario para el sitio de negocio: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
    

  
 **Consultas de búsqueda**
  
- Mantener en cuenta lo siguiente cuando se usa la lista de palabras clave para crear una consulta de búsqueda.
    
  - Se debe seleccionar la casilla de verificación **Mostrar la lista de palabras clave** y, a continuación, escriba cada palabra clave en una fila independiente para crear una consulta de búsqueda donde las palabras clave (o frases de palabras clave) de cada fila están conectados por el operador **OR** . Si sólo se pega una lista de palabras clave en el cuadro de palabra clave o presione la tecla **ENTRAR** después de escribir una palabra clave, no estar conectados por el operador **o** . A continuación presentamos ejemplo incorrecto y el correcto de la adición de una lista de palabras clave. 
    
    **Incorrecto**
    
    ![La manera incorrecta dar formato a una lista de palabras clave (pegar la lista en el cuadro de palabra clave)](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **Correcto**
    
    ![La forma correcta para dar formato a una lista de palabras clave (mediante la selección de casilla de verificación y, a continuación, Pegar lista)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
  - Puede preparar también una lista de palabras clave o frases de palabras clave en un archivo de Excel o un archivo de texto sin formato y, a continuación, copie y pegue la lista en a la lista de palabras clave. Para ello, se debe seleccionar la casilla de verificación **Mostrar la lista de palabras clave** . A continuación, haga clic en la primera fila en la lista de palabras clave y pegue la lista. Cada línea del archivo de Excel o el texto se pegará en separar la fila en la lista de palabras clave. 
    
  - Después de crear una consulta mediante la lista de palabras clave, es una buena idea para comprobar la sintaxis de consulta de búsqueda (en el panel de detalles de la búsqueda seleccionada) para realizar la búsqueda de consulta es lo que pretende. En la consulta de búsqueda que se muestra en la **consulta** en el panel de detalles, las palabras clave están separadas por el texto **(c:s)**. Esto indica que las palabras clave están conectadas por el operador **OR** . De forma similar, si la consulta de búsqueda incluye condiciones, las palabras clave y las condiciones están separadas por el texto **(c: c)**. Esto indica que las palabras clave están conectadas a las condiciones por el operador **y** . Este es un ejemplo de la consulta de búsqueda (que se muestra en el panel de detalles) que se produce cuando se usa la lista de palabras clave y una condición. 
    
    ![Ejemplo de la consulta que se crea cuando se usa la lista de palabras clave y una condición](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
  - Si tiene una consulta de búsqueda que contiene palabras clave para los caracteres no ingleses (por ejemplo, caracteres chinos), debe usar el cmdlet **Set-ComplianceSearch** para configurar la propiedad de idioma para la búsqueda de contenido. Cuando se crea una búsqueda de contenido mediante la interfaz gráfica de usuario en la seguridad &amp; centro de cumplimiento, el idioma predeterminado es neutro. 
    
    ¿Cómo se puede saber si necesita cambiar la configuración de idioma para una búsqueda de contenido? Si está seguro de ubicaciones de contenido contienen los caracteres que no sean inglés que está buscando, pero la búsqueda no devuelve ningún resultado, la configuración de idioma puede ser la causa.
    
    Para cambiar la configuración de idioma de una búsqueda de contenido existente, ejecute el siguiente comando en seguridad &amp; PowerShell de centro de cumplimiento:
    
  ```
  Set-ComplianceSearch <name of content search> -Language <culture code value>
  ```

    Por ejemplo, para cambiar la configuración de idioma para chino, utilice `zh-CN` para el valor de código de referencia cultural. Después de cambiar la configuración de idioma, debe volver a ejecutar la búsqueda. Para obtener una lista de valores de código de referencia cultural posibles, vea [CultureInfo (clase)](https://go.microsoft.com/fwlink/p/?LinkID=184859). Para las búsquedas de contenido, se recomienda que utilice códigos de referencia cultural de dos partes para el valor de la configuración de idioma; Por ejemplo, `ja-JP` y no `ja`.
    

  
 **Buscar buzones inactivos**
  
Como se ha indicado anteriormente, puede buscar buzones inactivos en una búsqueda de contenido. A continuación presentamos algunas cosas que debe tener en cuenta al buscar buzones inactivos.
  
- Si una búsqueda de contenido incluye un buzón de usuario y ese buzón, a continuación, se convierte en inactivo, continuará la búsqueda de contenido buscar el buzón de correo inactivo cuando vuelva a ejecutar la búsqueda después de que quede inactiva.
    
- En algunos casos, un usuario puede tener un buzón de correo activa y un buzón inactivo que tienen la misma dirección SMTP. En este caso, se buscarán sólo el buzón específico que seleccione como una ubicación para una búsqueda de contenido. En otras palabras, si el buzón de un usuario se agrega a una búsqueda, no se puede suponer que se buscará en sus buzones activos e inactivos; se buscarán sólo el buzón de correo que se agregue explícitamente a la búsqueda.
    
- Se recomienda encarecidamente que no tenga un buzón activo y el buzón de correo inactivo con la misma dirección SMTP. Si necesita volver a usar la dirección SMTP que está asignada actualmente a un buzón de correo inactivo, se recomienda que recuperar el buzón de correo inactivo o restaurar el contenido de un buzón inactivo en un buzón de correo activo (o el archivo de un buzón de active) y, a continuación, elimine el buzón de correo inactivo. Para obtener más información, vea uno de los siguientes temas:
    
  - [Recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md)
    
  - [Restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md)
    
  - [Eliminar un buzón inactivo en Office 365](delete-an-inactive-mailbox.md)
    

  
 **Varios**
  
- Creado en la página de **búsqueda de contenido** en la seguridad de las búsquedas de contenido &amp; centro de cumplimiento no se muestran en la **exhibición de documentos electrónicos en contexto &amp; suspensión** página en el centro de administración de Exchange. Esto es debido a que la arquitectura de búsqueda de contenido y los objetos de búsqueda se crean en la seguridad &amp; centro de cumplimiento son completamente diferentes de la característica de exhibición de documentos electrónicos en contexto en Exchange Online. 
    
    Por la misma razón, las búsquedas creadas en la página de **búsqueda de contenido** no se muestran en la página de **las búsquedas** de un caso de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento. 
    
- ¿Cuál es la diferencia entre reiniciar y volver a intentar una búsqueda? Cuando se reinicia una búsqueda, se buscan vuelva a todas las ubicaciones de contenido que se especifican en la búsqueda en una nueva búsqueda de vista previa. Sin embargo, cuando se vuelva a intentar una búsqueda, se buscan sólo las ubicaciones de contenido que no se pudo cuando se ejecutó por última vez la búsqueda nuevamente.
   

