---
title: Búsqueda de contenido de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: Use la herramienta de búsqueda de contenido del Centro de cumplimiento de Office 365 o Microsoft 365 para buscar contenido en buzones, sitios de SharePoint Online, cuentas de OneDrive, Microsoft Teams, grupos de Office 365 y conversaciones de Skype Empresarial. Puede restringir los resultados de la búsqueda mediante palabras clave y condiciones de búsqueda. Después, puede consultar una vista previa y exportar los resultados de búsqueda. La búsqueda de contenido también es una herramienta eficaz para encontrar información relacionada con la solicitud del interesado del RGPD.
ms.openlocfilehash: cc6a385ec639f6df787c2de23fece8cb53a4d25e
ms.sourcegitcommit: d55dab629ce1f8431b8370afde4131498dfc7471
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2019
ms.locfileid: "36675471"
---
# <a name="content-search-in-office-365"></a>Búsqueda de contenido de Office 365

Puede usar la herramienta eDiscovery de búsqueda de contenido en el Centro de cumplimiento en Office 365 o Microsoft 365 para buscar elementos locales como correo electrónico, documentos y conversaciones de mensajería instantánea en su organización de Office 365. Úsela para buscar elementos en los siguientes servicios de Office 365:
  
- Buzones de Exchange Online y carpetas públicas
    
- Sitios de SharePoint Online y cuentas de OneDrive para la Empresa
    
- Conversaciones de Skype Empresarial
    
- Microsoft Teams 
    
- Grupos de Office 365
    
Después de ejecutar una búsqueda de contenido, se mostrará el número de ubicaciones de contenido y un número estimado de resultados de la búsqueda en el perfil de búsqueda. También puede ver rápidamente estadísticas como las ubicaciones de contenido con la mayor cantidad de elementos encontrados por la consulta de búsqueda. Después de ejecutar una búsqueda, puede obtener una vista previa de los resultados o exportarlos a un equipo local.

## <a name="create-a-search"></a>Crear una búsqueda

Para acceder a la página de **Búsqueda de contenido** y buscar, obtener una vista previa o exportar los resultados de búsqueda, es necesario que un administrador, responsable de cumplimento normativo o administrador de eDiscovery sea miembro del grupo de roles de administradores de eDiscovery del Centro de seguridad y cumplimiento. Para obtener más información, consulte [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su dirección de correo electrónico y contraseña de Office 365.
    
2. Haga clic en **Buscar** \> **Búsqueda de contenido**.
    
3. En la página **Buscar**, haga clic en la flecha junto al ![icono Agregar](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Nueva búsqueda**. 
    
    ![La nueva lista desplegable de búsqueda](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    Puede elegir una de las opciones siguientes:
    
    - **Búsqueda guiada:** esta opción inicia un asistente que le guiará a través de la creación de la búsqueda. La interfaz de usuario para seleccionar ubicaciones de contenido y crear la consulta de búsqueda es la misma que la opción **Nueva Búsqueda**. 
    
    - **Nueva búsqueda**: esta opción muestra una interfaz de usuario actualizada para crear una búsqueda. Esta es la opción predeterminada si hace clic en **Nueva búsqueda**.
    
    - **Buscar por lista de id.**: le permite buscar mensajes de correo específicos y otros elementos del buzón con una lista de Id. de Exchange. Para crear una búsqueda por lista de Id (antes denominada búsqueda objetivo), debe enviar un archivo CSV que identifique los elementos de buzón específicos que desee buscar. Para sabe cómo hacerlo, consulte [Preparar un archivo CSV para una búsqueda de contenido de lista de identificadores en Office 365](csv-file-for-an-id-list-content-search.md)
    
    El resto de los pasos de este procedimiento siguen el nuevo flujo de trabajo de búsqueda predeterminado.
    
4. En la lista desplegable, haga clic en **Nueva búsqueda**. 
    
5. En **Consulta de búsqueda**, especifique las siguientes opciones:
    
    ![Indique las palabras clave, condiciones y ubicaciones a buscar](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
   - **Palabras clave para buscar:** escriba una consulta de búsqueda en el cuadro **Palabras clave**. Puede especificar palabras clave, propiedades del mensaje como la fecha de envío y de recepción, o propiedades del documento como nombres de archivo o la fecha de la última modificación de un documento. También puede usar consultas más complejas con operadores booleanos como **Y**, **O**, **NOT** y **NEAR**. Además, puede buscar información confidencial (como los números de la seguridad social) en documentos o buscar en documentos que se han compartido de forma externa. Si deja el cuadro de la palabra clave en blanco, todo el contenido en las ubicaciones especificadas se incluye en los resultados de la búsqueda.
    
      También puede marcar la casilla **Mostrar lista de palabras clave** y escribir una palabra clave en cada fila. En este caso, las palabras clave de cada fila estarán conectadas por un operador lógico (**c:s**) funcionalmente similar al operador **O** en la consulta de búsqueda creada. 
    
      ¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave. Esto le ayudará a identificar rápidamente las palabras clave más (y menos) efectivas. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para saber más sobre las estadísticas de búsqueda, consulte [Ver estadísticas de palabras clave para resultados de búsqueda de contenido](view-keyword-statistics-for-content-search.md).

     > [!NOTE]
     > Existe un límite máximo de 20 filas en la lista de palabras clave, con el fin de reducir los problemas causados por listas de palabras clave demasiado grandes.
    
    - **Condiciones**: puede agregar condiciones de búsqueda para recibir un conjunto de resultados más pertinente. Cada condición agrega una cláusula a la consulta de búsqueda que se crea y se ejecuta cuando se inicia la búsqueda. Una condición se conecta lógicamente a la consulta de palabras clave (especificada en el cuadro de palabras clave) mediante el operador **c:c**, que tiene una función parecida al operador **Y**. Eso significa que los elementos tienen que satisfacer la consulta de palabra clave y una o más condiciones para que se incluyan en los resultados. De esta manera, las condiciones permiten restringir los resultados. Para obtener una lista y descripciones de las condiciones permitidas en una consulta de búsqueda, vea la sección "Condiciones de búsqueda" en [Consultas de palabras clave y condiciones de búsqueda para la Búsqueda de contenido](keyword-queries-and-search-conditions.md#search-conditions).
    
       - **Ubicaciones**: elegir las ubicaciones de contenido a buscar
    
      - **Todas las ubicaciones**: Seleccione esta opción para buscar en todas las ubicaciones de contenido de su organización. Esto incluye el correo electrónico en todos los buzones de Exchange (incluidos todos los buzones inactivos, los buzones de todos los Grupos de Office 365 y todos los buzones de Microsoft Teams), todas las conversaciones de Skype Empresarial, todos los sitios de SharePoint y OneDrive para la Empresa (incluidos los sitios para todos los grupos de Office 365 y Microsoft Teams), y los elementos de todas las carpetas públicas de Exchange.
    
      - **Ubicaciones específicas**: Use esta opción para buscar en ubicaciones de contenido específicas. Puede buscar en todas las ubicaciones de contenido de un servicio específico de Office 365 (por ejemplo, en todos los buzones de Exchange o todos los sitios de SharePoint) o en ubicaciones específicas en cualquiera de los servicios de Office 365 que se muestren. 
    
        ![Interfaz de usuario para elegir ubicaciones de contenido en las que buscar](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
         También puede agregar grupos de distribución a la lista de buzones de Exchange en los que desea buscar. En los grupos de distribución, se busca en los buzones de los miembros del grupo. No se admiten grupos de distribución dinámicos.
    
       > [!NOTE]
       > Cuando busque en todas las ubicaciones del buzón o solo en buzones específicos, los datos de otras aplicaciones de Office 365 guardados en los buzones de usuario se incluirán en la exportación de resultados de una Búsqueda de contenido. Estos datos no se incluyen en los resultados de búsqueda estimados y no aparecen en la vista previa. Solo se incluyen cuando exporte y descargue los resultados de búsqueda. Para obtener más información, consulte [Contenido almacenado en los buzones de Exchange Online](what-is-stored-in-exo-mailbox.md).

    
6. Una vez que haya configurado la consulta de búsqueda, haga clic en **Guardar y ejecutar**.
    
7. En la página **Guardar búsqueda**, escriba un nombre y una descripción opcional que le ayude a identificar la búsqueda. El nombre de la búsqueda debe ser único en la organización. 
    
8. A continuación, haga clic en **Guardar** para iniciar la búsqueda. 
    
    Después de guardar y ejecutar la búsqueda, podrá ver los resultados en el panel de resultados. Según haya configurado la vista previa, los resultados de búsqueda se mostrarán directamente o tendrá que hacer clic en **Vista previa de resultados** para verlos. Consulte la siguiente sección para obtener detalles. 
    
Para acceder nuevamente a esta búsqueda de contenido o para ver otras búsquedas de contenido en la página **Búsqueda de contenido**, seleccione la búsqueda y, a continuación, haga clic en **Abrir**. 
  
Para borrar los resultados o crear otra búsqueda, haga clic en ![Agregar icono](media/O365-MDM-CreatePolicy-AddIcon.gif) **Nueva búsqueda**. 

  
## <a name="preview-search-results"></a>Vista previa de los resultados de búsqueda

Hay dos opciones de configuración para obtener una vista previa de los resultados de búsqueda. Después de ejecutar una búsqueda nueva o abrir una existente, haga clic en ** resultados individuales ** para ver la siguiente configuración de vista previa: 
  
![Opciones de vista previa de los resultados de búsqueda](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. **Vista previa de resultados automáticamente**: muestra los resultados de la búsqueda después de ejecutarla.
    
2. **Vista previa de resultados manualmente**: muestra marcadores de posición en el panel de resultados de la búsqueda. Para ver los resultados de la búsqueda, debe hacer clic en el botón **Vista previa de resultados**. Esta configuración es la predeterminada. Permite aumentar la rapidez de la búsqueda ya que no tiene que cargar los resultados automáticamente cada vez que abra una búsqueda existente. 
    
Existen límites para la cantidad de elementos disponibles en una vista previa. Para más información, vea la sección [Límites de la búsqueda de contenido](limits-for-content-search.md). 
  
Para obtener una lista de los tipos de archivo compatibles con una vista previa, vea [Vista previa de los resultados de búsqueda](#previewing-search-results) en la sección «Más información sobre la búsqueda de contenido». Si un tipo de archivo no es compatible con la vista previa o la opción de descargar una copia del documento, haga clic en **Descargar archivo original** para descargarlo en su propio ordenador. Para las páginas web .aspx se incluye la dirección URL de la página, aunque es posible que no tenga permiso para acceder a ella. 
  
Tenga en cuenta que no se puede obtener una vista previa de los elementos sin indexar.
  
## <a name="view-information-and-statistics-about-a-search"></a>Ver información y estadísticas sobre las búsquedas

Después de crear y ejecutar una búsqueda de contenido, puede ver estadísticas sobre los resultados de búsqueda estimados. Esto incluye un resumen de los resultados de la búsqueda, estadísticas de la consulta —como el número de ubicaciones de contenido con elementos que haya encontrado la consulta— y el nombre de las ubicaciones de contenido con más elementos encontrados. Puede mostrar las estadísticas de una o más búsquedas de contenido. Esto le permite comparar rápidamente los resultados de varias búsquedas y tomar decisiones sobre la efectividad de sus consultas de búsqueda.
  
También puede descargar estadísticas de búsqueda y de palabras clave en un archivo CSV. Así, una vez que abra el archivo con Excel podrá usar las opciones de filtrado y ordenación del programa para comparar los resultados, o preparar informes de los resultados de búsqueda.
  
Para ver las estadísticas de búsqueda:
  
1. En la página **Búsqueda de contenido**, haga clic en **Abrir** y, después, haga clic en la búsqueda cuyas estadísticas desea ver. 
    
2. En la página de control flotante, haga clic en **Abrir consulta**. 
    
3. En la lista desplegable de **resultados individuales**, haga clic en **Perfil de búsqueda**.
    
4. En la lista desplegable **Tipo**, haga clic en una de las siguientes opciones en función de las estadísticas de búsqueda que desee ver. 
    
  - **Resumen**: muestra estadísticas para cada tipo de ubicación de contenido buscada. Las estadísticas mostradas incluyen el número de ubicaciones de contenido con elementos que coinciden con la consulta de búsqueda, y el número total y tamaño de los elementos devueltos por la búsqueda. Esta configuración es la predeterminada.
    
  - **Consultas**: muestra estadísticas sobre las consultas de búsqueda. Incluye el tipo de ubicación de contenido al que se aplican las estadísticas de la consulta, la parte de la consulta de búsqueda a la que se aplican las estadísticas (aquí, **Primario** se refiere a toda la consulta de búsqueda), el número de ubicaciones de contenido que contienen elementos encontrados por la consulta de búsqueda, y el número total, el tamaño y los elementos encontrados (en la ubicación de contenido definida) que coincidan con la consulta de búsqueda. También se muestran estadísticas de los elementos sin indexar (conocidos como *elementos indexados parcialmente*). Sin embargo, en las estadísticas los únicos elementos indexados parcialmente que se incluyen son los de buzones. No se incluyen, en cambio, los elementos indexados parcialmente de SharePoint y OneDrive.
    
  - **Ubicaciones principales**: muestra estadísticas sobre el número de elementos que coinciden con la consulta de búsqueda en cada ubicación de contenido. Se mostrarán las 1000 ubicaciones más importantes.
    
Para saber más sobre las estadísticas de búsqueda, consulte [Ver estadísticas de palabras clave para resultados de búsqueda de contenido](view-keyword-statistics-for-content-search.md).
  
  
## <a name="export-search-results"></a>Exportar resultados de búsqueda

Después de que una búsqueda se ejecute correctamente, puede exportar los resultados de búsqueda a un equipo local. Cuando exporte los resultados de correo, puede descargarlos en su equipo como archivos PST o mensajes individuales (archivos .msg). Cuando exporta contenido desde los sitios de SharePoint y OneDrive, se exportan copias de documentos nativos de Office. Los resultados de búsqueda exportados también incluyen otros documentos e informes. Asimismo, puede exportar el informe de resultados de búsqueda (pero no los elementos reales).
  
Exportar resultados de búsqueda:
  
1. En la página **Búsqueda de contenido**, haga clic en la búsqueda cuyos resultados quiere exportar. 
    
2. En la página flotante, haga clic en el ![icono Exportar resultados de búsqueda](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Más** y después, haga clic, en **Exportar resultados**. También puede exportar un informe de resultados de búsqueda.
    
3. Complete las secciones de la página flotante **Exportar resultados**. Asegúrese de usar la barra de desplazamiento para ver todas las opciones de exportación. 
    
Para obtener instrucciones más detalladas y sugerencias para resolver problemas, consulte:
  
- [Exportar resultados de la búsqueda de contenido](export-search-results.md)
    
- [Exportar un informe de búsqueda de contenido](export-a-content-search-report.md)
    
  
## <a name="more-information-about-content-search"></a>Más información sobre la búsqueda de contenido

Vea las siguientes secciones para obtener más información sobre las búsquedas de contenido.
  
[Límites de búsqueda de contenido](#content-search-limits)
  
[Crear una consulta de búsqueda](#building-a-search-query)
  
[Buscar cuentas de OneDrive](#searching-onedrive-accounts)
  
[Buscar en grupos de Microsoft Teams y Office 365](#searching-microsoft-teams-and-office-365-groups)
  
[Buscar en buzones inactivos](#searching-inactive-mailboxes)
  
[Buscar en buzones que se desconectaron o se ha deshabilitado la licencia](#searching-disconnected-or-de-licensed-mailboxes)

[Vista previa de los resultados de búsqueda](#previewing-search-results)
  
[Elementos indexados parcialmente](#partially-indexed-items)

[Búsqueda de contenido en un entorno de SharePoint Multi-Geo](#searching-for-content-in-a-sharepoint-multi-geo-environment)
  
### <a name="content-search-limits"></a>Límites de búsqueda de contenido

- Para obtener una descripción de los límites que se aplican a la característica de búsqueda de contenido, consulte [Límites de búsqueda de contenido](limits-for-content-search.md).
    
- Microsoft recopila información del rendimiento de las búsquedas de contenido ejecutadas por todas las organizaciones de Office 365. Aunque la complejidad de una consulta de búsqueda puede afectar al tiempo que lleva ejecutarla, en realidad, el factor más determinante es el número de buzones incluidos en la búsqueda. Microsoft no proporciona un acuerdo de nivel de servicio para los tiempos de búsqueda. Sin embargo, en la siguiente tabla le mostramos los tiempos de búsqueda promedio en base al número de buzones.
    
|**Número de buzones**|**Promedio de tiempo de búsqueda**|
|:-----|:-----|
|100  <br/> |30 segundos  <br/> |
|1000  <br/> |45 segundos  <br/> |
|10 000  <br/> |4 minutos  <br/> |
|25 000  <br/> |10 minutos  <br/> |
|50 000  <br/> |20 minutos  <br/> |
|100 000  <br/> |25 minutos  <br/> |
  
### <a name="building-a-search-query"></a>Crear una consulta de búsqueda

Para obtener información detallada sobre cómo crear una consulta de búsqueda, usar operadores booleanos y condiciones de búsqueda, y buscar información confidencial y contenido compartido con usuarios fuera de la organización, vea [Consultas de palabras clave y condiciones de búsqueda para la Búsqueda de contenido](keyword-queries-and-search-conditions.md).
  
Tenga en cuenta lo siguiente cuando use la lista de palabras clave para crear una consulta de búsqueda.
  
- Debe seleccionar la casilla **Mostrar la lista de palabras clave** y, a continuación, escribir cada palabra clave en una fila. Si escribe varias palabras clave en una misma fila, quedarán relacionadas por el operador **O**. Si pega una lista de palabras clave en el cuadro de palabras clave o presiona **Entrar** después de escribir cada palabra clave, estas no quedarán conectadas por el operador **O**. Estos son algunos ejemplos incorrectos y correctos de cómo agregar una lista de palabras clave. 
    
    **Incorrecto:**
    
    ![La forma incorrecta de dar formato a una lista de palabras clave (pegar la lista en el cuadro de palabras clave)](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **Correcto:**
    
    ![La forma correcta de dar formato a una lista de palabras clave (seleccionar la casilla y, después, pegar la lista)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- También puede crear una lista de palabras clave o frases clave en un archivo de Excel o en un archivo de texto sin formato y, después, pegarla en la lista de palabras clave. Para hacerlo, seleccione la casilla **Mostrar lista de palabras clave**. Después, haga clic en la primera fila de la lista de palabras clave y pegue la lista. Cada línea del archivo de texto o Excel se pegará en la línea correspondiente de la lista de palabras clave. 
    
- Después de crear la consulta con la lista de palabras clave, es recomendable comprobar la sintaxis de la consulta para asegurarse de que es lo que desea buscar. En la consulta de búsqueda, que puede ver debajo de **Consulta** en el panel de detalles, las palabras clave quedan separadas por **(c:s)**. Esto significa que están conectadas por un operador lógico similar al operador **O**. Del mismo modo, si la consulta de búsqueda incluye condiciones, las palabras clave aparecen separadas de las condiciones por **(c:c)**. Esto significa que están conectadas a las condiciones por un operador lógico similar a **Y**. Este ejemplo muestra una consulta de búsqueda (situada en el panel de detalles) obtenida al usar la lista de palabras clave con una condición. 
    
    ![Ejemplo de consulta creada utilizando la lista de palabras clave y una condición](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- Cuando ejecuta una búsqueda de contenido, Office 365 comprueba automáticamente la búsqueda para verificar que no haya caracteres no admitidos ni operadores booleanos en minúsculas. Los caracteres no admitidos suelen estar ocultos y pueden provocar un error de búsqueda o devolver resultados no deseados. Para obtener más información acerca de la verificación de caracteres no compatibles, vea [Comprobar si hay errores en la consulta de búsqueda de contenido](check-your-content-search-query-for-errors.md).
    
- Si su consulta de búsqueda contiene palabras clave con caracteres especiales (que no pertenecen al alfabeto inglés), puede hacer clic en **Consulta idioma-país/región**![el icono Consulta idioma-país/región](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) y seleccionar el código cultural del idioma y país relevantes para la búsqueda. Por defecto, la versión del idioma/región es la neutra. ¿Cómo saber si es necesario cambiar la configuración de idioma para una búsqueda de contenido? Si sabe que las ubicaciones de contenido contienen los caracteres especiales que busca, pero la búsqueda no devuelve ningún resultado, la configuración de idioma puede ser la causa. 
  
### <a name="searching-onedrive-accounts"></a>Buscar en cuentas de OneDrive

- Para obtener una lista de las direcciones URL de los sitios de OneDrive de su organización, vea [Crear una lista de todas las ubicaciones de OneDrive en la organización](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). El script en este artículo crea un archivo de texto que contiene una lista de todos los sitios de OneDrive. Para ejecutar este script, tiene que instalar y usar el Shell de SharePoint Online Management. Asegúrese de anexar la dirección URL para el dominio MiSitio de su organización a cada sitio de OneDrive que quiera buscar. Este es el dominio que contiene todos los sitios OneDrive; por ejemplo, `https://contoso-my.sharepoint.com`. Este es un ejemplo de una dirección URL para un sitio de usuario de OneDrive: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
    
    En el caso poco habitual de que cambie el nombre principal de usuario (UPN) de una persona, la dirección URL de su ubicación de OneDrive cambiará para incorporar el nuevo UPN. Si esto ocurre, tendrá que modificar la búsqueda de contenido agregando la nueva dirección URL de OneDrive del usuario y eliminando la anterior.
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a>Buscar en Microsoft Teams y Grupos de Office 365

Puede buscar en el buzón asociado a un Grupo de Office 365 o Microsoft Teams. Como Microsoft Teams está basado en los Grupos de Office 365, la búsqueda en ambos es similar. En ambos casos, solo se busca en el buzón de grupo o de equipo. No se busca en los buzones del grupo o de los miembros del equipo. Si quiere buscar en estos, debe agregarlos específicamente a la búsqueda.
  
Tenga en cuenta lo siguiente al buscar contenido en Microsoft Teams y Grupos de Office 365:
  
- Para buscar contenido ubicado en Teams y Grupos de Office 365, debe especificar el buzón y el sitio de SharePoint asociados a un equipo o grupo.
    
- Ejecute el cmdlet **Get-UnifiedGroup** de Exchange Online para ver las propiedades de un equipo o grupo de Office 365. Este es un buen método para obtener la dirección URL del sitio asociado a un equipo o un grupo. Por ejemplo, el comando siguiente muestra las propiedades seleccionadas de un grupo de Office365 denominado Senior Leadership Team: 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroup** debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista. 
  
- Cuando se busca en el buzón de un usuario, no se buscará en los equipos o grupos de Office365 a los que pertenece dicho usuario. De forma similar, al buscar en un equipo o en un grupo de Office 365, solo se busca en el buzón de grupo y en el sitio de grupo que especifique. Tampoco se busca en los buzones y las cuentas de OneDrive para la Empresa de los miembros del grupo a menos que los agregue explícitamente a la búsqueda.
    
- Si quiere obtener una lista de los miembros de un equipo o grupo de Office 365 puede ver las propiedades en la página **Inicio \> Grupos** del Centro de administración de Microsoft 365. Además, puede ejecutar el comando siguiente en PowerShell de Exchange Online: 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroupLinks** debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista. 
  
- Las conversaciones de un canal de Teams se almacenan en el buzón de correo asociado al equipo. Asimismo, los archivos que los miembros del equipo comparten en un canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, tiene que agregar el buzón de equipo y el sitio de SharePoint como una ubicación de contenido para buscar conversaciones y archivos en un canal.
    
- Por otro lado, las conversaciones que forman parte de la lista de chat en Teams se almacenan en el buzón de Exchange Online de los usuarios que participan en el chat. Y los archivos que un usuario comparte en las conversaciones de chat se almacenan en la cuenta de OneDrive para la Empresa del usuario que comparte el archivo. Por lo tanto, tiene que agregar el buzón de usuario individual y las cuentas de OneDrive para la Empresa como ubicaciones de contenido para buscar conversaciones y archivos en la lista de chats.
    
    > [!NOTE]
    > En una implementación híbrida de Exchange, los usuarios con buzones locales podrían participar en conversaciones que forman parte de la lista de chats de Teams. En este caso, el contenido de estas conversaciones también se puede buscar ya que se guarda en un área de almacenamiento en la nube (*el buzón basado en la nube para usuarios locales*) para aquellos usuarios que tienen un buzón local. Para obtener más información, vea [Búsqueda en buzones de correo basados en la nube para usuarios locales en Office 365](search-cloud-based-mailboxes-for-on-premises-users.md).
  
- Cada equipo o canal de equipo contiene una wiki para tomar notas y colaborar. El contenido de esta se guarda automáticamente en un archivo con un formato .mht. Este archivo se almacena en la biblioteca de documentos de Datos Wiki de Teams en el sitio de SharePoint del equipo. Puede usar la herramienta de Búsqueda de contenido para buscar en la wiki. Para ello establezca el sitio de SharePoint del equipo como la ubicación de contenido en la que buscar. 
    
    > [!NOTE]
    > La función de búsqueda en el wiki de un equipo o un canal (cuando se busca en el sitio de SharePoint del grupo) se publicó el 22 de junio de 2017. Solo puede buscar en las páginas wiki guardadas o actualizadas en esa fecha o posteriores. Las páginas wiki guardadas o actualizadas por última vez antes de esa fecha no están disponibles para la búsqueda. 
 
- La información de resumen de reuniones y llamadas de un canal de equipo se almacena también en los buzones de los usuarios que entraran en la reunión o llamada. Esto significa que puede usar la Búsqueda de contenido para buscar en estos registros de resumen. Esta información de resumen incluye: 
  
  - Fecha, hora de inicio, hora de finalización y duración de una reunión o llamada

  - La fecha y hora en la que cada participante se incorporó o abandonó la reunión o llamada

  - Llamadas enviadas al correo de voz

  - Llamadas perdidas o sin responder

  - Transferencias de llamadas, que se representan como dos llamadas independientes

  La opción de buscar en resúmenes de reuniones y llamadas puede tardar hasta 8 horas en estar disponible.

  En los resultados de búsqueda, los resúmenes de reunión se identifican como **Reunión** en el **campo Tipo** y los resúmenes de llamadas se identifican como **Llamada**. Asimismo, las conversaciones que forman parte de un canal de Teams y los chats de Teams (conocidos como 1xN) se identifican como **Mensajería instantánea** en el campo **Tipo**.
  
  ![Las reuniones de Teams, las llamadas y los chats 1xN se identifican en el campo Tipo](media/O365-ContentSearch-Teams-MessageKind.png)

- Puede usar la propiedad de correo **Tipo** o la condición de búsqueda **Tipo de mensaje** para buscar contenido en Teams de forma más específica. 
  
  - Para usar la propiedad **Tipo** como parte de la consulta de búsqueda de palabras clave, escriba `kind:microsoftteams` en el cuadro de **palabras clave** de una consulta de búsqueda.

    ![Escriba kind:microsoftteams en el cuadro de palabras clave](media/O365-ContentSearch-Teams-Keywords.png)
  
  - Para usar una condición de búsqueda, agregue la condición de **Tipo de mensaje** y use el valor `microsoftteams`. 

    ![Use la condición de tipo de mensaje con el valor microsoftteams.](media/O365-ContentSearch-Teams-MessageKindCondition.png)

Tenga en cuenta que las condiciones están conectadas de forma lógica a la consulta de palabra clave por el operador **Y**. Esto significa que un elemento tiene que coincidir con la consulta de la palabra clave y con la condición de búsqueda para que aparezca en los resultados de la búsqueda. Para obtener más información, vea la sección de «Guías para utilizar condiciones» en [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions).
  
### <a name="searching-inactive-mailboxes"></a>Buscar en buzones inactivos

Puede buscar en buzones inactivos en una búsqueda de contenido. Para obtener una lista de los buzones inactivos de la organización, ejecute el comando `Get-Mailbox -InactiveMailboxOnly` en Exchange Online PowerShell. Como alternativa, puede ir a **Gobierno de datos** \> **Retención** en el Centro de cumplimiento y seguridad y, a continuación, hacer clic en **Más**![Puntos suspensivos en la barra de navegación](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Buzones inactivos**.
  
A continuación, se detallan algunos aspectos que se deben tener en cuenta al buscar buzones inactivos:

- Si una búsqueda de contenido incluye un buzón de usuario que deja de estar activo, la búsqueda de contenido seguirá buscando en el buzón inactivo al volver a ejecutarla después del cambio de estado.
    
- En algunas ocasiones, un usuario puede tener un buzón activo y uno inactivo con la misma dirección SMTP. En ese caso, solo se buscarán los buzones específicos que seleccione como ubicaciones en una búsqueda de contenido. Es decir, si agrega el buzón de un usuario a una búsqueda, no dé por sentado que se buscará tanto en el buzón activo como el inactivo. Solo se buscará en el buzón que agregue explícitamente a la búsqueda.
    
- Puede usar Security & PowerShell del centro de cumplimiento para crear una búsqueda de contenido para buscar en un buzón inactivo. Para ello, tiene que agregar previamente un punto (. Dirección de correo electrónico del propietario del buzón de correo. Por ejemplo, el comando siguiente crea una búsqueda de contenido que busca en un buzón inactivo con la dirección de correo electrónico pavelb@contoso.onmicrosoft.com:

   ``` 
   New-ComplianceSearch -name InactiveMailboxSearch -ExchangeLocation .pavelb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
   ```

- Le recomendamos que no tenga un buzón activo y un buzón inactivo con la misma dirección SMTP. Si necesita volver a usar la dirección SMTP que está asignada a un buzón inactivo, le recomendamos que recupere el buzón inactivo o restaure el contenido de un buzón inactivo a uno activo (o el archivo de un buzón activo) y, después, elimine el buzón inactivo. Para obtener más información, vea uno de los siguientes temas:
    
  - [Recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md)
    
  - [Restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md)
    
  - [Eliminar un buzón inactivo en Office 365](delete-an-inactive-mailbox.md)

### <a name="searching-disconnected-or-de-licensed-mailboxes"></a>Buscar en buzones que se desconectaron o se ha deshabilitado la licencia

Si la licencia de Exchange Online (o la licencia 365 completa de Office) se quita de una cuenta de usuario en Office 365 o en Azure Active Directory, el buzón del *usuario se convierte* en un buzón desconectado. Esto significa que el buzón ya no está asociado a la cuenta de usuario. Esto es lo que ocurre al buscar en buzones desconectados:

- Cuando se quita la licencia de un buzón, ya no se puede buscar en él. 

- Si una búsqueda de contenido existente incluye un buzón de usuario en el que se ha quitado la licencia, los resultados de búsqueda del buzón desconectado no se incluirán cuando vuelva a ejecutar la búsqueda.

- Si usa el cmdlet **New-ComplianceSearch** para crear una búsqueda de contenido y especifica un buzón desconectado como la ubicación de contenido de Exchange en la que buscar, la búsqueda de contenido no devolverá resultados de búsqueda del buzón desconectado.

Si necesita conservar los datos de un buzón desconectado para poder buscarlos, debe poner el buzón en suspensión antes de quitar la licencia. De este forma, se conservan los datos y se permite la búsqueda en el buzón desconectado hasta que se quite la suspensión. Para más información sobre las suspensiones, vea [Cómo identificar el tipo de suspensión en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md)

### <a name="previewing-search-results"></a>Vista previa de los resultados de búsqueda

Puede obtener una vista previa de los tipos de archivo compatibles en el panel de vista previa. Si un tipo de archivo no es compatible, necesitará descargar una copia en el equipo local para verlo. Se admiten los siguientes tipos de archivo y se puede obtener una vista previa en el panel Resultados de búsqueda.
  
- .txt, .html, .mhtml
    
- .eml
    
- .doc, .docx, .docm
    
- .pptm, .pptx
    
- .pdf
    
Asimismo, se admiten los siguientes tipos de contenedor de archivo. Puede ver la lista de archivos del contenedor en el panel de vista previa.
  
- .zip
    
- .gzip
    
### <a name="partially-indexed-items"></a>Elementos indexados parcialmente

- Como se ha explicado anteriormente, los elementos indexados parcialmente en los buzones se incluyen en los resultados de búsqueda estimados. En cambio, los elementos indexados parcialmente de SharePoint y OneDrive no se incluyen. 
    
- Si un elemento parcialmente indexado coincide con la búsqueda de consulta (porque otras propiedades del mensaje o documento cumplen los criterios de búsqueda), no se incluirá en el número estimado de elementos sin indexar. Si el criterio de búsqueda excluye un elemento parcialmente indexado, no se incluye en el número estimado de elementos sin indexar. Para más información, vea [Elementos parcialmente indexados en la búsqueda de contenido de Office 365](partially-indexed-items-in-content-search.md).

### <a name="searching-for-content-in-a-sharepoint-multi-geo-environment"></a>Búsqueda de contenido en un entorno de SharePoint Multi-Geo

Si es necesario que un administrador de eDiscovery busque contenido en SharePoint y OneDrive en distintas regiones en un [entorno de SharePoint Multi-Geo](https://go.microsoft.com/fwlink/?linkid=860840), tiene que hacer lo siguiente:
   
1. Cree una cuenta de usuario independiente para cada ubicación geográfica por satélite que necesite buscar el administrador de eDiscovery. Para buscar contenido en los sitios de esa ubicación geográfica, el administrador de eDiscovery debe iniciar sesión en la cuenta que usted creó para dicha ubicación y, después, ejecutar una búsqueda de contenido.

2. Cree un filtro de permisos de búsqueda para cada ubicación geográfica por satélite (y la cuenta de usuario correspondiente) en la que necesita realizar búsquedas el administrador de eDiscovery. Cada uno de estos filtros de permisos de búsqueda limita el ámbito de la búsqueda de contenido a una ubicación geográfica específica cuando el administrador de eDiscovery inicia sesión en la cuenta de usuario asociada a esa ubicación.
 
> [!TIP]
> No es necesario usar esta estrategia al usar la herramienta de búsqueda de [eDiscovery avanzado](compliance20/overview-ediscovery-20.md). Esto se debe a que se buscan todos los centros de datos al realizar una búsqueda de los sitios de SharePoint y cuentas de OneDrive en eDiscovery avanzado. Solo tiene que usar esta estrategia de filtros de permiso de búsqueda y cuentas de usuario específicos de la región al usar la herramienta de búsqueda de contenido y al ejecutar búsquedas relacionadas con [casos de eDiscovery](ediscovery-cases.md). 


Por ejemplo, supongamos que un administrador de eDiscovery tiene que buscar contenido de SharePoint y OneDrive en ubicaciones por satélite en Chicago, Londres y Tokio. El primer paso es crear tres cuentas de usuario, una para cada ubicación. El siguiente paso es crear tres filtros de permisos de búsqueda, uno para cada ubicación y cuenta de usuario correspondiente. Estos son algunos ejemplos de los tres filtros de permisos de búsqueda para este escenario. En cada uno de estos ejemplos, **Region** especifica la ubicación del centro de datos de SharePoint para dicha geoárea y el parámetro **Users** especifica la cuenta de usuario correspondiente. 

**Norteamérica**
```
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-Chicago" -Users ediscovery-chicago@contoso.com -Region NAM -Action ALL
```

**Europa**
```
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-London" -Users ediscovery-london@contoso.com -Region GBR -Action ALL
```

**Asia Pacífico**
```
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-Toyko" -Users ediscovery-tokyo@contoso.com -Region JPN -Action ALL
```

Tenga en cuenta lo siguiente al usar filtros de permisos de búsqueda para buscar contenido en entornos multigeográficos:

- El parámetro **Region** dirige las búsquedas a la ubicación por satélite especificada. Si el administrador de eDiscovery solo busca en los sitios de SharePoint y OneDrive fuera de la región especificada en el filtro de permisos de búsqueda, no se devuelve ningún resultado de búsqueda. 

- El parámetro **Region** no controla las búsquedas de los buzones de Exchange. Al realizar una búsqueda en los buzones se buscan todos los centros de datos. 
    
Para obtener más información sobre el uso de los filtros de permisos de búsqueda en un entorno multigeográfico, vea la sección "Búsqueda y exportación de contenido en entornos multigeográficos" en [Configurar límites de cumplimiento para investigaciones de eDiscovery en Office 365](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).
