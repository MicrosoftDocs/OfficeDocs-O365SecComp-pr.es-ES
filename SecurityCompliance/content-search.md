---
title: Búsqueda de contenido en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/28/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: Usar la búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento para buscar contenido en los buzones de correo, sitios de SharePoint Online, OneDrive cuentas, Microsoft Teams, grupos de Office 365 y Skype para conversaciones de negocios. Puede usar las consultas de búsqueda de palabra clave y las condiciones para restringir los resultados de búsqueda de búsqueda. A continuación, puede obtener una vista previa y exportar los resultados de búsqueda. Búsqueda de contenido también es una herramienta eficaz para buscar contenido que puede estar relacionado con una solicitud de asunto GDPR datos.
ms.openlocfilehash: 11e96c6a11dd66c0095b7c624413e9e39036d8d6
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782087"
---
# <a name="content-search-in-office-365"></a>Búsqueda de contenido en Office 365

Puede usar la herramienta de exhibición de documentos electrónicos de búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento para buscar elementos en contexto como correo electrónico, documentos y las conversaciones de la organización de Office 365 de mensajería instantánea. Use esta herramienta para buscar elementos en estos servicios de Office 365:
  
- Carpetas públicas y buzones de Exchange Online
    
- Sitios de SharePoint Online y OneDrive para las cuentas de negocio
    
- Skype para conversaciones de negocios
    
- Microsoft Teams 
    
- Grupos de Office 365
    
Después de ejecutar una búsqueda de contenido, el número de ubicaciones de contenido y un número estimado de resultados de búsqueda se muestra en el perfil de búsqueda. Puede ver también rápidamente estadísticas, como las ubicaciones de contenido que tienen la mayoría de los elementos que coinciden con la consulta de búsqueda. Después de ejecutar una búsqueda, puede obtener una vista previa de los resultados o exportarlos a un equipo local.


## <a name="create-a-new-search"></a>Crear una nueva búsqueda

Para tener acceso a la página de **búsqueda de contenido** para ejecutar búsquedas y vista previa y exportar los resultados de búsqueda, un administrador, el agente de cumplimiento o el Administrador de exhibición de documentos electrónicos debe ser miembro del grupo de roles de administrador de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento. Para obtener más información, vea [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Iniciar sesión con su dirección de correo electrónico de Office 365 y la contraseña. 
    
3. En la seguridad &amp; centro de cumplimiento, haga clic en **búsqueda &amp; investigación** \> **búsqueda de contenido**.
    
4. En la página de **búsqueda** , haga clic en la flecha junto a ![icono Agregar](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nueva búsqueda**. 
    
    ![La nueva lista desplegable de búsqueda](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    Se puede elegir entre las opciones siguientes:
    
  - **Búsqueda guiada** - esta opción inicia a un asistente que le guiará a través de la creación de la búsqueda. La interfaz de usuario para seleccionar las ubicaciones de contenido y crear la consulta de búsqueda son los mismos que la opción de **búsqueda nueva** . 
    
  - **Nueva búsqueda** - esta opción muestra una interfaz de usuario actualizada para crear una nueva búsqueda. Esto es la opción predeterminada si hace clic en **Buscar de nuevo**.
    
  - **Buscar por identificador de lista** - esta opción le permite buscar mensajes de correo electrónico específicos y otros elementos del buzón de correo con una lista de identificadores de Exchange. Para crear una búsqueda en la lista ID (anteriormente denominada una búsqueda de destino), enviar un archivo (CSV) de valores separados por comas que identifica los elementos de buzón específico para buscar. Para obtener instrucciones, vea [preparación de un archivo CSV para una lista de identificadores de búsqueda de contenido en Office 365](csv-file-for-an-id-list-content-search.md).
    
    En el resto de los pasos descritos en este procedimiento se siga el flujo de trabajo de búsqueda nueva de forma predeterminada.
    
5. En la lista desplegable, haga clic en **nueva búsqueda** . 
    
6. En la **consulta de búsqueda**, especifique lo siguiente.
    
    ![Especificar las palabras clave, las condiciones y ubicaciones de búsqueda](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
- **Palabras clave para buscar** - tipo de una búsqueda de consulta en el cuadro **palabras clave** . Puede especificar las palabras clave, mensaje propiedades como envían y reciben fechas, o las propiedades de documento, como los nombres de archivo o la fecha en que se modificó por última vez un documento. Puede usar una de las consultas más complejas que usan un operador booleano, como **AND**, **OR**, **no**y **NEAR**. También puede buscar información confidencial (como números de la seguridad social) en los documentos o buscar documentos que se han compartido externamente. Si deja vacío el cuadro de palabra clave, todo el contenido que se encuentra en las ubicaciones de contenido especificadas se incluirán en los resultados de búsqueda.
    
    Como alternativa, puede hacer clic en la casilla de verificación **Mostrar la lista de palabras clave** y el tipo de una palabra clave en cada fila. Si lo hace, las palabras clave en cada fila están conectadas mediante un operador lógico ( **c:s**) que es una funcionalidad similar para el operador **OR** en la consulta de búsqueda que se crea. 
    
    ¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave. Esto puede ayudarle a identificar rápidamente las palabras clave son los más (y menos) eficaces. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para obtener más información acerca de las estadísticas de búsqueda, vea [Ver las estadísticas de palabra clave para los resultados de la búsqueda de contenido](view-keyword-statistics-for-content-search.md).
    
- **Condiciones** - puede agregar condiciones de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda que se crean y ejecutan cuando se inicia la búsqueda. Una condición lógicamente está conectada a la consulta de palabras clave (especificada en el cuadro de palabra clave) por un operador lógico ( **c: c**) que es una funcionalidad similar para el operador **y** . Esto significa que los elementos tengan que satisfacer la consulta de palabras clave y una o varias condiciones que se deben incluir en los resultados. Se trata de cómo ayudar a condiciones para limitar los resultados. Para obtener una lista y descripción de las condiciones que puede utilizar en una consulta de búsqueda, vea la sección "Las condiciones de búsqueda" en [las consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md#search-conditions).
    
- **Ubicaciones** - elija las ubicaciones para buscar contenidas.
    
  - **Todas las ubicaciones de** -Use esta opción para buscar todas las ubicaciones de contenido de la organización. Esto incluye el correo electrónico en todos los buzones de Exchange (incluidos todos los buzones de correo inactivos, buzones de correo para todos los grupos de Office 365, los buzones de correo para todos los Teams Microsoft), todos los Skype para las conversaciones de negocio, todos los SharePoint y OneDrive para sitios de negocio (incluidos los sitios para todos los grupos de Office 365 y Microsoft Teams) y los elementos de todas las carpetas públicas de Exchange.
    
  - **Ubicaciones específicas** : Use esta opción para buscar en las ubicaciones de contenido específicas. Puede buscar todas las ubicaciones de contenido para un servicio específico de Office 365 (como la búsqueda de todos los buzones de Exchange o buscar en todos los sitios de SharePoint) o puede buscar ubicaciones específicas en cualquiera de los servicios de Office 365 que se muestran. 
    
    ![Interfaz de usuario para elegir las ubicaciones de contenido para buscar](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
    Tenga en cuenta que también se pueden agregar grupos de distribución a la lista de buzones de Exchange para buscar. Para los grupos de distribución, se buscan los buzones de correo de los miembros del grupo. Tenga en cuenta que no se admiten grupos de distribución dinámica.
    
    **Importante:** Al buscar en todas las ubicaciones de los buzones o buzones de correo específicos, datos de MyAnalytics y otras aplicaciones de Office 365 que ha guardado en buzones de usuario se incluirán al exportar los resultados de una búsqueda de contenido. Estos datos no se incluirá en los resultados de búsqueda estimado y no estará disponible para la vista previa. Sólo se incluirá cuando exporta y descargar los resultados de búsqueda; consulte [Exportar datos desde MyAnalytics y otras aplicaciones de Office 365](#exporting-data-from-myanalytics-and-other-office-365-applications) en la sección "Más información acerca de la búsqueda de contenido". 
    
7. Después de configurar la consulta de búsqueda, haga clic en **Guardar &amp; ejecutar**.
    
8. En la página **Guardar la búsqueda** , escriba un nombre para la búsqueda y una descripción opcional que ayuda a identificar la búsqueda. Tenga en cuenta que el nombre de la búsqueda debe ser único en la organización. 
    
9. Haga clic en **Guardar** para iniciar la búsqueda. 
    
    Después de guardar y ejecutar la búsqueda, se muestran los resultados devueltos por la búsqueda en el panel de resultados. Dependiendo de cómo haya configurado la configuración de vista previa, los resultados de búsqueda para mostrar o tiene que hacer clic en **vista previa de resultados** para verlos. Vea la sección siguiente para obtener información detallada. 
    
Para obtener acceso a esta búsqueda de contenido nuevo o tener acceso a otras búsquedas de contenido que aparecen en la página de **contenido de búsqueda** , seleccione la búsqueda y, a continuación, haga clic en **Abrir**. 
  
Para borrar los resultados o crear una nueva búsqueda, haga clic en ![icono Agregar](media/O365-MDM-CreatePolicy-AddIcon.gif) **nueva búsqueda**. 

  
## <a name="preview-search-results"></a>Obtener una vista previa de los resultados de la búsqueda

Hay dos opciones de configuración para obtener una vista previa de los resultados de búsqueda. Después de ejecutar un nuevo una nueva búsqueda o abrir una búsqueda existente, haga clic en ** resultados individuales ** para ver la configuración de vista previa siguiente: 
  
![Configuración de los resultados de búsqueda de vista previa](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. **Obtener una vista previa los resultados automáticamente** - esta opción muestra los resultados de búsqueda después de una ejecución de una búsqueda de este tipo.
    
2. **Obtener una vista previa los resultados manualmente** - esta opción muestra los marcadores de posición en el panel de resultados de búsqueda y muestra el botón **vista previa de resultados** que tiene que hacer clic para mostrar los resultados de búsqueda. Ésta es la configuración predeterminada; ayuda a mejorar el rendimiento de búsqueda no automáticamente mostrando los resultados de búsqueda cuando se abre una búsqueda existente. 
    
Hay algunos límites relacionados con cuántos elementos están disponibles para la vista preliminar. Para obtener más información, vea [límites para la búsqueda en la seguridad de Office 365 &amp; centro de cumplimiento](limits-for-content-search.md). 
  
Para obtener una lista de tipos de archivo admitidos que se puede obtener una vista previa, vea [obtener una vista preliminar de los resultados de búsqueda](#previewing-search-results) en la sección "Más información acerca de la búsqueda de contenido". Si no se admite un tipo de archivo de vista previa o para descargar una copia de un documento, haga clic en **descargar el archivo original** para descargar a su equipo local. Para .aspx páginas Web, la dirección URL de la página se incluye, aunque puede que no tenga permisos para tener acceso a la página. 
  
Tenga en cuenta también que los elementos no indizados no están disponibles para obtener una vista previa.
  
## <a name="view-information-and-statistics-about-a-search"></a>Ver la información y estadísticas sobre una búsqueda

Después de crear y ejecutar una búsqueda de contenido, puede ver estadísticas sobre los resultados de búsqueda estimado. Esto incluye un resumen de los resultados de búsqueda, las estadísticas de consulta, como el número de ubicaciones de contenido con los elementos que coinciden con la consulta de búsqueda y el nombre de las ubicaciones de contenido que tienen los elementos más coincidentes. Puede mostrar estadísticas para las búsquedas de contenido de uno o más. Esto le permite para comparar los resultados para varias búsquedas de forma rápida y tomar decisiones acerca de la eficacia de las consultas de búsqueda.
  
También puede descargar las estadísticas de búsqueda y palabras clave a un archivo CSV. Esto le permite usar las características de ordenación y filtradas en Excel para comparar los resultados y preparar informes para los resultados de búsqueda.
  
Para ver las estadísticas de búsqueda:
  
1. En la página de **búsqueda de contenido** en la seguridad &amp; centro de cumplimiento, haga clic en **Abrir** y, a continuación, haga clic en la búsqueda que desee ver la estadística de. 
    
2. Sobre la marcha página, haga clic en **Abrir consulta**. 
    
3. En la lista desplegable **resultados individuales** , haga clic en **perfil de búsqueda**.
    
4. En la lista desplegable **tipo** , haga clic en una de las siguientes opciones según las estadísticas de búsqueda que desee ver. 
    
  - **Resumen** : muestra las estadísticas para cada tipo de ubicaciones de contenido que desea buscado. Esto el número de ubicaciones de contenido que contiene los elementos que coinciden con la consulta de búsqueda, el contenido y el número total y el tamaño de los elementos de resultados de búsqueda. Ésta es la configuración predeterminada.
    
  - **Consultas** - muestra las estadísticas acerca de la consulta de búsqueda. Esto incluye el tipo de ubicación de contenido son aplicables a las estadísticas de consulta, parte de la consulta de búsqueda las estadísticas son aplicables para (tenga en cuenta que **principal** indica que la consulta de búsqueda completa), el número de las ubicaciones de contenido que contienen los elementos que coinciden con la consulta de búsqueda y el número total y tamaño y los elementos que se han encontrado (en la ubicación del contenido especificada) que coinciden con la consulta de búsqueda. Tenga en cuenta que también se muestran las estadísticas de los elementos sin indizar (también denominados elementos indizados parcialmente). Sin embargo, sólo los elementos indizados parcialmente desde los buzones de correo se incluyen en las estadísticas. Elementos indizados parcialmente desde SharePoint y OneDrive no se incluyen en las estadísticas.
    
  - **Ubicaciones principales** : muestra las estadísticas sobre el número de elementos que coinciden con la consulta de búsqueda en cada ubicación del contenido que se realizó la búsqueda. Se muestran las ubicaciones de la parte superior de 1.000.
    
Para obtener información más detallada acerca de las estadísticas de búsqueda, vea [Ver las estadísticas de palabra clave para los resultados de la búsqueda de contenido](view-keyword-statistics-for-content-search.md).
  
  
## <a name="export-search-results"></a>Exportar resultados de búsqueda

Después de ejecuta correctamente una búsqueda, puede exportar los resultados de búsqueda a un equipo local. Al exportar los resultados de correo electrónico, se pueden descargar en el equipo como los archivos PST o como los mensajes individuales (archivos .msg). Al exportar contenido de sitios de SharePoint y OneDrive, se exportan copias de los documentos de Office nativos. También existen otros documentos e informes que se incluyen con los resultados de búsqueda exportado. También puede exportar el informe de resultados de búsqueda y no los elementos reales.
  
Para exportar los resultados de búsqueda:
  
1. En la página de **búsqueda de contenido** en la seguridad &amp; centro de cumplimiento, haga clic en **Abrir** y, a continuación, haga clic en la búsqueda que se va a exportar los resultados de búsqueda para. 
    
2. Sobre la marcha página, haga clic en ![icono de resultados de búsqueda de exportación](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **más**y, a continuación, haga clic en **exportar los resultados**. Tenga en cuenta que también puede exportar un informe de resultados de búsqueda.
    
3. Rellene las secciones en la página **Exportar resultados**. Asegúrese de usar la barra de desplazamiento para ver todas las opciones de exportación. 
    
Para obtener instrucciones más detalladas y consejos para solucionar problemas, consulte:
  
- [Exportar los resultados de búsqueda de la seguridad de Office 365 &amp; centro de cumplimiento](export-search-results.md)
    
- [Exportar un informe de búsqueda de contenido](export-a-content-search-report.md)
    

  
## <a name="more-information-about-content-search"></a>Para obtener más información acerca de la búsqueda de contenido

Consulte las siguientes secciones para obtener más información acerca de las búsquedas de contenido.
  
[Límites de búsqueda de contenido](#content-search-limits)
  
[Creación de una consulta de búsqueda](#building-a-search-query)
  
[Búsqueda de cuentas de OneDrive](#searching-onedrive-accounts)
  
[Buscar en los equipos de Microsoft y los grupos de Office 365](#searching-microsoft-teams-and-office-365-groups)
  
[Buscar buzones inactivos](#searching-inactive-mailboxes)
  
[Obtener una vista previa de los resultados de búsqueda](#previewing-search-results)
  
[Elementos indizados parcialmente](#partially-indexed-items)
  
[Exportación de datos de MyAnalytics y otras aplicaciones de Office 365](#exporting-data-from-myanalytics-and-other-office-365-applications)
  
### <a name="content-search-limits"></a>Límites de búsqueda de contenido

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
  
### <a name="building-a-search-query"></a>Creación de una consulta de búsqueda

Para obtener información detallada acerca de la creación de una consulta de búsqueda, utilizando operadores de búsqueda booleanos y condiciones de búsqueda y búsqueda de tipos de información confidencial y contenido compartido con usuarios de fuera de la organización, vea consultas de palabra clave [y las condiciones de búsqueda Búsqueda de contenido ](keyword-queries-and-search-conditions.md).
  
Mantener en cuenta lo siguiente cuando se usa la lista de palabras clave para crear una consulta de búsqueda.
  
- Se debe seleccionar la casilla de verificación **Mostrar la lista de palabras clave** y, a continuación, escriba cada palabra clave en una fila independiente para crear una consulta de búsqueda donde las palabras clave (o frases de palabras clave) de cada fila están conectados por el operador **OR** . Si sólo se pega una lista de palabras clave en el cuadro de palabra clave o presione la tecla **ENTRAR** después de escribir una palabra clave, no estar conectados por el operador **o** . A continuación presentamos ejemplo incorrecto y el correcto de la adición de una lista de palabras clave. 
    
    **Incorrecto**
    
    ![La manera incorrecta dar formato a una lista de palabras clave (pegar la lista en el cuadro de palabra clave)](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **Correcto**
    
    ![La forma correcta para dar formato a una lista de palabras clave (mediante la selección de casilla de verificación y, a continuación, Pegar lista)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- Puede preparar también una lista de palabras clave o frases de palabras clave en un archivo de Excel o un archivo de texto sin formato y, a continuación, copie y pegue la lista en a la lista de palabras clave. Para ello, se debe seleccionar la casilla de verificación **Mostrar la lista de palabras clave** . A continuación, haga clic en la primera fila en la lista de palabras clave y pegue la lista. Cada línea del archivo de Excel o el texto se pegará en separar la fila en la lista de palabras clave. 
    
- Después de crear una consulta mediante la lista de palabras clave, es una buena idea para comprobar la sintaxis de consulta de búsqueda para realizar la consulta de búsqueda es lo que pretende. En la consulta de búsqueda que se muestra en la **consulta** en el panel de detalles, las palabras clave están separadas por el texto **(c:s)**. Esto indica que las palabras clave están conectadas mediante un operador lógico una funcionalidad similar para el operador **OR** . De forma similar, si la consulta de búsqueda incluye condiciones, las palabras clave y las condiciones están separadas por el texto **(c: c)**. Esto indica que las palabras clave están conectadas a las condiciones con un operador lógico una funcionalidad similar a **y** operador. Este es un ejemplo de la consulta de búsqueda (que se muestra en el panel de detalles) que se produce cuando se usa la lista de palabras clave y una condición. 
    
    ![Ejemplo de la consulta que se crea cuando se usa la lista de palabras clave y una condición](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- Cuando se ejecuta una búsqueda de contenido, Office 365 comprueba automáticamente la consulta de búsqueda de caracteres no admitidos y operadores booleanos que es posible que no se puso en mayúsculas. Caracteres no admitidos a menudo están ocultos y normalmente un error de búsqueda o devuelvan resultados inesperados. Para obtener más información acerca de los caracteres no admitidos que se deben comprobar, vea [comprobar la consulta de búsqueda de contenido para errores](check-your-content-search-query-for-errors.md).
    
- Si tiene una consulta de búsqueda que contiene palabras clave para los caracteres no ingleses (por ejemplo, caracteres chinos), haga clic en **consulta idioma-país o región**![icono de idioma-país o región de consulta de búsqueda de contenido](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) y seleccione un valor de código de referencia cultural del idioma nacional de la búsqueda. Tenga en cuenta que el idioma o la región predeterminada es neutra. ¿Cómo se puede saber si necesita cambiar la configuración de idioma para una búsqueda de contenido? Si está seguro de ubicaciones de contenido contienen los caracteres que no sean inglés que está buscando, pero la búsqueda no devuelve ningún resultado, la configuración de idioma puede ser la causa. 
  
### <a name="searching-onedrive-accounts"></a>Búsqueda de cuentas de OneDrive

- Para obtener una lista de las direcciones URL para los sitios de OneDrive en la organización, vea [crear una lista de todas las ubicaciones de OneDrive en la organización](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Esta secuencia de comandos en este artículo, crea un archivo de texto que contiene una lista de todos los sitios de OneDrive. Para ejecutar este script, debe instalar y usar el Shell de administración de SharePoint Online. Asegúrese de que se anexará la dirección URL de dominio de Mi sitio de la organización para cada sitio de OneDrive para la que desea buscar. Éste es el dominio que contiene su de OneDrive; Por ejemplo, `https://contoso-my.sharepoint.com`. Este es un ejemplo de una dirección URL para el sitio de un usuario OneDrive: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
    
    En el caso poco frecuente que se ha cambiado el nombre de entidad de seguridad de usuario (UPN) de una persona, también se cambiará la dirección URL de su ubicación de OneDrive para incorporar el UPN nuevo. En este caso, tendrá que modificar una búsqueda de contenido mediante la adición OneDrive para la nueva dirección URL del usuario y eliminar la antigua.
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a>Buscar en los equipos de Microsoft y los grupos de Office 365

Puede buscar en el buzón de correo que está asociado con un grupo de Office 365 o un Microsoft Team. Debido a que Microsoft Teams se basan en grupos de Office 365, la búsqueda de ellos es muy similar. En ambos casos, se busca en el buzón del equipo o grupo; no se buscan en los buzones de correo de los miembros del equipo o de grupo. Para buscar en ellos, debe agregarlos específicamente para la búsqueda.
  
Tenga en cuenta lo siguiente al buscar contenido en Microsoft Teams y grupos de Office 365.
  
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
    
- Como alternativa, las conversaciones que forman parte de la lista de Chat en Microsoft Teams se almacenan en el buzón de Exchange Online de los usuarios que participan en la conversación. Y los archivos que un usuario comparte en las conversaciones de Chat se almacenan en la OneDrive para la cuenta de la empresa del usuario que comparte el archivo. Por lo tanto, se debe agregar los buzones de usuario individual y OneDrive para las cuentas de negocio como ubicaciones de contenido para buscar las conversaciones y archivos en la lista de Chat.
    
    > [!NOTE]
    > Los usuarios que participan en las conversaciones que forman parte de la lista de Chat en Microsoft Teams deben tener un buzón de Exchange Online (basada en la nube) en orden para buscar las conversaciones de chat. Eso es porque las conversaciones que forman parte de la lista de Chat se almacenan en los buzones de correo basados en la nube de los participantes de chat. Si un participante de chat no tiene un buzón de Exchange Online, no podrá buscar las conversaciones de chat. Por ejemplo, en una implementación híbrida de Exchange, los usuarios con un buzón de correo local podrían ser capaz de participar en conversaciones que forman parte de la lista de Chat en Microsoft Teams. En este caso, sin embargo el contenido de estos conversación no que admite búsquedas debido a que los usuarios no dispongan de buzones de correo basados en la nube. 
  
- Todos los canales Microsoft Team o equipo contiene un sitio Wiki para colaboración y toma de notas. El contenido de Wiki se guarda automáticamente en un archivo con un formato .mht. Este archivo se almacena en la biblioteca de documentos de datos de Wiki de los equipos en el sitio de SharePoint del equipo. Puede usar la herramienta de búsqueda de contenido para buscar el sitio Wiki mediante la especificación de sitio de SharePoint del equipo como para buscar la ubicación del contenido. 
    
    > [!NOTE]
    > La capacidad de buscar el sitio Wiki para un canal o Microsoft Team (al buscar en sitios de SharePoint del grupo) se lanzó en 22 de junio de 2017. Páginas wiki que se han guardado o actualizado en que la fecha o después están disponibles que se desea buscar. Las páginas Wiki guardado por última vez o actualizado antes de dicha fecha no están disponibles para la búsqueda. 
 
- Información de resumen para las reuniones y las llamadas en un canal de Microsoft Teams también se almacenan en los buzones de los usuarios que marcó en la reunión o la llamada. Esto significa que puede usar la búsqueda de contenido para buscar estos registros de resumen. Información de resumen incluye: 
  - Fecha, hora de inicio, hora de finalización y duración de una reunión o llamada

  - La fecha y hora en que se unió a cada participante o la reunión o llamada de la izquierda

  - Llamadas enviadas al correo de voz

  - Llamadas no respondidas o perdidas

  - Transferencias de llamada, que se representan como dos llamadas independientes

  Tenga en cuenta que puede tardar hasta 8 horas de reunión y resumen registros de llamadas para que estén disponibles que se desea buscar.

  En los resultados de búsqueda, se identifican los resúmenes de reunión como **reunión** en el **campo de tipo**; resúmenes de llamada son identificados como **llamadas**. Además, las conversaciones que forman parte de un chats de canal y 1xN de los equipos son identificadas como **mensajería instantánea** en el campo **tipo** .
  
  ![Se identifican las reuniones de los equipos, las llamadas y chats 1xN en el campo tipo](media/O365-ContentSearch-Teams-MessageKind.png)

- Puede usar la propiedad de correo electrónico de **tipo** o la condición de búsqueda de **tipo de mensaje** para buscar contenido en Microsoft Teams específicamente. 
  - Para usar la propiedad **Kind** como parte de la consulta de búsqueda de palabra clave, en el cuadro **palabras clave** de una consulta de búsqueda, escriba `kind:microsoftteams`.

    ![Usar el tipo: microsoftteams en el cuadro palabras clave](media/O365-ContentSearch-Teams-Keywords.png)
  
  - Para utilizar una condición de búsqueda, agregar la condición de **tipo de mensaje** y use el valor `microsoftteams`. 

    ![Utilice la condición de tipo de mensaje con el valor microsoftteams.](media/O365-ContentSearch-Teams-MessageKindCondition.png)

Tenga en cuenta que las condiciones están conectadas lógicamente a la consulta de palabra clave por el operador **y** . Es decir, un elemento debe coincidir con la consulta de palabra clave y la condición de búsqueda que se devolverán en los resultados de búsqueda. Para obtener más información, vea la sección "Instrucciones para usar condiciones" en [consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)

  
### <a name="searching-inactive-mailboxes"></a>Buscar buzones inactivos

Puede buscar buzones inactivos en una búsqueda de contenido. Para obtener una lista de los buzones inactivos en la organización, ejecute el comando `Get-Mailbox -InactiveMailboxOnly` en Exchange Online PowerShell. Como alternativa, puede ir a la **gobernanza de datos** \> de **retención** en la seguridad &amp; centro de cumplimiento y, a continuación, haga clic en **más**![puntos suspensivos de la barra de navegación](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **buzones inactivos**.
  
A continuación presentamos algunas cosas que debe tener en cuenta al buscar buzones inactivos.
  
- Si una búsqueda de contenido incluye un buzón de usuario y ese buzón, a continuación, se convierte en inactivo, continuará la búsqueda de contenido buscar el buzón de correo inactivo cuando vuelva a ejecutar la búsqueda después de que quede inactiva.
    
- En algunos casos, un usuario puede tener un buzón de correo activa y un buzón inactivo que tienen la misma dirección SMTP. En este caso, se buscarán sólo el buzón específico que seleccione como una ubicación para una búsqueda de contenido. En otras palabras, si el buzón de un usuario se agrega a una búsqueda, no se puede suponer que se buscará en sus buzones activos e inactivos; se buscarán sólo el buzón de correo que se agregue explícitamente a la búsqueda.
    
- Se recomienda encarecidamente que no tenga un buzón activo y el buzón de correo inactivo con la misma dirección SMTP. Si necesita volver a usar la dirección SMTP que está asignada actualmente a un buzón de correo inactivo, se recomienda que recuperar el buzón de correo inactivo o restaurar el contenido de un buzón inactivo en un buzón de correo activo (o el archivo de un buzón de active) y, a continuación, elimine el buzón de correo inactivo. Para obtener más información, vea uno de los siguientes temas:
    
  - [Recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md)
    
  - [Restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md)
    
  - [Eliminar un buzón inactivo en Office 365](delete-an-inactive-mailbox.md)

  
### <a name="previewing-search-results"></a>Obtener una vista previa de los resultados de búsqueda

Puede obtener una vista previa de tipos de archivo admitidos en el panel de vista previa. Si no se admite un tipo de archivo, debe descargar una copia del archivo en el equipo local para verlo. Los siguientes tipos de archivo son compatibles y se pueden obtener una vista previa en el panel de resultados de búsqueda.
  
- .txt, .html, .mhtml
    
- EML
    
- .doc, .docx, .docm
    
- .pptm, .pptx
    
- .pdf
    
Además, se admiten los siguientes tipos de archivo contenedor. Puede ver la lista de archivos en el contenedor en el panel de vista previa.
  
- .zip
    
- .gzip
    
### <a name="partially-indexed-items"></a>Elementos indizados parcialmente

- Tal y como se explica anteriormente, parcialmente indizados los elementos en los buzones de correo se incluyen en los resultados de búsqueda estimado; elementos indizados parcialmente desde SharePoint y OneDrive no se incluyen en los resultados de búsqueda estimado. 
    
- Si un parcialmente elemento coincide con la búsqueda de consulta (debido a que otras propiedades de mensaje o el documento cumple con los criterios de búsqueda), no se incluirán en el número estimado de elementos sin indizar. Si un parcialmente excluya los criterios de búsqueda, también no se incluirán en el número estimado de los elementos indizados parcialmente. Para obtener más información, vea [elementos de la búsqueda de contenido en Office 365 parcialmente indizados](partially-indexed-items-in-content-search.md).
    
### <a name="exporting-data-from-myanalytics-and-other-office-365-applications"></a>Exportación de datos de MyAnalytics y otras aplicaciones de Office 365

- Datos de MyAnalytics (por ejemplo, conocimientos sobre cómo los usuarios dedican su tiempo en función de los datos de correo y de calendario en su buzón) y los datos de otras aplicaciones de Office 365 está guardada en una ubicación oculta (en un subárbol no IPM) del buzón de usuario basada en la nube. Después de ejecutar una búsqueda de contenido, estos datos no se incluyen en los resultados de búsqueda estimado, las estadísticas de consulta, y no está disponible para la vista previa. Sin embargo estos datos se exportarán al exportar los resultados de una búsqueda.
    
- Los datos de MyAnalytics y los datos de otras aplicaciones de Office 365 se exporta a una carpeta denominada "Otros datos de Office 365". Esta carpeta incluye subcarpetas para cada usuario.
  