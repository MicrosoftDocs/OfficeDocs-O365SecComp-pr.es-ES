---
title: Administrar las solicitudes de asunto GDPR datos con la herramienta de mayúsculas y minúsculas DSR en la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/25/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.assetid: ce9eb942-3589-42cb-88fd-1576ecb09c5c
description: El GDPR proporciona la Unión Europea (denominados a asuntos de datos) de los ciudadanos derechos específicos para sus datos personales; Estos derechos incluyen la obtención de copias de la misma, que solicita los cambios realizados en él, restringir el procesamiento del mismo, eliminarlo o recibir en formato electrónico. Una solicitud formal por un datos sujetos a tomar una acción en sus datos personales se denomina una solicitud de datos de asunto o DSR. Puede usar los casos de DSR en la seguridad de Office 365 &amp; centro de cumplimiento para administrar las investigaciones DSR de su organización.
ms.openlocfilehash: c8edee8d377865d46662ebbd7f18a5a6f3015192
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536294"
---
# <a name="manage-gdpr-data-subject-requests-with-the-dsr-case-tool-in-the-office-365-security-amp-compliance-center"></a>Administrar las solicitudes de asunto GDPR datos con la herramienta de mayúsculas y minúsculas DSR en la seguridad de Office 365 &amp; centro de cumplimiento

Es el de la UE generales datos protección Reglamento (GDPR) acerca de la protección y la habilitación de derechos de privacidad individuales dentro de la Unión Europea (UE). Los individuos GDPR se proporcionan en la Unión Europea (conocido como asuntos de datos) el derecho a tener acceso a, recuperar, corregir, borrar y restringir el procesamiento de sus datos personales. En el GDPR datos personales significan cualquier información relativa a una persona física identificada o identificable. Una solicitud formal por una persona a su organización a realizar alguna acción en sus datos personales se denomina una solicitud de datos de asunto o DSR. Para obtener información detallada sobre cómo responder a la valoración detallada para los datos de Office 365, vea la [Guía de solicitud de datos de asunto de Office 365](https://go.microsoft.com/fwlink/?linkid=871169 ).
  
Para administrar las investigaciones en respuesta a un DSR enviado por una persona de su organización, puede usar la herramienta de mayúsculas y minúsculas DSR en la seguridad de Office 365 &amp; centro de cumplimiento para buscar contenido almacenado en:
  
- Cualquier buzón de usuario de la organización. Esto incluye Skype para conversaciones de negocios y chats uno a uno en Microsoft Teams
    
- Todos los buzones de correo asociados con un grupo de Office 365 y todos los buzones de equipo en Microsoft Teams
    
- Todos los sitios de SharePoint Online y OneDrive para la Empresa de la organización
    
- Todos los sitios de equipos y grupo de Office 365 en su organización
    
- Todas las carpetas públicas de Exchange Online
    
Mediante la herramienta de mayúsculas y minúsculas DSR se puede:
  
- Crear un caso independiente para cada investigación de DSR.
    
- Controlar quién tiene acceso a las mayúsculas y minúsculas DSR mediante la adición de personas como miembros de las mayúsculas y minúsculas; sólo los miembros pueden tener acceso a las mayúsculas y minúsculas y sólo se puede ver sus casos en la lista de los casos en la página **casos DSR** en la seguridad &amp; centro de cumplimiento. Además, puede asignar permisos diferentes a los diferentes miembros de las mismas mayúsculas y minúsculas. Por ejemplo, puede permitir que algunos miembros sólo a ver el caso y resultados de búsqueda y permitir que otros participantes crear búsquedas y exportar los resultados de búsqueda. 
    
- Usar la búsqueda a integrados para todo el contenido creado o cargado por un asunto específico de datos.
    
- Si lo desea revisar la consulta de búsqueda integradas y vuelva a ejecutar la búsqueda para restringir los resultados de búsqueda.
    
- Agregue las búsquedas de contenido adicionales asociadas con el caso DSR. Esto incluye la creación de búsquedas que devuelven elementos indizados parcialmente y registros generados por el sistema de análisis de mi y el servicio de movilidad de Office.
    
- Exportar datos en respuesta a un acceso DSR o solicitud de exportación.
    
- Eliminar de los casos, cuando el proceso de investigación DSR está completado; se quitarán todas las búsquedas y exportar trabajos asociados con las mayúsculas y minúsculas.
    
Este es el proceso de alto nivel para el uso de la herramienta de mayúsculas y minúsculas DSR para administrar las investigaciones DSR:
  
[Paso 1: Asignar permisos de exhibición de documentos electrónicos a posibles miembros del caso](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[Paso 2: Crear un caso de DSR y agregar miembros](#step-2-create-a-dsr-case-and-add-members)

[Paso 3: Ejecutar la consulta de búsqueda](#step-3-run-the-search-query)

[Paso 4: Exportar los datos](#step-4-export-the-data)

[(Opcional) Paso 5: Revisar la consulta de búsqueda integradas](#optional-step-5-revise-the-built-in-search-query)

[Para obtener más información acerca del uso de la herramienta de mayúsculas y minúsculas de DSR](#more-information-about-using-the-dsr-case-tool)
  
> [!IMPORTANT]
> Nuestras herramientas pueden ayudar a los administradores realizar acceso DSR o solicitudes de exportación por lo que les permite utilizar la búsqueda integrada y funcionalidad que se encuentran en la herramienta de mayúsculas y minúsculas DSR de exportación. La herramienta de ayuda a facilitar un método de mejor esfuerzo para exportar los datos que es relevantes para una solicitud de DSR enviada por un asunto de datos. Sin embargo, es importante tener en cuenta que los resultados de búsqueda pueden variar en función del asunto de datos o las acciones de administración lleva a cabo que pueden afectar al si un elemento se considerará como "datos personales" para la exportación. Por ejemplo, si el asunto de datos fue la última persona que modificó un archivo no ha creado, el archivo no es posible que se devuelven en los resultados de búsqueda. De forma similar, un administrador puede exportar datos sin incluir los elementos indizados parcialmente o todas las versiones de documentos de SharePoint. Por lo tanto, las herramientas proporcionadas pueden ayudar a facilitar el acceso y exportación de las solicitudes de datos; Sin embargo, los resultados están sujetas a específicos escenarios de uso de asunto de administración y datos. 
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a>Paso 1: Asignar permisos de exhibición de documentos electrónicos a posibles miembros del caso

De forma predeterminada, un administrador global de Office 365 puede tener acceso a la herramienta de mayúsculas y minúsculas DSR en la seguridad &amp; centro de cumplimiento. Por diseño, otros usuarios como un responsable de privacidad de datos, un administrador de recursos humanos, u otras personas que participen en las investigaciones DSR no tienen acceso a la herramienta de mayúsculas y minúsculas de DSR y tendrán que asignar los permisos adecuados para tener acceso a la herramienta. La forma más sencilla de hacer esto es ir a la página de **permisos** en la seguridad &amp; centro de cumplimiento y agregar usuarios al grupo de roles de administrador de exhibición de documentos electrónicos. Tenga en cuenta que también se debe asignar estos permisos para que pueda agregar como miembros de la caja del DSR que cree en el paso 2. 
  
Para obtener instrucciones detalladas, consulte [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).
  
> [!NOTE]
> De forma predeterminada, un administrador global de Office 365 (u otros miembros del grupo de roles de administración de la organización en la seguridad &amp; centro de cumplimiento no tiene los permisos necesarios para exportar los resultados de búsqueda de contenido (consulte el paso 4 de este artículo). Para solucionar esto, un administrador puede agregar a sí mismos como un miembro del grupo de roles de administrador de exhibición de documentos electrónicos. 
  
## <a name="step-2-create-a-dsr-case-and-add-members"></a>Paso 2: Crear un caso de DSR y agregar miembros

El siguiente paso es crear un caso DSR. Cuando se crea un caso, puede elegir iniciar la búsqueda integrada o puede crear el caso sin iniciar la búsqueda. El siguiente procedimiento le indicará que para crear el caso sin iniciar la búsqueda y, a continuación, mostrar los procedimientos para agregar a miembros a las mayúsculas y minúsculas.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión en Office 365 con su cuenta de trabajo o escuela. 
    
2. En la seguridad &amp; centro de cumplimiento, haga clic en **privacidad de los datos** \> **las solicitudes de datos sujeto**y, a continuación, haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.gif) **DSR nuevo caso**.
    
3. En la página de emergente **DSR nuevo caso** , asigne un nombre a las mayúsculas y minúsculas, escriba una descripción opcional y, a continuación, haga clic en **siguiente**. Tenga en cuenta que el nombre de las mayúsculas y minúsculas debe ser único en la organización.
    
    > [!TIP]
    > Considere la posibilidad de agregar el nombre de la persona que envió la solicitud DSR que está investigar en el nombre o la descripción del nuevo caso. Tenga en cuenta que sólo los miembros de este caso (y los administradores de la exhibición de documentos electrónicos) podrán ver el caso de la lista de los casos en la página **solicitudes de asunto de datos** . 
  
4. En la página de **Detalles de la solicitud** , en **el asunto de datos (es decir, la persona que archivó esta solicitud)**, seleccione a la persona que desea buscar y exportar datos para y, a continuación, haga clic en **siguiente**.
    
5. En la página **Confirmar la configuración de mayúsculas y minúsculas** , puede cambiar el nombre del caso y la descripción y seleccione a un asunto de datos diferentes. De lo contrario, simplemente haga clic en **Guardar**.
    
    Se muestra una página que confirma que se ha creado el nuevo caso DSR.
    
    ![Iniciar la búsqueda o simplemente cierre la página caso DSR nuevo](media/b5e62c2c-cafe-4a8d-a38c-789ed9f9ccbd.png)
  
    En este momento, puede realizar una de estas dos cosas:
    
    r. al hacer clic en **Mostrar los resultados de la búsqueda** se inicia la búsqueda. Esta es la selección predeterminada. La búsqueda integrada que se ejecuta cuando se selecciona esta opción y los resultados que se devuelven se tratan en el paso 3.
    
    b. hacer clic en **Finalizar** , se cierra el nuevo caso DSR sin iniciar la búsqueda integrada. Cuando se selecciona esta opción, el nuevo caso DSR se muestra en la página **solicitudes de datos de asunto** .
    
6. Haga clic en **Finalizar** para que pueda ir el caso de DSR nueva y agregar a miembros a ella. 
    
7. En la página **solicitudes de sujeto de datos** , haga clic en el nombre de la caja del DSR que acaba de crear. 
    
8. En la página de emergente **administrar este caso** , en **miembros de administrar**, haga clic en **Agregar**. 
    
    En **usuarios**, se muestra una lista de personas que se han asignado los permisos adecuados exhibición de documentos electrónicos. Tenga en cuenta que las personas que asignó permisos de exhibición de documentos electrónicos para en el paso 1 se mostrará en esta lista. 
    
9. Seleccione las personas que desea agregar como miembros de la caja del DSR, haga clic en **Agregar**y, a continuación, guarde los cambios.
    
    Tenga en cuenta que también puede agregar grupos de roles como miembros del caso DSR haciendo clic en **Agregar** en **Administrar grupos de roles**. 
    
## <a name="step-3-run-the-search-query"></a>Paso 3: Ejecutar la consulta de búsqueda

Después de crear un caso de DSR y agregar a miembros, el siguiente paso es ejecutar la búsqueda integrada que está asociado con el caso. Esta consulta de búsqueda predeterminada hace lo siguiente:
  
- Busca en todos los buzones de la organización para todos los elementos de correo electrónico que se han enviado o recibido por el asunto de datos. Esto se logra mediante el uso de la propiedad de correo electrónico de *los participantes* , que busca el asunto de datos en todos los campos de personas en un mensaje de correo electrónico. Esta propiedad devuelve los elementos en los que el asunto de datos se encuentra en el **de**, **para**, **CC**y **CCO** campos. Las carpetas públicas en Exchange Online también se buscan mensajes enviados o recibidos por el objeto de datos. 
    
- Busca en todos los sitios de la organización de documentos y elementos que se crearon o cargados por el asunto de datos. Esto se logra mediante el uso de las siguientes propiedades de sitio:
    
  - La propiedad *Author* devuelve los elementos donde se muestra el asunto de datos en el campo autor en documentos de Office. Este valor se conserva, incluso si el documento se copia y cargado por otra persona. 
    
  - La propiedad *CreatedBy* devuelve los elementos que se crearon o cargados por el asunto de datos. 
    
Este es el aspecto de la consulta de palabras clave para la búsqueda integrada que se crea automáticamente cuando se crea un caso DSR.
  
```
participants:"<email address>" OR author:"<display name>" OR createdby:"<display name>"
```

Por ejemplo, si el nombre del sujeto de datos es Ina Leonte, la consulta de palabra clave tendría este aspecto:
  
```
participants:"ina@contoso.com" OR author:"Ina Leonte" OR createdby:"Ina Leonte"
```

 **Para ejecutar la búsqueda integrada para un caso de DSR:**
  
1. En la seguridad &amp; centro de cumplimiento, haga clic en **privacidad de los datos** \> de **las solicitudes de datos de asunto**y, a continuación, haga clic en **Abrir** junto al caso DSR que creó en el paso 2. 
    
    Haga clic en la ficha de **búsqueda** en la parte superior de la página y, a continuación, haga clic en la casilla de verificación situada junto a la búsqueda integrada que se creó cuando creó el nuevo caso DSR. Tenga en cuenta que la búsqueda tiene el mismo nombre que el caso DSR. 
    
2. En la página emergente de búsqueda, haga clic en **Abrir consulta**.
    
    Cuando se abre la consulta, la búsqueda se inicia y se completará en unos minutos. 
    
3. Una vez finalizada la búsqueda, haga clic en **vista previa de resultados** para obtener una vista previa de los resultados de búsqueda. Para obtener más información, vea [vista previa de resultados de búsqueda](content-search.md#preview-search-results).
    
    > [!TIP]
    > También puede ver las estadísticas de consulta de búsqueda para ver el número de buzones de correo y los elementos de sitio que son devueltos por la búsqueda y las ubicaciones de contenido principales que contienen elementos que coinciden con la consulta de búsqueda. Para obtener más información, vea [Ver la información y estadísticas sobre una búsqueda](content-search.md#view-information-and-statistics-about-a-search). 
  
Puede editar la consulta de búsqueda integradas, cambiar las ubicaciones de contenido que se buscan y, a continuación, vuelva a ejecutar la búsqueda. Para obtener más información, vea el [paso 5](#optional-step-5-revise-the-built-in-search-query) . 
  
## <a name="step-4-export-the-data"></a>Paso 4: Exportar los datos

Después de ejecutar la búsqueda integrada, puede exportar los resultados de búsqueda. Como alternativa, antes de exportar los datos, es posible que desee revisar la consulta para reducir el número de resultados de búsqueda. Vea el paso 5 para obtener más información acerca de los resultados de búsqueda de restricción.
  
Al exportar los resultados de búsqueda, se pueden descargar los elementos del buzón en los archivos PST o como los mensajes individuales. Al exportar el contenido de las cuentas de SharePoint y OneDrive, se exportan copias de los documentos de Office nativos y otros documentos. Un archivo de resultados que contiene información acerca de cada elemento que se ha exportado también se incluye con los resultados de búsqueda. Para obtener más información acerca de la exportación, vea [resultados de búsqueda de contenido de exportación de la seguridad de Office 365 &amp; centro de cumplimiento](export-search-results.md).
  
> [!NOTE]
> De forma predeterminada, un administrador global de Office 365 (u otros miembros del grupo de roles de administración de la organización en la seguridad &amp; centro de cumplimiento) no tiene los permisos necesarios para exportar los resultados de búsqueda de contenido. Para solucionar esto, un administrador puede agregar a sí mismos como un miembro del grupo de roles de administrador de exhibición de documentos electrónicos. 
  
El equipo que utilice para exportar datos debe cumplir los siguientes requisitos del sistema:
  
- Versiones de 32 o 64 bits de Windows 7 y versiones posteriores
    
- Microsoft .NET Framework 4.7
    
- Un explorador compatible:
    
  - Microsoft Edge
    
    O bien
    
  - Microsoft Internet Explorer 10 y versiones posteriores
    
    > [!NOTE]
    > Microsoft no fabrica las extensiones de terceros o complementos para las aplicaciones ClickOnce. No se admite la exportación de datos mediante un explorador no compatible con las extensiones de terceros o los complementos. 
  
 **Para exportar datos de la búsqueda integrada en un caso DSR:**
  
1. En la seguridad &amp; centro de cumplimiento, haga clic en **privacidad de los datos** \> de **las solicitudes de datos de asunto**y, a continuación, haga clic en **Abrir** junto al caso DSR que desea exportar datos desde. 
    
2. Haga clic en la ficha de **búsqueda** en la parte superior de la página y, a continuación, haga clic en la casilla de verificación situada junto a la búsqueda integrada que se creó cuando creó el caso DSR. O bien, haga clic en otra búsqueda para exportar datos desde que la búsqueda. 
    
3. En la página emergente de búsqueda, haga clic en ![icono de resultados de búsqueda de exportación](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **más**y, a continuación, seleccione **los resultados de la exportación** de la lista desplegable. 
    
4. En la página **exportar los resultados** , seleccione las siguientes opciones para las solicitudes de exportación DSR recomendadas. 
    
    ![Configurar las opciones de exportación](media/25416b79-57da-46a1-ae07-e640602a8fa4.png)
  
    r. en **las opciones de salida**, seleccione la primera opción ( **todos los artículos, excepto los que tienen las que tienen un formato no reconocido, se cifran o no estaban indizados por otras razones**) para exportar sólo los elementos indizados. La razón por la que no desea exportar elementos indizados parcialmente de la búsqueda integrada es debido a que se van a exportar los elementos parcialmente indizados de otros usuarios. Para exportar sólo los elementos indizados parcialmente para el asunto de datos, se recomienda que cree una búsqueda independiente. Para obtener más información, consulte [exportar elementos indizados parcialmente](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#exportunindexeditems) en la sección "Más información acerca del uso de la herramienta de mayúsculas y minúsculas DSR".
    
    b. en **Exchange exportar contenido como**, seleccione la tercera opción, **archivo PST uno que contiene todos los mensajes en una sola carpeta**. Debido a que algunos de los resultados pueden ser por los elementos que se originaron en el buzón de otro usuario, esta opción sólo muestra el elemento en una sola carpeta sin que indica que el buzón de correo real y es la mejor opción para usar cuando desaprovisionamiento duplicar los resultados como se recomienda en el siguiente elemento . Esta opción también permite el asunto datos revise los elementos en orden cronológico (los elementos se ordenan por fecha de envío) sin tener que desplazarse por la estructura de carpeta de buzón de correo original para cada elemento.
    
    c. Seleccione la opción de **Habilitar la desduplicación** excluye los mensajes de correo electrónico duplicados. Se recomienda esta opción debido a que la búsqueda integrada busca en todos los buzones de la organización. Por lo que si se encuentran varias copias del mismo mensaje en los buzones que se han buscado, esta opción significa que sólo una copia de un mensaje que se van a exportar. Esta opción, juntos va a exportar mensajes en una archivo PST en una sola carpeta da como resultado la mejor experiencia de usuario para DSR solicitudes de exportación. Tenga en cuenta que el informe de exportación Results.csv obtendrá una lista con todas las ubicaciones donde se han encontrado mensajes duplicados.
    
    De forma opcional, puede seleccionar la opción de **incluir las versiones de documentos de SharePoint** para exportar todas las versiones de documentos de SharePoint y OneDrive. Esto requiere que el control de versiones está activado para las bibliotecas de documentos. Esta opción ayuda a garantizar que todos los datos relevantes se exportan.
    
5. Después de elegir la configuración de exportación, haga clic en **Exportar**.
    
    Los resultados de búsqueda estén preparados para descargar el archivo, lo que significa que están cargados en el área de almacenamiento de Azure para su organización en la nube de Microsoft. Los siguientes pasos muestran cómo descargar estos datos en el equipo local.
    
6. Haga clic en la ficha **Exportar** para mostrar el trabajo de exportación que acaba de crear. Tenga en cuenta que los trabajos de exportación tienen el mismo nombre que el correspondiente **_Export** anexado al final del nombre de búsqueda para la búsqueda. 
    
7. Haga clic en el trabajo de exportación que acaba de crear para mostrar la página emergente de exportación. Esta página muestra información acerca de la búsqueda, como el tamaño y el número total de elementos que se va a exportar y el porcentaje de los elementos que se han transferido a un área de almacenamiento de Azure. Haga clic en **Actualizar** para actualizar la información de estado de carga. 
    
8. **Exportar la clave**, haga clic en **Copiar al Portapapeles**. Para descargar los resultados de búsqueda va a usar esta clave en el paso 11.
    
9. Haga clic en ![icono de resultados de búsqueda de exportación](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **descargar los resultados** en la parte superior de la página emergente de exportación. 
    
10. En la ventana emergente en la parte inferior de la página, haga clic en **Abrir** para abrir la **exhibición de documentos de Microsoft Office 365 herramienta para exportar**. La **herramienta de exportación de exhibición de documentos** se instalará la primera vez que descargue los resultados de búsqueda. 
    
11. En la **herramienta de exportación de eDiscovery**, pegue la clave de exportación que se copió en el paso 8 en el cuadro correspondiente.
    
12. Haga clic en **Examinar** para especificar la ubicación en la que desea descargar los archivos de los resultados de la búsqueda. 
    
    > [!NOTE]
    > Debido a la gran cantidad de actividad de disco (lecturas y escrituras), debe descargar los resultados de búsqueda a una unidad de disco local; No, se descargan en una unidad de red asignada u otra ubicación de red. 
  
13. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo. 
    
    La **exhibición de documentos electrónicos herramienta para exportar** muestra información de estado sobre el proceso de exportación, así como una estimación del número (y tamaño) de los elementos restantes para ser descargado. Cuando se completa el proceso de exportación, puede tener acceso a los archivos en la ubicación donde se han descargado. Para obtener más información acerca de los informes que incluyen al descargar los resultados de la búsqueda de contenido, vea la sección [obtener más información](export-search-results.md#more-information) en "resultados de búsqueda de contenido de exportación de la seguridad de Office 365 &amp; centro de cumplimiento". 
    
Después de que los datos se exportan, los resultados de la búsqueda y los informes de exportación se encuentran en una carpeta que tiene el mismo nombre que el caso DSR. Los archivos PST que contienen elementos de buzón de correo se encuentran en una subcarpeta con el nombre de **Exchange**. Documentos y otros elementos de los sitios se encuentran en una subcarpeta denominada **SharePoint**. 
  
## <a name="optional-step-5-revise-the-built-in-search-query"></a>(Opcional) Paso 5: Revisar la consulta de búsqueda integradas

Después de ejecutar la búsqueda integrada, puede revisarlo para reducir el ámbito para devolver menos los resultados de búsqueda. Para ello, puede agregar condiciones a la consulta. Una condición lógicamente está conectada a la consulta de palabra clave por el operador **AND** . Esto significa que se devuelve en los resultados de búsqueda, deben cumplir los elementos de la consulta de palabras clave y las condiciones que agrega. Se trata de cómo ayudar a condiciones para restringir los resultados. Si agrega dos o más condiciones únicas a una consulta de búsqueda (condiciones que especifican distintas propiedades), esas condiciones están conectadas lógicamente mediante el operador **AND** . Esto significa que se devuelven sólo los elementos que cumplen todas las condiciones (además de la consulta de palabras clave). Si agrega varios valores (separados por comas o punto y coma) a una única condición, esos valores están conectados por el operador **o** . Esto significa que se devuelven los elementos si contienen cualquiera de los valores especificados para la propiedad en la condición. 
  
Estos son algunos ejemplos de las condiciones que se pueden agregar a la consulta de búsqueda integradas de un caso de DSR. El nombre de la propiedad real utilizada en una consulta de búsqueda se muestra entre paréntesis.
  
- **Tipo de archivo ( `filetype`)** -especifica la extensión de un documento o archivo. Use esta condición para buscar documentos y los archivos creados por las aplicaciones específicas de Office, como Word, Excel y OneNote. 
    
- **Tipo de mensaje ( `kind`)** -especifica el tipo de elemento de correo electrónico que se va a buscar. Por ejemplo, puede usar la sintaxis `kind:email OR kind:im` para devolver solo los mensajes de correo electrónico y Skype para conversaciones de negocios o charlas uno a uno en Microsoft Teams. 
    
- **Etiqueta de cumplimiento (`compliancetag`)** -especifica una etiqueta asignada a un documento o un mensaje de correo electrónico. Esta condición devolverá los elementos que se clasifican con una etiqueta específica. Las etiquetas se usan para clasificar el correo electrónico y documentos de gobierno de datos y aplicar las reglas de retención basadas en la clasificación definida por la etiqueta. Ésta es una condición útil para investigaciones DSR debido a que su organización puede usar etiquetas para clasificar el contenido relacionado con la privacidad de los datos o que contenga datos personales o información confidencial. Para el valor de esta condición, use el nombre de la etiqueta completa o la primera parte del nombre de la etiqueta con un carácter comodín. Para obtener más información, vea [información general de las etiquetas en Office 365](labels.md).
    
Para una lista y una descripción de todas las condiciones disponibles en la herramienta de mayúsculas y minúsculas DSR, consulte [condiciones de búsqueda](keyword-queries-and-search-conditions.md#search-conditions) en el artículo "consultas de palabra clave y las condiciones de búsqueda para la búsqueda de contenido". 
  
### <a name="changing-the-content-locations-that-are-searched"></a>Cambiar las ubicaciones de contenido que se buscan

Además de revisar la búsqueda integrada para un caso de DSR, también puede cambiar las ubicaciones de contenido que se buscan. Como se explica anteriormente, la búsqueda integrada busca todos los buzones y sitios de la organización y las carpetas públicas de Exchange Online. Por ejemplo, podría restringir la búsqueda para buscar sólo el buzón de correo y la cuenta de OneDrive el asunto de datos y selecciona los sitios de SharePoint. Si opta por buscar en sitios específicos, debe agregar cada sitio que se va a buscar.
  
Para modificar las ubicaciones de contenido para buscar:
  
1. Abra la búsqueda integrada que desea cambiar las ubicaciones de contenido de.
    
2. En la consulta de búsqueda, en **las ubicaciones**, haga clic en **Modificar** junto a la opción **ubicaciones específicas** . 
    
    ![Haga clic en Modificar para cambiar las ubicaciones de contenido de la consulta de búsqueda integradas](media/d66f7ba7-b71f-4ff5-a030-460ff02e3123.png)
  
    Se muestra la página emergente **modificar ubicaciones** . Ésta es una descripción de las ubicaciones del contenido de la búsqueda integrada y cierta información acerca de cómo modificar las ubicaciones que se buscan. 
    
    ![Modificar página emergente de ubicaciones](media/56c033f6-6735-46ba-abb2-a263a2b79836.png)
  
    r. la alternancia en **Seleccionar todo** en la sección de buzón de correo en la parte superior de la página emergente está activada, lo que indica que se buscan todos los buzones. Para limitar el ámbito de la búsqueda, haga clic en la alternancia para anular la selección de él y, a continuación, haga clic en **Elegir usuarios, grupos o equipos** y elija buzones específicos para buscar.
    
    b. la alternancia en **Seleccionar todo** en la sección sitios del centro de la página emergente está activada, lo que indica que se busca en todos los sitios. Para restringir la búsqueda a los sitios seleccionados, ¿anular la selección de la alternancia y, a continuación, haga clic en **Elija sitios**. Tendrá que agregar cada sitio específico que se desea buscar, con la cuenta de OneDrive del interesado.
    
    c. la alternancia en la sección de las carpetas públicas de Exchange está activada, lo que significa que se buscan todas las carpetas públicas de Exchange. Tenga en cuenta que sólo puede buscar todas las carpetas públicas de Exchange o ninguno de ellos. No puede elegir cuáles específicos a buscar.
    
3. Si modifica las ubicaciones del contenido de la búsqueda integrada, haga clic en **Guardar &amp; ejecutar** para volver a iniciar la búsqueda. 
  
## <a name="more-information-about-using-the-dsr-case-tool"></a>Para obtener más información acerca del uso de la herramienta de mayúsculas y minúsculas de DSR

En las secciones siguientes contienen más información acerca del uso de la herramienta de mayúsculas y minúsculas DSR para responder a las solicitudes de exportación DSR.
  
[Exportación de datos desde MyAnalytics y el servicio de movilidad de Office](#exporting-data-from-myanalytics-and-the-office-roaming-service)

[Exportación de los elementos indizados parcialmente](#exporting-partially-indexed-items)

[Búsqueda y exportación de datos de Microsoft Teams y grupos de Office 365](#searching-and-exporting-data-from-microsoft-teams-and-office-365-groups)

[Buscar en carpetas públicas de Exchange](#searching-exchange-public-folders)
  
### <a name="exporting-data-from-myanalytics-and-the-office-roaming-service"></a>Exportación de datos desde MyAnalytics y el servicio de movilidad de Office

Puede usar la herramienta de mayúsculas y minúsculas DSR para buscar y exportar datos de uso que se generan por MyAnalytics y el servicio de movilidad de Office. Ésta es una descripción de lo que hacer estos servicios:
  
- **MyAnalytics** - proporciona a los usuarios con conocimientos acerca de cómo dedican el tiempo en función de los datos de correo y de calendario en su buzón. Todos los conocimientos de MyAnalytics se derivan de los encabezados de correo electrónico y reuniones en el buzón del usuario. Los usuarios que están asignados a una licencia de MyAnalytics pueden iniciar sesión en Office 365 y vaya al panel de MyAnalytics para ver toda la información acerca de cómo dedican el tiempo. (Los usuarios pueden capturas de pantalla de estos conocimientos en respuesta a una solicitud de acceso DSR). La búsqueda integrada en un caso DSR va a exportar los datos que se usan para generar conocimientos MyAnalytics. 
    
- **Servicio de movilidad de office** - móviles es un servicio que almacena la configuración relacionada con Office, como tema de Office, diccionario personalizado, configuración de idioma, modo de programador y automático correcta. 
    
Los datos de MyAnalytics y el servicio de movilidad de Office se almacenan en el buzón de un sujeto datos en carpetas ocultas que se encuentra en un subárbol de mensajes no interpersonales (no IPM) de buzones de Exchange Online. Esto significa que los datos están ocultos de la vista del usuario al usar Outlook u otros clientes de correo para tener acceso a su buzón. Para obtener más información acerca de las carpetas ocultas, vea [Carpetas ocultas de MAPI](https://go.microsoft.com/fwlink/?linkid=872758).
  
Puede crear una búsqueda de contenido independiente (y asociarlo a un caso DSR) que devuelve el MyAnalytics y los datos de uso del servicio de movilidad de Office en el buzón de asuntos de los datos. Estos datos no se incluyen en las estadísticas de búsqueda y no estará disponible para la vista previa. Pero puede exportarla y, a continuación, asígnele el asunto de datos en respuesta a una solicitud de exportación DSR.
  
Al exportar datos desde MyAnalytics y el servicio de movilidad de Office, se guardan los datos en una carpeta independiente para cada aplicación que se encuentra en la carpeta **ApplicationDataRoot** , que se encuentra en una carpeta que es el nombre con la dirección de correo electrónico del sujeto de datos. Estos datos se exportan como archivos JSON, que son similares a los archivos XML o TXT, que se adjuntan a los mensajes de correo electrónico de archivos de texto legible. Actualmente, estas carpetas se denominan con un identificador único global (GUID) que se asigna a MyAnalytics y el servicio de movilidad de Office, que se enumeran en la siguiente tabla. En las futuras versiones de la herramienta de mayúsculas y minúsculas DSR, el GUID se reemplazará con el nombre de la aplicación real. 
  
|**Aplicación**|**Nombre de la carpeta o GUID**|
|:-----|:-----|
|MyAnalytics  <br/> |3c896ded-22c5-450F-91f6-3d1ef0848f6e  <br/> |
|Servicio de roaming de Office  <br/> |1caee58f-eb14-4a6b-9339-1fe2ddf6692b  <br/> |
   
 **Para buscar y exportar datos MyAnalytics y servicio de movilidad de Office:**
  
1. En la seguridad &amp; centro de cumplimiento, haga clic en **privacidad de los datos** \> de **las solicitudes de datos de asunto**y, a continuación, haga clic en **Abrir** junto a las mayúsculas y minúsculas DSR para el asunto de datos que se va a exportar los datos de uso para. 
    
2. Haga clic en la ficha de **búsqueda** en la parte superior de la página y, a continuación, haga clic en ![icono Agregar](media/ITPro-EAC-AddIcon.gif) **búsqueda guiada**.
    
3. En la página **nombre de la búsqueda** , haga clic en **Cancelar** . 
    
4. En la **consulta de búsqueda**, en el **tipo de** condición, seleccione las casillas de verificación junto a **Servicio de movilidad de Office**y **MyAnalytics** . 
    
    ![Seleccione las casillas de verificación MyAnalytics y servicio de movilidad de Office para exportar los datos de uso](media/3dacbc7a-c314-492c-828c-6757fda84963.png)
  
    Tenga en cuenta que la condición de **tipo** (que son las clases de mensajes de correo electrónico) debe ser el único elemento en la consulta de búsqueda. Puede eliminar el cuadro **palabras clave** o déjelo en blanco. 
    
5. En **ubicaciones**, asegúrese de que está seleccionado **ubicaciones específicas** y, a continuación, haga clic en **Modificar**.
    
6. En la parte superior de la página de emergente de **modificar ubicaciones** (sección de buzón de correo), haga clic en **Elegir usuarios, grupos o equipos**.
    
7. En la página **Editar ubicaciones** , haga clic en **Elegir usuarios, grupos o equipos**, elija buzón del asunto de datos y, a continuación, guarde la selección. 
    
8. Haga clic en **Guardar &amp; ejecutar**y, a continuación, asigne el nombre de la búsqueda y vuelva a guardarla.
    
    Se inicia la búsqueda.
    
 **Para exportar datos de MyAnalytics y el servicio de movilidad de Office:**
  
1. Una vez finalizada la búsqueda que creó en el paso anterior, haga clic en la ficha de **búsqueda** en la parte superior de la página y, a continuación, haga clic en la casilla de verificación situada junto a la búsqueda. Es posible que deba haga clic en ![actualizar](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) **Actualizar** para mostrar la búsqueda. 
    
2. En la página emergente de búsqueda, haga clic en ![icono de resultados de búsqueda de exportación](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **más**y, a continuación, seleccione **los resultados de la exportación** de la lista desplegable. 
    
3. En la página **exportar los resultados** , seleccione estas opciones para exportar datos de uso recomendadas. 
    
    ![Opciones de exportación al exportar datos de uso MyAnalytics y servicio de movilidad de Office](media/470a7d1e-eeae-4b42-95aa-15cb82ce2f68.png)
  
    r. en **las opciones de salida**, seleccione la primera opción ( **todos los artículos, excepto los que tienen las que tienen un formato no reconocido, se cifran o no estaban indizados por otras razones**) para exportar sólo los elementos indizados.
    
    b. en **Exchange exportar contenido como**, seleccione la segunda opción, **archivo PST uno que contiene todos los mensajes**.
    
    c. deje las opciones de exportación restantes no está seleccionadas.
    
4. Después de elegir la configuración de exportación, haga clic en **Exportar**.
    
    Los resultados de búsqueda estén preparados para descargar el archivo, lo que significa que están cargados en el área de almacenamiento de Azure para su organización en la nube de Microsoft. Los siguientes pasos muestran cómo descargar estos datos en el equipo local.
    
5. Haga clic en la ficha **Exportar** para mostrar el trabajo de exportación que acaba de crear. Tenga en cuenta que los trabajos de exportación tienen el mismo nombre que el correspondiente **_Export** anexado al final del nombre de búsqueda para la búsqueda. 
    
6. Haga clic en el trabajo de exportación que acaba de crear para mostrar la página emergente de exportación. 
    
7. **Exportar la clave**, haga clic en **Copiar al Portapapeles**. Para descargar los resultados de búsqueda va a usar esta clave en el paso 10.
    
8. Haga clic en ![icono de resultados de búsqueda de exportación](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **descargar los resultados** en la parte superior de la página emergente de exportación. 
    
9. En la ventana emergente en la parte inferior de la página, haga clic en **Abrir** para abrir la **exhibición de documentos de Microsoft Office 365 herramienta para exportar**. La **herramienta de exportación de exhibición de documentos** se instalará la primera vez que descargue los resultados de búsqueda. 
    
10. En la **Herramienta de exportación de exhibición de documentos electrónicos**, pegue la clave de exportación que ha copiado en el paso 7 en el cuadro correspondiente.
    
11. Haga clic en **Examinar** para especificar la ubicación en la que desea descargar los archivos de los resultados de la búsqueda. 
    
    > [!NOTE]
    > Debido a la gran cantidad de actividad de disco (lecturas y escrituras), debe descargar los resultados de búsqueda a una unidad de disco local; No, se descargan en una unidad de red asignada u otra ubicación de red. 
  
12. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo. 
    
    La **exhibición de documentos electrónicos herramienta para exportar** muestra información de estado sobre el proceso de exportación, así como una estimación del número (y tamaño) de los elementos restantes para ser descargado. Cuando se completa el proceso de exportación, puede abrir el archivo PST de Exchange en Outlook y, a continuación, vaya a la carpeta **ApplicationDataRoot** para tener acceso a las subcarpetas al servicio MyAnalytics y móviles. 
    
    Como se explica anteriormente, los archivos JSON que contiene los datos de uso se adjuntan a los mensajes. Para ver un archivo JSON, haga clic en un mensaje y, a continuación, abra el archivo adjunto de JSON. 
  
### <a name="exporting-partially-indexed-items"></a>Exportación de los elementos indizados parcialmente

Se recomienda que no exportar elementos indizados parcialmente (también denominados elementos sin indizar) de la búsqueda integrada que se crea al crear un nuevo caso DSR. Que es debido a que la búsqueda de resultados más probable es que incluirá parcialmente indiza los elementos de otros usuarios de la organización y no sólo parcialmente indiza elementos para el asunto de datos). En su lugar, se recomienda que cree una búsqueda de contenido independiente que está asociado con el caso DSR que se ha diseñado para exportar sólo los elementos indizados parcialmente relacionados con el asunto de datos. 
  
Este es un proceso de alto nivel para exportar elementos indizados parcialmente. Después de que se estén de exportación, puede revisarlos para determinar si responde a un acceso DSR un elementos o solicitud de exportación.
  
1. Abra el caso DSR y crear una nueva búsqueda en la página de **búsqueda** . 
    
2. Utilice los criterios siguientes para configurar la consulta de búsqueda y las ubicaciones de contenido para buscar:
    
    - Usar una consulta de palabra clave empty o en blanco. Esto devolverá todos los elementos en las ubicaciones de contenido que se buscan.
    
    - Buscar sólo buzón de Exchange Online del interesado y su cuenta de OneDrive.
    
3. Después de ejecutar la búsqueda y finaliza, puede exportar y descargar los resultados de búsqueda (como se describe en el [paso 4](#step-4-export-the-data)). Use la siguiente configuración para exportar elementos indizados parcialmente. 
    
    - En **Opciones de salida**, seleccione la tercera opción para exportar sólo los elementos indizados parcialmente ( **sólo los elementos que tienen un formato no reconocido, se cifran, o no estaban indizados por otras razones**).
    
    - En **Exchange exportar contenido como**, puede seleccionar cualquier opción en función de sus preferencias. 
    
    - Seleccionar la opción de **incluir las versiones de documentos de SharePoint** va a exportar versiones de los documentos si una versión está indizada parcialmente. 
    
Para obtener más información acerca de los elementos indizados parcialmente, consulte: 
  
- [Elementos parcialmente indizados en la búsqueda de contenido en Office 365](partially-indexed-items-in-content-search.md)

- [Exportación de los elementos indizados parcialmente](export-search-results.md#exporting-partially-indexed-items)
    
### <a name="searching-and-exporting-data-from-microsoft-teams-and-office-365-groups"></a>Búsqueda y exportación de datos de Microsoft Teams y grupos de Office 365

Las conversaciones que forman parte de la lista de Chat en Teams Microsoft (denominado chats de equipo o charlas uno a uno) se almacenan en el buzón de Exchange Online de los usuarios que participan en los chats. Además, los archivos de que recursos compartidos de una persona en una charla de uno a uno se almacenan en la cuenta de OneDrive de la persona que comparte el archivo. Debido a que la búsqueda integrada busca todos los buzones de correo y las cuentas de OneDrive en la organización, se devolverán mediante la búsqueda integrada en un caso DSR chats de equipo y documentos compartidos en una sesión de chat (que crea o carga en el asunto de datos).
  
Como alternativa, las conversaciones que forman parte de un canal de los equipos (también denominado mensajes del canal) se almacenan en el buzón de correo que está asociado con un equipo. Estos tipos de conversaciones que el asunto de datos participó en también son devueltos por la búsqueda integrada debido a que se buscan todos los buzones asociados con Microsoft Teams. Además, los mosaicos que es posible que ha compartido un asunto de datos en un canal de los equipos se almacenan en el sitio de SharePoint del equipo. Los archivos crean o uploadedby el asunto de datos será devuelto por la búsqueda integrada en un caso DSR debido a que los sitios asociados con Microsoft Teams se incluyen en la búsqueda.
  
De forma similar, los buzones de correo y los sitios de SharePoint que corresponden a un grupo de Office 365 también se incluyen en la búsqueda integrada. Esto significa que los mensajes de correo electrónico donde enviados o recibidos por el asunto de datos y archivos creados o cargados por el asunto de datos que se devolverán. 
  
Para obtener más información acerca del uso de la búsqueda de contenido para buscar los elementos de Microsoft Teams y Office 365 grupos o para ver cómo obtener una lista de miembros, vea la sección "Búsqueda de los equipos y Office 365 grupos de Microsoft" en [Búsqueda de contenido en Office 365](content-search.md#searching-microsoft-teams-and-office-365-groups). 
  
### <a name="searching-exchange-public-folders"></a>Buscar en carpetas públicas de Exchange

La búsqueda integrada en un caso DSR va a mensajes de correo electrónico devolver únicamente que el asunto de datos enviados a una carpeta pública habilitada para correo o los mensajes que otra persona envía a una carpeta pública y también copió el asunto de datos. No devolverá el mensaje que es posible que haya registrado el asunto de datos a una carpeta pública. Para buscar los elementos que el asunto de datos enviado a una carpeta pública, puede crear un independiente crear una búsqueda de contenido independiente que busca cualquier elemento publicado en una carpeta pública por el objeto de datos.
  
Este es un proceso de alto nivel para buscar los elementos que es posible que haya registrado el asunto de datos para una carpeta pública. 
  
1. Abra el caso DSR y crear una nueva búsqueda en la página de **búsqueda** . 
    
2. Utilice los criterios siguientes para configurar la consulta de búsqueda y las ubicaciones de contenido para buscar:
    
  - En el cuadro **palabras clave** , utilice la siguiente consulta de búsqueda: 
    
    ```
    itemclass:ipm.post AND "<email address of the data subject>"
    ```

  - Buscar todas las carpetas públicas de Exchange
    
  - Después de ejecutar la búsqueda y finaliza, puede exportar y descargar los resultados de búsqueda (como se describe en el [paso 4](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#step4)). Use la siguiente configuración para exportar elementos indizados parcialmente. 
