---
title: Administración de solicitudes del interesado de RGPD con la herramienta de casos de DSR en el centro de cumplimiento de & de seguridad
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/25/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: ce9eb942-3589-42cb-88fd-1576ecb09c5c
description: El RGPD otorga a los ciudadanos de la UE (denominados "interesados en los datos) derechos específicos sobre sus datos personales; Estos derechos incluyen la obtención de copias del mismo, la solicitud de cambios, la restricción del procesamiento, la eliminación o la recepción del mismo en un formato electrónico. Una solicitud formal de un sujeto de datos para realizar una acción en sus datos personales se denomina solicitud de interesado o DSR. Puede usar casos de DSR en el centro de cumplimiento de Office 365 y Microsoft 365 para administrar las investigaciones de los DSR de su organización.
ms.openlocfilehash: a131da86350fc288c1c9af371d28464230b742d6
ms.sourcegitcommit: 6c9340e4eb221bf81472ff3f1ae25ae21aaf5297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "31814031"
---
# <a name="manage-gdpr-data-subject-requests-with-the-dsr-case-tool-in-the-security--compliance-center"></a>Administración de solicitudes del interesado de RGPD con la herramienta de casos de DSR en el centro de cumplimiento de & de seguridad

El Reglamento de protección general de datos (RGPD) de la Unión Europea trata sobre la protección y la habilitación de los derechos de privacidad de los individuos en la Unión Europea (UE). El RGPD da a los usuarios de la Unión Europea (conocidos como sujetos de datos) el derecho a acceder, recuperar, corregir, borrar y restringir el procesamiento de sus datos personales. Según la RGPD, los datos personales se refieren a cualquier información relacionada con una persona física identificada o identificable. Una solicitud formal de una persona a su organización para realizar una acción en sus datos personales se conoce como una solicitud de interesado o un DSR. Para obtener información detallada acerca de la respuesta a interesado para datos en Office 365, vea la [Guía de solicitud de asunto de datos de office 365](https://go.microsoft.com/fwlink/?linkid=871169 ).
  
Para administrar las investigaciones en respuesta a un DS1800 enviado por una persona de su organización, puede usar la herramienta de casos de DSR del centro de cumplimiento de seguridad & para encontrar contenido almacenado en:
  
- Cualquier buzón de usuario de la organización. Esto incluye conversaciones de Skype empresarial y chats uno a uno en Microsoft Teams
    
- Todos los buzones de correo asociados con un grupo de Office 365 y todos los buzones de equipo en Microsoft Teams
    
- Todos los sitios de SharePoint Online y OneDrive para la Empresa de la organización
    
- Todos los sitios de Teams y los sitios de grupo de Office 365 de la organización
    
- Todas las carpetas públicas de Exchange Online
    
Mediante el uso de la herramienta de caso DSR, puede:
  
- Crear un caso independiente para cada investigación de DSR.
    
- Controlar quién tiene acceso al caso del DSR al agregar personas como miembros del caso; solo los miembros pueden tener acceso al caso y solo pueden ver sus casos en la lista de casos de la página **casos de DSR** en el centro de seguridad & cumplimiento. Además, puede asignar diferentes permisos a diferentes miembros del mismo caso. Por ejemplo, puede permitir que algunos miembros solo vean el caso y los resultados de la búsqueda y permitir que otros miembros creen búsquedas y exporten los resultados de la búsqueda. 
    
- Use la búsqueda integrada para buscar todo el contenido creado o cargado por un titular de datos específico.
    
- Si lo desea, puede revisar la consulta de búsqueda integrada y volver a ejecutar la búsqueda para restringir los resultados de la búsqueda.
    
- Agregue búsquedas de contenido adicionales asociadas al caso DSR. Esto incluye la creación de búsquedas que devuelven elementos parcialmente indizados y registros generados por el sistema desde My Analytics y el servicio de itinerancia de Office.
    
- Exportar datos en respuesta a una solicitud de exportación o acceso de DSR.
    
- Eliminar casos cuando se completa el proceso de investigación del DS1800; se quitarán todas las búsquedas y los trabajos de exportación asociados con el caso.
    
Este es el proceso de alto nivel para usar la herramienta de caso DSR para administrar investigaciones de DSR:
  
[Paso 1: Asignar permisos de exhibición de documentos electrónicos a posibles miembros del caso](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[Paso 2: crear un caso de DSR y agregar miembros](#step-2-create-a-dsr-case-and-add-members)

[Paso 3: ejecutar la consulta de búsqueda](#step-3-run-the-search-query)

[Paso 4: exportar los datos](#step-4-export-the-data)

[Opcional Paso 5: revisar la consulta de búsqueda integrada](#optional-step-5-revise-the-built-in-search-query)

[Más información sobre el uso de la herramienta de casos de DSR](#more-information-about-using-the-dsr-case-tool)
  
> [!IMPORTANT]
> Nuestras herramientas pueden ayudar a los administradores a realizar solicitudes de acceso o exportación a los DSR, permitiéndoles usar la funcionalidad de búsqueda y exportación integrada que se encuentra en la herramienta para el caso del DSR. La herramienta ayuda a facilitar un método de mejor esfuerzo para exportar datos relevantes para una solicitud de DSR enviada por un titular de datos. Sin embargo, es importante tener en cuenta que los resultados de la búsqueda pueden variar en función del titular de los datos o de las acciones de administración realizadas que puedan afectar a si un elemento se consideraría o no como "datos personales" para fines de exportación. Por ejemplo, si el interesado fue la última persona que modificó un archivo que no ha creado, es posible que el archivo no se devuelva en los resultados de la búsqueda. De forma similar, un administrador puede exportar datos sin incluir elementos parcialmente indizados o todas las versiones de los documentos de SharePoint. Por lo tanto, las herramientas proporcionadas pueden ayudar a facilitar el acceso y la exportación de las solicitudes de datos; sin embargo, los resultados están sujetos a escenarios específicos de uso del interesado de administración y de datos. 
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a>Paso 1: Asignar permisos de exhibición de documentos electrónicos a posibles miembros del caso

De forma predeterminada, un administrador global de Office 365 puede tener acceso a la herramienta de caso DSR en el centro de seguridad & cumplimiento. Por diseño, otros usuarios, como un responsable de privacidad de datos, un administrador de recursos humanos u otras personas involucradas en investigaciones de DSR, no tienen acceso a la herramienta de caso DSR y deberán tener asignados los permisos adecuados para acceder a la herramienta. La forma más sencilla de hacerlo es ir a la página de **permisos** en el centro de seguridad & cumplimiento y agregar usuarios al grupo de roles eDiscovery Manager. Tenga en cuenta que también tiene que asignar estos permisos para que pueda agregarlos como miembros del caso DSR que cree en el paso 2. 
  
Para obtener instrucciones paso a paso, consulte [asignar permisos de exhibición de documentos electrónicos en el centro de seguridad _AMP_ cumplimiento de Office 365](assign-ediscovery-permissions.md).
  
> [!NOTE]
> De forma predeterminada, un administrador global de Office 365 (u otros miembros del grupo de roles de administración de la organización en el centro de seguridad & cumplimiento no dispone de los permisos necesarios para exportar los resultados de la búsqueda de contenido (vea el paso 4 de este artículo). Para solucionar esto, un administrador puede agregarse a sí mismo como miembro del grupo de roles eDiscovery Manager. 
  
## <a name="step-2-create-a-dsr-case-and-add-members"></a>Paso 2: crear un caso de DSR y agregar miembros

El siguiente paso es crear un caso DSR. Al crear un caso, puede optar por iniciar la búsqueda integrada o puede crear el caso sin iniciar la búsqueda. El siguiente procedimiento le indicará que cree el caso sin iniciar la búsqueda y, a continuación, le mostrará cómo agregar miembros al caso.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión en Office 365 con su cuenta profesional o educativa. 
    
2. En el centro de seguridad & cumplimiento, haga clic en **solicitudes de asunto de datos**de ![ **privacidad** \> de](media/ITPro-EAC-AddIcon.gif) datos y, a continuación, haga clic en agregar icono **nuevo caso DSR**.
    
3. En la página flotante de **nuevo caso de DSR** , indique un nombre, escriba una descripción opcional y, a continuación, haga clic en **siguiente**. Tenga en cuenta que el nombre del caso debe ser único en su organización.
    
    > [!TIP]
    > Considere la posibilidad de agregar el nombre de la persona que envió la solicitud del DSR que está investigando en el nombre o la descripción del nuevo caso. Tenga en cuenta que solo los miembros de este caso (y los administradores de eDiscovery) podrán ver el caso en la lista de casos de la página **solicitudes de interesados** . 
  
4. En la página Detalles de la **solicitud** , en titular de los **datos (la persona que archivó esta solicitud)**, seleccione la persona para la que desea buscar y exportar los datos y, a continuación, haga clic en **siguiente**.
    
5. En la página **confirmar la configuración del caso** , puede cambiar el nombre y la descripción del caso y seleccionar un asunto de datos diferente. De lo contrario, haga clic en **Guardar**.
    
    Se muestra una página que confirma que se ha creado el nuevo maletín DSR.
    
    ![Inicie la búsqueda o simplemente cierre la página del nuevo caso de DSR](media/b5e62c2c-cafe-4a8d-a38c-789ed9f9ccbd.png)
  
    En este punto, puede hacer una de estas dos cosas:
    
    a. Al hacer clic en **Mostrar los resultados** de la búsqueda se inicia la búsqueda. Ésa es la selección predeterminada. La búsqueda integrada que se ejecuta cuando se selecciona esta opción y los resultados que se devuelven se explican en el paso 3.
    
    b. Al hacer clic en **Finalizar** se cierra el nuevo maletín DSR sin iniciar la búsqueda integrada. Si selecciona esta opción, se mostrará el nuevo maletín DSR en la página **solicitudes de interesados** .
    
6. Haga clic en **Finalizar** para que pueda ir al nuevo caso de DSR y agregarle miembros. 
    
7. En la página **solicitudes de interesados** , haga clic en el nombre del caso del DSR que acaba de crear. 
    
8. En la página desplegable **administrar este caso** , en **administrar miembros**, haga clic en **Agregar**. 
    
    En **users**, se muestra una lista de las personas a las que se han asignado los permisos de eDiscovery apropiados. Tenga en cuenta que los usuarios a los que haya asignado permisos de exhibición de documentos electrónicos en el paso 1 se mostrarán en esta lista. 
    
9. Seleccione los usuarios que se agregarán como miembros del caso del DSR, haga clic en **Agregar**y, a continuación, guarde los cambios.
    
    Tenga en cuenta que también puede agregar grupos de roles como miembros del caso del DSR si hace clic en **Agregar** en **administrar grupos de roles**. 
    
## <a name="step-3-run-the-search-query"></a>Paso 3: ejecutar la consulta de búsqueda

Después de crear un caso de DSR y agregar miembros, el siguiente paso es ejecutar la búsqueda integrada asociada con el caso. Esta consulta de búsqueda predeterminada hace lo siguiente:
  
- Busca en todos los buzones de la organización todos los elementos de correo electrónico enviados o recibidos por el titular de los datos. Esto se logra mediante el uso de la propiedad email de los *participantes* , que busca el asunto de los datos en todos los campos People en un mensaje de correo electrónico. Esta propiedad devuelve los elementos en los que el asunto de los datos se encuentra en los campos **from**, **to**, **CC**y **BCC** . Las carpetas públicas de Exchange Online también se buscan en busca de mensajes enviados o recibidos por el titular de los datos. 
    
- Busca en todos los sitios de la organización documentos y elementos creados o cargados por el titular de los datos. Esto se consigue mediante las siguientes propiedades de sitio:
    
  - La propiedad *Author* devuelve los elementos en los que el asunto de los datos aparece en el campo Author de los documentos de Office. Este valor persiste, incluso si el documento se copia y se carga por otro usuario. 
    
  - La propiedad *CreatedBy* devuelve los elementos que el asunto de datos ha creado o cargado. 
    
Este es el aspecto de la consulta de palabra clave para la búsqueda integrada que se crea automáticamente al crear un caso DSR.
  
```
participants:"<email address>" OR author:"<display name>" OR createdby:"<display name>"
```

Por ejemplo, si el nombre del titular de los datos está en INA Robledo, la consulta de palabra clave tendría el siguiente aspecto:
  
```
participants:"ina@contoso.com" OR author:"Ina Leonte" OR createdby:"Ina Leonte"
```

 **Para ejecutar la búsqueda integrada para un caso de DSR:**
  
1. En el centro de seguridad & cumplimiento, haga clic en **solicitudes de asunto de datos**de privacidad \> de **datos** y, a continuación, haga clic en **abrir** junto al caso DSR que ha creado en el paso 2. 
    
    Haga clic en la ficha **búsqueda** en la parte superior de la página y, a continuación, haga clic en la casilla situada junto a la búsqueda integrada que se creó cuando creó el nuevo maletín DSR. Nota la búsqueda tiene el mismo nombre que el caso del DSR. 
    
2. En la página flotante de búsqueda, haga clic en **abrir consulta**.
    
    Al abrir la consulta, la búsqueda se inicia y se completará en unos momentos. 
    
3. Una vez finalizada la búsqueda, haga clic en **vista previa de resultados** para obtener una vista previa de los resultados de búsqueda. Para obtener más información, vea [vista previa de resultados](content-search.md#preview-search-results)de la búsqueda.
    
    > [!TIP]
    > También puede ver las estadísticas de la consulta de búsqueda para ver el número de buzones y elementos de sitio devueltos por la búsqueda, y las ubicaciones de contenido principales que contienen elementos que coinciden con la consulta de búsqueda. Para obtener más información, vea [ver información y estadísticas sobre una búsqueda](content-search.md#view-information-and-statistics-about-a-search). 
  
Puede editar la consulta de búsqueda integrada, cambiar las ubicaciones de contenido que se van a buscar y, a continuación, volver a ejecutar la búsqueda. Consulte el [paso 5](#optional-step-5-revise-the-built-in-search-query) para obtener más información. 
  
## <a name="step-4-export-the-data"></a>Paso 4: exportar los datos

Después de ejecutar la búsqueda integrada, puede exportar los resultados de la búsqueda. Como alternativa, antes de exportar los datos, es posible que desee revisar la consulta para reducir el número de resultados de búsqueda. Consulte el paso 5 para obtener más información sobre cómo restringir los resultados de la búsqueda.
  
Al exportar los resultados de la búsqueda, los elementos del buzón pueden descargarse en archivos PST o como mensajes individuales. Al exportar contenido de las cuentas de SharePoint y OneDrive, se exportan copias de documentos nativos de Office y otros documentos. También se incluye en los resultados de la búsqueda los archivos de resultados que contienen información sobre cada uno de los elementos que se exportan. Para obtener información más detallada acerca de la exportación, consulte [exportar resultados](export-search-results.md)de la búsqueda de contenido.
  
> [!NOTE]
> De forma predeterminada, un administrador global de Office 365 (u otros miembros del grupo de roles de administración de la organización en el centro de seguridad & cumplimiento) no tiene los permisos necesarios para exportar los resultados de la búsqueda de contenido. Para solucionar esto, un administrador puede agregarse a sí mismo como miembro del grupo de roles eDiscovery Manager. 
  
El equipo que use para exportar datos debe cumplir con los siguientes requisitos del sistema:
  
- Versiones de 32 o 64 bits de Windows 7 y versiones posteriores
    
- Microsoft .NET Framework 4,7
    
- Un explorador compatible:
    
  - Microsoft Edge
    
    O bien
    
  - Microsoft Internet Explorer 10 y versiones posteriores
    
    > [!NOTE]
    > Microsoft no fabrica extensiones de terceros o complementos para aplicaciones ClickOnce. No se admite la exportación de datos con un explorador no compatible con extensiones de terceros o complementos. 
  
 **Para exportar datos de la búsqueda integrada en un caso de DSR:**
  
1. En el centro de seguridad & cumplimiento, haga clic en **solicitudes de asunto de datos**de privacidad \> de **datos** y, a continuación, haga clic en **abrir** junto al caso DSR del que desea exportar datos. 
    
2. Haga clic en la ficha **búsqueda** en la parte superior de la página y, a continuación, haga clic en la casilla situada junto a la búsqueda integrada que se creó al crear el caso del DSR. O bien, haga clic en otra búsqueda para exportar datos de esa búsqueda. 
    
3. En la página desplegable de búsqueda ![, haga clic en](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) exportar resultados de búsqueda **más**y, a continuación, seleccione **exportar resultados** en la lista desplegable. 
    
4. En la página resultados de la **exportación** , seleccione las siguientes opciones recomendadas para las solicitudes de exportación de DSR. 
    
    ![Configuración de las opciones de exportación](media/25416b79-57da-46a1-ae07-e640602a8fa4.png)
  
    a. En **Opciones de salida**, seleccione la primera opción ( **todos los elementos, excluidos los que tienen los que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos**) para exportar solo los elementos indizados. El motivo por el que no desea exportar elementos parcialmente indizados de la búsqueda integrada es porque se exportarán los elementos parcialmente indizados de otros usuarios. Para exportar solo los elementos parcialmente indizados del titular de los datos, se recomienda crear una búsqueda independiente. Para obtener más información, vea [exportar elementos indexados parcialmente](#exporting-partially-indexed-items) en la sección "más información sobre el uso de la herramienta de casos de DSR".
    
    b. En **exportar contenido de Exchange como**, seleccione la tercera opción, **un archivo pst que contiene todos los mensajes en una sola carpeta**. Debido a que algunos de los resultados pueden ser para los elementos que se originaron en el buzón de otro usuario, esta opción solo muestra el elemento en una sola carpeta sin indicar el buzón real y es la mejor opción para usar cuando se desduplican los resultados según se recomienda en el siguiente elemento. . Esta opción también permite que el interesado Revise los elementos en orden cronológico (los elementos se ordenan por fecha de envío) sin tener que navegar por la estructura de carpetas del buzón original para cada elemento.
    
    c. Seleccione **Habilitar opción de** desduplicación para excluir los mensajes de correo electrónico duplicados. Se recomienda esta opción porque la búsqueda integrada busca en todos los buzones de la organización. Por lo tanto, si se encuentran varias copias del mismo mensaje en los buzones en los que se realizó la búsqueda, esta opción significa que solo se exportará una copia de un mensaje. Esta opción, en conjunto, la exportación de mensajes en un archivo PST en una sola carpeta da como resultado la mejor experiencia de usuario para las solicitudes de exportación de la DSR. Tenga en cuenta que el informe de exportación Results. csv mostrará todas las ubicaciones en las que se han encontrado mensajes duplicados.
    
    Opcionalmente, puede seleccionar la opción **incluir versiones para documentos de SharePoint** para exportar todas las versiones de documentos de SharePoint y OneDrive. Esto requiere que el control de versiones esté activado para las bibliotecas de documentos. Esta opción ayuda a garantizar que se exportan todos los datos relevantes.
    
5. Una vez elegida la configuración de exportación, haga clic en **exportar**.
    
    Los resultados de la búsqueda se preparan para la descarga, lo que significa que se cargan en el área de almacenamiento de Azure para su organización en la nube de Microsoft. Los pasos siguientes muestran cómo descargar estos datos en el equipo local.
    
6. Haga clic en la pestaña **exportar** para mostrar el trabajo de exportación que acaba de crear. Tenga en cuenta que los trabajos de exportación tienen el mismo nombre que la búsqueda correspondiente con **_Export** anexado al final del nombre de búsqueda. 
    
7. Haga clic en el trabajo de exportación que acaba de crear para mostrar la página de desplegable exportar. Esta página muestra información sobre la búsqueda, como el tamaño y el número total de elementos que se van a exportar, y el porcentaje de los elementos que se han transferido a un área de almacenamiento de Azure. Haga clic en **Actualizar** para actualizar la información del estado de carga. 
    
8. En **Clave de exportación**, haga clic en **Copiar al Portapapeles**. Esta clave se utilizará en el paso 11 para descargar los resultados de la búsqueda.
    
9. Haga ![clic en exportar el](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) icono resultados de la búsqueda **Descargar resultados** en la parte superior de la página de desplegable de exportación. 
    
10. En la ventana emergente situada en la parte inferior de la página, haga clic en **abrir** para abrir la herramienta de exportación de exhibición de documentos electrónicos **365 de Microsoft Office**. La **herramienta de exportación de exhibición** de documentos electrónicos se instalará la primera vez que descargue los resultados de búsqueda. 
    
11. En la **herramienta de exportación de exhibición**de documentos electrónicos, pegue la clave de exportación que ha copiado en el paso 8 en el cuadro correspondiente.
    
12. Haga clic en **Examinar** para especificar la ubicación en la que desea descargar los archivos de los resultados de la búsqueda. 
    
    > [!NOTE]
    > Debido a la gran cantidad de actividad de disco (lecturas y escrituras), debe descargar los resultados de la búsqueda en una unidad de disco local; no descárguelos en una unidad de red asignada ni en otra ubicación de red. 
  
13. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo. 
    
    La **Herramienta de exportación de exhibición de documentos electrónicos** muestra información del estado acerca del proceso de exportación, incluida una estimación del número (y tamaño) de los elementos restantes que se van a descargar. Una vez finalizado el proceso de exportación, puede tener acceso a los archivos en la ubicación en la que se descargaron. Para obtener más información acerca de los informes que se incluyeron al descargar los resultados de la búsqueda de contenido, consulte la sección [más información](export-search-results.md#more-information) en "exportar resultados de la búsqueda de contenido". 
    
Una vez exportados los datos, los resultados de la búsqueda y los informes de exportación se encuentran en una carpeta con el mismo nombre que el caso del DSR. Los archivos PST que contienen elementos de buzón de correo se encuentran en una subcarpeta llamada **Exchange**. Los documentos y otros elementos de los sitios se encuentran en una subcarpeta denominada **SharePoint**. 
  
## <a name="optional-step-5-revise-the-built-in-search-query"></a>Opcional Paso 5: revisar la consulta de búsqueda integrada

Después de ejecutar la búsqueda integrada, puede revisarla para reducir el ámbito para devolver menos resultados de búsqueda. Para ello, puede agregar condiciones a la consulta. Una condición está conectada lógicamente a la consulta de palabras clave por el operador **and** . Esto significa que debe devolverse en los resultados de la búsqueda, los elementos deben cumplir la consulta de palabra clave y las condiciones que se agreguen. De este modo, las condiciones ayudan a restringir los resultados. Si agrega dos o más condiciones únicas a una consulta de búsqueda (condiciones que especifican propiedades diferentes), las condiciones se conectan lógicamente mediante el operador **and** . Esto significa que solo se devuelven los elementos que cumplen todas las condiciones (además de la consulta de palabras clave). Si agrega varios valores (separados por comas o puntos y coma) a una única condición, esos valores están conectados por el operador **or** . Eso significa que se devuelven los elementos que contengan cualquiera de los valores especificados para la propiedad en la condición. 
  
A continuación se muestran algunos ejemplos de las condiciones que puede Agregar a la consulta de búsqueda integrada en un caso de DSR. El nombre de la propiedad real que se usa en una consulta de búsqueda se muestra entre paréntesis.
  
- **Tipo de archivo `filetype`()** : especifica la extensión de un documento o archivo. Use esta condición para buscar documentos y archivos creados por aplicaciones específicas de Office, como Word, Excel y OneNote. 
    
- **Tipo de mensaje `kind`()** : especifica el tipo de elemento de correo electrónico que se buscará. Por ejemplo, puede usar la sintaxis `kind:email OR kind:im` para devolver solo mensajes de correo electrónico y conversaciones de Skype empresarial o chats uno a uno en Microsoft Teams. 
    
- **Etiqueta de cumplimiento`compliancetag`()** : especifica una etiqueta asignada a un mensaje de correo electrónico o a un documento. Esta condición devolverá los elementos clasificados con una etiqueta específica. Las etiquetas se usan para clasificar el correo electrónico y los documentos para el gobierno de datos y aplicar las reglas de retención en función de la clasificación definida por la etiqueta. Esta es una condición útil para las investigaciones de los DSR porque su organización puede usar etiquetas para clasificar el contenido relacionado con la privacidad de los datos o que contiene datos personales o información confidencial. Para el valor de esta condición, use el nombre completo de la etiqueta o la primera parte del nombre de la etiqueta con un comodín. Para obtener más información, vea [información general sobre las etiquetas en Office 365](labels.md).
    
Para obtener una lista y una descripción de todas las condiciones disponibles en la herramienta de casos de DSR, vea [condiciones de búsqueda](keyword-queries-and-search-conditions.md#search-conditions) en el artículo "consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido". 
  
### <a name="changing-the-content-locations-that-are-searched"></a>Cambio de las ubicaciones de contenido que se buscan

Además de revisar la búsqueda integrada para un caso DSR, también puede cambiar las ubicaciones de contenido que se buscan. Como se ha explicado anteriormente, la búsqueda integrada busca en todos los buzones y sitios de la organización, y en todas las carpetas públicas de Exchange Online. Por ejemplo, puede restringir la búsqueda para que solo busque en el buzón del titular del usuario, en la cuenta de OneDrive y en los sitios de SharePoint seleccionados. Si decide buscar sitios específicos, tendrá que agregar cada uno de los sitios en los que desee buscar.
  
Para modificar las ubicaciones de contenido que se van a buscar:
  
1. Abra la búsqueda integrada para la que desea cambiar las ubicaciones de contenido.
    
2. En la consulta de búsqueda, en **ubicaciones**, haga clic en **modificar** junto a la opción **ubicaciones específicas** . 
    
    ![Haga clic en modificar para cambiar las ubicaciones de contenido de la consulta de búsqueda integrada](media/d66f7ba7-b71f-4ff5-a030-460ff02e3123.png)
  
    Se muestra la página de control flotante **modificar ubicaciones** . Esta es una descripción de las ubicaciones de contenido en la búsqueda integrada y de información sobre cómo modificar las ubicaciones en las que se realiza la búsqueda. 
    
    ![Página de control flotante de modificar ubicaciones](media/56c033f6-6735-46ba-abb2-a263a2b79836.png)
  
    a. La opción alternar de la sección **seleccionar todo** en el buzón de la parte superior de la página de flotante está seleccionada, lo que indica que se busca en todos los buzones. Para restringir el ámbito de la búsqueda, haga clic en el botón de alternancia para anular la selección y, a continuación, haga clic en **elegir usuarios, grupos o equipos** y elija buzones específicos para buscar.
    
    b. La opción alternar de la sección **seleccionar todo** de la sección sitios en la parte central de la página flotante está seleccionada, lo que indica que se busca en todos los sitios. Para restringir la búsqueda a los sitios seleccionados, desactive la opción alternar y, a continuación, haga clic en **elegir sitios**. Tendrá que agregar cada sitio específico que quiera buscar, incluida la cuenta de OneDrive del titular de los datos.
    
    c. Se selecciona la sección alternar carpetas públicas de Exchange, que significa que se busca en todas las carpetas públicas de Exchange. Tenga en cuenta que solo puede buscar en todas las carpetas públicas de Exchange o en ninguna de ellas. No puede elegir una búsqueda específica.
    
3. Si modifica las ubicaciones de contenido en la búsqueda integrada, haga clic en **Guardar &amp; ejecución** para volver a iniciar la búsqueda. 
  
## <a name="more-information-about-using-the-dsr-case-tool"></a>Más información sobre el uso de la herramienta de casos de DSR

Las secciones siguientes contienen más información sobre el uso de la herramienta de caso DSR para responder a las solicitudes de exportación del DSR.
  
[Exportar datos de myanalytics y el servicio de itinerancia de Office](#exporting-data-from-myanalytics-and-the-office-roaming-service)

[Exportar elementos parcialmente indizados](#exporting-partially-indexed-items)

[Búsqueda y exportación de datos de grupos de Microsoft Teams y Office 365](#searching-and-exporting-data-from-microsoft-teams-and-office-365-groups)

[Búsqueda en carpetas públicas de Exchange](#searching-exchange-public-folders)
  
### <a name="exporting-data-from-myanalytics-and-the-office-roaming-service"></a>Exportar datos de myanalytics y el servicio de itinerancia de Office

Puede usar la herramienta de casos de DSR para buscar y exportar datos de uso generados por myanalytics y el servicio de itinerancia de Office. Esta es una descripción de lo que hacen estos servicios:
  
- **Myanalytics** : proporciona a los usuarios información sobre cómo invierte su tiempo en función de los datos de correo y calendario de sus buzones. Toda la información de myanalytics se deriva de los encabezados de reuniones y del correo electrónico en el buzón del usuario. Los usuarios a los que se asigna una licencia de myanalytics pueden iniciar sesión en Office 365 y ir al panel de myanalytics para ver información sobre cómo invierte su tiempo. (Los usuarios pueden obtener una captura de pantalla de estas información en respuesta a una solicitud de acceso de DSR). La búsqueda incorporada en un caso DSR exportará los datos que se usan para generar información de myanalytics. 
    
- **Servicio de itinerancia de Office** : itinerancia es un servicio que almacena configuraciones relacionadas con Office, como el tema de Office, el diccionario personalizado, la configuración de idioma, el modo para programadores y la corrección automática. 
    
Los datos de myanalytics y el servicio de itinerancia de Office se almacenan en el buzón de correo de un interesado en carpetas ocultas que se encuentran en un subárbol de mensajes no interpersonales (no IPM) de buzones de Exchange Online. Esto significa que los datos se ocultan de la vista del usuario cuando usan Outlook u otros clientes de correo para tener acceso a su buzón. Para obtener más información acerca de las carpetas ocultas, consulte [MAPI Hidden folders](https://go.microsoft.com/fwlink/?linkid=872758).
  
Puede crear una búsqueda de contenido independiente (y asociarla con un caso de DSR) que devuelve los datos de uso del servicio de itinerancia de Office y myanalytics en el buzón de correo de asuntos de los datos. Estos datos no se incluyen en las estadísticas de búsqueda y no estarán disponibles para la vista previa. Pero puede exportarla y, a continuación, asignarla al interesado en respuesta a una solicitud de exportación de DSR.
  
Al exportar datos de myanalytics y el servicio de itinerancia de Office, los datos se guardan en una carpeta independiente para cada aplicación que se encuentra en la carpeta **ApplicationDataRoot** , que se encuentra en una carpeta que es el nombre de la dirección de correo del interesado. Estos datos se exportan como archivos JSON, que son archivos de texto legibles, similares a los archivos XML o TXT, que se adjuntan a los mensajes de correo electrónico. Actualmente, estas carpetas se denominan con un identificador único global (GUID) que se asigna a myanalytics y al servicio de itinerancia de Office, que se enumeran en la siguiente tabla. En versiones futuras de la herramienta de casos DSR, el GUID se reemplazará por el nombre de la aplicación real. 
  
|**Aplicación**|**GUID/nombre de carpeta**|
|:-----|:-----|
|MyAnalytics  <br/> |3c896ded-22c5-450F-91f6-3d1ef0848f6e  <br/> |
|Servicio de itinerancia de Office  <br/> |1caee58f-EB14-4a6b-9339-1fe2ddf6692b  <br/> |
   
 **Para buscar y exportar myanalytics y datos del servicio de itinerancia de Office:**
  
1. En el centro de seguridad & cumplimiento, haga clic en **solicitudes de asunto de datos**de privacidad \> de **datos** y, a continuación, haga clic en **abrir** junto al caso del DS1800 para el interesado al que desea exportar datos de uso. 
    
2. Haga clic en la ficha **búsqueda** en la parte superior de la página y ![, a](media/ITPro-EAC-AddIcon.gif) continuación, haga clic en agregar icono de **búsqueda guiada**.
    
3. Haga clic en **Cancelar** en la página **asigne un nombre a la búsqueda** . 
    
4. En **consulta de búsqueda**, en la condición **tipo** , active las casillas de verificación situadas junto a **myanalytics** y servicio de **itinerancia de Office**. 
    
    ![Seleccione las casillas de verificación myanalytics y servicio de itinerancia de Office para exportar datos de uso](media/3dacbc7a-c314-492c-828c-6757fda84963.png)
  
    Tenga en cuenta que la condición **tipo** (que son clases de mensajes de correo electrónico) debe ser el único elemento de la consulta de búsqueda. Puede eliminar el cuadro **palabras clave** o dejarlo en blanco. 
    
5. En **ubicaciones**, asegúrese de que **ubicaciones específicas** está seleccionada y, a continuación, haga clic en **modificar**.
    
6. En la parte superior de la página de control flotante **modificar ubicaciones** (la sección buzón de correo), haga clic en **elegir usuarios, grupos o equipos**.
    
7. En la página **Editar ubicaciones** , haga clic en **elegir usuarios, grupos o equipos**, elija el buzón de correo del interesado y, a continuación, guarde la selección. 
    
8. Haga clic en **Guardar &amp; ejecución**y, a continuación, asigne un nombre a la búsqueda y guárdela.
    
    La búsqueda se inicia.
    
 **Para exportar myanalytics y datos del servicio de itinerancia de Office:**
  
1. Una vez completada la búsqueda que ha creado en el paso anterior, haga clic en la ficha **búsqueda** situada en la parte superior de la página y, a continuación, haga clic en la casilla situada junto a la búsqueda. Puede que tenga que hacer ![clic](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) en actualizar **actualización** para mostrar la búsqueda. 
    
2. En la página desplegable de búsqueda ![, haga clic en](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) exportar resultados de búsqueda **más**y, a continuación, seleccione **exportar resultados** en la lista desplegable. 
    
3. En la página **exportar resultados** , seleccione las opciones recomendadas para exportar datos de uso. 
    
    ![Opciones de exportación al exportar los datos de uso del servicio de movilidad de Office y myanalytics](media/470a7d1e-eeae-4b42-95aa-15cb82ce2f68.png)
  
    a. En **Opciones de salida**, seleccione la primera opción ( **todos los elementos, excluidos los que tienen los que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos**) para exportar solo los elementos indizados.
    
    b. En **exportar contenido de Exchange como**, seleccione la segunda opción: **un archivo pst que contiene todos los mensajes**.
    
    c. Deje la opción de exportación restante desactivada.
    
4. Una vez elegida la configuración de exportación, haga clic en **exportar**.
    
    Los resultados de la búsqueda se preparan para la descarga, lo que significa que se cargan en el área de almacenamiento de Azure para su organización en la nube de Microsoft. Los pasos siguientes muestran cómo descargar estos datos en el equipo local.
    
5. Haga clic en la pestaña **exportar** para mostrar el trabajo de exportación que acaba de crear. Tenga en cuenta que los trabajos de exportación tienen el mismo nombre que la búsqueda correspondiente con **_Export** anexado al final del nombre de búsqueda. 
    
6. Haga clic en el trabajo de exportación que acaba de crear para mostrar la página de desplegable exportar. 
    
7. En **Clave de exportación**, haga clic en **Copiar al Portapapeles**. Usará esta clave en el paso 10 para descargar los resultados de la búsqueda.
    
8. Haga ![clic en exportar el](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) icono resultados de la búsqueda **Descargar resultados** en la parte superior de la página de desplegable de exportación. 
    
9. En la ventana emergente situada en la parte inferior de la página, haga clic en **abrir** para abrir la herramienta de exportación de exhibición de documentos electrónicos **365 de Microsoft Office**. La **herramienta de exportación de exhibición** de documentos electrónicos se instalará la primera vez que descargue los resultados de búsqueda. 
    
10. En la **Herramienta de exportación de exhibición de documentos electrónicos**, pegue la clave de exportación que ha copiado en el paso 7 en el cuadro correspondiente.
    
11. Haga clic en **Examinar** para especificar la ubicación en la que desea descargar los archivos de los resultados de la búsqueda. 
    
    > [!NOTE]
    > Debido a la gran cantidad de actividad de disco (lecturas y escrituras), debe descargar los resultados de la búsqueda en una unidad de disco local; no descárguelos en una unidad de red asignada ni en otra ubicación de red. 
  
12. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo. 
    
    La **Herramienta de exportación de exhibición de documentos electrónicos** muestra información del estado acerca del proceso de exportación, incluida una estimación del número (y tamaño) de los elementos restantes que se van a descargar. Una vez finalizado el proceso de exportación, puede abrir el archivo PST de Exchange en Outlook y, a continuación, ir a la carpeta **ApplicationDataRoot** para tener acceso a las subcarpetas de myanalytics y itineranciaing Service. 
    
    Como se ha explicado anteriormente, los archivos JSON que contienen datos de uso se adjuntan a los mensajes. Para ver un archivo JSON, haga clic en un mensaje y, a continuación, abra el archivo JSON adjunto. 
  
### <a name="exporting-partially-indexed-items"></a>Exportar elementos parcialmente indizados

Le recomendamos que no exporte elementos parcialmente indizados (también denominados elementos sin indexar) de la búsqueda integrada que se crea al crear un nuevo caso DSR. Esto se debe a que los resultados de la búsqueda son más de lo probable, incluidos los elementos parcialmente indizados para otros usuarios de la organización, y no solo los elementos parcialmente indizados del titular de los datos). En su lugar, se recomienda crear una búsqueda de contenido independiente asociada con el caso del DSR, que se ha diseñado para exportar sólo los elementos parcialmente indizados relacionados con el titular de los datos. 
  
Este es un proceso de alto nivel para exportar elementos indexados parcialmente. Una vez exportados, puede revisarlos para determinar si un elemento responde a una solicitud de exportación o acceso a DSR.
  
1. Abra el caso del DS1800 y cree una nueva búsqueda en la página de **búsqueda** . 
    
2. Use los siguientes criterios para configurar la consulta de búsqueda y las ubicaciones de contenido para buscar:
    
    - Use una consulta de palabras clave vacía o en blanco. Se devolverán todos los elementos de las ubicaciones de contenido en las que se realiza la búsqueda.
    
    - Busque solo el buzón de correo de Exchange online del titular de los datos y su cuenta de OneDrive.
    
3. Después de ejecutar la búsqueda y de que finalice, puede exportar y descargar los resultados de la búsqueda (como se describe en el [paso 4](#step-4-export-the-data)). Use la siguiente configuración para exportar elementos parcialmente indizados. 
    
    - En **Opciones de salida**, seleccione la tercera opción ( **solo los elementos que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos**) para exportar solo los elementos indizados parcialmente.
    
    - En **exportar contenido de Exchange como**, puede seleccionar cualquier opción en función de sus preferencias. 
    
    - Si se selecciona la opción **incluir versiones de los documentos de SharePoint** , se exportarán las versiones de los documentos si una versión está indizada parcialmente. 
    
Para obtener más información acerca de los elementos parcialmente indizados, vea: 
  
- [Elementos parcialmente indizados en la búsqueda de contenido en Office 365](partially-indexed-items-in-content-search.md)

- [Exportar elementos parcialmente indizados](export-search-results.md#exporting-partially-indexed-items)
    
### <a name="searching-and-exporting-data-from-microsoft-teams-and-office-365-groups"></a>Búsqueda y exportación de datos de grupos de Microsoft Teams y Office 365

Las conversaciones que forman parte de la lista de chats en Microsoft Teams (llamados chats de equipo o chats uno a uno) se almacenan en el buzón de Exchange online de los usuarios que participan en los chats. Además, los archivos que una persona comparte en un chat de uno a uno se almacenan en la cuenta de OneDrive de la persona que comparte el archivo. Debido a que la búsqueda integrada busca en todos los buzones y en las cuentas de OneDrive de la organización, los chats de equipo y los documentos compartidos en una sesión de chat (que el sujeto de los datos creado o cargado) se devolverán mediante la búsqueda incorporada en un caso DSR.
  
Como alternativa, las conversaciones que forman parte de un canal de Microsoft Teams (también denominados mensajes de canal) se almacenan en el buzón de correo que está asociado a un equipo. Estos tipos de conversaciones que el interesado en el tema de los datos también se devuelven mediante la búsqueda integrada, ya que se busca en todos los buzones asociados con Microsoft Teams. Además, los mosaicos que un sujeto de datos puede haber compartido en un canal de Microsoft Teams se almacenan en el sitio de SharePoint del equipo. Archivos creados o uploadedby el asunto de los datos será devuelto por la búsqueda incorporada en un caso DSR, ya que los sitios asociados con Microsoft Teams se incluyen en la búsqueda.
  
De forma similar, los buzones de correo y los sitios de SharePoint que corresponden a un grupo de Office 365 también se incluyen en la búsqueda integrada. Esto significa que se devolverán los mensajes de correo electrónico en los que se enviará o recibirá el titular de los datos y los archivos creados o cargados por el interesado. 
  
Para obtener más información sobre cómo usar la búsqueda de contenido para buscar elementos en Microsoft Teams y Office 365 grupos o para ver cómo obtener una lista de los miembros, consulte la sección "búsqueda en Microsoft Teams y Office 365 groups" de [búsqueda de contenido en Office 365](content-search.md#searching-microsoft-teams-and-office-365-groups). 
  
### <a name="searching-exchange-public-folders"></a>Búsqueda en carpetas públicas de Exchange

La búsqueda incorporada en un caso DSR solo devolverá los mensajes de correo electrónico que el interesado envíe a una carpeta pública habilitada para correo o a los mensajes que otra persona haya enviado a una carpeta pública y que también haya copiado el asunto de los datos. No devolverá un mensaje que indica que es posible que el titular de los datos haya publicado en una carpeta pública. Para buscar elementos que el asunto de los datos envió en una carpeta pública, puede crear una búsqueda de contenido independiente que busque cualquier elemento publicado en una carpeta pública por el titular de los datos.
  
Este es un proceso de alto nivel para buscar elementos que el interesado podría haber publicado en una carpeta pública. 
  
1. Abra el caso del DS1800 y cree una nueva búsqueda en la página de **búsqueda** . 
    
2. Use los siguientes criterios para configurar la consulta de búsqueda y las ubicaciones de contenido para buscar:
    
  - En el cuadro **palabras clave** , use la siguiente consulta de búsqueda: 
    
    ```
    itemclass:ipm.post AND "<email address of the data subject>"
    ```

  - Buscar en todas las carpetas públicas de Exchange
    
  - Después de ejecutar la búsqueda y de que finalice, puede exportar y descargar los resultados de la búsqueda (como se describe en el [paso 4](#step-4-export-the-data)). Use la siguiente configuración para exportar elementos parcialmente indizados. 
