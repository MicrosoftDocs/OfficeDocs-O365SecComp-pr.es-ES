---
title: Edición masiva de búsquedas de contenido
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/29/2016
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 39e4654a-9588-41f6-892b-c33ab57bfbe2
description: Use el editor de búsqueda en masa en el centro de seguridad y cumplimiento de Office 365 o Microsoft 365 para cambiar rápidamente las ubicaciones de consulta y de contenido de una o más búsquedas de contenido.
ms.openlocfilehash: 3a484ad689b1c638e0e14ed1643edea0f2f56c09
ms.sourcegitcommit: 6c9340e4eb221bf81472ff3f1ae25ae21aaf5297
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "31813941"
---
# <a name="bulk-edit-content-searches"></a>Edición masiva de búsquedas de contenido

Puede usar el editor de búsqueda en masa en la herramienta de búsqueda de contenido para editar varias búsquedas al mismo tiempo. El uso de esta herramienta le permite cambiar rápidamente las ubicaciones de consultas y contenido para una o más búsquedas. A continuación, puede volver a ejecutar las búsquedas y obtener nuevos resultados de búsqueda estimados para las búsquedas revisadas. El editor también le permite copiar y pegar consultas y ubicaciones de contenido de un archivo de texto o de un archivo de Microsoft Excel. Esto significa que puede usar la herramienta de estadísticas de búsqueda para ver las estadísticas de una o más búsquedas, exportar las estadísticas a un archivo CSV donde puede editar las consultas y ubicaciones de contenido en Excel. A continuación, use el editor de búsqueda en masa para agregar las consultas revisadas y las ubicaciones de contenido a las búsquedas. Una vez que haya revisado una o más búsquedas, puede volver a iniciarlas y obtener nuevos resultados de búsqueda estimados.
  
Para obtener más información acerca del uso de la herramienta de estadísticas de búsqueda, consulte [View keyword Statistics for Content Search Results](view-keyword-statistics-for-content-search.md).
  
## <a name="use-the-bulk-search-editor-to-change-queries"></a>Usar el editor de búsqueda en masa para cambiar las consultas

1. Vaya a [https://protection.office.com](https://protection.office.com)y, a continuación, haga clic en buscar **contenido**de **búsqueda** \> .
    
2. En la lista de búsquedas, seleccione una o más búsquedas y, a continuación **** ![, haga clic en el botón](media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png)editor de búsqueda en masa del editor de búsqueda masiva.
    
    ![Seleccione una o más búsquedas y, a continuación, haga clic en editor de búsqueda masiva](media/600c9716-89a2-4451-b111-fa7cfaad2006.png)
  
    La siguiente información se muestra en la página **consultas** del editor masivo de búsqueda. 
    
    ![La página editor de búsqueda en masa muestra las consultas de las búsquedas seleccionadas](media/189659af-cc78-4479-b0bc-a93decad2f6c.png)
  
    a. La columna **Buscar** muestra el nombre de la búsqueda de contenido. Como se mencionó anteriormente, puede editar la consulta para varias búsquedas. 
    
    b. La columna **consulta** muestra la consulta de la búsqueda de contenido que aparece en la columna **búsqueda** . Si la consulta se ha creado mediante la característica lista de palabras clave, las palabras clave se separan con el texto * * `(c:s)` **. Esto indica que las palabras clave están conectadas por el operador **or** . Además, si la consulta incluye condiciones, las palabras clave y las condiciones están separadas por el texto * `(c:c)`* **. Esto indica que las palabras clave (o las fases de palabra clave) están conectadas a las condiciones por el operador **and** . Por ejemplo, en la captura de pantalla anterior, el para búsqueda ContosoSearch1, la consulta de KQL `customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)` equivale a `(customer OR pricing) AND (date=2002-01-01..2016-09-30)`.
    
3. Para editar una consulta, haga clic en la celda de la consulta que desea cambiar y realice una de las acciones siguientes. Tenga en cuenta que la celda está rodeada por un cuadro azul al hacer clic en ella.
    
   - Escriba la nueva consulta en la celda. Tenga en cuenta que no se puede editar una parte de la consulta. Tiene que escribir toda la consulta.
    
      O bien
    
    - Pega una nueva consulta en la celda. En este ejemplo se supone que se ha copiado el texto de la consulta desde un archivo, como un archivo de texto o un archivo de Excel.
    
4. Una vez que haya editado una o más consultas en la página **consultas** , haga clic en **Guardar**.
    
    La consulta revisada se muestra en la columna **consulta** de la búsqueda seleccionada. 
    
5. Haga clic en **cerrar** para cerrar el editor de búsqueda masiva. 
    
6. En la página **búsqueda de contenido** , seleccione la búsqueda que editó y haga clic en **iniciar** búsqueda para reiniciar la búsqueda con la consulta revisada. 
    
Estas son algunas sugerencias para editar consultas con el editor de búsqueda en masa:
  
- Copie la consulta existente (usando **Ctrl C** ) en un archivo de texto. Edite la consulta en el archivo de texto y, a continuación, copie la consulta revisada y péguela (mediante **Ctrl V** ) en la celda de la página **consultas** . 
    
- También puede copiar consultas de otras aplicaciones (como Microsoft Word o Microsoft Excel). Sin embargo, tenga en cuenta que podría agregar involuntariamente caracteres no admitidos a una consulta con el editor masivo de búsqueda. La mejor forma de evitar caracteres no admitidos es simplemente escribir la consulta en una celda de la página **consultas** . De manera alternativa, puede copiar una consulta de Word o Excel y, después, pegarla en un archivo de un editor de texto sin formato, como Microsoft Notepad. A continuación, guarde el archivo de texto y seleccione **ANSI** en la lista desplegable **Codificación**. Esto quitará cualquier carácter no admitido y de formato. A continuación, puede copiar y pegar la consulta desde el archivo de texto a la página **consultas** . 
    
  
## <a name="use-the-bulk-search-editor-to-change-content-locations"></a>Usar el editor de búsqueda en masa para cambiar las ubicaciones de contenido

1. En el editor de búsqueda en masa de una o varias búsquedas seleccionadas, haga clic en **Habilitar el editor de ubicación en masa**y, a continuación, haga clic en el vínculo **ubicaciones** que se muestra en la página. 
    
    La siguiente información se muestra en la página **ubicaciones** del editor masivo de búsqueda. 
    
    ![Haga clic en habilitar el editor de ubicación en masa y, a continuación, en ubicaciones para agregar o quitar ubicaciones de contenido](media/a5a468ce-bd63-4c53-bc37-ff64cf769e59.png)
  
    a. **Buzones de correo para buscar** En esta sección se muestra una columna para cada búsqueda de contenido seleccionada y una fila para cada buzón de correo que se incluye en la búsqueda. Una marca de verificación indica que el buzón de correo se incluye en la búsqueda. Puede Agregar buzones adicionales a una búsqueda si escribe la dirección de correo electrónico del buzón en una fila en blanco y, a continuación, hace clic en la casilla de verificación de la búsqueda de contenido a la que desea agregarlo. O bien, puede quitar un buzón de una búsqueda desactivando la casilla.
    
    b. **Sitios de SharePoint para buscar** En esta sección se muestra una fila para cada sitio de SharePoint y OneDrive que se incluye en cada búsqueda de contenido seleccionada. Una marca de verificación indica que el sitio está incluido en la búsqueda. Puede Agregar sitios adicionales a una búsqueda si escribe la dirección URL del sitio en una fila en blanco y, a continuación, hace clic en la casilla de verificación de la búsqueda de contenido a la que desea agregarlo. O bien, puede quitar un sitio de una búsqueda desactivando la casilla.
    
    c. **Otras opciones de búsqueda** En esta sección se indica si los elementos sin indexar y las carpetas públicas se incluyen en la búsqueda. Para incluirlos, asegúrese de que la casilla está seleccionada. Para quitarlos, desactive la casilla.
    
2. Una vez que haya editado una o varias secciones en la página **ubicaciones** , haga clic en **Guardar**.
    
    Las ubicaciones de contenido revisadas se muestran en la sección correspondiente para las búsquedas seleccionadas.
    
3. Haga clic en **cerrar** para cerrar el editor de búsqueda masiva. 
    
4. En la página **búsqueda de contenido** , seleccione la búsqueda que editó y haga clic en **iniciar** búsqueda para reiniciar la búsqueda con las ubicaciones de contenido revisadas. 
    
Estas son algunas sugerencias para editar ubicaciones de contenido con el editor de búsqueda en masa:
  
- Puede editar las búsquedas de contenido para buscar en todos los buzones o sitios de la organización; para ello, escriba **todo** en una fila en blanco en la sección **buzones de correo para buscar** o **sitios de SharePoint** y, a continuación, haga clic en la casilla. 
    
- Puede agregar varias ubicaciones de contenido a una o más búsquedas si copia varias filas de un archivo de texto o un archivo de Excel y, a continuación, las pega en una sección de la página **ubicaciones** . Después de agregar nuevas ubicaciones, asegúrese de activar la casilla de verificación de cada búsqueda a la que desea agregar la ubicación. 
    
    > [!TIP]
    > Para generar una lista de direcciones de correo electrónico para todos los usuarios de la organización, ejecute el comando PowerShell en el paso 2 de [usar búsqueda de contenido para buscar en el buzón y en el sitio de OneDrive para la empresa para obtener una lista de usuarios](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step2). O bien, use el script en [crear una lista de todas las ubicaciones de onedrive de la organización](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a) para generar una lista de todos los sitios de onedrive para la empresa de su organización. Tenga en cuenta que tendrá que anexar la dirección URL del dominio organization's de mi sitio (por ejemplo https://contoso-my.sharepoint.com) , a los sitios de OneDrive para la empresa que crea el script. Una vez que tenga una lista de direcciones de correo electrónico o sitios de OneDrive para la empresa, puede copiarlos y pegarlos en la página **ubicaciones** del editor de búsqueda en masa. 
  
- Después de hacer clic en **Guardar** para guardar los cambios en el editor de búsqueda en masa, se validará la dirección de correo electrónico para los buzones que agregó a la búsqueda. Si no existe la dirección de correo electrónico, aparecerá un mensaje de error que indica que no se encuentra el buzón. Tenga en cuenta que las direcciones URL de los sitios no se validan. 
  

