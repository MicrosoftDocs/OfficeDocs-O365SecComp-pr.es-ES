---
title: Edición en masa de búsquedas de contenido en la seguridad de Office 365 &amp; centro de cumplimiento
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/29/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 39e4654a-9588-41f6-892b-c33ab57bfbe2
description: Use el Editor de búsqueda de forma masiva en la seguridad de Office 365 &amp; centro de cumplimiento para cambiar rápidamente las ubicaciones de consulta y el contenido de las búsquedas de contenido de uno o más.
ms.openlocfilehash: 45c9a3fc4bcc5e5d8ce9945d3094bfb4a39d6dcf
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536081"
---
# <a name="bulk-edit-content-searches-in-the-office-365-security-amp-compliance-center"></a>Edición en masa de búsquedas de contenido en la seguridad de Office 365 &amp; centro de cumplimiento

Puede usar el Editor de búsqueda de forma masiva en la seguridad de Office 365 &amp; centro de cumplimiento para editar varias búsquedas de contenido al mismo tiempo. Uso de esta herramienta le permite cambiar rápidamente las ubicaciones de consulta y el contenido de una o varias de las búsquedas. A continuación, puede volver a ejecutar las búsquedas y obtener nuevos resultados de búsqueda estimado para las búsquedas revisadas. El editor también permite copiar y pegar las consultas y las ubicaciones de contenido desde un archivo de Microsoft Excel o un archivo de texto. Esto significa que puede usar la herramienta estadísticas de búsqueda para ver las estadísticas de una o varias búsquedas, las estadísticas de exportación a un archivo CSV, donde puede editar las consultas y las ubicaciones de contenido en Excel. A continuación, use el Editor de búsqueda masiva para agregar las consultas revisadas y ubicaciones de contenido para las búsquedas. Después de que ha revisado las búsquedas de uno o más, puede volver a iniciar ellos y obtener nuevos resultados de búsqueda estimado.
  
Para obtener más información acerca del uso de la herramienta estadísticas de búsqueda, vea [Ver las estadísticas de palabra clave para los resultados de la búsqueda de contenido](view-keyword-statistics-for-content-search.md).
  
## <a name="use-the-bulk-search-editor-to-change-queries"></a>Use el Editor de búsqueda de forma masiva para cambiar las consultas

1. En la seguridad &amp; centro de cumplimiento, vaya a **búsqueda &amp; investigación** \> **búsqueda de contenido**.
    
2. En la lista de búsquedas, seleccione uno o más de las búsquedas y, a continuación, haga clic en **Editor de búsqueda masiva** ![botón Editor de búsqueda masiva](media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png).
    
    ![Seleccione uno o más de las búsquedas y, a continuación, haga clic en editor de búsqueda de forma masiva](media/600c9716-89a2-4451-b111-fa7cfaad2006.png)
  
    La siguiente información se muestra en la página de **consultas** del Editor de búsqueda masiva. 
    
    ![La página del editor de búsqueda masiva muestra las consultas para las búsquedas seleccionadas](media/189659af-cc78-4479-b0bc-a93decad2f6c.png)
  
    r. la columna de **búsqueda** muestra el nombre de la búsqueda de contenido. Como se ha indicado anteriormente, puede editar la consulta para varias búsquedas. 
    
    b. la columna de la **consulta** muestra la consulta para la búsqueda de contenido que aparecen en la columna de **búsqueda** . Si la consulta se creó mediante la característica de la lista de palabras clave, las palabras clave están separadas por el texto ** `(c:s)` **. Esto indica que las palabras clave están conectadas por el operador **OR** . Además, si la consulta incluye las condiciones, las palabras clave y las condiciones están separadas por el texto ** `(c:c)` **. Esto indica que las palabras clave (o fases de palabra clave) están conectadas a las condiciones por el operador **y** . Por ejemplo, en la captura de pantalla anterior el para la búsqueda ContosoSearch1, la consulta de KQL que es equivalente a `customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)` sería `(customer OR pricing) AND (date=2002-01-01..2016-09-30)`.
    
3. Para editar una consulta, haga clic en la celda de la consulta que desea cambiar y realizando una de las siguientes acciones. Tenga en cuenta que la celda rodeada por un cuadro de color azul cuando haga clic en él.
    
   - Escriba la nueva consulta en la celda. Tenga en cuenta que no se puede editar una parte de la consulta. Tendrá que escribir toda la consulta.
    
      O bien
    
    - Pegue una nueva consulta en la celda. Se supone que ha copiado el texto de consulta desde un archivo, como un archivo de texto o un archivo de Excel.
    
4. Después de editar una o más consultas en la página de **consultas** , haga clic en **Guardar**.
    
    La consulta revisada se muestra en la columna de **consulta** para la búsqueda seleccionada. 
    
5. Haga clic en **Cerrar** para cerrar el Editor de búsqueda masiva. 
    
6. En la página de **búsqueda de contenido** , seleccione la búsqueda que ha editado y haga clic en **Iniciar** búsqueda para reiniciar la búsqueda mediante la consulta revisada. 
    
Estas son algunas sugerencias para su edición con el Editor de búsqueda masiva de consultas:
  
- Copie la consulta existente (mediante el uso de **Ctrl C** ) en un archivo de texto. Modificar la consulta en el archivo de texto y, a continuación, copie la consulta revisada y pegarla (mediante **Ctrl V** ) en la celda en la página de **consultas** . 
    
- También puede copiar las consultas de otras aplicaciones (como Microsoft Word o Microsoft Excel). Sin embargo, tenga en cuenta que puede agregar sin darse cuenta caracteres no admitidos en una consulta con el Editor de búsqueda masiva. Sólo tiene que escribir la consulta en una celda en la página de **consultas** es la mejor forma de evitar que los caracteres no admitidos. Como alternativa, puede copiar una consulta de Word o Excel y, a continuación, péguelo en el archivo en un editor de texto sin formato, como Microsoft Notepad. A continuación, guarde el archivo de texto y seleccione **ANSI** en la lista desplegable de **codificación** . Esta acción eliminará todos los caracteres no admitidos y formato. A continuación, puede copiar y pegar la consulta desde el archivo de texto a la página de **consultas** . 
    
  
## <a name="use-the-bulk-search-editor-to-change-content-locations"></a>Use el Editor de búsqueda de forma masiva para cambiar las ubicaciones de contenido

1. En el masiva búsqueda Editor para una o varias búsquedas seleccionadas, haga clic en **Habilitar editor de ubicación de forma masiva**y, a continuación, haga clic en el vínculo de **ubicaciones** que se muestra en la página. 
    
    La siguiente información se muestra en la página **ubicaciones** del Editor de búsqueda masiva. 
    
    ![Haga clic en Habilitar masiva ubicación editor y, a continuación, haga clic en ubicaciones para agregar o quitar ubicaciones de contenido](media/a5a468ce-bd63-4c53-bc37-ff64cf769e59.png)
  
    r. **los buzones de correo para buscar**en esta sección se muestra una columna para cada fila para cada buzón de correo que se incluye en la búsqueda y búsqueda de contenido seleccionado. Una marca de verificación indica que el buzón de correo se incluye en la búsqueda. Puede agregar buzones de correo adicionales a una búsqueda escribiendo la dirección de correo electrónico del buzón en una fila en blanco y, a continuación, haga clic en la casilla de verificación para la búsqueda de contenido que desea agregar a. O bien, puede quitar un buzón de correo de una búsqueda, desactive la casilla de verificación.
    
    en esta sección se muestra una fila para cada sitio de SharePoint y OneDrive para la que se incluye en cada uno de **los sitios de SharePoint para buscar**b. seleccionado búsqueda de contenido. Una marca de verificación indica que el sitio está incluido en la búsqueda. Puede agregar sitios adicionales a una búsqueda escribiendo la dirección URL para el sitio en una fila en blanco y, a continuación y haga clic en la casilla de verificación para la búsqueda de contenido que va a agregar. O bien, puede quitar un sitio de una búsqueda, desactive la casilla de verificación.
    
    c. **otras opciones de búsqueda**en esta sección se indica si los elementos sin indizar y las carpetas públicas se incluyen en la búsqueda. Para incluir estos, asegúrese de que esté activada la casilla de verificación. Para quitarlos, desactive la casilla de verificación.
    
2. Después de editar una o varias de las secciones en la página **ubicaciones** , haga clic en **Guardar**.
    
    Las ubicaciones de contenido revisadas se muestran en la sección adecuada para las búsquedas seleccionadas.
    
3. Haga clic en **Cerrar** para cerrar el Editor de búsqueda masiva. 
    
4. En la página de **contenido de búsqueda** , seleccione la búsqueda que ha editado y haga clic en **Iniciar** búsqueda para reiniciar la búsqueda con las ubicaciones de contenido revisadas. 
    
Estas son algunas sugerencias para su edición con el Editor de búsqueda masiva de ubicaciones de contenido:
  
- Puede editar las búsquedas de contenido para buscar todos los buzones de correo o sitios en la organización, escriba **todos** en una fila en blanco en la sección de **buzones de correo para buscar** o **sitios de SharePoint para buscar** y, a continuación, haga clic en la casilla de verificación. 
    
- Puede agregar varias ubicaciones de contenido a una o varias búsquedas copiar varias filas de un archivo de texto o un archivo de Excel y, a continuación, los pegando a una sección en la página **ubicaciones** . Después de agregar nuevas ubicaciones, asegúrese de seleccionar la casilla de verificación para cada búsqueda que desee agregar la ubicación a. 
    
    > [!TIP]
    > Para generar una lista de direcciones de correo electrónico para todos los usuarios de la organización, ejecute el comando de PowerShell en el paso 2 en [Usar la búsqueda de contenido para buscar en el buzón de correo y OneDrive para el sitio de negocio para obtener una lista de los usuarios](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step2). O bien, use el script en [crear una lista de todas las ubicaciones de OneDrive en la organización](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a) para generar una lista de todos los OneDrive para sitios de profesionales de la organización. Tenga en cuenta que tendrá que anexe la dirección URL del dominio de Mi sitio de la organización (por ejemplo, https://contoso-my.sharepoint.com) a la OneDrive para sitios de profesionales que se crea mediante la secuencia de comandos. Una vez que tenga la lista de direcciones de correo electrónico o OneDrive para los sitios de negocio, puede copiar y péguelas en la página **ubicaciones** en el Editor de búsqueda de forma masiva. 
  
- Después de hacer clic en **Guardar** para guardar los cambios en el Editor de búsqueda de forma masiva, se validará la dirección de correo electrónico para los buzones de correo que ha agregado a una búsqueda. Si no existe la dirección de correo electrónico, se muestra un mensaje de error que indica que no se puede encontrar el buzón de correo. Tenga en cuenta que no se validan las direcciones URL para los sitios. 
  

