---
title: Configurar una directiva de archivo y eliminación para los buzones de la organización de Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
description: Crear una directiva de archivado y eliminación en Office 365 que mueva automáticamente elementos al buzón de archivo de un usuario.
ms.openlocfilehash: a32c6607ec43634e317ee92b8fed6698e3a5c3b9
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30297013"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-office-365-organization"></a>Configurar una directiva de archivo y eliminación para los buzones de la organización de Office 365

 En Office 365, los administradores pueden crear una directiva de archivado y eliminación que mueva automáticamente los elementos al buzón de archivo de un usuario y elimine automáticamente los elementos del buzón. Para ello, el administrador crea una directiva de retención que se asigna a los buzones de correo y mueve los elementos al buzón de archivo de un usuario después de un período de tiempo determinado y también elimina los elementos del buzón una vez que alcanzan un determinado límite de antigüedad. Las reglas reales que determinan qué elementos se mueven o eliminan y cuándo se producen se denominan etiquetas de retención. Las etiquetas de retención están vinculadas a una directiva de retención, que, a su vez, se asigna al buzón de correo de un usuario. Una etiqueta de retención aplica la configuración de retención a los mensajes individuales y las carpetas en el buzón de un usuario. Define cuánto tiempo permanece un mensaje en el buzón de correo y qué acción se lleva a cabo cuando el mensaje alcanza la antigüedad de retención especificada. Cuando un mensaje alcanza su antigüedad de retención, se mueve al buzón de archivo del usuario o se elimina. 
  
Los pasos descritos en este artículo configuran una directiva de archivado y retención para una organización ficticia denominada Alpine House. La configuración de esta directiva incluye las siguientes tareas:
  
- Habilitación de un buzón de archivo para todos los usuarios de la organización. Esto proporciona a los usuarios el almacenamiento de buzones de correo adicional y es necesario para que una directiva de retención pueda mover elementos al buzón de archivo. También permite que un usuario almacene la información de archivado moviendo elementos a su buzón de archivo. 
    
- Crear tres etiquetas de retención personalizadas que hagan lo siguiente: 
    
  - Mueve automáticamente los elementos que tienen un antigüedad de 3 años para el buzón de archivo del usuario. Al mover elementos al buzón de archivo, se libera espacio en el buzón de correo principal de un usuario.
    
  - Elimina automáticamente los elementos que tienen 5 años de antigüedad de la carpeta elementos eliminados. Esto también libera espacio en el buzón de correo principal del usuario. El usuario tendrá la oportunidad de recuperar estos elementos si es necesario. Vea la nota al pie en la sección [más información](#more-information) para obtener más información. 
    
  - Elimina automáticamente (y permanentemente) los elementos que tienen 7 años de antigüedad tanto en el buzón de archivo como en el principal. Debido a las regulaciones de cumplimiento, es necesario que algunas organizaciones conserven el correo electrónico durante un período de tiempo determinado. Una vez transcurrido este período de tiempo, es posible que una organización quiera quitar permanentemente los buzones de usuario de los elementos. 
    
- Crear una nueva Directiva de retención y agregarle nuevas etiquetas de retención personalizadas. Además, también agregará etiquetas de retención integradas a la nueva Directiva de retención. Esto incluye etiquetas personales que los usuarios pueden asignar a los elementos de su buzón de correo. También agregará una etiqueta de retención que mueve los elementos de la carpeta elementos recuperables del buzón de correo principal del usuario a la carpeta elementos recuperables de su buzón de archivo. Esto ayuda a liberar espacio en la carpeta elementos recuperables de un usuario cuando su buzón de correo se coloca en retención.
    
Puede seguir algunos o todos los pasos de este artículo para configurar una directiva de archivo y eliminación para los buzones de correo de su propia organización. Se recomienda probar este proceso en unos pocos buzones antes de implementarlo en todos los buzones de la organización.
  
## <a name="before-you-begin"></a>Antes de empezar

- Debe ser administrador global de la organización de Office 365 para realizar los pasos de este tema. 
    
-  Al crear una nueva cuenta de usuario en Office 365 y asignar al usuario una licencia de Exchange Online, se crea automáticamente un buzón para el usuario. Cuando se crea el buzón de correo, se le asigna automáticamente una directiva de retención predeterminada, denominada Directiva de MRM predeterminada. En este artículo, creará una nueva Directiva de retención y la asignará a los buzones de usuario, reemplazando la Directiva de MRM predeterminada. Un buzón solo puede tener una directiva de retención asignada en un momento dado.
    
- Para obtener más información sobre las directivas de retención y las etiquetas de retención en Exchange Online, consulte [Retention Tags and](https://go.microsoft.com/fwlink/p/?LinkId=404424)Retention Policies.
    
## <a name="step-1-enable-archive-mailboxes-for-users"></a>Paso 1: habilitar buzones de archivo para los usuarios

El primer paso consiste en habilitar el buzón de archivo para cada usuario de la organización. El buzón de archivo de un usuario debe estar habilitado para que una etiqueta de retención con una acción de retención "mover al archivo" pueda mover el elemento cuando expire la antigüedad de retención. 
  
> [!NOTE]
> Puede habilitar los buzones de archivo en cualquier momento durante este proceso, siempre y cuando estén habilitados en algún momento antes de completar el proceso. Si un buzón de archivo no está habilitado, no se realiza ninguna acción en ninguno de los elementos que tienen asignada una directiva de archivo. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta de administrador global.
    
    
3. En el centro &amp; de seguridad y cumplimiento, vaya a **archivo**de **gobierno** \> de datos.
    
    Se muestra una lista de los buzones de correo de la organización y si el buzón de archivo correspondiente está habilitado o deshabilitado. 
    
4. Para seleccionar todos los buzones, haga clic en el primero de la lista, mantenga presionada la tecla **MAYÚS** y, a continuación, haga clic en el último de la lista. 
    
    > [!TIP]
    > En este paso se presupone que no hay buzones de archivo habilitados. Si tiene buzones con el archivo habilitado, mantenga presionada la tecla **Ctrl** y haga clic en cada buzón de correo que tenga un buzón de archivo deshabilitado. O puede hacer clic en el encabezado de la columna **buzón de archivo** para ordenar las filas en función de si el buzón de archivo está habilitado o deshabilitado para facilitar la selección de buzones. 
  
5. En el panel de detalles, en **edición en masa**, haga clic en **Habilitar**.
    
    Se muestra una advertencia que indica que los elementos que tienen más de dos años se moverán al nuevo buzón de archivo. Esto se debe a que la Directiva de retención predeterminada asignada a un nuevo buzón de usuario cuando se crea tiene una etiqueta de directiva de archivado predeterminada con una antigüedad de retención de 2 años. La etiqueta de directiva predeterminada de archivo personalizado que creará en el paso 2 tiene una antigüedad de retención de 3 años. Esto significa que los elementos de 3 años o más se moverán al buzón de archivo.
    
6. Haga clic en **sí** para cerrar el mensaje de advertencia e iniciar el proceso para habilitar el buzón de archivo para cada buzón seleccionado. 
    
7. Una vez completado el proceso, haga **** ![clic en](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) actualizar actualización para actualizar la lista en la página **archivo** . 
    
    El buzón de archivo está habilitado para todos los usuarios de la organización.
    
    ![La lista de buzones con el buzón de archivo habilitado](media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)
  
8. Deje abierto el &amp; centro de seguridad y cumplimiento. Lo usará en el paso siguiente.
    
## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>Paso 2: crear nuevas etiquetas de retención para las directivas de archivo y eliminación

En este paso, creará las tres etiquetas de retención personalizadas descritas anteriormente.
  
- Mover a archivo desde Alpine House a 3 años (Directiva de archivo personalizada)
    
- Eliminación permanente de Alpine House de 7 años (Directiva de eliminación personalizada)
    
- Eliminar y permitir recuperación de los elementos eliminados de Alpine House 5 años (etiqueta personalizada para la carpeta elementos eliminados)
    
Para crear nuevas etiquetas de retención, debe usar el centro de administración de Exchange (EAC) en su organización de Exchange Online.
  
1. En el centro &amp; de seguridad y cumplimiento, haga clic en el iniciador de aplicaciones en la esquina superior izquierda y, a continuación, en el icono **Administración** . 
    
2. En el panel de navegación izquierdo del centro de administración de Office 365, haga clic en **centros de administración**y, a continuación, en **Exchange**.
    
    ![Screenshot shows the Office 365 admin center with the Admin centers option expanded and Exchange selected.](media/47399df2-0bc4-42e2-b183-07750a46bc68.png)
  
3. En el EAC, vaya a **** \> **etiquetas de retención** de administración de cumplimiento.
    
    Se muestra una lista de las etiquetas de retención de la organización.
    
### <a name="create-a-custom-archive-default-policy-tag"></a>Crear una etiqueta de directiva predeterminada de archivo personalizado
  
En primer lugar, deberá crear una etiqueta de directiva predeterminada de archivo (DPT) personalizada que moverá los elementos al buzón de archivo después de tres años. 
  
1. En la **Página etiquetas de retención** , haga clic en **nueva etiqueta**![nuevo icono](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)y, a continuación, seleccione **aplicado automáticamente a todo el buzón (predeterminado)**. 
    
2. En la página **nueva etiqueta aplicada automáticamente a todo el buzón (predeterminado)** , complete los campos siguientes: 
    
    ![Configuración para crear una nueva etiqueta de directiva predeterminada de archivado](media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
1. **Nombre** de Escriba un nombre para la nueva etiqueta de retención. 
    
2. **Acción de retención** Seleccione **mover a archivo** para mover elementos al buzón de archivo cuando expire el período de retención. 
    
3. **Período de retención** Seleccione **cuando el elemento alcanza la siguiente antigüedad (en días)** y, a continuación, escriba la duración del período de retención. Para este escenario, los elementos se moverán al buzón de archivo después de 1095 días (3 años).
    
4. **Comentario** Opcional Escriba un comentario que explique el propósito de la etiqueta de retención personalizada. 
    
3. Haga clic en **Guardar** para crear la DPT de archivo personalizada. 
    
    La nueva DPT de archivo se muestra en la lista de etiquetas de retención.
    
### <a name="create-a-custom-deletion-default-policy-tag"></a>Crear una etiqueta de directiva predeterminada de eliminación personalizada
  
A continuación, creará otra DPT personalizada, pero ésta será una directiva de eliminación que eliminará permanentemente los elementos después de 7 años.
  
1. En la **Página etiquetas de retención** , haga clic en **nueva etiqueta**![nuevo icono](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)y, a continuación, seleccione **aplicado automáticamente a todo el buzón (predeterminado)**. 
    
2. En la página **nueva etiqueta aplicada automáticamente a todo el buzón (predeterminado)** , complete los campos siguientes: 
    
    ![Configuración para crear una nueva etiqueta de directiva predeterminada de eliminación](media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
1. **Nombre** de Escriba un nombre para la nueva etiqueta de retención. 
    
2. **Acción de retención** Seleccione **eliminar permanentemente** para purgar los elementos del buzón de correo cuando expire el período de retención. 
    
3. **Período de retención** Seleccione **cuando el elemento alcanza la siguiente antigüedad (en días)** y, a continuación, escriba la duración del período de retención. Para este escenario, los elementos se purgarán después de 2555 días (7 años).
    
4. **Comentario** Opcional Escriba un comentario que explique el propósito de la etiqueta de retención personalizada. 
    
3. Haga clic en **Guardar** para crear la DPT de eliminación personalizada. 
    
    La nueva DPT de eliminación se muestra en la lista de etiquetas de retención.
    
### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Crear una etiqueta de directiva de retención personalizada para la carpeta elementos eliminados
  
La última etiqueta de retención que creará es una etiqueta de directiva de retención (RPT) personalizada para la carpeta elementos eliminados. Esta etiqueta eliminará los elementos de la carpeta elementos eliminados después de 5 años y proporciona un período de recuperación en el que los usuarios pueden usar la herramienta recuperar elementos eliminados para recuperar un elemento.
  
1. En la **Página etiquetas de retención** , haga clic en **nueva etiqueta** ![nuevo icono](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)y, a continuación, seleccione **aplicado automáticamente a una carpeta predeterminada**. 
    
2. En la página **nueva etiqueta aplicada automáticamente a una carpeta predeterminada** , complete los campos siguientes: 
    
    ![Configuración para crear una nueva etiqueta de directiva de retención para la carpeta elementos eliminados](media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
1. **Nombre** de Escriba un nombre para la nueva etiqueta de retención. 
    
2. **Aplicar esta etiqueta a la siguiente carpeta predeterminada** En la lista desplegable, seleccione **elementos eliminados**.
    
3. **Acción de retención** Seleccione **eliminar y permitir recuperación** para eliminar elementos cuando expire el período de retención, pero permitir a los usuarios recuperar un elemento eliminado dentro del período de retención de elementos eliminados (que de forma predeterminada son 14 días). 
    
4. **Período de retención** Seleccione **cuando el elemento alcanza la siguiente antigüedad (en días)** y, a continuación, escriba la duración del período de retención. Para este escenario, los elementos se eliminarán después de 1825 días (5 años).
    
5. **Comentario** Opcional Escriba un comentario que explique el propósito de la etiqueta de retención personalizada. 
    
3. Haga clic en **Guardar** para crear la RPT personalizada para la carpeta elementos eliminados. 
    
    La nueva RPT se muestra en la lista de etiquetas de retención.

## <a name="step-3-create-a-new-retention-policy"></a>Paso 3: crear una nueva Directiva de retención

Después de crear las etiquetas de retención personalizadas, el siguiente paso consiste en crear una nueva Directiva de retención y agregar las etiquetas de retención. Agregará las tres etiquetas de retención personalizadas que creó en el paso 2 y las etiquetas integradas mencionadas en la primera sección. En el paso 4, asignará esta nueva Directiva de retención a los buzones de usuario.
  
1. En el EAC, vaya a **** \> **directivas de retención**de administración de cumplimiento.
    
2. En la **Página directivas de retención** , haga clic en](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **nuevo** ![icono nuevo.
    
3. En el cuadro **nombre** , escriba un nombre para la nueva Directiva de retención; por ejemplo, **Directiva de archivo y eliminación de Alpine House**. 
    
4. En **etiquetas de retención**, haga clic en](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **Agregar** ![nuevo icono.
    
    Se muestra una lista de las etiquetas de retención de la organización. Nota se muestran las etiquetas personalizadas que creó en el paso 2.
    
5. Agregue las 9 etiquetas de retención resaltadas en la siguiente captura de pantalla (estas etiquetas se describen con más detalle en la sección [más información](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo) ). Para agregar una etiqueta de retención, selecciónela y, a continuación, haga clic en **Agregar**. 
    
    ![Agregar etiquetas de retención a la nueva Directiva de retención](media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > Puede seleccionar varias etiquetas de retención Si mantiene presionada la tecla **Ctrl** y, a continuación, hace clic en cada etiqueta. 
  
6. Una vez que haya agregado las etiquetas de retención, haga clic en **Aceptar**.
    
7. En la página **nueva Directiva de retención** , haga clic en **Guardar** para crear la nueva Directiva. 
    
    La nueva Directiva de retención se muestra en la lista. Selecciónelo para mostrar las etiquetas de retención vinculadas en el panel de detalles.
    
    ![La nueva Directiva de retención y la lista de etiquetas de retención vinculadas](media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>Paso 4: asignar la nueva Directiva de retención a los buzones de usuario

Cuando se crea un nuevo buzón de correo, se le asigna de forma predeterminada una directiva de retención denominada Directiva de MRM predeterminada. En este paso, reemplazará esta directiva de retención (porque un buzón solo puede tener asignada una directiva de retención) asignando la nueva Directiva de retención que ha creado en el paso 3 a los buzones de usuario de la organización. En este paso se supone que asignará la nueva Directiva a todos los buzones de la organización.
  
1. En el EAC, vaya a **Destinatarios** \> **Buzones de correo**.
    
    Se muestra una lista de todos los buzones de usuario de la organización. 
    
2. Para seleccionar todos los buzones, haga clic en el primero de la lista, mantenga presionada la tecla **MAYÚS** y, a continuación, haga clic en el último de la lista. 
    
3. En el panel de detalles de la parte derecha del EAC, en **edición en masa**, haga clic en **más opciones**.
    
4. En **Directiva de retención**, haga clic en **Actualizar**.
    
5. En la página **Directiva de retención de asignación masiva** , en la lista desplegable **seleccionar Directiva** de retención, seleccione la Directiva de retención que ha creado en el paso 3; por ejemplo, **Directiva de archivo y retención de Alpine House**.
    
6. Haga clic en **Guardar** para guardar la nueva asignación de directiva de retención. 
    
7. Para comprobar que la nueva Directiva de retención se asignó a los buzones, puede hacer lo siguiente: Seleccione un buzón en la página buzones de correo y, a continuación, haga clic en Editar. 
    
1. Seleccione un buzón en la página buzones de **correo** y, a continuación](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png), haga clic en **Editar** ![edición. 
    
2. En la página de propiedades del buzón del usuario seleccionado, haga clic en **características de buzón**.
    
    El nombre de la nueva directiva asignada al buzón se muestra en la lista desplegable **Directiva de retención** . 

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>Opcional Paso 5: ejecutar el Asistente para carpeta administrada para aplicar la nueva configuración

Después de aplicar la nueva Directiva de retención a los buzones del paso 4, puede tardar hasta 7 días en Exchange Online para aplicar la nueva configuración de retención a los buzones. Esto se debe a que un proceso denominado el Asistente para carpeta administrada procesa los buzones una vez cada 7 días. En lugar de esperar a que se ejecute el Asistente para carpeta administrada, puede obligar a que esto suceda mediante la ejecución del cmdlet **Start-ManagedFolderAssistant** en Exchange Online PowerShell. 
  
 **¿Qué sucede cuando se ejecuta el Asistente para carpeta administrada?** Para aplicar la configuración de la Directiva de retención, inspeccione los elementos del buzón de correo y determine si están sujetos a retención. A continuación, se marcan los elementos sujetos a retención con la etiqueta de retención correspondiente y, a continuación, se lleva a cabo la acción de retención especificada en los elementos anteriores a su antigüedad de retención. 
  
Estos son los pasos para conectarse a PowerShell de Exchange Online y, a continuación, ejecutar el Asistente para carpeta administrada en todos los buzones de la organización.
  
1. En el equipo local, abra Windows PowerShell y ejecute el siguiente comando.
    
    ```
    $UserCredential = Get-Credential
    ```

    En el cuadro de diálogo solicitud de credenciales para **Windows PowerShell** , escriba el nombre de usuario y la contraseña de su cuenta de administrador global de Office 365 y, a continuación, haga clic en **Aceptar**.
    
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
    > Para obtener más información o si tiene problemas para conectarse a su organización de Exchange Online, vea [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283). 
  
5. Ejecute los dos comandos siguientes para iniciar el Asistente para carpeta administrada para todos los buzones de usuario de la organización.
    
    ```
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

Esto es todo. Ha configurado una directiva de archivo y eliminación para la organización de Alpine House.
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a>Opcional Paso 6: convertir la nueva Directiva de retención en la opción predeterminada para su organización

En el paso 4, tiene que asignar la nueva Directiva de retención a los buzones existentes. Sin embargo, puede configurar Exchange Online para que la nueva Directiva de retención se asigne a los nuevos buzones que se creen en el futuro. Para ello, debe usar Exchange Online PowerShell para actualizar el plan de buzón de correo predeterminado de su organización. Un *plan de buzón de correo* es una plantilla que configura las propiedades de los nuevos buzones de forma automática.  En este paso opcional, puede reemplazar la Directiva de retención actual asignada al plan de buzón (de forma predeterminada, la Directiva de MRM predeterminada) con la Directiva de retención que ha creado en el paso 3. Después de actualizar el plan de buzón de correo, la nueva Directiva de retención se asignará a los nuevos buzones.

1. [Conéctese a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) o vea el paso 5.

2. Ejecute el siguiente comando para mostrar información sobre los planes de buzón de correo de su organización.

    ```
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```
    Anote el plan de buzón que se establece como predeterminado.

3. Ejecute el siguiente comando para asignar la nueva Directiva de retención que creó en el paso 3 (por ejemplo, la **Directiva de archivo y retención de Alpine House**) al plan de buzón de correo predeterminado. En este ejemplo se supone que el nombre del plan de buzón predeterminado es **ExchangeOnlineEnterprise**.

    ```
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```
4. Puede volver a ejecutar el comando en el paso 2 para comprobar que la Directiva de retención asignada al plan de buzones de correo predeterminado se ha cambiado.

## <a name="more-information"></a>Más información

- ¿Cómo se calcula la antigüedad de retención? La antigüedad de retención de los elementos del buzón de correo se calcula a partir de la fecha de entrega o la fecha de creación de elementos como borradores de mensajes que no se envían pero que son creados por el usuario. Cuando el Asistente para carpeta administrada procesa elementos en un buzón de correo, marca una fecha de inicio y una fecha de caducidad para todos los elementos que tienen etiquetas de retención con la acción eliminar y permitir recuperación o eliminar permanentemente retención. Los elementos que tienen una etiqueta de archivo se marcan con una fecha de movimiento. 
    
- En la tabla siguiente se proporciona más información sobre cada etiqueta de retención que se agrega a la Directiva de retención personalizada que se creó siguiendo los pasos de este tema.
    
    |**Etiqueta de retención**|**Qué hace esta etiqueta**|**¿Integrada o personalizada?**|**Type**|
    |:-----|:-----|:-----|:-----|
    |Mover a archivo desde Alpine House a 3 años  <br/> |Mueve los elementos que tienen un antigüedad de 1095 días (3 años) al buzón de archivo.  <br/> |Personalizado (vea [el paso 2: crear nuevas etiquetas de retención para las directivas de archivo y eliminación](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Etiqueta de directiva predeterminada (archivo); Esta etiqueta se aplica automáticamente a todo el buzón.  <br/> |
    |Eliminación permanente de Alpine House de 7 años  <br/> |Elimina permanentemente los elementos del buzón de correo principal o del buzón de archivo cuando tienen 7 años de antigüedad.  <br/> |Personalizado (vea [el paso 2: crear nuevas etiquetas de retención para las directivas de archivo y eliminación](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Etiqueta de directiva predeterminada (eliminación); Esta etiqueta se aplica automáticamente a todo el buzón.  <br/> |
    |Eliminar y permitir la recuperación de los elementos eliminados de Alpine House 5 años  <br/> |Elimina los elementos de la carpeta elementos eliminados que tienen 5 años de antigüedad. Los usuarios pueden recuperar estos elementos durante un máximo de 14 días después de su eliminación.<sup>\*</sup> <br/> |Personalizado (vea [el paso 2: crear nuevas etiquetas de retención para las directivas de archivo y eliminación](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Etiqueta de directiva de retención (elementos eliminados); Esta etiqueta se aplica automáticamente a los elementos de la carpeta elementos eliminados.  <br/> |
    |Mover a archivo los elementos recuperables después de 14 días  <br/> |Mueve los elementos que han estado en la carpeta elementos recuperables durante 14 días a la carpeta elementos recuperables del buzón de archivo.  <br/> |Integrado  <br/> |Etiqueta de directiva de retención (elementos recuperables); Esta etiqueta se aplica automáticamente a los elementos de la carpeta elementos recuperables.  <br/> |
    |Correo electrónico no deseado  <br/> |Elimina permanentemente los elementos que han estado en la carpeta de correo no deseado durante 30 días. Los usuarios pueden recuperar estos elementos durante un máximo de 14 días después de su eliminación.<sup>\*</sup> <br/> |Integrado  <br/> |Etiqueta de directiva de retención (correo no deseado); Esta etiqueta se aplica automáticamente a los elementos de la carpeta correo electrónico no deseado.  <br/> |
    |Eliminar después de un mes  <br/> |Elimina de forma permanente los elementos que tienen 30 días de antigüedad. Los usuarios pueden recuperar estos elementos durante un máximo de 14 días después de su eliminación.<sup>\*</sup> <br/> |Integrado  <br/> |Informático Esta etiqueta puede ser aplicada por los usuarios.  <br/> |
    |Eliminar después de un año  <br/> |Elimina de forma permanente los elementos que tienen 365 días de antigüedad. Los usuarios pueden recuperar estos elementos durante un máximo de 14 días después de su eliminación.<sup>\*</sup> <br/> |Integrado  <br/> |Informático Esta etiqueta puede ser aplicada por los usuarios.  <br/> |
    |No eliminar nunca  <br/> |Esta etiqueta impide que los elementos se eliminen mediante una directiva de retención.  <br/> |Integrado  <br/> |Informático Esta etiqueta puede ser aplicada por los usuarios.  <br/> |
    |Mover al archivo después de 1 años en forma personal  <br/> |Mueve elementos al buzón de archivo después de un año.  <br/> |Integrado  <br/> |Informático Esta etiqueta puede ser aplicada por los usuarios.  <br/> |
   
    > <sup>\*</sup>Los usuarios pueden usar la herramienta recuperar elementos eliminados en Outlook y Outlook en la web (anteriormente conocido como Outlook Web App) para recuperar un elemento eliminado dentro del período de retención de elementos eliminados, que de forma predeterminada son 14 días en Exchange Online. Un administrador puede usar Windows PowerShell para aumentar el período de retención de elementos eliminados a un máximo de 30 días. Para obtener más información, vea: [recuperar elementos eliminados en Outlook para Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) y [cambiar el período de retención de elementos eliminados para un buzón de correo en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940) .
  
- El uso de la etiqueta de retención Recoverable **Items 14 Days to Archive** Retention Tag ayuda a liberar espacio de almacenamiento en la carpeta elementos recuperables del buzón de correo principal del usuario. Esto es útil cuando el buzón de un usuario se coloca en retención, lo que significa que no se eliminará nada permanentemente el buzón del usuario. Sin mover elementos al buzón de archivo, es posible que se alcance la cuota de almacenamiento de la carpeta elementos recuperables en el buzón principal. Para obtener más información acerca de este y cómo evitarlo, consulte [aumentar la cuota de elementos recuperables para los buzones de correo en retención](https://go.microsoft.com/fwlink/p/?LinkId=786479).
