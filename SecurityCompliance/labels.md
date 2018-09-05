---
title: Información general sobre las etiquetas
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/22/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: Las etiquetas de Office 365 ayudan a realizar las acciones adecuadas en el contenido adecuado. Con las etiquetas, puede clasificar los datos de su organización para administrarlos mejor y aplicar reglas de retención basadas en esa clasificación. También puede usar etiquetas para implementar la administración de registros en Office 365.
ms.openlocfilehash: e08a1772a7e04f459b80762e3da17600ef84c95a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013754"
---
# <a name="overview-of-labels"></a>Información general sobre las etiquetas

Es posible que su organización disponga de distintos tipos de contenido que haya que usar de manera diferente para cumplir con las normativas del sector y las directivas internas. Por ejemplo:
  
- Formularios fiscales que sea necesario **conservar** durante un período de tiempo mínimo. 
    
- Materiales de prensa que deban **eliminarse de forma permanente** cuando alcancen una determinada antigüedad. 
    
- Información sobre la competencia que sea necesario **conservar** y, después, **eliminar de forma permanente**. 
    
- Visados de trabajo que tengan que **marcarse como registros** para que no se puedan editar ni eliminar. 
    
En todos estos casos, las etiquetas de Office 365 pueden ayudarle a realizar las acciones adecuadas en el contenido adecuado. Con las etiquetas, puede clasificar los datos de su organización para administrarlos mejor y aplicar reglas de retención basadas en esa clasificación.
  
Con las etiquetas, puede:
  
- **Permitir que los usuarios de la organización apliquen manualmente una etiqueta** a contenido de Outlook en la Web, Outlook 2010 y versiones posteriores, OneDrive para la Empresa, SharePoint Online y Grupos de Office 365. Con frecuencia, los usuarios son los que mejor saben con qué tipo de contenido están trabajando, por lo que pueden clasificarlo correctamente y aplicar la directiva adecuada. 
    
- **Aplicar etiquetas a contenido automáticamente** si coincide con condiciones específicas, como: 
    
  - Tipos específicos de información confidencial.
    
  - Palabras clave específicas que coinciden con una consulta que haya creado.
    
    La capacidad de aplicar etiquetas automáticamente al contenido ofrece las ventajas siguientes:
    
  - No es necesario formar a los usuarios para que conozcan todas las clasificaciones.
    
  - No es necesario depender de los usuarios para clasificar todo el contenido correctamente.
    
  - Los usuarios ya no necesitan conocer las directivas de gobierno de datos; en su lugar, pueden centrarse en su trabajo.
    
    Tenga en cuenta que, para aplicar automáticamente las etiquetas, se necesita una suscripción de Office 365 Enterprise E5.
    
- **Aplicar una etiqueta predeterminada a una biblioteca de documentos** en un sitio de grupo de Office 365 y SharePoint, para que todos los documentos de esa biblioteca obtengan la etiqueta predeterminada. 
    
- **Implementar la administración de registros en todo Office 365**, tanto en correos electrónicos como en documentos. Puede usar una etiqueta para clasificar contenido como un registro. Cuando ocurra esto, la etiqueta no se puede cambiar ni quitar, y el contenido no se puede editar ni eliminar. 
    
Para crear y administrar etiquetas, vaya a la página **Etiquetas** del Centro de seguridad y cumplimiento de Office 365. 
  
![Página Etiquetas](media/42d1865d-f0f5-436d-8e09-0e547302c816.png)
 
## <a name="how-labels-work-with-label-policies"></a>Funcionamiento de las etiquetas con directivas de etiquetas

El proceso para que los usuarios de su organización puedan usar etiquetas para clasificar contenido se divide en dos pasos: primero, se crean las etiquetas y, después, se publican en las ubicaciones seleccionadas. Al publicar etiquetas, se crea una directiva de etiquetas.
  
![Diagrama de roles y tareas para etiquetas](media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
Las etiquetas son bloques de creación independientes y reutilizables que se incluyen en una directiva de etiquetas y se publican en distintas ubicaciones. Las etiquetas se pueden reutilizar en un gran número de directivas. La finalidad principal de la directiva de etiquetas es agrupar un conjunto de etiquetas y especificar las ubicaciones donde quiere que aparezcan esas etiquetas.
  
![Diagrama de etiquetas, directivas de etiquetas y ubicaciones](media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. Al publicar etiquetas, se incluyen en una directiva de etiquetas. Una única etiqueta se puede incluir en varias directivas.
    
2. Las directivas de etiquetas especifican las ubicaciones donde se publicarán las etiquetas.
    
## <a name="only-one-label-at-a-time"></a>Solo una etiqueta cada vez

Es importante saber que solo se puede asignar una etiqueta al contenido (como un correo electrónico o un documento):
  
- En el caso de las etiquetas asignadas manualmente por los usuarios finales, estos pueden quitar o cambiar la etiqueta asignada.
    
- Si el contenido tiene asignada una etiqueta de aplicación automática, un usuario final puede reemplazarla por una etiqueta asignada manualmente.
    
- Si el contenido tiene una etiqueta asignada manualmente por un usuario final, una etiqueta de aplicación automática no puede reemplazar a la etiqueta asignada de forma manual.
    
- Si hay varias reglas que asignan una etiqueta de aplicación automática y el contenido cumple las condiciones de varias reglas, se asignará la etiqueta de la regla más antigua.
    
Las etiquetas asignadas manualmente se asignan de manera explícita; las etiquetas de aplicación automática se asignan de forma implícita; una etiqueta explícita tiene precedencia sobre una etiqueta implícita. Para obtener más información, vea la sección siguiente [Los principios de retención o qué tiene precedencia](labels.md#principles).
  
## <a name="how-long-it-takes-for-labels-to-take-effect"></a>Tiempo que tardan las etiquetas en aplicarse

Al publicar o aplicar automáticamente etiquetas, no surten efecto inmediatamente:
  
1. Primero, la directiva de etiquetas tiene que sincronizarse desde el Centro de seguridad y cumplimiento con las ubicaciones en la directiva.
    
2. Después, puede que la ubicación necesite algún tiempo hasta que las etiquetas manuales estén disponibles para los usuarios finales o para que se apliquen automáticamente las etiquetas al contenido. El tiempo necesario depende de la ubicación y del tipo de etiqueta.
    
### <a name="manual-labels"></a>Etiquetas manuales

Si publica etiquetas en SharePoint o OneDrive, puede que tarden un día en mostrarse a los usuarios finales. Además, si publica etiquetas en Exchange, pueden tardar hasta siete días en mostrarse a los usuarios finales y, además, el buzón necesita contener como mínimo 10 MB de datos.
  
![Diagrama de cuándo entran en vigor las etiquetas manuales](media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-labels"></a>Etiquetas de aplicación automática

Si aplica automáticamente etiquetas a contenido que coincida con condiciones específicas, estas pueden tardar hasta siete días en aplicarse a todo el contenido que coincida con las condiciones.
  
![Diagrama de cuándo entran en vigor las etiquetas de aplicación automática](media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-exchange-labels"></a>Comprobar el estado de las etiquetas de Exchange

En Exchange Online, las etiquetas se publican para los usuarios finales mediante un proceso que se ejecuta cada siete días. Con PowerShell, puede ver cuándo se ha ejecutado este proceso por última vez y, por tanto, determinar cuándo volverá a ejecutarse.
  
1. [Conexión a PowerShell de Exchange Online](https://go.microsoft.com/fwlink/?linkid=799773).
    
2. Ejecute estos comandos.
    
  ```
  $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
  ```

  ```
  $xmlprops = [xml]($logProps.MailboxLog)
  ```

  ```
  $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
  ```

    En los resultados, la propiedad `ELCLastSuccessTimeStamp` (UTC) indica la última vez que el sistema ha procesado el buzón. Si no se ha ejecutado desde el momento en que se crea la directiva, las etiquetas no aparecerán. Para forzar el procesamiento, ejecute `Start-ManagedFolderAssistant -Identity <user>`.
    
    Si las etiquetas no aparecen en Outlook en la Web y cree que tendrían que aparecer, asegúrese de vaciar la caché del explorador (CTRL+F5).
    
## <a name="label-policies-and-locations"></a>Ubicaciones y directivas de etiquetas

En función de la finalidad de las etiquetas, pueden publicarse en distintas ubicaciones.
  
|**Si la etiqueta…**|**La directiva de etiquetas se puede aplicar en…**|
|:-----|:-----|
|Se publica a los usuarios finales  <br/> |Exchange, SharePoint, OneDrive, Grupos de Office 365  <br/> |
|Se aplica automáticamente basándose en tipos de información confidencial  <br/> |Exchange (solo todos los buzones), SharePoint, OneDrive  <br/> |
|Se aplica automáticamente basándose en una consulta  <br/> |Exchange, SharePoint, OneDrive, Grupos de Office 365  <br/> |
   
Tenga en cuenta que, en Exchange, las etiquetas de aplicación automática (tanto para consultas como para tipos de información confidencial) solo se aplican en los nuevos mensajes enviados (datos en tránsito), no en todos los elementos que ya están presentes en el buzón (datos en reposo). Además, las etiquetas de aplicación automática para tipos de información confidencial se aplican a todos los buzones (no se pueden seleccionar buzones específicos).
  
Tenga en cuenta que las carpetas públicas de Exchange y Skype no admiten las etiquetas.
  
## <a name="how-labels-enforce-retention"></a>Forma en que las etiquetas aplican la retención

Las etiquetas pueden aplicar exactamente las mismas acciones de retención que una directiva. Puede usar etiquetas para implementar un plan de contenido sofisticado (o un plan de archivos). Para obtener más información sobre cómo funciona la retención, vea [Información general sobre las directivas de retención](retention-policies.md).
  
Además, una etiqueta tiene dos opciones de retención que solo están disponibles en una etiqueta, pero no están disponibles en una directiva de retención. Con una etiqueta, puede:
  
- Desencadenar una revisión para eliminación al finalizar el período de retención para que los documentos de OneDrive y SharePoint tengan que revisarse antes de ser eliminados. Para obtener más información, vea [Información general sobre revisiones para eliminación](disposition-reviews.md).
    
- Iniciar el período de retención desde el momento en que se etiquete el contenido, en lugar de la antigüedad del contenido o la fecha de la última modificación.
    
![Configuración de retención con opciones específicas para etiquetas](media/c49118c9-6279-4661-94db-deffa76e27ac.png)
  
## <a name="where-published-labels-can-appear-to-end-users"></a>Ubicaciones donde los usuarios pueden ver las etiquetas publicadas

Si los usuarios finales asignarán la etiqueta al contenido, puede publicarla en:
  
- Outlook en la Web
    
- Outlook 2010 y versiones posteriores
    
- OneDrive
    
- SharePoint
    
- Grupos de Office 365 (tanto en el sitio de grupo como el buzón de grupo de Outlook en la Web)
    
En las secciones siguientes, se explica cómo se mostrarán las etiquetas en diferentes aplicaciones para los usuarios de su organización.
  
### <a name="outlook-on-the-web"></a>Outlook en la Web

Para etiquetar un elemento en Outlook en la Web, haga clic con el botón derecho en el elemento \> **Asignar directiva** \> seleccione la etiqueta. 
  
![Menú Asignar directiva en Outlook en la Web](media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
Después de aplicarla, puede ver la etiqueta y la acción que realiza en la parte superior del elemento. Si un correo electrónico se clasifica y tiene asociado un período de retención, podrá ver rápidamente cuándo expirará el correo electrónico.
  
![Etiqueta asignada a correo electrónico en Outlook en la Web](media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
También puede aplicar etiquetas a carpetas, en cuyo caso:
  
- Se asignará automáticamente la misma etiqueta en todos los elementos de la carpeta, **excepto** en los elementos donde se haya aplicado de forma explícita una etiqueta. Los elementos etiquetados de forma explícita mantienen la etiqueta existente. Para obtener más información, vea la sección siguiente sobre los principios de retención. 
    
- Si cambia o quita la etiqueta predeterminada de una carpeta, también se cambiará o quitará la etiqueta de todos los elementos de la carpeta, **excepto** en los elementos con etiquetas explícitas. 
    
- Si mueve un elemento con una etiqueta predeterminada de una carpeta a otra carpeta con una etiqueta predeterminada distinta, la nueva etiqueta predeterminada se aplicará en el elemento.
    
- Si mueve un elemento con una etiqueta predeterminada de una carpeta a otra sin una etiqueta predeterminada, se quitará la etiqueta predeterminada anterior.
    
### <a name="outlook-2010-and-later"></a>Outlook 2010 y versiones posteriores

Para etiquetar un elemento en Outlook en la Web, haga clic con el botón derecho en el elemento \> en la **Cinta de opciones** \> **Asignar directiva** y seleccione la etiqueta. 
  
![Botón Asignar directiva](media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
Después de aplicarla, puede ver la etiqueta y la acción que realiza en la parte superior del elemento. Si un correo electrónico se clasifica y tiene asociado un período de retención, podrá ver rápidamente cuándo expirará el correo electrónico.
  
También puede aplicar etiquetas en carpetas. Este procedimiento funciona de la misma forma en Outlook en la Web que en Outlook 2010 y versiones posteriores (para obtener más información, vea la sección anterior).
  
### <a name="onedrive-and-sharepoint"></a>OneDrive y SharePoint

Para etiquetar un documento (incluidos archivos de OneNote) en OneDrive o SharePoint, seleccione el elemento \> en la esquina superior derecha, haga clic en **Abrir el panel de detalles**![icono de panel de información](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Aplicar etiqueta** y seleccione la etiqueta. 
  
Tenga en cuenta que también puede aplicar una etiqueta en una carpeta o un conjunto de documentos, así como establecer una etiqueta predeterminada para una biblioteca de documentos (para obtener más información, vea la sección siguiente).
  
![Aplicar una lista de etiquetas a un elemento en SharePoint](media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
Después de aplicar una etiqueta a un elemento, puede verla en el panel de detalles cuando esté seleccionado el elemento.
  
![Etiqueta aplicada mostrada en el panel de detalles](media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
También puede crear una vista de la biblioteca que contenga la columna **Etiquetas** o la columna **El elemento es un registro** para ver rápidamente las etiquetas asignadas a todos los elementos y conocer qué elementos son registros. Pero tenga en cuenta que no puede filtrar la vista por la columna **El elemento es un registro**. 
  
![Columna de la biblioteca para etiquetas mostrada en vista personalizada](media/e3392627-c0a3-405e-bb57-55f27c34cfdd.png)
  
### <a name="office-365-groups"></a>Grupos de Office 365

Al publicar etiquetas en un grupo de Office 365, las etiquetas aparecen tanto en el sitio de grupo como en el buzón de grupo de Outlook en la Web. La experiencia de aplicar una etiqueta al contenido es idéntica a la que se muestra anteriormente para el correo electrónico y los documentos.
  
## <a name="applying-a-label-automatically-based-on-conditions"></a>Aplicar automáticamente una etiqueta basándose en condiciones

Una de las características más útiles de las etiquetas es la capacidad de aplicarlas automáticamente a contenido que coincida con determinadas condiciones. En ese caso, los usuarios de su organización no necesitan aplicar las etiquetas: Office 365 lo hace automáticamente.
  
![Diagrama de roles y tareas para etiquetas de aplicación automática](media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
Las etiquetas de aplicación automática son realmente útiles porque:
  
- No es necesario formar a los usuarios para que conozcan todas las clasificaciones.
    
- No es necesario depender de los usuarios para clasificar todo el contenido correctamente.
    
- Los usuarios ya no necesitan conocer las directivas de gobierno de datos; en su lugar, pueden centrarse en su trabajo.
    
Puede aplicar automáticamente etiquetas en contenido cuando este coincida con:
  
- Tipos específicos de información confidencial.
    
- Palabras clave específicas que coinciden con una consulta que haya creado.
    
![Página de selección de condición para una etiqueta de aplicación automática](media/c0b7a3ef-bda0-494c-941d-f1f93753ecdd.png)
  
Tenga en cuenta que, para usar las etiquetas de aplicación automática, se necesita una suscripción de Office 365 Enterprise E5; además, estas pueden tardar hasta siete días en aplicarse automáticamente a todo el contenido que coincida con las condiciones, como se ha descrito anteriormente.
  
### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>Aplicar automáticamente etiquetas a contenido con tipos específicos de información confidencial

Al crear etiquetas de aplicación automática para información confidencial, verá la misma lista de plantillas de directiva que al crear una directiva de prevención de pérdida de datos (DLP). Cada plantilla de directiva está preconfigurada para buscar tipos específicos de información confidencial (por ejemplo, la plantilla que se muestra aquí busca números de pasaporte, números del seguro social y números ITIN estadounidenses). Para obtener más información sobre DLP, vea [Información general sobre las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md).
  
![Plantillas de directiva con tipos de información confidencial](media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
Después de seleccionar una plantilla de directiva, puede agregar o quitar los tipos de información confidencial, así como cambiar el recuento de instancias y la precisión de coincidencia. En el ejemplo que se muestra aquí, solo se aplicará automáticamente una etiqueta cuando:
  
- El contenido tenga entre 1 y 9 instancias de alguno de estos tres tipos de información confidencial. Puede eliminar el valor **máximo** para que cambie a **cualquiera**.
    
- El tipo de información confidencial detectado tiene una precisión de coincidencia (o nivel de confianza) mínima de 75. Muchos tipos de información confidencial se definen con varios patrones, donde un patrón con una precisión de coincidencia más alta necesita encontrar más evidencias (como palabras clave, fechas o direcciones), mientras que un patrón con una precisión de coincidencia inferior necesita menos evidencias. En resumen, cuanto menor sea la precisión de coincidencia **mínima**, más fácil será que el contenido coincida con la condición. 
    
    Si cambia la precisión de coincidencia (o el nivel de confianza), tendrá que usar uno de los niveles de confianza de un patrón para ese tipo de información confidencial, como se define en [Información que buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
    
![Opciones para identificar tipos de información confidencial](media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-specific-keywords"></a>Aplicar automáticamente etiquetas a contenido con palabras clave específicas

Puede aplicar automáticamente etiquetas a contenido que cumpla determinadas condiciones. Las condiciones disponibles ahora permiten aplicar una etiqueta a contenido que coincida con palabras o frases específicas. Puede restringir la consulta con operadores de búsqueda como AND, OR y NOT. Para obtener más información sobre los operadores, vea [Consultas de palabras clave y condiciones de búsqueda para Búsqueda de contenido](keyword-queries-and-search-conditions.md).
  
La compatibilidad para agregar propiedades que admiten búsquedas (por ejemplo, **asunto:**) estará disponible próximamente. 
  
Tenga en cuenta que las etiquetas basadas en consultas usan el índice de búsqueda para identificar contenido.
  
![Editor de consultas](media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)
  
## <a name="applying-a-default-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a>Aplicar una etiqueta predeterminada a todo el contenido de una biblioteca, carpeta o conjunto de documentos de SharePoint

Además de permitir que los usuarios apliquen una etiqueta a documentos individuales, también puede aplicar una etiqueta predeterminada a una biblioteca, carpeta o conjunto de documentos de SharePoint para aplicar la etiqueta predeterminada a todos los documentos de esa ubicación.
  
En el caso de una biblioteca de documentos, esto se realiza en la página **Configuración de la biblioteca** de una biblioteca de documentos. Al seleccionar la etiqueta predeterminada, también puede aplicarla a los elementos existentes de la biblioteca. 
  
Por ejemplo, si tiene una etiqueta para materiales de marketing y sabe que una biblioteca de documentos específica solo contendrá ese tipo de contenido, puede hacer que la etiqueta “Materiales de marketing” sea la predeterminada para todos los documentos de esa biblioteca.
  
![Opción “Aplicar etiqueta” en la página Configuración de la biblioteca](media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
Si aplica una etiqueta predeterminada a elementos existentes de una biblioteca, carpeta o conjunto de documentos:
  
- Se aplicará automáticamente la misma etiqueta a todos los elementos de esa biblioteca, carpeta o conjunto de documentos, **excepto** en los elementos donde se haya aplicado de forma explícita una etiqueta. Los elementos etiquetados de forma explícita mantienen la etiqueta existente. Para obtener más información, vea la sección siguiente [Los principios de retención o qué tiene precedencia](labels.md#principles).
    
- Si cambia o quita la etiqueta predeterminada de una biblioteca, carpeta o conjunto de documentos, también se cambiará o quitará la etiqueta de todos los elementos de la biblioteca, carpeta o conjunto de documentos, **excepto** de los elementos con etiquetas explícitas. 
    
- Si mueve un elemento con una etiqueta predeterminada de una biblioteca, carpeta o conjunto de documentos a otra biblioteca, carpeta o conjunto de documentos, el elemento mantendrá su etiqueta predeterminada existente, incluso si la nueva ubicación tiene otra etiqueta predeterminada.
    
## <a name="applying-a-label-to-email-by-using-rules"></a>Aplicar una etiqueta a correo electrónico mediante reglas

En Outlook 2010 o versiones posteriores, puede crear reglas para aplicar una etiqueta o directiva de retención.
  
Por ejemplo, puede crear una regla que aplique una etiqueta específica a todos los mensajes enviados a un grupo de distribución específico o desde este.
  
Para crear una regla, haga clic con el botón derecho en un elemento \> **Reglas** \> **Crear regla** \> **Opciones avanzadas** \> **Asistente para reglas** \> **aplicar directiva de retención**.
  
![Asistente para reglas con opción para aplicar directivas de retención](media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a>Clasificar contenido sin aplicar acciones

Al crear una etiqueta, puede hacerlo sin activar ninguna retención u otras acciones, como se muestra abajo. En este caso, puede usar una etiqueta simplemente como una etiqueta de texto, sin exigir ninguna acción.
  
Por ejemplo, puede crear una etiqueta llamada “Revisar más tarde” sin ninguna acción y, después, aplicar automáticamente esa etiqueta al contenido con tipos de información confidencial o contenido consultado.
  
![Página “Configuración de etiquetas” con la retención desactivada](media/17ce863b-a823-426e-aaad-83718465f762.png)
  
## <a name="using-labels-for-records-management"></a>Uso de etiquetas para la administración de registros

De forma general, la administración de registros significa que:
  
- Los usuarios clasifican el contenido importante como registros.
    
- Un registro no se puede modificar ni eliminar.
    
- Por último, los registros se eliminan cuando se cumple la duración indicada.
    
Puede usar etiquetas para implementar una única estrategia de administración de registros coherente en Office 365, mientras que otras características de administración de registros (como el Centro de registros) solo se aplican a contenido de SharePoint. También puede exigir acciones de retención en registros para que se eliminen automáticamente al finalizar su ciclo de vida.
  
Al crear una etiqueta, puede usarla para clasificar el contenido como un registro.
  
![Casilla Clasificar contenido como un registro](media/9c300739-d5d0-41d2-88dd-137f1cfc9cb6.png)
  
Al etiquetar un elemento como un registro, ocurren cuatro cosas:
  
- El elemento no se puede eliminar de forma permanente.
    
- El elemento no se puede editar.
    
- La etiqueta no se puede cambiar.
    
- La etiqueta no se puede quitar.
    
### <a name="who-can-classify-content-as-a-record"></a>Quién puede clasificar contenido como un registro

En el caso de contenido de SharePoint, cualquier usuario del grupo predeterminado Miembros (el nivel de permisos Colaborar) puede aplicar una etiqueta de registro a contenido. Solo el administrador de la colección de sitios puede quitar o cambiar la etiqueta una vez aplicada. Además, las etiquetas que clasifican contenido como registros tienen que aplicarse de forma manual (no se pueden aplicar automáticamente).
  
### <a name="records-and-folders"></a>Registros y carpetas

Puede aplicar una etiqueta a una carpeta en Exchange, SharePoint o OneDrive. Si una carpeta se etiqueta como un registro y mueve un elemento dentro de esa carpeta, el elemento se etiquetará como un registro. Al mover el elemento fuera de la carpeta, este mantendrá la etiqueta de registro.
  
### <a name="records-cant-be-deleted"></a>Los registros no se pueden eliminar

Si intenta eliminar un registro en Exchange, el elemento se moverá a la carpeta Elementos recuperables, como se describe en [Funcionamiento de una directiva de retención con contenido local](retention-policies.md#how-a-retention-policy-works-with-content-in-place).
  
Si intenta eliminar un registro en SharePoint, verá un error que indica que el elemento no se ha eliminado y puede comprobar que este permanecerá en la biblioteca.
  
![Mensaje que indica que el elemento no se elimina de SharePoint](media/d0020726-1593-4a96-b07c-89b275e75c49.png)
  
Si intenta eliminar un registro en OneDrive, el elemento se moverá a la biblioteca de conservación de documentos, como se describe en [Funcionamiento de una directiva de retención con contenido local](retention-policies.md#how-a-retention-policy-works-with-content-in-place).
  
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a>Usar una etiqueta como condición en una directiva DLP

Una etiqueta puede exigir acciones de **retención** en el contenido. Además, puede usar una etiqueta como una condición en una directiva de prevención de pérdida de datos (DLP). Esto quiere decir que una directiva DLP puede exigir acciones de **protección** (como restringir el acceso) en contenido que coincida con una etiqueta específica. 
  
Para obtener más información, vea [Usar una etiqueta como una condición en una directiva DLP](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).
  
## <a name="using-the-label-activity-explorer-and-the-data-governance-reports"></a>Usar el Explorador de actividad de etiquetas y los informes de gobierno de datos

Después de publicar o aplicar automáticamente las etiquetas, puede comprobar que se hayan aplicado en el contenido según lo previsto. Para supervisar las etiquetas, puede usar el:
  
- **Explorador de actividad de etiquetas**. Con el explorador (que se muestra abajo), puede buscar y visualizar rápidamente la actividad de etiquetas de todo el contenido en SharePoint y OneDrive para la Empresa en los últimos 30 días. Para obtener más información, vea [Ver actividad de etiquetas para documentos](view-label-activity-for-documents.md).
    
- **Informes de gobierno de datos**. Con estos informes, puede ver rápidamente actividades y tendencias de etiquetas de todo el contenido en Exchange, SharePoint y OneDrive para la Empresa en los últimos 90 días. Para obtener más información, vea [Ver los informes de gobierno de datos](view-the-data-governance-reports.md).
    
![Explorador de actividad de etiquetas](media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="using-content-search-to-find-all-content-with-a-specific-label-applied-to-it"></a>Usar Búsqueda de contenido para encontrar todo el contenido que tenga aplicada una etiqueta específica

Después de asignar etiquetas a contenido (ya sea por los usuarios o aplicadas automáticamente), puede usar Búsqueda de contenido en el Centro de seguridad y cumplimiento para encontrar todo el contenido clasificado con una etiqueta específica.
  
![Página Búsqueda de contenido](media/564d5dfe-285a-4a7e-800e-907b12a1b273.png)
  
Al crear una búsqueda de contenido, seleccione la condición **Etiqueta de cumplimiento** y, después, escriba el nombre completo de la etiqueta o una parte del nombre de la etiqueta y use un comodín. Para obtener más información, vea [Consultas de palabras clave y condiciones de búsqueda para Búsqueda de contenido](keyword-queries-and-search-conditions.md).
  
![Condición Etiqueta de cumplimiento](media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Los principios de retención o qué tiene precedencia

Es posible (o incluso probable) que se apliquen varias directivas de retención a contenido, cada una con una acción (conservar, eliminar o ambas) y un período de retención. ¿Qué tiene precedencia? En general, puede estar seguro de que el contenido conservado por una directiva no se puede eliminar de forma permanente con otra directiva.
  
![Diagrama de los principios de retención](media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Para entender cómo se aplican a contenido distintas etiquetas con acciones de retención, tenga en cuenta estos principios de retención:
  
1. **La retención tiene prioridad sobre la eliminación.** Imagine que una directiva de retención dice que es necesario eliminar el correo electrónico de Exchange después de tres años, pero otra directiva de retención dice que se conserve durante cinco años y, después, se elimine. Todo el contenido que alcance los tres años de antigüedad se eliminará y quedará oculto para el usuario, pero se seguirá conservando en la carpeta Elementos recuperables hasta que alcance los cinco años, momento en que se eliminará de forma permanente. 
    
2. **El período de retención más largo tiene prioridad.** Si el contenido está sujeto a varias directivas de retención, se conservará hasta el final del período de retención más largo. 
    
3. **La inclusión explícita tiene prioridad sobre la inclusión implícita.** Esto significa que: 
    
    1. Si una etiqueta con configuración de retención se asigna de forma manual a un usuario o elemento (como un correo electrónico de Exchange o un documento de OneDrive), tendrá precedencia sobre la directiva asignada en el nivel de sitio o buzón y una etiqueta predeterminada asignada por la biblioteca de documentos. Por ejemplo, si la etiqueta explícita indica que tiene que conservarse durante diez años, pero la directiva asignada al sitio dice que solo tiene que conservarse durante cinco años, la etiqueta tiene precedencia. Tenga en cuenta que las etiquetas de aplicación automática se consideran implícitas, no explícitas, porque Office 365 las aplica automáticamente.
    
    2. Si una directiva de retención incluye una ubicación específica (como el buzón de un usuario o una cuenta de OneDrive para la Empresa), tendrá precedencia sobre cualquier otra directiva de retención que se aplique a los buzones de todos los usuarios o a las cuentas de OneDrive para la Empresa, pero que no incluyan específicamente ese buzón de usuario.
    
4. **El período de eliminación más corto tiene prioridad.** De forma similar, si el contenido está sujeto a varias directivas que eliminan contenido (sin retención), se eliminará al final del período de retención más corto. 
    
Tenga en cuenta que los principios de retención funcionan como un flujo de desempate de arriba abajo: si las reglas aplicadas por todas las directivas o etiquetas son las mismas en un nivel, el flujo baja al siguiente nivel para determinar la precedencia de la regla que se aplica.
  
Por último, una etiqueta o directiva de retención no puede eliminar de forma permanente ningún contenido si está en suspensión para eDiscovery. Cuando se levante la suspensión, el contenido volverá a estar disponible para el proceso de limpieza descrito anteriormente.
  
## <a name="use-labels-instead-of-these-features"></a>Usar etiquetas en lugar de estas características

Las etiquetas se pueden publicar fácilmente para toda la organización, así como su contenido, en Office 365, incluidos Exchange, SharePoint, OneDrive y Grupos de Office 365. Si necesita clasificar contenido o administrar registros en cualquier lugar en Office 365, le recomendamos que use etiquetas.
  
Hay otras características que se han usado anteriormente para clasificar contenido o administra registros en Office 365. Estas se indican abajo. Estas características seguirán funcionando en paralelo con las etiquetas creadas en el Centro de seguridad y cumplimiento. Tenga en cuenta que, aunque hay casos en los que la implementación de etiquetas es distinta en comparación con las características anteriores, la evolución de las etiquetas dirigirá el futuro de la administración de registros en todo Office 365. Por tanto, a partir de ahora, para el gobierno de datos le recomendamos que use etiquetas en lugar de estas características.
  
### <a name="exchange-online"></a>Exchange Online

- [Etiquetas de retención y directivas de retención](https://go.microsoft.com/fwlink/?linkid=846125), lo que también se conoce como [administración de registros de mensajes (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (solo eliminación) 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online y OneDrive para la Empresa

- [Configuración de administración de registros local](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retención) 
    
- [Introducción al Centro de registros](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (retención) 
    
- [Directivas de administración de información](intro-to-info-mgmt-policies.md) (solo eliminación) 
    
## <a name="permissions"></a>Permisos

Los miembros de su equipo de cumplimiento normativo que vayan a crear etiquetas necesitan permisos en el Centro de seguridad y cumplimiento. De forma predeterminada, el administrador de inquilinos tendrá acceso a esta ubicación y puede proporcionar acceso a los responsables de cumplimiento normativo y otros usuarios al Centro de seguridad y cumplimiento sin concederles todos los permisos de un administrador de inquilinos. Para hacerlo, le recomendamos que vaya a la página **Permisos** del Centro de seguridad y cumplimiento, edite el grupo de roles **Administrador de cumplimiento** y agregue miembros al mismo. 
  
Para obtener más información, vea [Conceder acceso a los usuarios al Centro de seguridad y cumplimiento de Office 365](grant-access-to-the-security-and-compliance-center.md).
  
Estos permisos solo son necesarios para crear y aplicar una directiva de etiquetas. La aplicación de directivas no necesita acceso al contenido.
  
## <a name="find-the-powershell-cmdlets-for-labels"></a>Encontrar los cmdlets de PowerShell para etiquetas

Para usar los cmdlets de etiquetas, necesita:
  
1. [Conectarse al Centro de seguridad y cumplimiento de Office 365 mediante PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Usar estos [Cmdlets del Centro de seguridad y cumplimiento de Office 365](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
## <a name="more-information"></a>Más información

- [Información general sobre las directivas de retención](retention-policies.md)
    

