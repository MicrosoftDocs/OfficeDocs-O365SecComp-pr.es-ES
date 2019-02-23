---
title: casos de eDiscovery en el centro de &amp; seguridad y cumplimiento de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 8dd335ab-29d0-41c3-8dd8-9f7c7481e60c
description: Use el centro de seguridad &amp; y cumplimiento de Office 365 para crear y administrar casos de exhibición de documentos electrónicos en su organización. Puede asignar miembros al caso, poner ubicaciones de contenido en retención, ejecutar búsquedas de contenido asociadas con el caso y exportar los resultados de la búsqueda. También puede preparar datos de casos para un análisis más avanzado en la exhibición avanzada de documentos electrónicos.
ms.openlocfilehash: 92ef00bbdd8de5b1ba6bdae40bce96720ac46089
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214020"
---
# <a name="ediscovery-cases-in-the-office-365-security-amp-compliance-center"></a>casos de eDiscovery en el centro de &amp; seguridad y cumplimiento de Office 365

Puede usar casos de exhibición de documentos electrónicos en el &amp; centro de seguridad y cumplimiento de Office 365 para controlar quién puede crear, acceder y administrar casos de eDiscovery en su organización. Si su organización tiene una suscripción a Office 365 E5, también puede usar casos de exhibición de documentos electrónicos para analizar los resultados de la búsqueda con Office 365 Advanced eDiscovery.
  
Un caso de exhibición de documentos electrónicos permite agregar miembros a un caso, controlar los tipos de acciones que pueden realizar determinados miembros de caso, poner una retención en las ubicaciones de contenido relevantes para un caso legal y asociar varias búsquedas de contenido con un solo caso. También puede exportar los resultados de cualquier búsqueda de contenido que esté asociado a un caso o preparar los resultados de búsqueda para analizarlos en la exhibición avanzada de documentos electrónicos. los casos de eDiscovery son una buena forma de limitar quién tiene acceso a las búsquedas de contenido y los resultados de búsqueda para un caso legal específico en su organización.
  
Use el siguiente flujo de trabajo para configurar y usar casos de eDiscovery en &amp; el centro de seguridad y cumplimiento y la exhibición avanzada de documentos electrónicos.

[Paso 1: Asignar permisos de exhibición de documentos electrónicos a posibles miembros del caso](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[Paso 2: crear un nuevo caso](#step-2-create-a-new-case)

[Paso 3: agregar miembros a un caso](#step-3-add-members-to-a-case)

[Paso 4: poner las ubicaciones de contenido en retención](#step-4-place-content-locations-on-hold)

[Paso 5: crear y ejecutar una búsqueda de contenido asociada a un caso](#step-5-create-and-run-a-content-search-associated-with-a-case)

[Paso 6: exportar los resultados de una búsqueda de contenido asociada a un caso](#step-6-export-the-results-of-a-content-search-associated-with-a-case)

[Paso 7: preparar los resultados de búsqueda para la exhibición avanzada de documentos electrónicos](#step-7-prepare-search-results-for-advanced-ediscovery)

[Paso 8: ir al caso en la exhibición avanzada de documentos electrónicos](#step-8-go-to-the-case-in-advanced-ediscovery)

[Opcional Paso 9: cerrar un caso](#optional-step-9-close-a-case)

[Opcional Paso 10: volver a abrir un caso cerrado](#optional-step-10-re-open-a-closed-case)

[Más información](#more-information)
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a>Paso 1: Asignar permisos de exhibición de documentos electrónicos a posibles miembros del caso

El primer paso consiste en asignar los permisos adecuados relacionados con eDiscovery a los usuarios para que pueda agregarlos a un caso de exhibición de documentos electrónicos en el paso 2. Debe ser miembro del grupo de roles de administración de la organización (o tener asignado el rol de administración de roles) en el centro &amp; de seguridad y cumplimiento de Office 365 para asignar permisos de exhibición de documentos electrónicos. En la lista siguiente se describen los grupos de roles relacionados con la &amp; exhibición de documentos electrónicos en el centro de seguridad y cumplimiento. 
  
- **Revisor** : este grupo de roles tiene los permisos más restrictivos relacionados con la exhibición de documentos electrónicos. El objetivo principal de este grupo de roles es permitir a los miembros ver y obtener acceso a los datos de caso en eDiscovery avanzado de Office 365. Los miembros de este grupo solo pueden ver y abrir la lista de los casos de la página de **eDiscovery** en &amp; el centro de seguridad y cumplimiento del que son miembros. Una vez que el usuario tiene acceso a un caso en el centro de seguridad & cumplimiento, puede hacer clic en **cambiar a eDiscovery avanzado** para acceder y analizar los datos del caso en la exhibición avanzada de documentos electrónicos. No pueden crear casos, agregar miembros a un caso, crear suspensiones, crear búsquedas, obtener una vista previa de los resultados de la búsqueda, exportar resultados de la búsqueda o preparar los resultados para la exhibición avanzada de documentos electrónicos. 
    
- **Administrador de eDiscovery** : los miembros de este grupo de roles pueden crear y administrar casos de eDiscovery. Pueden agregar y quitar miembros, poner ubicaciones de contenido en suspensión, crear y editar búsquedas de contenido asociadas a un caso, exportar los resultados de una búsqueda de contenido y preparar los resultados de la búsqueda para analizarlos en la exhibición avanzada de documentos electrónicos. Hay dos sub-grupos en este grupo de roles. La diferencia entre estos subgrupos se basa en el ámbito.
    
  - **Administrador de exhibición** de documentos electrónicos: puede ver y administrar los casos de exhibición de documentos electrónicos que crean o de los que son miembros. Si otro administrador de exhibición de documentos electrónicos crea un caso pero no agrega un segundo administrador de eDiscovery como miembro de ese caso, el segundo administrador de eDiscovery no podrá ver ni abrir el **** caso en la página de &amp; exhibición de documentos electrónicos en el centro de seguridad y cumplimiento. los administradores de eDiscovery también pueden acceder a sus casos en eDiscovery avanzado para realizar tareas de análisis. 
    
  - **Administrador de exhibición** de documentos electrónicos: puede realizar todas las tareas de administración de casos que puede realizar un administrador de exhibición de documentos electrónicos. Además, un administrador de eDiscovery puede:
    
    - Ver todos los casos que se enumeran en la página **Exhibición de documentos electrónicos**. 
    
    - Administrar cualquier caso en la organización después de que se agreguen como miembro del caso.
    
    - Obtenga acceso a los datos de caso en eDiscovery avanzado para cualquier caso de la organización.
    
    Consulte la sección [More information](#more-information) para saber por qué quizás quiera tener un administrador de exhibición de documentos electrónicos en su organización. 
    
> [!IMPORTANT]
> Si una persona no es miembro de uno de estos grupos de roles relacionados con la exhibición de documentos electrónicos, o no es miembro de un grupo de roles que tiene asignado el rol de revisor, no puede agregarlo como miembro de un caso de exhibición de documentos electrónicos. 

Para obtener más información acerca de los permisos de eDiscovery, consulte [asignar permisos de exhibición &amp; de documentos electrónicos en el centro de seguridad y cumplimiento de Office 365](assign-ediscovery-permissions.md).
  
 **Para asignar permisos de exhibición de documentos electrónicos:**
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el centro &amp; de seguridad y cumplimiento, haga clic en **permisos**y, a continuación, realice una de las siguientes acciones en función de los permisos de exhibición de documentos electrónicos que desee asignar.
    
    - Para asignar permisos de revisor, seleccione el **** grupo de roles de revisor y, a continuación, junto a **miembros**, haga clic en **Editar**. Haga clic en **seleccionar miembros**, haga clic en **Editar**, ![haga clic en agregar icono](media/ITPro-EAC-AddIcon.gif) **Agregar**, seleccione el usuario que desea agregar al grupo de funciones de revisor y, a continuación, haga clic en **Agregar**.
    
    - Para asignar permisos de administrador de eDiscovery, seleccione el grupo de roles **eDiscovery Manager** y, a continuación, junto a **eDiscovery Manager**, haga clic en **Editar**. Haga clic en **elegir administrador de exhibición**de documentos ![electrónicos,](media/ITPro-EAC-AddIcon.gif) haga clic en **Editar**, haga clic en agregar icono * * Agregar * *, seleccione el usuario que desea agregar como administrador de exhibición de documentos electrónicos y, a continuación, haga clic en **Agregar**.
    
    - Para asignar permisos de administrador de eDiscovery, seleccione el grupo de roles **eDiscovery Manager** y, a continuación, junto a **Administrador de exhibición**de documentos electrónicos, haga clic en **Editar**. Haga clic en **elegir administrador de eDiscovery**, haga ![clic en](media/ITPro-EAC-AddIcon.gif) **Editar**, haga clic en agregar icono **Agregar**, seleccione el usuario que desea agregar como administrador de exhibición de documentos electrónicos y, a continuación, haga clic en **Agregar**.
    
4. Una vez que haya agregado todos los usuarios, haga clic en **listo**, haga clic en **Guardar** para guardar los cambios en el grupo de roles y, a continuación, haga clic en **cerrar**.

## <a name="step-2-create-a-new-case"></a>Paso 2: crear un nuevo caso

El siguiente paso es crear un nuevo caso de exhibición de documentos electrónicos. Debe ser miembro del grupo de roles eDiscovery Managers para poder crear casos de eDiscovery. Como se ha explicado anteriormente, después de crear un nuevo caso &amp; en el centro de seguridad y cumplimiento, usted (y otros miembros de mayúsculas y minúsculas) podrá tener acceso al mismo caso en eDiscovery avanzado si la organización tiene una suscripción a Office 365 E5.
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el centro &amp; de seguridad y cumplimiento, haga clic en ** &amp; búsqueda** \> **** en exhibición ![de documentos electrónicos y, a continuación, en agregar icono](media/ITPro-EAC-AddIcon.gif) **crear un caso**.
    
4. En la página **nuevo caso** , indique el caso como un nombre, escriba una descripción opcional y, a continuación, haga clic en **Guardar**. Tenga en cuenta que el nombre del caso debe ser único en su organización.
    
    ![Crear un nuevo caso](media/7f78f83b-1525-4c77-9888-4b6bda1e148d.png)
  
    El nuevo caso se muestra en la lista de casos de la página de **exhibición** de documentos electrónicos. Tenga en cuenta que puede desplazar el cursor sobre un nombre de caso para mostrar información sobre el caso, incluido el estado del caso ( **activo** o **cerrado**), la descripción del caso (creado en el paso anterior) y cuándo se cambió el caso la última vez y Quién lo modificó.
    
    > [!TIP]
    > Después de crear un nuevo caso, puede cambiarle el nombre en cualquier momento. Solo tiene que hacer clic en el nombre del caso en la página de **exhibición** de documentos electrónicos. En la página desplegable **administrar este caso** , cambie el nombre que se muestra en el cuadro de **nombre**y, a continuación, guarde el cambio. 
  
## <a name="step-3-add-members-to-a-case"></a>Paso 3: agregar miembros a un caso

Después de crear un nuevo caso, el siguiente paso consiste en Agregar miembros al caso. Como se ha explicado anteriormente, solo los usuarios que son miembros de los grupos de roles Reviewer o eDiscovery Manager pueden agregarse como miembros del caso. Tenga en cuenta que el administrador de eDiscovery que ha creado el caso se agrega automáticamente como miembro.
  
1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Haga clic en el nombre del caso al que desea agregar miembros.
    
    Se muestra la página flotante **administrar este caso** . 
    
    ![Página para administrar un escenario flotante](media/11f35ceb-6c98-4580-a3bc-ad688e9c7af9.png)
  
3. En **administrar miembros**, haga ![clic en](media/ITPro-EAC-AddIcon.gif) agregar icono **Agregar** para agregar miembros al caso. 
    
    También puede optar por agregar un grupo de funciones al caso. En **administrar grupos de roles**, ![haga clic](media/ITPro-EAC-AddIcon.gif) en agregar icono **Agregar**.
    
    > [!NOTE]
    > Los grupos de roles controlan quién puede asignar miembros a un caso de exhibición de documentos electrónicos. Esto significa que solo puede asignar a un caso los grupos de roles de los que es miembro.
    
4. En la lista de personas o grupos de roles que se pueden agregar como miembros del caso, haga clic en la casilla situada junto a los nombres de los grupos de personas o roles que desea agregar.
    
    > [!TIP]
    > Si tiene una lista grande de personas que pueden agregarse como miembros, use el cuadro de **búsqueda** para buscar una persona específica en la lista. 
  
5. Una vez que haya seleccionado los grupos de personas o roles que desea agregar como miembros del grupo, haga clic en **Agregar**.
    
    En **administrar este caso**, haga clic en **Guardar** para guardar la nueva lista de miembros de mayúsculas y minúsculas. 
    
6. Haga clic en **Guardar** para guardar la nueva lista de miembros de caso. 
  
## <a name="step-4-place-content-locations-on-hold"></a>Paso 4: poner las ubicaciones de contenido en retención

Puede usar un caso de exhibición de documentos electrónicos para crear suspensiones y conservar el contenido que pueda ser relevante para el caso. Puede retener una retención en los buzones y en los sitios de OneDrive para la empresa de las personas que son custodios en el caso. También puede poner una retención en el buzón de grupo, el sitio de SharePoint y el sitio de OneDrive para la empresa para un grupo de Office 365. De forma similar, puede poner una retención en el buzón de correo y el sitio asociados a Microsoft Teams. Cuando se colocan ubicaciones de contenido en retención, el contenido se conserva hasta que se quita la retención de la ubicación del contenido o hasta que se elimina la suspensión.

> [!NOTE]
> Después de poner una ubicación de contenido en retención, la retención tarda hasta 24 horas en surtir efecto. 
>   
Al crear una suspensión, tiene las siguientes opciones para limitar el contenido que se almacena en las ubicaciones de contenido especificadas:
  
- Se crea una retención infinita en la que todo el contenido se coloca en retención. Como alternativa, puede crear una retención basada en consultas en la que solo se coloca en retención el contenido que coincide con una consulta de búsqueda.
    
- Puede especificar un intervalo de fechas para contener solo el contenido enviado, recibido o creado dentro del intervalo de fechas. Como alternativa, puede retener todo el contenido independientemente de Cuándo se haya enviado, recibido o creado.
    
> [!NOTE]
> Puede tener un máximo de 10.000 directivas de retención en todos los casos de eDiscovery de su organización. 
  
Para crear una suspensión para un caso de exhibición de documentos electrónicos:
  
1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Haga clic en **abrir** junto al caso en el que desea crear las suspensiones. 
    
3. En la página **principal** del caso, haga clic en la pestaña **retención** . 
    
    ![Haga clic en la pestaña retención.](media/3fef2db4-36de-4517-a34d-82f47b82d9bf.png)
  
4. En la página **suspensión** , haga ![clic en](media/ITPro-EAC-AddIcon.gif) agregar icono **crear**.
    
5. En la página nombre de la **retención** , asigne un nombre a la retención. El nombre de la retención debe ser único en la organización. 
    
    ![Asigne un nombre único a la retención.](media/7e15ea63-abd1-4f14-a29c-7ecfb9571d2c.png)
  
6. Opcional En el cuadro **Descripción** , agregue una descripción de la suspensión. 
    
7. Haga clic en **Siguiente**.
    
8. Elija las ubicaciones de contenido que desea poner en retención. Puede poner buzones de correo, sitios y carpetas públicas en retención.
    
    ![Elegir las ubicaciones de contenido para colocar en suspensión](media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   a. **Exchange email** : haga clic en **elegir usuarios, grupos o equipos** y, a continuación, haga clic en **elegir usuarios, grupos o equipos** de nuevo. para especificar los buzones que se deben poner en retención. Use el cuadro de búsqueda para buscar los buzones de usuario y los grupos de distribución (para poner una retención en los buzones de los miembros del grupo) para ponerlos en retención. También puede poner una retención en el buzón asociado para un grupo de Office 365 o un equipo de Microsoft. Active la casilla de verificación usuario, grupo, equipo, haga clic en **elegir**y, a continuación, haga clic en **listo**.
    
    > [!NOTE]
    > Al hacer clic en **elegir usuarios, grupos o equipos** para especificar los buzones que se deben poner en espera, el selector de buzón mostrado está vacío. Esto se debe a su diseño para mejorar el rendimiento. Para agregar personas a esta lista, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda. 
  
   b. **sitios de SharePoint** : haga clic en **elegir sitios** y, a continuación, haga clic en **elegir sitios** de nuevo para especificar que los sitios de SharePoint y OneDrive para la empresa se retienen en suspensión. Escriba la dirección URL de cada sitio que quiera poner en retención. También puede Agregar la dirección URL del sitio de SharePoint para un grupo de Office 365 o un equipo de Microsoft. Haga clic en **elegir**y, a continuación, en **listo**.
    
    Consulte la sección [More Information](#more-information) para obtener sugerencias sobre cómo poner en espera grupos de Office 365 y Microsoft Teams. 
    
    > [!NOTE]
    > En el caso poco probable de que se cambie el nombre principal de usuario (UPN) de una persona, también se cambiará la dirección URL de su cuenta de OneDrive para incorporar el nuevo UPN. Si esto ocurre, tendrá que modificar la retención agregando la nueva dirección URL de OneDrive del usuario y quitando la antigua. 
  
   c. **carpetas públicas de Exchange** : mueva el control](media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) de ![alternancia del conmutador de alternancia a la posición **todas** para poner todas las carpetas públicas en la organización de Exchange online en retención. Tenga en cuenta que no puede elegir carpetas públicas específicas que poner en retención. Deje el modificador de alternancia establecido en **ninguno** si no desea mantener una retención en las carpetas públicas.
    
9. Cuando haya acabado de agregar ubicaciones de contenido a la suspensión, haga clic en **siguiente**.
    
10. Para crear una retención basada en consultas con condiciones, realice lo siguiente. De lo contrario, haga clic en **siguiente**
    
    ![Crear una suspensión basada en consulta con condiciones](media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    
       a. en el cuadro bajo **palabras clave**, escriba una consulta de búsqueda en el cuadro para que solo se conserve el contenido que cumpla los criterios de búsqueda. Puede especificar palabras clave, propiedades de mensaje o propiedades de documento, como nombres de archivo. También puede usar consultas más complejas que usen un operador booleano, como **and**, **or**o **Not**. Si deja vacío el cuadro palabra clave, todo el contenido ubicado en las ubicaciones de contenido especificadas se colocará en retención.
    
    b. Haga ![clic en](media/ITPro-EAC-AddIcon.gif) agregar icono **Agregar condiciones** para agregar una o más condiciones para restringir la consulta de búsqueda para la suspensión. Cada condición agrega una cláusula a la consulta de búsqueda de KQL que se crea y se ejecuta cuando se crea la suspensión. Por ejemplo, puede especificar un intervalo de fechas para que los documentos de correo electrónico o de sitio creados en el intervalo de fechas se coloquen en suspensión. Una condición está conectada lógicamente a la consulta de palabras clave (que se especifica en el cuadro palabra clave) por el operador **and** . Esto significa que los elementos deben cumplir con la consulta de palabras clave y la condición que se va a poner en retención.

    Para obtener más información acerca de la creación de una consulta de búsqueda y el uso de condiciones, consulte [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).
    
11. Después de configurar una retención basada en consultas, haga clic en **siguiente**.
    
12. Revise la configuración y, a continuación, haga clic en **crear esta suspensión**.
    
### <a name="hold-statistics"></a>Almacenar estadísticas

Después de un rato, se muestra información sobre la nueva retención en el panel de detalles **** de la página suspensiones para la suspensión seleccionada. Esta información incluye el número de buzones de correo y sitios en espera y estadísticas sobre el contenido que se ha puesto en suspensión, como el número total y el tamaño de los elementos que se encuentran en suspensión y la última vez que se calcularon las estadísticas de retención. Estas estadísticas de retención ayudan a identificar cuánto contenido está relacionado con el caso de exhibición de documentos electrónicos. 
  
![Almacenar estadísticas](media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
Tenga en cuenta lo siguiente en cuanto a la retención de estadísticas:
  
- El número total de elementos en espera indica el número de elementos de todos los orígenes de contenido que se encuentran en retención. Si ha creado una suspensión basada en consulta, esta estadística indica el número de elementos que coinciden con la consulta.
    
- El número de elementos en espera también incluye los elementos sin indexar encontrados en las ubicaciones de contenido. Tenga en cuenta que si crea una suspensión basada en consulta, todos los elementos sin indexar en las ubicaciones de contenido se colocan en retención. Esto incluye los elementos sin indexar que no coinciden con los criterios de búsqueda de una retención basada en consultas y los elementos sin indexar que podrían estar fuera de una condición de intervalo de fechas. Esto es diferente a lo que sucede cuando se ejecuta una búsqueda de contenido, en la que los elementos no indexados que no coinciden con la consulta de búsqueda o se excluyen por una condición de intervalo de fechas no se incluyen en los resultados de la búsqueda. Para obtener más información acerca de los elementos sin indexar, vea [elementos parcialmente indizados en la búsqueda de contenido en Office 365](partially-indexed-items-in-content-search.md).
    
- Puede obtener las estadísticas de retención más recientes haciendo clic en **actualizar estadísticas** para volver a ejecutar una estimación de búsqueda que calcula el número actual de elementos en espera. Si es necesario, ****![haga clic en](media/O365-MDM-Policy-RefreshIcon.gif) actualizar icono de actualización en la barra de herramientas para actualizar las estadísticas de retención en el panel de detalles. 
    
- Es normal que el número de elementos que se retengan se incremente con el transcurso del tiempo porque los usuarios cuyo buzón o sitio está en espera suelen enviar o recibir nuevos mensajes de correo electrónico y crear nuevos documentos de SharePoint y OneDrive para la empresa.
    
> [!NOTE]
> Si un sitio de SharePoint o una cuenta de OneDrive se mueven a otra región en un entorno multigeográfico, las estadísticas de ese sitio no se incluirán en las estadísticas de retención. Sin embargo, el contenido del sitio seguirá en espera. Además, si un sitio se mueve a otra región, la dirección URL que se muestra en la retención no se actualizará. Tendrá que editar la retención y actualizar la dirección URL. 
  
## <a name="step-5-create-and-run-a-content-search-associated-with-a-case"></a>Paso 5: crear y ejecutar una búsqueda de contenido asociada a un caso

Una vez que se crea un caso de exhibición de documentos electrónicos y se colocan en suspensión los custodios relacionados con el caso, puede crear y ejecutar una o más búsquedas de contenido asociadas con el caso. Las búsquedas de contenido asociadas a un caso no se **** enumeran en la página &amp; de búsqueda del centro de seguridad y cumplimiento. Esto significa que solo se puede tener acceso a las búsquedas de contenido asociadas a un caso por parte de los miembros que también son miembros del grupo de roles eDiscovery Manager. 
  
1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Haga clic en **abrir** junto al caso en el que desea crear una búsqueda de contenido. 
    
3. En la página **principal** del caso, haga clic en la ficha **búsqueda** . 
    
    ![Ficha de búsqueda](media/2e15fe32-1a2e-4588-ad0b-5d96f77cece9.png)
  
4. En la página **Buscar** , haga ![clic en](media/ITPro-EAC-AddIcon.gif) agregar icono **nueva búsqueda**. 
    
5. En la página **Nueva búsqueda**, puede agregar palabras clave y condiciones para crear la consulta de búsqueda. 
    
    ![Nueva búsqueda](media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
6. Puede especificar palabras clave, propiedades del mensaje, como las fechas de envío y recepción, o propiedades del documento, como nombres de archivo o la fecha en que se modificó por última vez un documento. Puede usar consultas más complejas que usen un operador booleano, como **and**, **or**, **Not**, **Near**o **ONEAR**. También puede buscar información confidencial (por ejemplo, los números de la seguridad social) en documentos o buscar documentos que se han compartido de forma externa. Si deja vacío el cuadro palabra clave, todo el contenido ubicado en las ubicaciones de contenido especificadas se incluirá en los resultados de la búsqueda. 
    
7. Puede hacer clic en la casilla **Mostrar lista de palabras clave** y escribir una palabra clave en cada fila. Si hace esto, las palabras clave de cada fila están conectadas mediante el operador **or** en la consulta de búsqueda que se crea. 
    
    ![Lista de palabras clave](media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    ¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestren cuántos elementos coinciden con cada palabra clave. Esto puede ayudarle a identificar rápidamente qué palabras clave son más (y menos) efectivas. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para obtener más información acerca de las estadísticas de búsqueda, consulte [View keyword Statistics for Content Search Results](view-keyword-statistics-for-content-search.md).
    
    Para obtener más información acerca del uso de la lista de palabras clave, vea [Building a Search Query](content-search.md#building-a-search-query).
    
8. En **condiciones**, agregue condiciones a una consulta de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda de KQL que se crea y se ejecuta cuando se inicia la búsqueda. Una condición está conectada lógicamente a la consulta de palabras clave (que se especifica en el cuadro palabra clave) por el operador **and** . Esto significa que los elementos deben cumplir con la consulta de palabras clave y la condición que se va a incluir en los resultados. Este es el modo en que las condiciones ayudan a restringir los resultados. 
    
    Para obtener más información sobre cómo crear una consulta de búsqueda y el uso de las condiciones, consulte [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).
    
9. En **ubicaciones: ubicaciones en espera**, elija las ubicaciones de contenido en las que desea realizar la búsqueda. Puede buscar buzones de correo, sitios y carpetas públicas en la misma búsqueda.
    
    ![Ubicaciones, ubicaciones en suspensión](media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - **Todas las ubicaciones** : Seleccione esta opción para buscar en todas las ubicaciones de contenido de la organización. Si selecciona esta opción, puede elegir buscar todos los buzones de Exchange (que incluye los buzones de todos los grupos de Office 365 y Microsoft Teams), todos los sitios de SharePoint y OneDrive para la empresa (que incluye los sitios de todos los grupos de Office 365 y Microsoft Teams) y todas las carpetas públicas.
    
    - **Todas las ubicaciones en suspensión** : Seleccione esta opción para buscar en todas las ubicaciones de contenido que se encuentran en espera en el caso. Si el caso contiene varias suspensiones, las ubicaciones de contenido de todas las suspensiones se buscarán cuando seleccione esta opción. Además, si se colocó una ubicación de contenido en una suspensión basada en consulta, solo se buscará en los elementos que están en espera cuando ejecute la búsqueda de contenido que está creando en este paso. Por ejemplo, si un usuario se colocó en la suspensión de casos basada en consultas y conserva los elementos que se enviaron o crearon antes de una fecha específica, solo se buscarían en esos elementos usando los criterios de búsqueda de la búsqueda de contenido. Esto se logra conectando la consulta de suspensión de casos y la consulta de búsqueda de contenido por un operador **and** . Consulte la sección [más información](ediscovery-cases.md#moreinfo_1) al final de este artículo para obtener más información sobre cómo buscar contenido de casos. 
    
    - **Ubicaciones específicas** : Seleccione esta opción para seleccionar los buzones y sitios en los que desea buscar. Cuando seleccione esta opción y haga clic en **modificar**, aparecerá una lista de ubicaciones. Puede elegir buscar en cualquiera o todos los usuarios, grupos, equipos o ubicaciones de sitio.
    
      ![Seleccionar ubicaciones específicas](media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
      También puede optar por buscar en todas las carpetas públicas de la organización, pero si selecciona esta opción y busca en cualquier ubicación de contenido que esté en espera, cualquier consulta de una suspensión de casos basada en consultas no se aplicará a la consulta de búsqueda. En otras palabras, se busca en todo el contenido de una ubicación, no solo en el contenido que se conserva mediante una retención de casos basada en la consulta.
    
      Puede quitar las ubicaciones de contenido de casos rellenados previamente o agregar otros nuevos. Si elige esta opción, también tendrá flexibilidad para buscar en todas las ubicaciones de contenido de un servicio específico (como buscar en todos los buzones de Exchange) o puede buscar ubicaciones de contenido específicas para un servicio. También puede elegir si desea buscar o no las carpetas públicas de la organización.
    
      Tenga en cuenta lo siguiente al agregar ubicaciones de contenido a la búsqueda:
    
      - Al hacer clic en **elegir usuarios, grupos o equipos** para especificar los buzones en los que se va a buscar, el selector de buzones que se muestra está vacío. Esto se debe a su diseño para mejorar el rendimiento. Para agregar destinatarios a esta lista, haga clic en **elegir usuarios, grupos o equipos**, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda, active la casilla de verificación situada junto al nombre y, a continuación, haga clic en **elegir**. 
    
      - Puede Agregar buzones inactivos, Office 365 grupos, Microsoft Teams y grupos de distribución a la lista de buzones para buscar. No se admiten los grupos de distribución dinámicos. Si agrega grupos de Office 365 o Microsoft Teams, se busca el buzón de grupo o de equipo; no se busca en los buzones de los miembros del grupo.
    
      - Para agregar sitios, haga clic en **elegir sitios**, haga clic en **elegir sitios** de nuevo y, a continuación, escriba la dirección URL de cada sitio que desee buscar. También puede Agregar la dirección URL del sitio de SharePoint para los grupos de Office 365 y Microsoft Teams. 
    
10. Una vez seleccionadas las ubicaciones de contenido para buscar, haga clic en **listo** y, a continuación, en **Guardar**.
    
11. En la página **nueva búsqueda** , haga clic en **Guardar** y, a continuación, escriba un nombre para la búsqueda. Las búsquedas de contenido asociadas a un caso deben tener nombres únicos en la organización de Office 365. 
    
12. Haga clic en **Guardar &amp; ejecución** para guardar la configuración de búsqueda. 
    
13. Escriba un nombre único para la búsqueda y haga clic en **Guardar** para iniciar la búsqueda. 
    
    Se inicia la búsqueda. Después de un rato, se muestra una estimación de los resultados de la búsqueda en el panel de detalles. La estimación incluye el tamaño total y el número de elementos que coinciden con los criterios de búsqueda. La estimación de la búsqueda también incluye el número de elementos sin indexar en las ubicaciones de contenido en las que se realizó la búsqueda. El número de elementos sin indexar que no cumplen los criterios de búsqueda se incluirá en las estadísticas de búsqueda que se muestran en el panel de detalles. Si un elemento sin indizar coincide con la consulta de búsqueda (porque otras propiedades de mensaje o documento cumplen los criterios de búsqueda), no se incluirá en el número estimado de elementos sin indexar. Si un elemento sin indexar se excluye por los criterios de búsqueda, tampoco se incluirá en la estimación de los elementos sin indexar.
    
  Una vez completada la búsqueda, puede obtener una vista previa de los resultados de la búsqueda. Si es necesario, ****![haga clic en](media/O365-MDM-Policy-RefreshIcon.gif) actualizar icono de actualización para actualizar la información en el panel de detalles. 
    
## <a name="step-6-export-the-results-of-a-content-search-associated-with-a-case"></a>Paso 6: exportar los resultados de una búsqueda de contenido asociada a un caso

Una vez ejecutada correctamente la búsqueda, puede exportar los resultados de la búsqueda. Al exportar los resultados de la búsqueda, los elementos del buzón se descargan en archivos PST o como mensajes individuales. Al exportar contenido de sitios de SharePoint y OneDrive para la empresa, se exportan copias de documentos nativos de Office y otros documentos. También se exporta un archivo de manifiesto (en formato XML) que contiene información sobre todos los resultados de búsqueda.
  
Puede exportar los resultados de una [exportación con los resultados de una sola búsqueda asociada a un caso](ediscovery-cases.md#singlesearch_1) o puede exportar los resultados de la [exportación de los resultados de varias búsquedas asociadas a un caso](ediscovery-cases.md#multiplesearches_1).
  
### <a name="export-the-results-of-a-single-search-associated-with-a-case"></a>Exportar los resultados de una sola búsqueda asociada a un caso

1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Haga clic en **abrir** junto al caso en el que desea exportar la búsqueda. 
    
3. En la página **principal** del caso, haga clic en **Buscar**.
    
4. En la lista de búsquedas del caso, haga clic en la búsqueda de la que desea exportar resultados de búsqueda, ![haga clic en exportar](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) resultados de búsqueda **más**y, a continuación, seleccione **exportar resultados** en la lista desplegable. 
    
    Se mostrará la página resultados de la **exportación** . 
    
    ![Página de resultados de la exportación](media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    El flujo de trabajo para exportar los resultados de una búsqueda de contenido asociada a un caso es el mismo que exportar los resultados de búsqueda para una búsqueda en la página **búsqueda de contenido** . Para obtener instrucciones paso a paso, consulte [exportar resultados de búsqueda de contenido desde el centro de &amp; seguridad y cumplimiento de Office 365](export-search-results.md).
    
    > [!NOTE]
    > Al exportar los resultados de búsqueda, tiene la opción de habilitar la desduplicación para que solo se exporte una copia de un mensaje de correo electrónico, aunque se hayan encontrado varias instancias del mismo mensaje en los buzones en los que se realizó la búsqueda. Para obtener más información acerca de la desduplicación y cómo se identifican los elementos duplicados, vea desduplicación [en resultados de la búsqueda de exhibición](de-duplication-in-ediscovery-search-results.md)de documentos electrónicos. 
  
5. Haga clic en la pestaña **exportar** para mostrar la lista de trabajos de exportación que existen en ese caso. 
    
    ![Ficha exportar](media/1b84c45e-4ec9-4ecd-9e07-eaf8fc4cc307.png)
  
    Es posible que deba hacer ****![clic en actualizar](media/O365-MDM-Policy-RefreshIcon.gif) icono de actualización para actualizar la lista de trabajos de exportación de modo que muestre el trabajo de exportación que acaba de crear. Tenga en cuenta que los trabajos de exportación tienen el mismo nombre que la búsqueda de contenido correspondiente con **_Export** anexado al final del nombre de búsqueda. 
    
6. Haga clic en el trabajo de exportación que acaba de crear para mostrar la información de estado en el panel de detalles. Esta información incluye el porcentaje de elementos que se han transferido a un área de almacenamiento de Azure en la nube de Microsoft.
    
    Una vez transferidos todos los elementos, haga clic en **Descargar resultados** para descargar los resultados de la búsqueda en el equipo local. Para obtener más información, consulte el paso 2 de [exportar resultados de búsqueda de contenido desde &amp; el centro de seguridad y cumplimiento de Office 365](export-search-results.md)
    
### <a name="export-the-results-of-multiple-searches-associated-with-a-case"></a>Exportar los resultados de varias búsquedas asociadas a un caso

Como alternativa a la exportación de los resultados de una sola búsqueda de contenido asociada a un caso, puede exportar los resultados de varias búsquedas desde el mismo caso en una sola exportación. Exportar los resultados de varias búsquedas es más rápido y sencillo que exportar los resultados una búsqueda cada vez.
  
> [!NOTE]
> No puede exportar los resultados de varias búsquedas si una de esas búsquedas se configuró para buscar en todo el contenido de caso. exportar solo los resultados de varias búsquedas de búsquedas asociadas a un caso de exhibición de documentos electrónicos. No puede exportar los resultados de varias búsquedas que aparecen en la página de **búsqueda** de contenido &amp; en el centro de seguridad y cumplimiento. 
  
1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Haga clic en **abrir** junto al caso desde el que desea exportar los resultados de la búsqueda. 
    
3. En la página **principal** del caso, haga clic en **Buscar**.
    
4. En la lista de búsquedas del caso, seleccione dos o más búsquedas de las que desee exportar resultados de la búsqueda.
    
    > [!NOTE]
    > Para seleccionar varias búsquedas, mantenga presionada la tecla Ctrl mientras hace clic en cada búsqueda. O bien, puede seleccionar varias búsquedas adyacentes si hace clic en la primera búsqueda, mantiene presionada la tecla Mayús y, a continuación, hace clic en la última búsqueda. 
  
5. Después de seleccionar las búsquedas, aparece la página **acciones en masa** . 
    
    ![En la página acciones en masa, haga clic en exportar resultados](media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
    
6. Haga ![clic en exportar](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **resultados**de búsqueda.

7. En la página **exportar resultados** , asigne un nombre único a la exportación, seleccione Opciones de resultados y elija cómo se exportará el contenido. Haga clic en **exportar**.
    
    El flujo de trabajo para exportar los resultados de varias búsquedas de contenido asociadas a un caso es el mismo que exportar los resultados de la búsqueda para una sola búsqueda. Para obtener instrucciones paso a paso, consulte [exportar resultados de búsqueda de contenido desde el centro de &amp; seguridad y cumplimiento de Office 365](export-search-results.md).
    
    > [!NOTE]
    > Al exportar los resultados de búsqueda de varias búsquedas asociadas a un caso, también tiene la opción de habilitar la desduplicación para que solo se exporte una copia de un mensaje de correo electrónico, aunque se hayan encontrado varias instancias del mismo mensaje en el buzones de correo que se han buscado en una o varias de las búsquedas. Para obtener más información acerca de la desduplicación y cómo se identifican los elementos duplicados, vea desduplicación [en resultados de la búsqueda de exhibición](de-duplication-in-ediscovery-search-results.md)de documentos electrónicos. 
  
8. Después de iniciar la exportación, haga clic en la pestaña **exportar** para mostrar la lista de trabajos de exportación para ese caso. 
    
    ![Ficha exportar, varias búsquedas](media/b9505e1b-559f-4a8c-96b3-a3f734753926.png)
  
    Puede que tenga que hacer **** ![clic en actualizar](media/O365-MDM-Policy-RefreshIcon.gif) icono para actualizar la lista de trabajos de exportación para mostrar el trabajo de exportación que acaba de crear. Tenga en cuenta que las búsquedas incluidas en el trabajo de exportación se muestran en la columna **búsquedas** . 
    
8. Haga clic en el trabajo de exportación que acaba de crear para mostrar la información de estado en el panel de detalles. Esta información incluye el porcentaje de elementos que se han transferido a un área de almacenamiento de Azure en la nube de Microsoft.
    
9. Una vez transferidos todos los elementos, haga clic en **Descargar resultados** para descargar los resultados de la búsqueda en el equipo local. Para obtener más información, consulte el paso 2 en [exportar resultados de la búsqueda del &amp; centro de seguridad y cumplimiento de Office 365](export-search-results.md)
    
#### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>Más información sobre cómo exportar los resultados de varias búsquedas

- Cuando se exportan los resultados de varias búsquedas, las consultas de búsqueda de todas las búsquedas se combinan mediante operadores **or** y, a continuación, se inicia la búsqueda combinada. Los resultados estimados de la búsqueda combinada se muestran en el panel de detalles del trabajo de exportación seleccionado. A continuación, los resultados de la búsqueda se transfieren al área de almacenamiento de Azure en la nube de Microsoft. El estado de la transferencia también se muestra en el panel de detalles. Como se mencionó anteriormente, una vez que se han transferido todos los resultados de búsqueda, puede descargarlos en el equipo local. 
    
- El número máximo de palabras clave de las consultas de búsqueda para todas las búsquedas que desea exportar es de 500. (este es el mismo límite para una sola búsqueda de contenido). Esto se debe a que el trabajo de exportación combina todas las consultas de búsqueda mediante el operador **or** . Si supera este límite, se devolverá un error. En este caso, tendrá que exportar los resultados de menos búsquedas o simplificar las consultas de búsqueda de las búsquedas que desea exportar. 
    
- Los resultados de la búsqueda que se exportan están organizados por el origen de contenido en el que se encontró el elemento. Esto significa que un origen de contenido en los resultados de la exportación puede tener elementos devueltos por diferentes búsquedas. Por ejemplo, si decide exportar los mensajes de correo electrónico de un archivo PST para cada buzón, el archivo PST podría tener resultados de varias búsquedas.
    
- Si más de una de las búsquedas que se exportan devuelven el mismo documento o elemento de correo electrónico de la misma ubicación de contenido, solo se exportará una copia del elemento.
    
- No puede editar una exportación para varias búsquedas después de crearla. Por ejemplo, no puede agregar ni quitar búsquedas de la exportación. Tendrá que crear un nuevo trabajo de exportación para cambiar los resultados de la búsqueda que se van a exportar. Después de crear un trabajo de exportación, solo puede descargar los resultados en un equipo, reiniciar la exportación o eliminar el trabajo de exportación.
    
- Si reinicia la exportación, los cambios en las consultas de las búsquedas que componen el trabajo de exportación no afectarán a los resultados de la búsqueda que se recuperarán. Cuando se reinicia una exportación, se ejecutará de nuevo el mismo trabajo de consulta de búsqueda combinado que se ejecutó al crear el trabajo de exportación.
    
- Si reinicia una exportación desde la página **exportaciones** en un caso de exhibición de documentos electrónicos, los resultados de la búsqueda que se transfieren al área de almacenamiento de Azure sobrescribirán los resultados anteriores; los resultados anteriores que haya transferido no estarán disponibles para su descarga. 
    
- No está disponible la preparación de los resultados de varias búsquedas para el análisis en la exhibición avanzada de documentos electrónicos. Solo puede preparar los resultados de una sola búsqueda para el análisis en la exhibición avanzada de documentos electrónicos.

## <a name="step-7-prepare-search-results-for-advanced-ediscovery"></a>Paso 7: preparar los resultados de búsqueda para la exhibición avanzada de documentos electrónicos

Si su organización tiene una suscripción de Office 365 E5, puede preparar los resultados de las búsquedas de contenido asociadas a un caso para el análisis en la exhibición avanzada de documentos electrónicos. Después de preparar los resultados de la búsqueda, puede ir a la exhibición avanzada de documentos electrónicos (vea [el paso 8: ir al caso en la exhibición avanzada](#step-8-go-to-the-case-in-advanced-ediscovery)de documentos electrónicos) y procesar los datos de los resultados de búsqueda para realizar más análisis en la exhibición avanzada de documentos electrónicos.
  
Al preparar los resultados de búsqueda para la exhibición avanzada de documentos electrónicos, la funcionalidad de reconocimiento óptico de caracteres (OCR) extrae automáticamente el texto de las imágenes. OCR es compatible con archivos sueltos, datos adjuntos de correo electrónico e imágenes incrustadas. Esto le permite aplicar las capacidades de análisis de texto de eDiscovery avanzado (casi duplicados, subprocesamiento de correo electrónico, temas y codificación de predicción) a cualquier texto de los archivos de imagen.
  
> [!NOTE]
> Para analizar los datos de un usuario con la exhibición avanzada de documentos electrónicos, el usuario (el custodio de los datos) debe tener asignada una licencia de Office 365 E5. Como alternativa, se puede asignar una licencia independiente de eDiscovery avanzado a los usuarios con una licencia de Office 365 E1 o E3. Los administradores y los responsables de cumplimiento que se asignan a los casos y usan la exhibición avanzada de documentos electrónicos para analizar los datos no necesitan una licencia E5. 
  
1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Haga clic en **abrir** junto al caso en el que desea preparar los resultados de búsqueda para el análisis en la exhibición avanzada de documentos electrónicos. 
    
3. En la página **principal** del caso, haga clic en **Buscar**y, a continuación, seleccione la búsqueda.
    
4. En el panel de detalles, ![haga clic en exportar](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) resultados de búsqueda **más**y, a continuación, haga clic en **preparar exhibición avanzada de**documentos electrónicos.
    
    ![Preparar los resultados para la exhibición avanzada de documentos electrónicos](media/b6548ff0-a6e9-42b1-9ae4-5c15146f5690.png)
  
5. En la página **preparar para la exhibición avanzada** de documentos electrónicos, elija preparar una de las siguientes opciones: 
    
    - Todos los elementos, excluidos los que tienen formato no reconocido, están cifrados o no se indizaron por otros motivos.
    
    - Todos los elementos, incluidos los que tienen un formato no reconocido, están cifrados o no se indizaron por otros motivos.
    
    - Solo los elementos que tienen un formato irreconocible, están cifrados o no se indizaron por otros motivos.
    
6. Opcional Haga clic en la casilla de verificación **incluir versiones de los archivos de SharePoint** . 
    
7. Haga clic en **Preparar**.
    
    Los resultados de la búsqueda están preparados para el análisis con eDiscovery avanzado.
    
8. Haga clic en **cerrar** para cerrar el panel de detalles. 
    
## <a name="step-8-go-to-the-case-in-advanced-ediscovery"></a>Paso 8: ir al caso en la exhibición avanzada de documentos electrónicos

Después de crear un caso en el centro &amp; de seguridad y cumplimiento, puede ir al mismo caso en la exhibición avanzada de documentos electrónicos.
  
Para ir a un caso en eDiscovery avanzado:
  
1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Haga clic en **abrir** junto al caso al que desea ir en la exhibición avanzada de documentos electrónicos. 
    
3. En la página **principal** del caso, haga clic en **cambiar a exhibición avanzada**de documentos electrónicos.
    
    ![Seleccionar cambiar a eDiscovery avanzado](media/d7e31558-e79c-4782-b841-2b735568a576.png)
  
    Se muestra la barra de progreso **conectarse a la exhibición avanzada de** documentos electrónicos. Cuando está conectado a la exhibición avanzada de documentos electrónicos, se muestra una lista de contenedores en la página. 
    
    ![Barra de progreso de eDiscorvery avanzada](media/4a84273d-765b-44b8-9006-c20e810ea393.png)
  
    Estos contenedores representan los resultados de búsqueda que ha preparado para el análisis en la exhibición avanzada de documentos electrónicos en el paso 7. Tenga en cuenta que el nombre del contenedor tiene el mismo nombre que la búsqueda de contenido en el caso &amp; del centro de seguridad y cumplimiento. Los contenedores de la lista son los que ha preparado. Si un usuario diferente ha preparado los resultados de búsqueda para la exhibición avanzada de documentos electrónicos, los contenedores correspondientes no se incluirán en la lista.
    
4. Para cargar los datos de los resultados de búsqueda de un contenedor en el caso de la exhibición avanzada de documentos electrónicos, seleccione un contenedor y haga clic en **proceso**.
    
    Para obtener información sobre cómo procesar contenedores, consulte [ejecutar el módulo de proceso y cargar datos en la exhibición avanzada de documentos electrónicos de Office 365](run-the-process-module-and-load-data-in-advanced-ediscovery.md).
    
> [!TIP]
> Haga clic en **cambiar a eDiscovery** para volver al mismo caso en el centro &amp; de seguridad y cumplimiento. 
  
## <a name="optional-step-9-close-a-case"></a>Opcional Paso 9: cerrar un caso

Cuando se completa el caso legal o la investigación admitidos por un caso de exhibición de documentos electrónicos, puede cerrar el caso. Esto es lo que sucede cuando se cierra un caso:
  
- Si el caso contiene ubicaciones de contenido en suspensión, dichas suspensiones se desactivarán. Esto puede dar lugar a que el usuario o un proceso automatizado eliminen o purguen permanentemente el contenido, como una directiva de eliminación.
    
- Si se cierra un caso, sólo se desactivan las suspensiones asociadas a ese caso. Si hay otras suspensiones en una ubicación de contenido (como una retención por juicio. una directiva de conservación o una retención de un caso de exhibición de documentos electrónicos distinto), estas se conservarán.
    
- El caso todavía aparece en la página exhibición de documentos electrónicos del &amp; centro de seguridad y cumplimiento. Se conservan los detalles, las suspensiones, las búsquedas y los miembros de un caso cerrado.
    
- Puede editar un caso después de cerrarlo. Por ejemplo, puede Agregar o quitar miembros, crear búsquedas, exportar resultados de búsqueda y preparar los resultados de búsqueda para el análisis en la exhibición avanzada de documentos electrónicos. La principal diferencia entre los casos activos y cerrados es que las suspensiones se desactivan cuando se cierra un caso.
    
Para cerrar un caso:
  
1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Haga clic en el nombre del caso que desea cerrar.
    
    Se muestra la página flotante **administrar este caso** . 
    
3. En **administrar estado de caso**, ![haga clic en quitar](media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) el **cierre**de mayúsculas del botón de inspección.
    
    Se muestra una advertencia que indica que las suspensiones asociadas con el caso se desactivarán.
    
4. Haga clic en **sí** para cerrar el caso. 
    
    El estado de la página desplegable **administrar este caso** se cambia de **activo** a **cierre**.
    
5. Cierre la página **administrar este caso** . 
    
6. En la **Página exhibición** de documentos ![electrónicos,](media/O365-MDM-Policy-RefreshIcon.gif) haga clic en actualizar icono **Actualizar** para actualizar el estado del caso cerrado. El proceso de cierre puede tardar hasta 60 minutos en completarse. 
    
    Una vez finalizado el proceso, el estado del caso cambia a **cerrado** en la página de **exhibición** de documentos electrónicos. Vuelva a hacer clic en el nombre del caso para mostrar la página flotante **administrar este caso** , que contiene información sobre cuándo se cerró el caso y quién lo cerró. 
     
## <a name="optional-step-10-re-open-a-closed-case"></a>Opcional Paso 10: volver a abrir un caso cerrado

Cuando vuelva a abrir un caso, las suspensiones que estuvieran en su ubicación cuando se cerró el caso no se restituyerán automáticamente. Después de volver a abrir el caso, tendrá que ir a la página de **retención** y activar las suspensiones anteriores. Para activar una retención, selecciónela y haga clic en **Activar** en el panel de detalles. 
  
1. En el Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** \> **eDiscovery** para mostrar la lista de casos en su organización. 
    
2. Haga clic en el nombre del caso que desea volver a abrir.
    
    Se muestra la página flotante **administrar este caso** . 
    
3. En **administrar estado de caso**, haga clic en **volver a abrir el caso**.
    
    Se muestra una advertencia que indica que las suspensiones asociadas con el caso cuando se cerró no se activarán automáticamente.
    
4. Haga clic en **sí** para volver a abrir el caso. 
    
    El estado de la página desplegable **administrar este caso** se ha cambiado de **cerrado** a **activo**.
    
5. Cierre la página **administrar este caso** . 
    
6. En la **Página exhibición** de documentos ![electrónicos,](media/O365-MDM-Policy-RefreshIcon.gif) haga clic en actualizar icono **Actualizar** para actualizar el estado del caso reabierto. El proceso de reapertura puede tardar hasta 60 minutos en completarse. 
    
    Una vez finalizado el proceso, el estado del caso cambia a **activo** en la página de **exhibición** de documentos electrónicos. 
  
## <a name="more-information"></a>Más información

- **¿Hay algún límite para casos de eDiscovery o suspensiones asociados a un caso de exhibición de** documentos electrónicos? En la siguiente tabla se enumeran los límites de casos de eDiscovery y suspensiones de casos.
    
  |**Descripción del límite**|**Límite**|
  |:-----|:-----|
  |Número máximo de casos para una organización  <br/> |Sin límite  <br/> |
  |Número máximo de retenciones de casos para una organización  <br/> |10,000  <br/> |
  |Número máximo de buzones en una sola suspensión de casos  <br/> |1,000  <br/> |
  |Número máximo de sitios de SharePoint y OneDrive para la empresa en una sola suspensión de mayúsculas y minúsculas  <br/> |100  <br/> |
   
- **¿Qué ocurre con los casos creados en la página Administración de casos en EDiscovery avanzado?** Puede obtener acceso a una lista de casos de eDiscovery avanzados más antiguos si hace clic en el vínculo **** que se encuentra en la &amp; parte inferior de la página eDiscovery en el centro de seguridad y cumplimiento. Sin embargo, para realizar cualquier trabajo en un caso anterior, debe ponerse en contacto con el soporte técnico de Office 365 y solicitar que se mueva el caso a un nuevo &amp; caso de exhibición de documentos electrónicos en el centro de seguridad y cumplimiento. 
    
- **¿Por qué crear un administrador de exhibición** de documentos electrónicos? Como se ha explicado anteriormente, un administrador de eDiscovery es miembro del grupo de roles eDiscovery Manager que puede ver y tener acceso a todos los casos de eDiscovery de su organización. Esta capacidad de tener acceso a todos los casos de eDiscovery tiene dos propósitos importantes:
    
  - Si una persona que es el único miembro de un caso de exhibición de documentos electrónicos deja a su organización, nadie (incluidos los miembros del grupo de roles de administración de la organización u otro miembro del grupo de roles de eDiscovery Manager) puede tener acceso a ese caso de eDiscovery porque no son miembros. de un caso. En esta situación, no habría ninguna forma de obtener acceso a los datos en el caso. Pero como un administrador de eDiscovery puede tener acceso a todos los casos de eDiscovery de la organización, pueden ver el &amp; caso en el centro de seguridad y cumplimiento y agregarse a sí mismos o a otro administrador de eDiscovery como miembro del caso.
    
  - Dado que un administrador de eDiscovery puede ver y tener acceso a todos los casos de eDiscovery, puede auditar y supervisar todos los casos y las búsquedas de contenido asociadas. Esto puede ayudar a evitar cualquier uso incorrecto de búsquedas de contenido o casos de exhibición de documentos electrónicos. Y, dado que los administradores de eDiscovery pueden tener acceso a información potencialmente confidencial en los resultados de una búsqueda de contenido, debe limitar el número de usuarios que son administradores de eDiscovery.
    
    Por último, como se explicó anteriormente, los administradores de eDiscovery &amp; en el centro de seguridad y cumplimiento se agregan automáticamente como administradores en eDiscovery avanzado. Eso significa que una persona que es un administrador de eDiscovery puede realizar tareas administrativas en eDiscovery avanzado, como configurar usuarios, crear casos y agregar datos a los casos.
    
- **¿Cuáles son los requisitos de licencia para poner las ubicaciones de contenido en retención?** En general, las organizaciones requieren una suscripción a Office 365 E3 o una versión superior para poner las ubicaciones de contenido en suspensión. Para poner buzones en retención, se necesita una licencia de Exchange Online (plan 2) para el buzón que desea poner en retención.
    
- **¿Qué más debe saber sobre cómo buscar en todo el contenido del caso en el paso 5?** Como se ha explicado anteriormente, puede buscar en las ubicaciones de contenido que se han puesto en espera en el caso. Cuando lo haga, solo se buscará el contenido que coincida con los criterios de retención. Si no hay ningún criterio de retención, se busca en todo el contenido. Si el contenido se encuentra en una suspensión basada en consulta, solo se devuelve con los resultados de la búsqueda el contenido que coincide con los dos criterios de retención (de la retención realizada en el paso 4) y los criterios de búsqueda (de la búsqueda en el paso 5).
    
    Estas son algunas otras cosas que debe tener en cuenta al buscar todo el contenido del caso:
    
  - Si una ubicación de contenido forma parte de varias suspensiones en el mismo caso, las consultas de retención se combinan mediante un operador **or** cuando busca en esa ubicación de contenido con la opción de contenido All Case. De forma similar, si una ubicación de contenido forma parte de dos suspensiones diferentes, donde una se basa en la consulta y la otra es una retención infinita (donde todo el contenido se coloca en retención), se buscará todo el contenido debido a la suspensión infinita. 
    
  - Si una búsqueda de contenido es para un caso y se ha configurado para buscar en todo el contenido de caso y, a continuación, se cambia una retención (agregando o quitando una ubicación de contenido o cambiando la consulta de retención), la configuración de búsqueda se actualizará con dichos cambios. Sin embargo, tiene que volver a ejecutar la búsqueda una vez cambiada la retención para actualizar los resultados de la búsqueda.
    
  - Si se colocan varios casos en una ubicación de contenido en un caso de exhibición de documentos electrónicos y selecciona buscar en todo el contenido de caso, el número máximo de palabras clave para esa consulta de búsqueda es de 500. Esto se debe a que la búsqueda de contenido combina todas las retenciones basadas en consultas mediante el operador **or** . Si hay más de 500 palabras clave en las consultas de retención combinada y la consulta de búsqueda de contenido, se buscará en todo el contenido del buzón, no solo en ese contenido que coincida con el de los casos basados en consultas. 
    
  - Si una suspensión de casos tiene un estado de **activación**, puede seguir buscando en las ubicaciones de contenido de caso mientras se activa la suspensión.
    
  - Como se mencionó anteriormente, si una búsqueda se configura para buscar en todo el contenido del caso, no podrá incluir esa búsqueda si desea exportar los resultados de varias búsquedas. Si una búsqueda está configurada para realizar búsquedas en todo el contenido del caso, tendrá que exportar los resultados de esa búsqueda única.
    
- **Si un buzón, un sitio de SharePoint o una cuenta de OneDrive que se encuentra en suspensión se mueven a otra región en un entorno multigeográfico, ¿se seguirá aplicando la retención?** En todos los casos, el contenido de un buzón de correo, un sitio o una cuenta de OneDrive se conservará de todos modos. Sin embargo, las estadísticas de retención ya no incluirán elementos de una ubicación de contenido que se haya movido a otra región. Para incluir estadísticas de retención para una ubicación de contenido que se ha movido, tendrá que editar la retención y actualizar la dirección URL (o la dirección SMTP de un buzón) para que la ubicación del contenido vuelva a estar incluida en las estadísticas de retención. 
    
- **¿Qué ocurre al realizar una retención en grupos de Office 365 y Microsoft Teams?** Microsoft Teams se basa en grupos de Office 365. Por lo tanto, colocarlos en espera en un caso de exhibición de documentos electrónicos es muy similar. Tenga en cuenta lo siguiente cuando coloque los grupos de Office 365 y Microsoft Teams en espera. 
    
  - Para colocar contenido ubicado en Office 365 grupos y Microsoft Teams en espera, tiene que especificar el buzón de correo y el sitio de SharePoint que están asociados con un grupo o un equipo.
    
  - Ejecute el cmdlet **Get-UnifiedGroup** en Exchange Online para ver las propiedades de un grupo de Office 365 o un equipo de Microsoft. Esta es una buena forma de obtener la dirección URL del sitio que está asociada con un grupo de Office 365 o un equipo de Microsoft. Por ejemplo, el siguiente comando muestra las propiedades seleccionadas de un grupo de Office 365 llamado equipo de liderazgo Senior: 
    
     ```
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

     DisplayName            : Senior Leadership Team
     Alias                  : seniorleadershipteam
     PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
     SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroup** , debe tener asignado el rol destinatarios con permiso de vista en Exchange online o ser miembro de un grupo de roles que tenga asignado el rol destinatarios con permiso de vista. 
  
  - Cuando se realiza una búsqueda en el buzón de un usuario, no se buscará ningún grupo de Office 365 o equipo de Microsoft del que el usuario sea miembro. De forma similar, cuando se coloca un grupo de Office 365 o una retención en Microsoft Team, solo el buzón de grupo y el sitio de grupo se colocan en retención; los buzones y los sitios de OneDrive para la empresa de los miembros del grupo no se colocan en suspensión a menos que los agregue explícitamente a la suspensión. Por lo tanto, si necesita tener un grupo de Office 365 o un equipo de Microsoft en espera por motivos legales, considere la posibilidad de agregar los buzones y los sitios de OneDrive para la empresa a los integrantes de grupo y de equipo en la misma retención.
    
  - Para obtener una lista de los miembros de un grupo de Office 365 o de Microsoft Team, puede ver las propiedades de la página de **grupos principales \> ** en el centro de administración de Office 365. Como alternativa, puede ejecutar el siguiente comando en Exchange Online PowerShell: 
    
      ```
      Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
      ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroupLinks** , debe tener asignado el rol destinatarios con permiso de vista en Exchange online o ser miembro de un grupo de roles que tenga asignado el rol destinatarios con permiso de vista. 
  
  - Las conversaciones que forman parte de un canal de Microsoft Teams se almacenan en el buzón de correo asociado con el equipo de Microsoft. De forma similar, los archivos que los miembros del equipo comparten en un canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, tiene que poner el buzón de Microsoft Team y el sitio de SharePoint en espera para conservar conversaciones y archivos en un canal.
    
    Como alternativa, las conversaciones que forman parte de la lista de chats en Microsoft Teams se almacenan en el buzón de correo del usuario que participa en el chat. Y los archivos que un usuario comparte en conversaciones de chat se almacenan en el sitio de OneDrive para la empresa del usuario que comparte el archivo. Por lo tanto, tiene que poner los buzones de usuario individuales y los sitios de OneDrive para la empresa en espera para conservar conversaciones y archivos de la lista de chats. Por eso es una buena idea retener una retención de los buzones de los miembros de un equipo de Microsoft, además de colocar el buzón de equipo (y el sitio) en retención.
    
    > [!IMPORTANT]
    > Los usuarios que participan en conversaciones que forman parte de la lista de chats en Microsoft Teams deben tener un buzón de correo de Exchange Online (basado en la nube) para conservar las conversaciones de chat cuando el buzón de correo se coloca en una suspensión de eDiscovery. Esto se debe a que las conversaciones que forman parte de la lista de chats se almacenan en buzones de correo basados en la nube de los participantes del chat. Si un participante de chat no tiene un buzón de correo de Exchange Online, no podrá conservar las conversaciones de chat. Por ejemplo, en una implementación híbrida de Exchange, es posible que los usuarios con un buzón local puedan participar en conversaciones que formen parte de la lista de chats de Microsoft Teams. Sin embargo, en este caso, el contenido de esta conversación no se puede conservar porque los usuarios no tienen buzones de correo basados en la nube. 
  
  - Todos los canales de equipo o equipo de Microsoft contienen un wiki para la toma de notas y la colaboración. El contenido de la wiki se guarda automáticamente en un archivo con formato. mht. Este archivo se almacena en la biblioteca de documentos de datos wiki de Microsoft Teams en el sitio de SharePoint del equipo. Puede colocar el contenido en el sitio Wiki en espera colocando el sitio de SharePoint del equipo en retención.
    
    > [!NOTE]
    > La capacidad de retener contenido de wiki para un canal de equipo o equipo de Microsoft (cuando se ubica el sitio de SharePoint del equipo en espera) se presentó el 22 de junio de 2017. Si un sitio de grupo está en suspensión, el contenido de la wiki se conservará a partir de esa fecha. Sin embargo, si un sitio de grupo está en suspensión y el contenido de la wiki se eliminó antes del 22 de junio de 2017, no se conservó el contenido de la wiki. 
  
- **¿Cómo encuentro la dirección URL de los sitios de OneDrive para la empresa?** Para recopilar una lista de las direcciones URL de los sitios de OneDrive para la empresa de su organización para que pueda agregarlas a una suspensión o una búsqueda asociada a un caso de exhibición de documentos electrónicos, vea [crear una lista de todas las ubicaciones de OneDrive en la organización](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Este script de este artículo crea un archivo de texto que contiene una lista de todos los sitios de OneDrive. Para ejecutar este script, tendrá que instalar y usar el shell de administración de SharePoint Online. Asegúrese de anexar la dirección URL para el dominio de mi sitio de la organización en cada sitio de OneDrive que desee buscar. Este es el dominio que contiene todos los OneDrive; por ejemplo, `https://contoso-my.sharepoint.com`. Este es un ejemplo de una dirección URL para el sitio de OneDrive de `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`un usuario:.
