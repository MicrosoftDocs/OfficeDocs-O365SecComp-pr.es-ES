---
title: Búsqueda de contenido en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: Use la herramienta de búsqueda de contenido en el centro de cumplimiento de Office 365 o Microsoft 365 para buscar contenido en buzones de correo, sitios de SharePoint Online, cuentas de OneDrive, Microsoft Teams, grupos de Office 365 y conversaciones de Skype empresarial. Puede usar consultas de búsqueda de palabras clave y condiciones de búsqueda para restringir los resultados de la búsqueda. A continuación, puede obtener una vista previa y exportar los resultados de búsqueda. La búsqueda de contenido también es una herramienta eficaz para buscar contenido relacionado con una solicitud de sujeto de datos de RGPD.
ms.openlocfilehash: 76c3ddbbd6cd7432a06506be62c63fbfa0291b46
ms.sourcegitcommit: 6b2ca6bd153d24a717d6c537efd2d41d35c20a0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35587827"
---
# <a name="content-search-in-office-365"></a>Búsqueda de contenido en Office 365

Puede usar la herramienta de búsqueda de contenido eDiscovery en el centro de cumplimiento de Office 365 o Microsoft 365 para buscar elementos locales como correo electrónico, documentos y conversaciones de mensajería instantánea en su organización de Office 365. Use esta herramienta para buscar elementos en estos servicios de Office 365:
  
- Buzones de correo y carpetas públicas de Exchange Online
    
- Sitios de SharePoint Online y cuentas de OneDrive para la empresa
    
- Conversaciones de Skype empresarial
    
- Microsoft Teams 
    
- Grupos de Office 365
    
Después de ejecutar una búsqueda de contenido, el número de ubicaciones de contenido y el número estimado de resultados de la búsqueda se muestran en el perfil de búsqueda. También puede ver rápidamente las estadísticas, como las ubicaciones de contenido que tienen la mayoría de los elementos que coinciden con la consulta de búsqueda. Después de ejecutar una búsqueda, puede obtener una vista previa de los resultados o exportarlos a un equipo local.

## <a name="create-a-search"></a>Create a search

Para tener acceso a la página de **búsqueda de contenido** para ejecutar las búsquedas y obtener una vista previa de los resultados de la búsqueda, el administrador, el responsable de cumplimiento o el administrador de eDiscovery deben ser miembros del grupo de roles eDiscovery Manager en el centro de seguridad & cumplimiento. Para obtener más información, consulte [asignar permisos de exhibición](assign-ediscovery-permissions.md)de documentos electrónicos.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su dirección de correo electrónico y contraseña de Office 365.
    
2. Haga clic en búsqueda de **contenido**de **búsqueda** \> .
    
3. En la página **Buscar** , haga clic en la flecha ![junto a](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) agregar icono **nueva búsqueda**. 
    
    ![La nueva lista desplegable de búsqueda](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    Use la pestaña Búsquedas DNS internas para especificar si desea usar los servidores DNS que están configurados en un adaptador de red instalado en este servidor o usar servidores DNS específicos al resolver las direcciones de servidores de correo para la entrega de correo interno. Los servidores DNS internos se usan para resolver direcciones IP para servidores de la organización.
    
    - * * Búsqueda guiada: esta opción inicia un asistente que le guía a través de la creación de la búsqueda. La interfaz de usuario para seleccionar ubicaciones de contenido y crear la consulta de búsqueda son las mismas que las de la nueva opción de **búsqueda** . 
    
    - **Nueva búsqueda** : esta opción muestra una interfaz de usuario actualizada para crear una búsqueda. Esta es la opción predeterminada si hace clic en **nueva búsqueda**.
    
    - **Buscar por lista** de identificadores: esta opción le permite buscar mensajes de correo electrónico específicos y otros elementos de buzón mediante una lista de identificadores de Exchange. Para crear una búsqueda de lista de IDENTIFICADOres (formalmente denominada búsqueda dirigida), envíe un archivo de valores separados por comas (CSV) que identifique los elementos de buzón específicos que se van a buscar. Para obtener instrucciones, vea [preparar un archivo CSV para una búsqueda de contenido de la lista de identificadores en Office 365](csv-file-for-an-id-list-content-search.md).
    
    El resto de los pasos de este procedimiento sigue el nuevo flujo de trabajo de búsqueda predeterminado.
    
4. Haga clic en **nueva búsqueda** en la lista desplegable. 
    
5. En **consulta de búsqueda**, especifique las siguientes opciones:
    
    ![Especificar palabras clave, condiciones y ubicaciones para la búsqueda](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
   - **Palabras clave para buscar** : escriba una consulta de búsqueda en el cuadro **palabras clave** . Puede especificar palabras clave, propiedades del mensaje como la fecha de envío y de recepción, o propiedades del documento como nombres de archivo o la fecha de la última modificación de un documento. Puede usar consultas más complejas que usen un operador booleano, como **and**, **or**, **Not**y **Near**. También puede buscar información confidencial (por ejemplo, los números de la seguridad social) en documentos o buscar documentos que se han compartido de forma externa. Si deja vacío el cuadro palabra clave, todo el contenido ubicado en las ubicaciones de contenido especificadas se incluirá en los resultados de la búsqueda.
    
      Como alternativa, puede hacer clic en la casilla **Mostrar lista de palabras clave** y escribir una palabra clave en cada fila. Si hace esto, las palabras clave de cada fila están conectadas por un operador lógico (**c:s**) que es similar en funcionalidad al operador **or** en la consulta de búsqueda que se crea. 
    
      ¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestren cuántos elementos coinciden con cada palabra clave. Esto puede ayudarle a identificar rápidamente qué palabras clave son más (y menos) efectivas. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para obtener más información acerca de las estadísticas de búsqueda, consulte [View keyword Statistics for Content Search Results](view-keyword-statistics-for-content-search.md).

     > [!NOTE]
     > Para ayudar a reducir los problemas causados por listas de palabras clave grandes, ahora está limitado a un máximo de 20 filas en la lista de palabras clave.
    
    - **Condiciones** : puede agregar condiciones de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda que se crea y se ejecuta cuando se inicia la búsqueda. Una condición está conectada lógicamente a la consulta de palabras clave (especificada en el cuadro palabra clave) por un operador lógico (**c:c**) que es similar en funcionalidad al operador **and** . Esto significa que los elementos deben cumplir con la consulta de palabra clave y una o más condiciones que se van a incluir en los resultados. De esta manera, las condiciones permiten restringir los resultados. Para obtener una lista y una descripción de las condiciones que puede usar en una consulta de búsqueda, consulte la sección "condiciones de búsqueda" en [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md#search-conditions).
    
       - **Ubicaciones** : elija las ubicaciones de contenido en las que desea realizar la búsqueda.
    
      - **Todas las ubicaciones** : Use esta opción para buscar en todas las ubicaciones de contenido de la organización. Esto incluye el correo electrónico en todos los buzones de Exchange (incluidos todos los buzones inactivos, buzones de todos los grupos de Office 365, buzones para todos los equipos de Microsoft Teams), todas las conversaciones de Skype empresarial, todos los sitios de SharePoint y OneDrive para la empresa (incluidos los sitios para todos los grupos de Office 365 y Microsoft Teams) y los elementos de todas las carpetas públicas de Exchange.
    
      - **Ubicaciones específicas** : Use esta opción para buscar ubicaciones de contenido específicas. Puede buscar en todas las ubicaciones de contenido de un servicio de Office 365 específico (como buscar en todos los buzones de Exchange o buscar en todos los sitios de SharePoint) o puede buscar ubicaciones específicas en cualquiera de los servicios de Office 365 que se muestran. 
    
        ![Interfaz de usuario para elegir ubicaciones de contenido para buscar](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
         También puede agregar grupos de distribución a la lista de buzones de Exchange para realizar búsquedas. Para los grupos de distribución, se busca en los buzones de los miembros del grupo. No se admiten grupos de distribución dinámicos.
    
       > [!NOTE]
       > Cuando se busca en todas las ubicaciones del buzón o solo en determinados buzones, los datos de otras aplicaciones de Office 365 que se guardan en los buzones de usuario se incluyen al exportar los resultados de una búsqueda de contenido. Estos datos no se incluirán en los resultados de búsqueda estimados y no están disponibles para la vista previa. Se incluye cuando se exportan y se descargan los resultados de la búsqueda. Para obtener más información, vea [contenido almacenado en buzones de correo de Exchange Online](what-is-stored-in-exo-mailbox.md).

    
6. Una vez configurada la consulta de búsqueda, haga clic en **guardar & ejecutar**.
    
7. En la página **Guardar búsqueda** , escriba un nombre para la búsqueda y una descripción opcional que le ayude a identificar la búsqueda. El nombre de la búsqueda tiene que ser único en su organización. 
    
8. Haga clic en **Guardar** para iniciar la búsqueda. 
    
    Después de guardar y ejecutar la búsqueda, los resultados devueltos por la búsqueda se muestran en el panel de resultados. En función de la configuración de la vista previa, se mostrarán los resultados de la búsqueda o tendrá que hacer clic en **vista previa de resultados** para verlos. Consulte la siguiente sección para obtener más detalles. 
    
Para tener acceso a esta búsqueda de contenido de nuevo o tener acceso a otras búsquedas de contenido en la página **búsqueda de contenido** , seleccione la búsqueda y, a continuación, haga clic en **abrir**. 
  
Para borrar los resultados o crear otra búsqueda, haga ![clic en](media/O365-MDM-CreatePolicy-AddIcon.gif) agregar icono **nueva búsqueda**. 

  
## <a name="preview-search-results"></a>Vista previa de los resultados de búsqueda

Hay dos opciones de configuración para obtener una vista previa de los resultados de búsqueda. Una vez que haya ejecutado una nueva búsqueda o haya abierto una búsqueda existente, haga clic en * * resultados individuales * * para ver la siguiente configuración de vista previa: 
  
![Opciones de vista previa de resultados de búsqueda](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. **Obtener vista previa de los resultados automáticamente** : esta configuración muestra los resultados de la búsqueda después de ejecutar una búsqueda.
    
2. **Vista previa de resultados manualmente** : esta configuración muestra marcadores de posición en el panel de resultados de búsqueda y muestra el botón **vista previa de resultados** en el que tiene que hacer clic para mostrar los resultados de la búsqueda. Esta es la configuración predeterminada. Ayuda a mejorar el rendimiento de la búsqueda, ya que no muestra automáticamente los resultados de la búsqueda cuando se abre una búsqueda existente. 
    
Hay límites relacionados con el número de elementos disponibles para la vista previa. Para obtener más información, consulte [límites de la búsqueda de contenido](limits-for-content-search.md). 
  
Para obtener una lista de los tipos de archivo compatibles con los que se puede obtener una vista previa, vea [vista previa de los resultados de búsqueda](#previewing-search-results) en la sección "más información sobre la búsqueda de contenido". Si no se admite un tipo de archivo para la vista previa o para descargar una copia de un documento, puede hacer clic en **Descargar archivo original** para descargarlo en el equipo local. Para las páginas Web. aspx, la dirección URL de la página se incluye aunque es posible que no tenga permisos para obtener acceso a la página. 
  
Además, tenga en cuenta que los elementos no indexados no están disponibles para la vista previa.
  
## <a name="view-information-and-statistics-about-a-search"></a>Ver información y estadísticas sobre una búsqueda

Después de crear y ejecutar una búsqueda de contenido, puede ver estadísticas sobre los resultados de búsqueda estimados. Esto incluye un resumen de los resultados de la búsqueda, las estadísticas de consulta, como el número de ubicaciones de contenido con elementos que coinciden con la consulta de búsqueda, y el nombre de las ubicaciones de contenido que tienen más elementos coincidentes. Puede mostrar estadísticas de una o más búsquedas de contenido. Esto le permite comparar rápidamente los resultados de varias búsquedas y tomar decisiones sobre la eficacia de las consultas de búsqueda.
  
También puede descargar las estadísticas de búsqueda y las estadísticas de palabras clave en un archivo CSV. Esto le permite usar las características de filtrado y ordenación de Excel para comparar los resultados y preparar los informes para los resultados de la búsqueda.
  
Para ver las estadísticas de búsqueda:
  
1. En la página **búsqueda de contenido** , haga clic en **abrir** y, a continuación, haga clic en la búsqueda para la que desea ver las estadísticas. 
    
2. En la página flotante, haga clic en **abrir consulta**. 
    
3. En la lista desplegable **resultados individuales** , haga clic en **Perfil de búsqueda**.
    
4. En la lista desplegable **tipo** , haga clic en una de las siguientes opciones en función de las estadísticas de búsqueda que desee ver. 
    
  - **Resumen** : muestra estadísticas para cada tipo de ubicaciones de contenido que se han buscado. Este contenido el número de ubicaciones de contenido que contenían los elementos que coincidían con la consulta de búsqueda y el número total y el tamaño de los elementos de resultados de búsqueda. Esta es la configuración predeterminada.
    
  - **Consultas** : muestra estadísticas sobre la consulta de búsqueda. Esto incluye el tipo de ubicación de contenido a la que se aplican las estadísticas de consulta, parte de la consulta de búsqueda a la **** que se aplican las estadísticas (tenga en cuenta que Primary indica toda la consulta de búsqueda), el número de ubicaciones de contenido que contienen elementos que hacer coincidir la consulta de búsqueda y el número y tamaño totales y los elementos encontrados (en la ubicación de contenido especificada) que coinciden con la consulta de búsqueda. También se muestran las estadísticas de los elementos sin indexar (también denominados *elementos parcialmente indizados*). Sin embargo, en las estadísticas solo se incluyen los elementos parcialmente indizados de los buzones. Los elementos parcialmente indizados de SharePoint y OneDrive no se incluyen en las estadísticas.
    
  - **Ubicaciones principales** : muestra estadísticas sobre el número de elementos que coinciden con la consulta de búsqueda en cada ubicación de contenido. Se muestran las principales 1.000 ubicaciones.
    
Para obtener información más detallada acerca de las estadísticas de búsqueda, consulte [ver las estadísticas de palabras clave para los resultados de búsqueda de contenido](view-keyword-statistics-for-content-search.md).
  
  
## <a name="export-search-results"></a>Exportar resultados de búsqueda

Una vez ejecutada correctamente la búsqueda, puede exportar los resultados de la búsqueda a un equipo local. Cuando se exportan los resultados del correo electrónico, se pueden descargar en el equipo como archivos PST o como mensajes individuales (archivos. msg). Al exportar contenido desde sitios de SharePoint y OneDrive, se exportan copias de documentos nativos de Office. También existen otros documentos e informes que se incluyen con los resultados de la búsqueda exportados. También puede exportar el informe de resultados de búsqueda y no los elementos reales.
  
Para exportar los resultados de la búsqueda:
  
1. En la página **búsqueda de contenido** , haga clic en la búsqueda para la que desea exportar los resultados de la búsqueda. 
    
2. En la página flotante, haga ![clic en exportar resultados](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) de búsqueda **más**y, a continuación, haga clic en **exportar resultados**. También puede exportar un informe de resultados de búsqueda.
    
3. Complete las secciones de la página volar en los resultados de la **exportación** . Asegúrese de usar la barra de desplazamiento para ver todas las opciones de exportación. 
    
Para obtener instrucciones más detalladas y sugerencias para la solución de problemas, consulte:
  
- [Exportar resultados de la búsqueda de contenido](export-search-results.md)
    
- [Exportar un informe de búsqueda de contenido](export-a-content-search-report.md)
    
  
## <a name="more-information-about-content-search"></a>Más información acerca de la búsqueda de contenido

Consulte las siguientes secciones para obtener más información acerca de las búsquedas de contenido.
  
[Límites de búsqueda de contenido](#content-search-limits)
  
[Creación de una consulta de búsqueda](#building-a-search-query)
  
[Buscar cuentas de OneDrive](#searching-onedrive-accounts)
  
[Búsqueda de grupos de Microsoft Teams y Office 365](#searching-microsoft-teams-and-office-365-groups)
  
[Buscar buzones inactivos](#searching-inactive-mailboxes)
  
[Vista previa de los resultados de búsqueda](#previewing-search-results)
  
[Elementos parcialmente indizados](#partially-indexed-items)
  
### <a name="content-search-limits"></a>Límites de búsqueda de contenido

- Para obtener una descripción de los límites que se aplican a la característica de búsqueda de contenido, consulte [limits for Content Search](limits-for-content-search.md).
    
- Microsoft recopila información de rendimiento para las búsquedas de contenido ejecutadas por todas las organizaciones de Office 365. Aunque la complejidad de la consulta de búsqueda puede influir en las horas de búsqueda, el factor más importante que afecta a la duración de las búsquedas es el número de buzones buscados. Aunque Microsoft no proporciona un acuerdo de nivel de servicio para los tiempos de búsqueda, en la tabla siguiente se enumeran los tiempos de búsqueda promedio de una búsqueda de contenido basada en el número de buzones que se incluyen en la búsqueda.
    
|**Número de buzones**|**Tiempo medio de búsqueda**|
|:-----|:-----|
|100  <br/> |30 segundos  <br/> |
|1,000  <br/> |de 45 segundos  <br/> |
|10,000  <br/> |4 minutos  <br/> |
|25.000  <br/> |10 minutos  <br/> |
|50.000  <br/> |20 minutos  <br/> |
|100,000  <br/> |25 minutos  <br/> |
  
### <a name="building-a-search-query"></a>Creación de una consulta de búsqueda

Para obtener información detallada sobre cómo crear una consulta de búsqueda, usar operadores de búsqueda booleanos y condiciones de búsqueda, y buscar tipos de información confidencial y contenido compartido con usuarios externos a la organización, vea [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido ](keyword-queries-and-search-conditions.md).
  
Tenga en cuenta lo siguiente cuando use la lista de palabras clave para crear una consulta de búsqueda.
  
- Debe activar la casilla de verificación **Mostrar lista de palabras clave** y, a continuación, escribir cada palabra clave en una fila separada para crear una consulta de búsqueda en la que el operador **or** Conecte las palabras clave (o frases de palabra clave) de cada fila. Si pega una lista de palabras clave en el cuadro palabra clave o presiona la tecla **entrar** después de escribir una palabra clave, no se conectará al operador **or** . A continuación, se muestran ejemplos incorrectos y correctos de cómo agregar una lista de palabras clave. 
    
    **Correctas**
    
    ![La forma incorrecta de aplicar formato a una lista de palabras clave (pegando la lista en el cuadro palabra clave)](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **Corregi**
    
    ![La forma correcta de dar formato a una lista de palabras clave (seleccionando CheckBox y, a continuación, lista de pegado)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- También puede preparar una lista de palabras clave o frases de palabras clave en un archivo de Excel o en un archivo de texto sin formato y, a continuación, copiar y pegar la lista en la lista de palabras clave. Para ello, debe activar la casilla **Mostrar lista de palabras clave** . A continuación, haga clic en la primera fila de la lista de palabras clave y pegue la lista. Cada línea del archivo de texto o Excel se pega en una fila independiente en la lista de palabras clave. 
    
- Después de crear una consulta con la lista de palabras clave, es una buena idea comprobar la sintaxis de la consulta de búsqueda para que la consulta de búsqueda sea la deseada. En la consulta de búsqueda que se muestra en **consulta** en el panel de detalles, las palabras clave están separadas por el texto **(c:s)**. Esto indica que las palabras clave están conectadas por un operador lógico similar en funcionalidad al operador **or** . De forma similar, si la consulta de búsqueda incluye condiciones, las palabras clave y las condiciones están separadas por el texto **(c:c)**. Esto indica que las palabras clave están conectadas a las condiciones con un operador lógico similar en funcionalidad al operador **and** . Este es un ejemplo de la consulta de búsqueda (que se muestra en el panel de detalles) que se obtiene al usar la lista de palabras clave y una condición. 
    
    ![Ejemplo de la consulta que se crea al usar la lista de palabras clave y una condición](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- Cuando se ejecuta una búsqueda de contenido, Office 365 comprueba automáticamente la consulta de búsqueda en busca de caracteres no admitidos y de operadores booleanos que podrían no estar en mayúsculas. Los caracteres no admitidos suelen estar ocultos y, por lo general, causan un error de búsqueda o devuelven resultados no deseados. Para obtener más información acerca de los caracteres no admitidos que se comprueban, vea [comprobar si hay errores en la consulta de búsqueda de contenido](check-your-content-search-query-for-errors.md).
    
- Si tiene una consulta de búsqueda que contiene palabras clave para caracteres que no son ingleses (como caracteres chinos), puede hacer clic en **idioma de consulta, idioma de consulta de país o región**![, icono de](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) país o región en búsqueda de contenido y seleccionar un valor del código de referencia cultural del país de idioma para la búsqueda. El idioma o región predeterminados es neutro. ¿Cómo se puede conocer si es necesario cambiar la configuración de idioma para una búsqueda de contenido? Si algunas ubicaciones de contenido contienen caracteres que no son del alfabeto inglés que está buscando, pero la búsqueda no devuelve resultados, la configuración de idioma puede ser la causa. 
  
### <a name="searching-onedrive-accounts"></a>Buscar cuentas de OneDrive

- Para recopilar una lista de las direcciones URL de los sitios de OneDrive de la organización, vea [crear una lista de todas las ubicaciones de onedrive en la organización](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Este script de este artículo crea un archivo de texto que contiene una lista de todos los sitios de OneDrive. Para ejecutar este script, tiene que instalar y usar el shell de administración de SharePoint Online. Asegúrese de anexar la dirección URL para el dominio de mi sitio de la organización en cada sitio de OneDrive que desee buscar. Este es el dominio que contiene todos los OneDrive; por ejemplo, `https://contoso-my.sharepoint.com`. Este es un ejemplo de una dirección URL para el sitio de OneDrive de `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`un usuario:.
    
    En el caso poco probable de que cambie el nombre principal de usuario (UPN) de una persona, la dirección URL de su ubicación de OneDrive se cambia para incorporar el nuevo UPN. Si esto ocurre, tiene que modificar una búsqueda de contenido agregando la nueva dirección URL de OneDrive del usuario y quitando la antigua.
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a>Búsqueda de grupos de Microsoft Teams y Office 365

Puede buscar en el buzón de correo asociado con un grupo de Office 365 o un equipo de Microsoft. Debido a que Microsoft Teams se basa en los grupos de Office 365, la búsqueda es similar. En ambos casos, solo se busca en el buzón de grupo o de equipo. No se busca en los buzones de los miembros del equipo o del grupo. Para realizar búsquedas, deberá agregarlas específicamente a la búsqueda.
  
Tenga en cuenta lo siguiente cuando busque contenido en Microsoft Teams y grupos de Office 365.
  
- Para buscar el contenido que se encuentra en Teams and Office 365 grupos, tiene que especificar el buzón de correo y el sitio de SharePoint que están asociados con un equipo o grupo.
    
- Ejecute el cmdlet **Get-UnifiedGroup** en Exchange Online para ver las propiedades de un equipo o un grupo de Office 365. Esta es una buena forma de obtener la dirección URL del sitio que está asociado con un equipo o un grupo. Por ejemplo, el siguiente comando muestra las propiedades seleccionadas de un grupo de Office 365 llamado equipo de liderazgo Senior: 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroup** , debe tener asignado el rol destinatarios con permiso de vista en Exchange online o ser miembro de un grupo de roles que tenga asignado el rol destinatarios con permiso de vista. 
  
- Cuando se realiza una búsqueda en el buzón de un usuario, no se buscará en ningún equipo o grupo de Office 365 del que el usuario sea miembro. De forma similar, cuando se realiza una búsqueda en un equipo o un grupo de Office 365, solo se busca en el buzón de grupo y el sitio de grupo que especifique. Los buzones y las cuentas de OneDrive para la empresa de los miembros del grupo no se buscan a menos que los agregue explícitamente a la búsqueda.
    
- Para obtener una lista de los miembros de un equipo o un grupo de Office 365, puede ver las propiedades de la página de **grupos principales \> ** en el centro de administración de Microsoft 365. Como alternativa, puede ejecutar el siguiente comando en Exchange Online PowerShell: 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroupLinks** , debe tener asignado el rol destinatarios con permiso de vista en Exchange online o ser miembro de un grupo de roles que tenga asignado el rol destinatarios con permiso de vista. 
  
- Las conversaciones que forman parte de un canal de Microsoft Teams se almacenan en el buzón de correo que está asociado al equipo. De forma similar, los archivos que los miembros del equipo comparten en un canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, tiene que agregar el buzón de equipo y el sitio de SharePoint como una ubicación de contenido para buscar conversaciones y archivos en un canal.
    
- Como alternativa, las conversaciones que forman parte de la lista de chats en Microsoft Teams se almacenan en el buzón de correo de Exchange online de los usuarios que participan en el chat. Y los archivos que un usuario comparte en conversaciones de chat se almacenan en la cuenta de OneDrive para la empresa del usuario que comparte el archivo. Por lo tanto, tiene que agregar los buzones de usuario individuales y las cuentas de OneDrive para la empresa como ubicaciones de contenido para buscar conversaciones y archivos en la lista de chats.
    
    > [!NOTE]
    > En una implementación híbrida de Exchange, los usuarios con un buzón de correo local pueden participar en conversaciones que forman parte de la lista de chats de Microsoft Teams. En este caso, el contenido de estas conversaciones también se puede buscar porque se guarda en un área de almacenamiento basada en la nube (denominada *buzón basado en la nube para los usuarios locales*) para los usuarios que tienen un buzón local. Para obtener más información, vea [Buscar buzones de correo basados en la nube para usuarios locales en Office 365](search-cloud-based-mailboxes-for-on-premises-users.md).
  
- Cada canal de equipo o equipo contiene un wiki para la toma de notas y la colaboración. El contenido de la wiki se guarda automáticamente en un archivo con formato. mht. Este archivo se almacena en la biblioteca de documentos de datos wiki de Microsoft Teams en el sitio de SharePoint del equipo. Puede usar la herramienta de búsqueda de contenido para buscar en el sitio wiki especificando el sitio de SharePoint del equipo como la ubicación de contenido en la que se va a buscar. 
    
    > [!NOTE]
    > La capacidad de buscar un equipo o un canal (cuando se realiza una búsqueda en el sitio de SharePoint del equipo) se presentó el 22 de junio de 2017. Las páginas wiki que se guardaron o actualizaron en esa fecha o después están disponibles para su búsqueda. Las páginas wiki que se guardaron o actualizaron por última vez antes de esa fecha no están disponibles para la búsqueda. 
 
- La información de Resumen de las reuniones y las llamadas de un canal de Microsoft Teams también se almacena en los buzones de correo de los usuarios que marcaron la reunión o la llamada. Esto significa que puede usar la búsqueda de contenido para realizar búsquedas en estos registros de resumen. La información de resumen incluye: 
  
  - Fecha, hora de inicio, hora de finalización y duración de una reunión o llamada

  - La fecha y la hora en que cada participante se unió o abandonó la reunión o llamada

  - Llamadas enviadas al correo de voz

  - Llamadas perdidas o no respondidas

  - Transferencias de llamadas, que se representan como dos llamadas independientes

  Las reuniones y los registros de Resumen de llamadas pueden tardar hasta 8 horas en estar disponibles para su búsqueda.

  En los resultados de la búsqueda, los resúmenes de las reuniones se identifican como **reuniones** en el **campo tipo**y los resúmenes de llamadas se identifican como **llamadas**. Además, las conversaciones que forman parte de un canal de Microsoft Teams y los chats 1xN se identifican como **mensajería instantánea** en el campo **tipo** .
  
  ![Las reuniones de Microsoft Teams, las llamadas y los chats de 1xN se identifican en el campo tipo](media/O365-ContentSearch-Teams-MessageKind.png)

- Puede usar la propiedad email de **Kind** o la condición de búsqueda **tipo de mensaje** para buscar contenido en Teams de forma específica. 
  
  - Para usar la propiedad **Kind** como parte de la consulta de búsqueda de palabras clave, escriba `kind:microsoftteams`en el cuadro **palabras clave** de una consulta de búsqueda.

    ![Use el tipo: Microsoft Teams en el cuadro palabras clave](media/O365-ContentSearch-Teams-Keywords.png)
  
  - Para usar una condición de búsqueda, agregue la condición de **tipo de mensaje** y `microsoftteams`use el valor. 

    ![Use la condición de tipo de mensaje con el valor Microsoft Teams.](media/O365-ContentSearch-Teams-MessageKindCondition.png)

Tenga en cuenta que las condiciones se conectan lógicamente a la consulta de palabra clave por el operador **and** . Esto significa que un elemento debe coincidir con la consulta de palabra clave y la condición de búsqueda que se va a devolver en los resultados de la búsqueda. Para obtener más información, vea la sección "instrucciones para usar condiciones" en [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)

  
### <a name="searching-inactive-mailboxes"></a>Buscar buzones inactivos

Puede buscar buzones inactivos en una búsqueda de contenido. Para obtener una lista de los buzones inactivos en su organización, ejecute el `Get-Mailbox -InactiveMailboxOnly` comando en Exchange Online PowerShell. Como alternativa, puede ir a **retención** de **gobierno** \> de datos en el centro de seguridad & cumplimiento y, a continuación, hacer clic](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> en **más**![barra de navegación para los **buzones**inactivos.
  
Estas son algunas de las cosas que debe tener en cuenta al buscar buzones inactivos.
  
- Si una búsqueda de contenido incluye un buzón de correo de usuario y ese buzón de correo se convierte en inactivo, la búsqueda de contenido continuará buscando en el buzón inactivo cuando vuelva a ejecutar la búsqueda después de que se vuelva inactiva.
    
- A veces, un usuario puede tener un buzón activo y un buzón inactivo con la misma dirección SMTP. En este caso, solo se busca en el buzón específico que seleccione como ubicación para una búsqueda de contenido. Es decir, si agrega el buzón de un usuario a una búsqueda, no puede suponer que se busca en los buzones activos e inactivos. Solo se busca en el buzón que agregue explícitamente a la búsqueda.
    
- Le recomendamos encarecidamente que Evite tener un buzón activo y un buzón inactivo con la misma dirección SMTP. Si necesita volver a usar la dirección SMTP asignada a un buzón inactivo, se recomienda que recupere el buzón inactivo o que restaure el contenido de un buzón inactivo en un buzón activo (o el archivo de un buzón activo) y, a continuación, elimine la inactiva bandeja. Para obtener más información, vea uno de los siguientes temas:
    
  - [Recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md)
    
  - [Restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md)
    
  - [Eliminar un buzón inactivo en Office 365](delete-an-inactive-mailbox.md)

  
### <a name="previewing-search-results"></a>Vista previa de los resultados de búsqueda

Puede obtener una vista previa de los tipos de archivo compatibles en el panel de vista previa. Si no se admite un tipo de archivo, tiene que descargar una copia del archivo en el equipo local para poder verlo. Se admiten los siguientes tipos de archivo, que se pueden mostrar en la vista previa del panel de resultados de búsqueda.
  
- . txt,. html,. MHTML
    
- . eml
    
- . doc,. docx y. docm
    
- . pptm,. pptx
    
- .pdf
    
Además, se admiten los siguientes tipos de contenedor de archivos. Puede ver la lista de archivos del contenedor en el panel de vista previa.
  
- .zip
    
- . gzip
    
### <a name="partially-indexed-items"></a>Elementos parcialmente indizados

- Como se ha explicado anteriormente, los elementos parcialmente indizados de los buzones se incluyen en los resultados de búsqueda estimados. Los elementos parcialmente indizados de SharePoint y OneDrive no se incluyen en los resultados de búsqueda estimados. 
    
- Si un elemento parcialmente indizado coincide con la consulta de búsqueda (porque otras propiedades de mensaje o documento cumplen los criterios de búsqueda), no se incluye en el número estimado de elementos sin indexar. Si un elemento parcialmente indizado se excluye por los criterios de búsqueda, no se incluye en el número estimado de elementos sin indexar. Para obtener más información, vea [elementos parcialmente indizados en la búsqueda de contenido en Office 365](partially-indexed-items-in-content-search.md).