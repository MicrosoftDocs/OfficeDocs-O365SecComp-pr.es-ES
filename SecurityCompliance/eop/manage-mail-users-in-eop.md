---
title: Administrar usuarios de correo en EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: La definición de usuarios de correo es una parte importante de la administración del servicio de Protección en línea de Exchange (EOP).
ms.openlocfilehash: 69ed6460966a399ac5b1e3cf71bd985917bec82c
ms.sourcegitcommit: f57d411e06c955d648dfa1a2a473aa45416e1377
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "36620494"
---
# <a name="manage-mail-users-in-eop"></a>Administrar usuarios de correo en EOP

La definición de usuarios de correo es una parte importante de la administración del servicio de Protección en línea de Exchange (EOP). Hay varios métodos para administrar usuarios en EOP:
  
- Usar la sincronización de directorios para administrar usuarios de correo: si su empresa tiene cuentas de usuario existentes en un entorno local de Active Directory, puede sincronizarlas con Azure Active Directory (AD), donde se almacena una copia de las cuentas en la nube. Cuando sincroniza las cuentas de usuario existentes con Azure Active Directory, puede ver esos usuarios en el panel **Destinatarios** del Centro de administración de Exchange (EAC). Se recomienda usar la sincronización de directorios. 
    
- Usar el EAC para administrar usuarios de correo: agregar y administrar usuarios de correo directamente en el EAC. Es la manera más fácil de agregar usuarios de correo y resulta útil para agregar un usuario cada vez.
    
- Usar Windows PowerShell remoto para administrar usuarios de correo: agregar y administrar usuarios de correo ejecutando Windows PowerShell remoto. Este método es útil para agregar varios registros y crear scripts.
    
> [!NOTE]
> Puede Agregar usuarios en el centro de administración de Microsoft 365, pero estos usuarios no se pueden usar como destinatarios de correo. 
  
## <a name="before-you-begin"></a>Antes de empezar

- Los procedimientos descritos en este tema requieren permisos específicos. Vea cada procedimiento para ver la información de permisos.
    
- Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.
    
> [!TIP]
> ¿Tiene algún problema? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a>Usar la sincronización de directorios para administrar usuarios de correo

En esta sección se proporciona información sobre cómo administrar usuarios de correo mediante la sincronización de directorios.
  
> [!IMPORTANT]
> Si usa la sincronización de directorios para administrar los destinatarios, puede seguir agregando y administrando usuarios en el centro de administración de Microsoft 365, pero no se sincronizarán con Active Directory local. Esto se debe a que la sincronización de directorios solo sincroniza los destinatarios de Active Directory local con la nube. 
  
> [!TIP]
>  Se recomienda usar la sincronización de directorios con las siguientes características: > **Listas de remitentes bloqueados y de remitentes seguros de Outlook**: cuando se sincronizan con el servicio, estas listas tienen prioridad sobre filtrado de correo no deseado del servicio. Esto permite a los usuarios administrar sus propias listas de remitentes seguros y remitentes bloqueados por usuario o por dominio. > **Bloqueo perimetral basado en directorios (DBEB)**: para obtener más información sobre DBEB, vea [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx). > **Cuarentena de correo no deseado de usuarios finales**: para poder acceder a la cuarentena de correo no deseado de usuarios finales, los usuarios finales deben tener un identificador de usuario de Office 365 y una contraseña válidos. Los clientes de EOP que protejan los buzones locales deben ser usuarios de correo electrónico válidos. > **Reglas de flujo de correo** : cuando se usa la sincronización de directorios, los usuarios y grupos de Active Directory existentes se cargan automáticamente en la nube y, a continuación, se pueden crear reglas de flujo de correo (también conocidas como reglas de transporte) dirigidas a usuarios específicos o grupos sin tener que agregarlos manualmente a través del EAC o PowerShell de Exchange Online Protection. Tenga en cuenta que los [grupos de distribución dinámicos](https://go.microsoft.com/fwlink/?LinkId=507569) no se pueden sincronizar mediante la sincronización de directorios. 
  
 **Antes de empezar**
  
Obtenga los permisos necesarios y prepárese para la sincronización de directorios, tal como se describe en [Preparar la sincronización de directorios](https://go.microsoft.com/fwlink/p/?LinkId=308908).
  
### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a>Para sincronizar los directorios de usuario con Azure Active Directory Connect (AAD Connect)

Para sincronizar los usuarios con Azure Active Directory (AAD), primero tiene que **activar la sincronización de directorios**, tal como se describe en activar la sincronización de [directorios](https://go.microsoft.com/fwlink/p/?LinkId=308909).

A continuación se encuentra la instalación y la configuración de un equipo local para ejecutar AAD Connect (si todavía no tiene una, merece la pena comprobar por adelantado el tiempo). En el artículo siguiente se indica cómo configurar y sincronizar las cuentas de forma local a Azure AD con AAD Connect.

[Configuración de AAD Connect, la manera Express.](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-install-express)

Pero, antes de hacerlo, asegúrese de que se cumplen [usted cumple los requisitos previos] (https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-install-prerequisitesy [Elija el tipo de instalación](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-install-select-installation). El vínculo publicado anteriormente es un breve artículo para las instalaciones rápidas. También puede encontrar artículos en [instalaciones personalizadas](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-install-custom)o [la autenticación de paso a través](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-pta-quick-start) si es necesario.

> [!IMPORTANT]
> Cuando finaliza el Asistente de configuración de la herramienta de sincronización de Microsoft Azure Active Directory, se crea la cuenta **MSOL_AD_SYNC** en el bosque de Active Directory. Esta cuenta se utiliza para leer y sincronizar la información de Active Directory local. Para que la sincronización de directorios funcione correctamente, asegúrese de que esté abierto TCP 443 en el servidor de sincronización de directorios local 

Una vez configurada la sincronización, asegúrese de comprobar que EOP se está sincronizando correctamente. En el EAC, vaya a **Destinatarios** \> **Contactos** y vea que la lista de usuarios se haya sincronizado correctamente desde el entorno local.
    
## <a name="use-the-eac-to-manage-mail-users"></a>Usar el EAC para administrar usuarios de correo

En esta sección se proporciona información sobre cómo agregar y administrar usuarios de correo electrónico directamente en el EAC.
  
 **Antes de empezar**
  
Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Usuarios, contactos y grupos de roles" en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).
  
### <a name="to-add-a-mail-user-in-the-eac"></a>Para agregar un usuario de correo en el EAC

1. Para crear un usuario de correo electrónico, vaya a **Destinatarios**\> **Contactos** en el EAC y después haga clic en **Nuevo +**.
    
2. En la página **Nuevo usuario de correo**, escriba la información del usuario, incluido lo siguiente: 
    
   ****

|**Propiedad de usuario de correo**|**Descripción**|
|:-----|:-----|
|**Nombre**, **Iniciales** y **Apellidos** <br/> |Escriba el nombre completo del usuario en los cuadros correspondientes.  <br/> |
|**Nombre para mostrar** <br/> |Escriba un nombre con un máximo de 64 caracteres. De manera predeterminada, este cuadro muestra los nombres en los cuadros **Nombre**, **Iniciales** y **Apellidos** si hay alguno. El nombre para mostrar es un campo obligatorio.  <br/> |
|**Alias** <br/> |Escriba un alias exclusivo, con un máximo de 64 caracteres, para el usuario. El alias es obligatorio.  <br/> |
|**Dirección de correo electrónico externa** <br/> |Escriba la dirección de correo electrónico externa del usuario.  <br/> |
|**Id. de usuario** <br/> |Escriba el nombre que el usuario de correo usará para iniciar sesión en el servicio. El nombre de inicio de sesión del usuario consta de un nombre de usuario a la izquierda del símbolo arroba (@) y un sufijo a la derecha. Por lo general, el sufijo es el nombre de dominio en el que reside la cuenta de usuario.  <br/> |
|**Contraseña nueva** <br/> |Escriba la contraseña que el usuario de correo usará para iniciar sesión en el servicio. Asegúrese de que la contraseña que proporciona cumple los requisitos de longitud, complejidad e historial de la contraseña del dominio en el que va a crear la cuenta de usuario.  <br/> |
|**Confirmar contraseña** <br/> |Vuelva a escribir la contraseña para confirmarla.  <br/> |
   
3. Haga clic en **Guardar** para crear el nuevo usuario de correo. El nuevo usuario debe aparecer en la lista de usuarios. 
    
### <a name="to-edit-or-remove-a-mail-user-in-the-eac"></a>Para editar o quitar un usuario de correo en el EAC

- En el EAC, vaya a **Destinatarios** \> **Contactos**. En la lista de usuarios, haga clic en el usuario que desea ver o modificar y, a continuación **** ![, seleccione Editar](../media/ITPro-EAC-EditIcon.gif) icono Editar para actualizar la configuración del usuario según sea necesario. Puede cambiar el nombre, el alias o la información de contacto del usuario, y puede registrar información detallada sobre el rol del usuario en la organización. También puede seleccionar un usuario y elegir **Quitar**![Icono de quitar](../media/ITPro-EAC-RemoveIcon.gif) para eliminarlo. 
    
## <a name="use-remote-windows-powershell-to-manage-mail-users"></a>Usar Windows PowerShell remoto para administrar usuarios de correo

En esta sección se proporciona información sobre cómo agregar y administrar usuarios de correo mediante Windows PowerShell remoto.
  
 **Antes de empezar**
  
- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Usuarios, contactos y grupos de roles" en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).
    
- Tenga en cuenta que, al crear usuarios de correo mediante los cmdlets de PowerShell remoto, podría encontrarse con límites.
    
- Este cmdlet usa un método de procesamiento por lotes que provoca un retraso en la propagación de unos minutos antes de que los resultados del cmdlet sean visibles.
    
- Para aprender cómo usar Windows PowerShell para conectarse a Exchange Online Protection, vea [Conectarse a Exchange Online Protection mediante PowerShell remoto](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).
    
 **Para agregar un usuario de correo mediante PowerShell remoto**
  
En este ejemplo, se usa el cmdlet [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) para crear una cuenta de usuario habilitada para correo para Jeffrey Zeng en EOP con los siguientes detalles: 
  
- El nombre es Jeffrey y el apellido es Zeng.
    
- El nombre es Jeffrey y el nombre para mostrar es Jeffrey Zeng.
    
- El alias es jeffreyz.
    
- La dirección de correo electrónico externa es jzeng@tailspintoys.com.
    
- El nombre de inicio de sesión de Office 365 es jeffreyz@contoso.onmicrosoft.com.
    
- La contraseña es Pa$$word1.
    
```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

 **Para comprobar que esto funcionó**
  
Ejecute el cmdlet [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) como se indica a continuación para mostrar información sobre el nuevo usuario de correo Jeffrey Zeng: 
  
```Powershell
Get-User "Jeffrey Zeng"

```

 **Para editar las propiedades de un usuario de correo mediante PowerShell remoto**
  
Use los cmdlets [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) y [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) para ver o cambiar las propiedades de los usuarios de correo. 
  
Este ejemplo establece la dirección de correo electrónico externa de Pilar Pinilla.
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

Este ejemplo establece la propiedad de la empresa para todos los usuarios de correo de Contoso.
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}

```

 **Para comprobar que esto funcionó**
  
En el ejemplo anterior, donde cambiamos las propiedades del usuario de correo Pilar Pinilla, use el cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) para comprobar los cambios. (Tenga en cuenta que puede ver varias propiedades de varios contactos de correo). 
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List 

```

En el ejemplo anterior, donde la propiedad Empresa estaba configurada para Contoso para todos los usuarios de correo, ejecute el siguiente comando para comprobar los cambios:
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> Este cmdlet usa un método de procesamiento por lotes que provoca un retraso en la propagación de unos minutos antes de que los resultados del cmdlet sean visibles. 
  
 **Para quitar un usuario de correo mediante PowerShell remoto**
  
En este ejemplo se usa el cmdlet [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) para eliminar el usuario Jeffrey Zeng: 
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 **Para comprobar que esto funcionó**
  
Ejecute el cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) como se indica a continuación. Obtendrá un mensaje de error porque el usuario no existe. 
  
```Powershell
Get-Recipient Jeffrey | fl
```


