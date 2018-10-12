---
title: Configurar una directiva de eliminación y de archivo para los buzones de correo en la organización de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/9/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
description: Crear una directiva de archivado y eliminación en Office 365 que mueve automáticamente los elementos al buzón de archivo de un usuario.
ms.openlocfilehash: 740164ee840a32aff20f5c2dc1b1ae433d95cfe5
ms.sourcegitcommit: 448c5897e44448adfc82e3eaffb774c770c04815
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "25522301"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-office-365-organization"></a>Configurar una directiva de eliminación y de archivo para los buzones de correo en la organización de Office 365

 **En este artículo está dirigido a administradores. ¿Desea agregar las directivas de retención y de archivo para los elementos de su buzón de correo? Vea [asignar directivas de retención a mensajes de correo electrónico](https://support.office.com/article/3e5fd2dc-633f-4a38-b313-b31b81f7cf7a) | [las directivas de retención y de archivo de Outlook en la web para la empresa](https://support.office.com/article/465372e4-e16b-47db-bee0-aba44799085e)**
  
En Office 365, puede crear una directiva de archivado y eliminación que mueve automáticamente los elementos al buzón de archivo de un usuario y elimina automáticamente los elementos del buzón de correo. Puede hacerlo mediante la creación de una directiva de retención que ' s asignado a los buzones de correo y los elementos se mueve al buzón de archivo de un usuario después de un determinado período de tiempo y que también elimina los elementos desde el buzón de correo después de que lleguen a un límite de edad determinado. Las reglas reales que determinan qué elementos se movió o eliminó y cuando sucede que son etiquetas de retención llamado. Etiquetas de retención están vinculadas a una directiva de retención, que a su vez, se asigna al buzón de un usuario. Una etiqueta de retención aplica la configuración de retención a los mensajes individuales y carpetas en el buzón del usuario. Define un mensaje cuánto permanece en el buzón de correo y qué acción se realiza cuando el mensaje llega a la antigüedad de retención especificado. Cuando un mensaje alcanza su antigüedad de retención, ya sea se mueve al buzón de archivo del usuario o se elimina. 
  
Los pasos descritos en este tema va a configurar una directiva de archivado y de retención para una organización ficticia denominada House alpino. Configuración de esta directiva incluye las siguientes tareas:
  
- Habilitación de un buzón de archivo para todos los usuarios de la organización. Esto proporciona a los usuarios de almacenamiento de buzones de adición y es necesario para que una directiva de retención puede mover elementos en el buzón de archivo. Lo también vamos a un almacén de usuario archiving información al mover los elementos a su buzón de archivo. 
    
- Creación de tres etiquetas de retención personalizada que haga lo siguiente: 
    
  - Mueve automáticamente los elementos que están 3 años al buzón de archivo del usuario. Mover elementos en el buzón de archivo libera espacio en el buzón principal de un usuario.
    
  - Elimina automáticamente los elementos que son de 5 años desde la carpeta Elementos eliminados. Esto también libera espacio en el buzón del usuario principal. Un usuario tendrá la oportunidad de recuperar estos elementos si es necesario. Vea la nota al pie en la sección [más información](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo) para obtener más detalles. 
    
  - Automáticamente (y permanentemente) elimina los elementos que son 7 años de ambos la principal y buzón de archivo. Debido a las normativas de cumplimiento, algunos organización es necesarios para conservar el correo electrónico para un determinado período de tiempo. Después de que expire este período de tiempo, es posible que una organización desea quitar de forma permanente estos buzones de correo de usuario de elementos. 
    
- Crear una nueva directiva de retención y agregar las nuevas etiquetas de retención personalizada a ella. Además, agregará también las etiquetas de retención integradas a la nueva directiva de retención. Esto incluye etiquetas personales que pueden asignar a los usuarios a los elementos de su buzón. También agregará una etiqueta de retención que mueve los elementos de la carpeta elementos recuperables en el buzón del usuario principal a la carpeta elementos recuperables en su buzón de archivo. Esto ayuda a libera espacio en la carpeta elementos recuperables de un usuario cuando su buzón se pondrá en espera.
    
Puede seguir algunos o todos los pasos de este artículo para configurar una directiva de eliminación y de archivo para los buzones de correo en su propia organización. Se recomienda que pruebe este proceso en unos pocos buzones antes de implementar en todos los buzones de la organización.
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe ser un administrador global de la organización de Office 365 para llevar a cabo los pasos de este tema. 
    
-  Cuando cree una nueva cuenta de usuario en Office 365 y asignar al usuario una licencia de Exchange Online, se crea automáticamente un buzón de correo para el usuario. Cuando se crea el buzón de correo, se les asigna automáticamente una directiva de retención de forma predeterminada, denominada directiva MRM predeterminada. En este artículo, va a crear una nueva directiva de retención y, a continuación, asignar a buzones de usuario, reemplazando la directiva MRM predeterminada. Un buzón de correo puede tener sólo una directiva de retención asignada a él en un momento dado.
    
- Para obtener más información acerca de las etiquetas de retención y las directivas de retención en Exchange Online, consulte [etiquetas de retención y las directivas de retención](https://go.microsoft.com/fwlink/p/?LinkId=404424).
    
## <a name="step-1-enable-archive-mailboxes-for-users"></a>Paso 1: Habilitar archive los buzones de correo para los usuarios

Es el primer paso habilitar el buzón de archivo para cada usuario en la organización. Buzón de archivo de un usuario debe estar habilitada para que una etiqueta de retención con una acción de retención "Mover a archivo" puede mover el elemento después de que expire la antigüedad de retención. 
  
> [!NOTE]
> Puede habilitar buzones de archivo en cualquier momento durante este proceso, siempre que están habilitados en algún momento antes de completar el proceso de. Si un buzón de archivo no está habilitado, se realiza ninguna acción en los elementos que tienen asignada una directiva de archivo. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta de administrador global.
    
    
3. En la seguridad &amp; centro de cumplimiento, vaya a la **gobernanza de datos** \> **archivo**.
    
    Se muestra una lista de buzones de correo en la organización y si está habilitado o deshabilitado el buzón de archivo correspondientes. 
    
4. Al hacer clic en el primero de ellos en la lista, mantenga presionada la tecla **MAYÚS** , y, a continuación, haciendo clic en el último uno en la lista, seleccione todos los buzones. 
    
    > [!TIP]
    > Este paso se presupone que no hay buzones de archivo están habilitados. Si tiene todos los buzones con el archivo habilitado, mantenga presionada la tecla **Ctrl** y haga clic en cada buzón de correo que tiene un buzón de archivo deshabilitados. O bien, puede hacer clic en el encabezado de columna de **buzón de archivo** para ordenar las filas en función de si el buzón de archivo está habilitado o deshabilitado para facilitar la tarea seleccionar los buzones de correo. 
  
5. En el panel de detalles, en **Editar en masa**, haga clic en **Habilitar**.
    
    Se muestra una advertencia que indica que se moverán los elementos que son más de dos años para el nuevo buzón de archivo. Esto es debido a que la directiva de retención predeterminada que se ha asignado a un nuevo buzón de usuario cuando se crea tiene una etiqueta de directiva predeterminada de archivo que tiene una antigüedad de retención de 2 años. La etiqueta de directiva predeterminada de archivo personalizado que se creará en el paso 2 tiene una antigüedad de retención de 3 años. Es decir, los elementos que están 3 años o más antiguos se moverán al buzón de archivo.
    
6. Haga clic en **Sí** para cerrar el mensaje de advertencia e iniciar el proceso para habilitar el buzón de archivo para todos los buzones seleccionados. 
    
7. Una vez completado el proceso, haga clic en **Actualizar** ![actualizar](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) para actualizar la lista en la página de **archivo** . 
    
    El buzón de archivo está habilitado para todos los usuarios de la organización.
    
    ![La lista de buzones de correo con el buzón de archivo habilitado](media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)
  
8. Deje la seguridad &amp; abrir Centro de cumplimiento. Se usará en el siguiente paso.
    
## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>Paso 2: Crear nuevas etiquetas de retención de las directivas de eliminación y de archivo

En este paso, creará las tres etiquetas de retención personalizada que se han descrito anteriormente.
  
- Alpino House 3 año mover a archivo (directiva de archivo personalizados)
    
- Alpino House 7 año eliminar permanentemente (directiva de eliminación personalizadas)
    
- Alpino House eliminar elementos de 5 años eliminar y permitir recuperación (etiqueta personalizada para la carpeta Elementos eliminados)
    
Para crear nuevas etiquetas de retención, debe usar el centro de administración de Exchange (EAC) en la organización de Exchange Online.
  
1. En la seguridad &amp; centro de cumplimiento, haga clic en el iniciador de la aplicación en la esquina superior izquierda y, a continuación, haga clic en el icono de **administración** . 
    
2. En el panel de navegación izquierdo del centro de administración de Office 365, haga clic en **centros de administración**y, a continuación, haga clic en **Exchange**.
    
    ![Screenshot shows the Office 365 admin center with the Admin centers option expanded and Exchange selected.](media/47399df2-0bc4-42e2-b183-07750a46bc68.png)
  
3. En el EAC, vaya a **administración de cumplimiento** \> **etiquetas de retención**
    
    Se muestra una lista de las etiquetas de retención para la organización.
    
### <a name="create-a-custom-archive-default-policy-tag"></a>Crear una etiqueta de directiva predeterminada de archivo personalizado
  
En primer lugar, creará una etiqueta de directiva personalizado del archivo predeterminado (DPT) que se moverá los elementos en el buzón de archivo después de 3 años. 
  
1. En la página **etiquetas de retención** , haga clic en **nueva etiqueta**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)y, a continuación, seleccione **aplica automáticamente a todo el buzón (valor predeterminado)**. 
    
2. En la página **nueva etiqueta que se aplican automáticamente a todo el buzón (valor predeterminado)** , complete los siguientes campos: 
    
    ![Configuración para crear una nueva etiqueta de directiva predeterminada de archivo](media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
1. **Nombre** Escriba un nombre para la nueva etiqueta de retención. 
    
2. **Acción de retención** Seleccione **mover a archivo** para mover los elementos en el buzón de archivo cuando expire el período de retención. 
    
3. **Período de retención** Seleccione **cuando el elemento alcanza la antigüedad siguiente (en días)** y, a continuación, escriba la duración del período de retención. Para este escenario, los elementos se moverán al buzón de archivo después de días 1095 (3 años).
    
4. **Comentario** (Opcional) Escriba un comentario que explica el propósito de la etiqueta de retención personalizada. 
    
3. Haga clic en **Guardar** para crear el archivo personalizado DPT. 
    
    El nuevo DPT de archivo se muestra en la lista de etiquetas de retención.
    
### <a name="create-a-custom-deletion-default-policy-tag"></a>Crear una etiqueta de directiva predeterminada de eliminación personalizadas
  
A continuación, va a crear otra DPT personalizado pero ésta será una directiva de eliminación que elimina de forma permanente los elementos después de 7 años.
  
1. En la página **etiquetas de retención** , haga clic en **nueva etiqueta**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)y, a continuación, seleccione **aplica automáticamente a todo el buzón (valor predeterminado)**. 
    
2. En la página **nueva etiqueta que se aplican automáticamente a todo el buzón (valor predeterminado)** , complete los siguientes campos: 
    
    ![Configuración para crear una nueva etiqueta de directiva de eliminación predeterminada](media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
1. **Nombre** Escriba un nombre para la nueva etiqueta de retención. 
    
2. **Acción de retención** Seleccione **Eliminar permanentemente** a purgar los elementos del buzón de correo cuando expire el período de retención. 
    
3. **Período de retención** Seleccione **cuando el elemento alcanza la antigüedad siguiente (en días)** y, a continuación, escriba la duración del período de retención. Para este escenario, los elementos se purgarán después de 2555 días (7 años).
    
4. **Comentario** (Opcional) Escriba un comentario que explica el propósito de la etiqueta de retención personalizada. 
    
3. Haga clic en **Guardar** para crear la eliminación personalizada DPT. 
    
    El nuevo DPT de eliminación se muestra en la lista de etiquetas de retención.
    
### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Crear una etiqueta de directiva de retención personalizada para la carpeta Elementos eliminados
  
La última etiqueta de retención que se va a crear es una etiqueta de directiva de retención personalizada (RPT) para la carpeta Elementos eliminados. Esta etiqueta, elimina los elementos de la carpeta Elementos eliminados después de 5 años y proporciona un punto de recuperación cuando los usuarios pueden usar la herramienta de recuperar elementos eliminados para recuperar un elemento.
  
1. En la página **etiquetas de retención** , haga clic en **nueva etiqueta** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)y, a continuación, seleccione **aplica automáticamente a una carpeta predeterminada**. 
    
2. En la página **nueva etiqueta que se aplica automáticamente a una carpeta predeterminada** , complete los siguientes campos: 
    
    ![Configuración para crear una nueva etiqueta de directiva de retención para la carpeta Elementos eliminados](media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
1. **Nombre** Escriba un nombre para la nueva etiqueta de retención. 
    
2. **Aplicar esta etiqueta a la siguiente carpeta predeterminada** En la lista desplegable, seleccione los **Elementos eliminados**.
    
3. **Acción de retención** Seleccione **eliminar y permitir recuperación** para eliminar los elementos cuando caduca el período de retención, pero permitir que los usuarios recuperar un elemento eliminado dentro del período de retención de elementos eliminados (que, de forma predeterminada, es de 14 días). 
    
4. **Período de retención** Seleccione **cuando el elemento alcanza la antigüedad siguiente (en días)** y, a continuación, escriba la duración del período de retención. Para este escenario, los elementos se eliminarán después de días 1825 (5 años).
    
5. **Comentario** (Opcional) Escriba un comentario que explica el propósito de la etiqueta de retención personalizada. 
    
3. Haga clic en **Guardar** para crear el RPT personalizado para la carpeta Elementos eliminados. 
    
    El nuevo RPT se muestra en la lista de etiquetas de retención.

## <a name="step-3-create-a-new-retention-policy"></a>Paso 3: Crear una nueva directiva de retención

Después de crear las etiquetas de retención personalizada, el siguiente paso es crear una nueva directiva de retención y agregue las etiquetas de retención. Va a agregar las tres etiquetas de retención personalizada que ha creado en el paso 2 y las etiquetas integradas que se mencionaron en la primera sección. En el paso 4, podrá asignar esta nueva directiva de retención a los buzones de usuario.
  
1. En el EAC, vaya a **administración de cumplimiento** \> **las directivas de retención**.
    
2. En la página de **directivas de retención** , haga clic en **nuevo** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).
    
3. En el cuadro **nombre** , escriba un nombre para la nueva directiva de retención; Por ejemplo, **Directiva de eliminación y de archivo de casa alpino**. 
    
4. En **las etiquetas de retención**, haga clic en **Agregar** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).
    
    Se muestra una lista de las etiquetas de retención de la organización. Tenga en cuenta que se muestran las etiquetas personalizadas que ha creado en el paso 2.
    
5. Agregue las etiquetas de retención 9 que se resaltan en la siguiente captura de pantalla (estas etiquetas se describen con más detalle en la sección [más información](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo) ). Para agregar una etiqueta de retención, selecciónela y, a continuación, haga clic en **Agregar**. 
    
    ![Agregar etiquetas de retención a la nueva directiva de retención](media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > Puede seleccionar varias etiquetas de retención manteniendo presionada la tecla **Ctrl** y, a continuación, haciendo clic en cada etiqueta. 
  
6. Una vez que haya agregado las etiquetas de retención, haga clic en **Aceptar**.
    
7. En la página **nueva directiva de retención** , haga clic en **Guardar** para crear la nueva directiva. 
    
    La nueva directiva de retención se muestra en la lista. Selecciónelo para mostrar las etiquetas de retención vinculadas a ella en el panel de detalles.
    
    ![La nueva directiva de retención y la lista de etiquetas de retención vinculadas](media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>Paso 4: Asignar la nueva directiva de retención a los buzones de usuario

Cuando se crea un nuevo buzón de correo, se asigna una directiva de retención denominada directiva MRM predeterminada a él de forma predeterminada. En este paso, va a reemplazar esta directiva de retención (debido a que un buzón puede tener sólo una directiva de retención asignada a él) mediante la asignación de la nueva directiva de retención que se ha creado en el paso 3 para los buzones de usuario en la organización. Este paso se presupone que asignará la nueva directiva a todos los buzones de la organización.
  
1. En el EAC, vaya a **Destinatarios** \> **Buzones de correo**.
    
    Se muestra una lista de todos los buzones de usuario de la organización. 
    
2. Al hacer clic en el primero de ellos en la lista, mantenga presionada la tecla **MAYÚS** , y, a continuación, haciendo clic en el último uno en la lista, seleccione todos los buzones. 
    
3. En el panel de detalles en el lado derecho de la EAC, en **Editar en masa**, haga clic en **más opciones**.
    
4. En **Directiva de retención**, haga clic en **Actualizar**.
    
5. En la página **masiva Asignar directiva de retención** , en la lista desplegable **Seleccione la directiva de retención** , seleccione la directiva de retención que creó en el paso 3; Por ejemplo, **Directiva de retención y de archivo de casa alpino**.
    
6. Haga clic en **Guardar** para guardar la nueva asignación de la directiva de retención. 
    
7. Para comprobar que la nueva directiva de retención se asignó a los buzones de correo, puede hacer lo siguiente: seleccione un buzón de correo en la página de los buzones de correo y, a continuación, haga clic en Editar. 
    
1. Seleccione un buzón de correo en la página de **los buzones de correo** y, a continuación, haga clic en **Editar** ![editar](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png). 
    
2. En la página de propiedades de buzón de correo del usuario seleccionado, haga clic en **características de buzón de correo**.
    
    El nombre de la nueva directiva asignada para el buzón de correo se muestra en la lista desplegable de **la directiva de retención** . 
    

  
## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>(Opcional) Paso 5: Ejecutar el Asistente para carpeta administrada para aplicar la nueva configuración
<a name="step3"> </a>

Después de aplicar la nueva directiva de retención a buzones de correo en el paso 4, puede tardar hasta 7 días en Exchange Online para que la nueva configuración de retención que se aplicará a los buzones de correo. Esto es debido a que un proceso llama el Asistente para carpeta administrada buzones de procesos una vez cada siete días. En lugar de esperar el Asistente para carpeta administrada ejecutar, puede forzar a que esto ocurra ejecutando el cmdlet **Start-ManagedFolderAssistant** en Exchange Online PowerShell. 
  
 **¿Qué sucede cuando se ejecuta el Asistente para carpeta administrada?** Se aplica la configuración de la directiva de retención mediante la inspección de los elementos en el buzón de correo y determinar si están sujetos a retención. A continuación, marca elementos sujetos a retención con la etiqueta de retención correspondientes y, a continuación, realiza la acción de retención especificado en los elementos más allá de su antigüedad de retención. 
  
Estos son los pasos para conectarse a Exchange Online PowerShell y, a continuación, ejecute el Asistente para carpeta administrada en cada buzón de correo en la organización.
  
1. En el equipo local, abra Windows PowerShell y ejecute el siguiente comando.
    
    ```
    $UserCredential = Get-Credential
    ```

    En el cuadro de diálogo **Solicitud de credenciales de Windows PowerShell** , escriba el nombre de usuario y la contraseña de su cuenta de administrador global de Office 365 y, a continuación, haga clic en **Aceptar**.
    
2. Ejecute el comando siguiente.
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. Ejecute el comando siguiente.
    
    ```
    Import-PSSession $Session
    ```

4. Para comprobar que se ha conectado a su organización de Exchange Online, ejecute el comando siguiente para obtener una lista de todos los buzones de correo de su organización.
    
    ```
    Get-Mailbox
    ```

    > [!NOTE]
    > Para obtener más información o si tiene problemas para conectarse a su organización de Exchange Online, consulte [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=517283). 
  
5. Ejecute los dos comandos siguientes para iniciar el Asistente para carpeta administrada para todos los buzones de usuario en la organización.
    
    ```
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

¡Eso es todo! Ha configurado una directiva de eliminación y de archivo para la organización de casa alpino.
  
## <a name="more-information"></a>Más información
<a name="moreinfo"> </a>

- ¿Cómo se calcula la antigüedad de retención? La antigüedad de retención de los elementos del buzón se calcula a partir de la fecha de entrega o la fecha de creación de elementos como los mensajes de borrador que no se enviarán, pero son creados por el usuario. Cuando el Asistente para carpeta administrada procesa los elementos de un buzón de correo, marca una fecha de inicio y una fecha de caducidad para todos los elementos que tienen etiquetas de retención con la acción de retención eliminar y permitir recuperación o eliminar de forma permanente. Los elementos que tienen una etiqueta de archivo están marcados con una fecha de movimiento. 
    
- En la siguiente tabla se proporciona más información acerca de cada etiqueta de retención que se agrega a la directiva de retención personalizada que se creó siguiendo los pasos descritos en este tema.
    
    |**Etiqueta de retención**|**Lo que hace esta etiqueta**|**¿Integrada o personalizada?**|**Tipo**|
    |:-----|:-----|:-----|:-----|
    |Movimiento de tres años de casa alpino al archivo  <br/> |Mueve los elementos que tengan 1095 días (3 años) para el buzón de archivo.  <br/> |Personalizado (vea [paso 2: crear nuevas etiquetas de retención de las directivas de eliminación y de archivo](set-up-an-archive-and-deletion-policy-for-mailboxes.md#step3) )  <br/> |Etiqueta de directiva predeterminada (archivo); Esta etiqueta se aplica automáticamente a todo el buzón.  <br/> |
    |Casa alpino 7 años eliminar permanentemente  <br/> |Elimina de forma permanente los elementos en el buzón principal o el buzón de archivo cuando se inician 7 años de antigüedad.  <br/> |Personalizado (vea [paso 2: crear nuevas etiquetas de retención de las directivas de eliminación y de archivo](set-up-an-archive-and-deletion-policy-for-mailboxes.md#step3) )  <br/> |Etiqueta de directiva predeterminada (eliminación); Esta etiqueta se aplica automáticamente a todo el buzón.  <br/> |
    |Casa alpino elimina elementos 5 años eliminar y permite recuperación  <br/> |Elimina los elementos de la carpeta Elementos eliminados que son de 5 años. Los usuarios pueden recuperar estos elementos para copia de seguridad 14 días después de que se eliminan.<sup>\*</sup> <br/> |Personalizado (vea [paso 2: crear nuevas etiquetas de retención de las directivas de eliminación y de archivo](set-up-an-archive-and-deletion-policy-for-mailboxes.md#step3) )  <br/> |Etiqueta de directiva de retención (elementos eliminados); Esta etiqueta se aplica automáticamente a los elementos de la carpeta Elementos eliminados.  <br/> |
    |Mover los días de 14 elementos recuperables a archivo  <br/> |Mueve los elementos que han sido en la carpeta elementos recuperables durante 14 días a la carpeta elementos recuperables en el buzón de archivo.  <br/> |Integrado  <br/> |Etiqueta de directiva de retención (elementos recuperables); Esta etiqueta se aplica automáticamente a los elementos de la carpeta elementos recuperables.  <br/> |
    |Correo electrónico no deseado  <br/> |Elimina de forma permanente los elementos que han sido en la carpeta correo no deseado durante 30 días. Los usuarios pueden recuperar estos elementos para copia de seguridad 14 días después de que se eliminan.<sup>\*</sup> <br/> |Integrado  <br/> |Etiqueta de directiva de retención (correo no deseado); Esta etiqueta se aplica automáticamente a los elementos de carpeta de correo electrónico no deseado.  <br/> |
    |Eliminar después de un mes  <br/> |Elimina de forma permanente los elementos que son 30 días de antigüedad. Los usuarios pueden recuperar estos elementos para copia de seguridad 14 días después de que se eliminan.<sup>\*</sup> <br/> |Integrado  <br/> |Personal; Esta etiqueta se puede aplicar a los usuarios.  <br/> |
    |Eliminar después de un año  <br/> |Elimina de forma permanente los elementos que están 365 días de antigüedad. Los usuarios pueden recuperar estos elementos para copia de seguridad 14 días después de que se eliminan.<sup>\*</sup> <br/> |Integrado  <br/> |Personal; Esta etiqueta se puede aplicar a los usuarios.  <br/> |
    |No eliminar nunca  <br/> |Esta etiqueta impide que los elementos se va a eliminar una directiva de retención.  <br/> |Integrado  <br/> |Personal; Esta etiqueta se puede aplicar a los usuarios.  <br/> |
    |Mover al archivo después de 1 años en forma personal  <br/> |Mueve los elementos en el buzón de archivo después de 1 año.  <br/> |Integrado  <br/> |Personal; Esta etiqueta se puede aplicar a los usuarios.  <br/> |
   
    > <sup>\*</sup>Los usuarios pueden usar la herramienta de recuperar elementos eliminados en Outlook y Outlook Web App para recuperar un elemento eliminado dentro del período de retención de elementos eliminados, que de forma predeterminada es de 14 días en Exchange Online. Un administrador puede usar Windows PowerShell para aumentar el período de retención de elementos eliminados a un máximo de 30 días. Para obtener más información, vea: [recuperar elementos eliminados en Outlook para Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) y [cambiar el período de retención de elementos eliminados de un buzón en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940)
  
- Utilizando el **14 de elementos recuperables días mover a archivo de** retención etiqueta ayuda a libre un espacio de almacenamiento en la carpeta elementos recuperables en el buzón del usuario principal. Esto es útil cuando el buzón de un usuario se pondrá en espera, lo que significa que nunca permanentemente nada es elimina el buzón del usuario. Sin mover elementos en el buzón de archivo, es posible que se alcanzará la cuota de almacenamiento para la carpeta elementos recuperables en el buzón principal. Para obtener más información sobre este y cómo evitarlo, vea [aumentar la cuota de buzones de correo en suspensión de elementos recuperables](https://go.microsoft.com/fwlink/p/?LinkId=786479).
