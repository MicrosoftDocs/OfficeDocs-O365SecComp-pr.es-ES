---
title: Administrar usuarios de correo en EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: La definición de usuarios de correo es una parte importante de la administración del servicio de Protección en línea de Exchange (EOP).
ms.openlocfilehash: 48d530be17a7e75f6e179a50067b1b9526606cb0
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676720"
---
# <a name="manage-mail-users-in-eop"></a>Administrar usuarios de correo en EOP

La definición de usuarios de correo es una parte importante de la administración del servicio de Protección en línea de Exchange (EOP). Hay varios métodos para administrar usuarios en EOP:
  
- Usar la sincronización de directorios para administrar usuarios de correo: si su empresa tiene cuentas de usuario existentes en un entorno local de Active Directory, puede sincronizarlas con Azure Active Directory (AD), donde se almacena una copia de las cuentas en la nube. Cuando sincroniza las cuentas de usuario existentes con Azure Active Directory, puede ver esos usuarios en el panel **Destinatarios** del Centro de administración de Exchange (EAC). Se recomienda usar la sincronización de directorios. 

- Usar el EAC para administrar usuarios de correo: agregar y administrar usuarios de correo directamente en el EAC. Es la manera más fácil de agregar usuarios de correo y resulta útil para agregar un usuario cada vez.

- Usar Windows PowerShell remoto para administrar usuarios de correo: agregar y administrar usuarios de correo ejecutando Windows PowerShell remoto. Este método es útil para agregar varios registros y crear scripts.

> [!NOTE]
> Puede Agregar usuarios en el centro de administración de Microsoft 365, pero estos usuarios no se pueden usar como destinatarios de correo.
  
## <a name="before-you-begin"></a>Antes de empezar

- Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).

- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Usuarios, contactos y grupos de roles" en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).

- Tenga en cuenta que al crear usuarios de correo mediante los cmdlets de PowerShell de Exchange Online Protection, es posible que se encuentre con limitaciones.

- Los comandos de PowerShell de este tema usan un método de procesamiento por lotes que da como resultado un retraso en la propagación de unos minutos antes de que los resultados de los comandos estén visibles.

- Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> ¿Problemas? Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a>Usar la sincronización de directorios para administrar usuarios de correo

En esta sección se proporciona información sobre cómo administrar usuarios de correo mediante la sincronización de directorios.
  
> [!NOTE]
> Si usa la sincronización de directorios para administrar los destinatarios, puede seguir agregando y administrando usuarios en el centro de administración de Microsoft 365, pero no se sincronizarán con Active Directory local. Esto se debe a que la sincronización de directorios solo sincroniza los destinatarios de Active Directory local con la nube. <br/><br/> Se recomienda usar la sincronización de directorios con las siguientes características: <br/><br/>• **Remitente seguro de Outlook y listas**de remitentes bloqueados: cuando se sincronizan con el servicio, estas listas tienen prioridad sobre el filtrado de correo no deseado en el servicio. Esto permite a los usuarios administrar sus propias listas de remitentes seguros y remitentes bloqueados por usuario o por dominio. <br/><br/>• **Bloqueo perimetral basado en directorios (DBEB)**: para obtener más información sobre DBEB, vea [use Directory based Edge blocking to Reject messages sent to invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx). <br/><br/>• **Cuarentena de correo no deseado del usuario final**: para poder obtener acceso a la cuarentena de correo no deseado del usuario final, los usuarios finales deben tener un identificador de usuario y una contraseña de Office 365 válidos. Los clientes de EOP que protejan los buzones locales deben ser usuarios de correo electrónico válidos. <br/><br/>• **Reglas de flujo de correo**: cuando usa la sincronización de directorios, los usuarios y grupos de Active Directory existentes se cargan automáticamente en la nube y, después, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) dirigidas a usuarios específicos o grupos sin tener que agregarlos manualmente a través del EAC o PowerShell de Exchange Online Protection. Tenga en cuenta que los [grupos de distribución dinámicos](https://go.microsoft.com/fwlink/?LinkId=507569) no se pueden sincronizar mediante la sincronización de directorios.
  
Obtenga los permisos necesarios y prepárese para la sincronización de directorios, tal como se describe en [Preparar la sincronización de directorios](https://go.microsoft.com/fwlink/p/?LinkId=308908).
  
### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a>Para sincronizar los directorios de usuario con Azure Active Directory Connect (AAD Connect)

Para sincronizar los usuarios con Azure Active Directory (AAD), primero tiene que **activar la sincronización de directorios**, tal como se describe en activar la sincronización de [directorios](https://go.microsoft.com/fwlink/p/?LinkId=308909).

A continuación se encuentra la instalación y la configuración de un equipo local para ejecutar AAD Connect (si todavía no tiene una, merece la pena comprobar por adelantado el tiempo). El tema de [configuración de AAD Connect, la forma exprés](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) le indica cómo configurar y sincronizar sus cuentas de local a Azure ad con AAD Connect.

Pero, antes de hacerlo, asegúrese de que [cumple los requisitos previos](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)y [Elija el tipo de instalación](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation). El vínculo anterior es un breve artículo para instalaciones rápidas. También puede encontrar artículos en [instalaciones personalizadas](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)o [la autenticación de paso a través](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) si es necesario.

> [!IMPORTANT]
> Cuando finaliza el Asistente de configuración de la herramienta de sincronización de Microsoft Azure Active Directory, se crea la cuenta **MSOL_AD_SYNC** en el bosque de Active Directory. Esta cuenta se utiliza para leer y sincronizar la información de Active Directory local. Para que la sincronización de directorios se realice correctamente, debe asegurarse de que el TCP 443 esté abierto en el servidor de sincronización de directorios local.

Una vez configurada la sincronización, asegúrese de comprobar que EOP se está sincronizando correctamente. En el EAC, vaya a **Destinatarios** \> **Contactos** y vea que la lista de usuarios se haya sincronizado correctamente desde el entorno local.

## <a name="use-the-eac-to-manage-mail-users"></a>Usar el EAC para administrar usuarios de correo

En esta sección se proporciona información sobre cómo agregar y administrar usuarios de correo electrónico directamente en el EAC.
  
### <a name="use-the-eac-to-add-a-mail-user"></a>Usar el EAC para agregar un usuario de correo

1. Para crear un usuario de correo electrónico, vaya a **Destinatarios**\> **Contactos** en el EAC y después haga clic en **Nuevo +**.

2. En la página **Nuevo usuario de correo**, escriba la información del usuario, incluido lo siguiente: 

   ****

   |**Propiedad de usuario de correo**|**Descripción**|
   |:-----|:-----|
   |**Nombre**, **Iniciales** y **Apellidos**|Escriba el nombre completo del usuario en los cuadros correspondientes.|
   |**Nombre para mostrar**|Escriba un nombre con un máximo de 64 caracteres. De manera predeterminada, este cuadro muestra los nombres en los cuadros **Nombre**, **Iniciales** y **Apellidos** si hay alguno. El nombre para mostrar es un campo obligatorio.  |
   |**Alias**|Escriba un alias exclusivo, con un máximo de 64 caracteres, para el usuario. El alias es obligatorio.|
   |**Dirección de correo electrónico externa**|Escriba la dirección de correo electrónico externa del usuario.|
   |**Id. de usuario**|Escriba el nombre que el usuario de correo usará para iniciar sesión en el servicio. El nombre de inicio de sesión del usuario consta de un nombre de usuario a la izquierda del símbolo arroba (@) y un sufijo a la derecha. Por lo general, el sufijo es el nombre de dominio en el que reside la cuenta de usuario.|
   |**Contraseña nueva**|Escriba la contraseña que el usuario de correo usará para iniciar sesión en el servicio. Asegúrese de que la contraseña que proporciona cumple los requisitos de longitud, complejidad e historial de la contraseña del dominio en el que va a crear la cuenta de usuario.|
   |**Confirmar contraseña**|Vuelva a escribir la contraseña para confirmarla.|

3. Haga clic en **Guardar** para crear el nuevo usuario de correo. El nuevo usuario debe aparecer en la lista de usuarios.

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a>Usar el EAC para editar o quitar un usuario de correo

- En el EAC, vaya a **Destinatarios** \> **Contactos**. En la lista de usuarios, haga clic en el usuario que desea ver o modificar y, a continuación **** ![, seleccione Editar](../media/ITPro-EAC-EditIcon.gif) icono Editar para actualizar la configuración del usuario según sea necesario. Puede cambiar el nombre, el alias o la información de contacto del usuario, y puede registrar información detallada sobre el rol del usuario en la organización. También puede seleccionar un usuario y, a continuación **** ![, elegir quitar](../media/ITPro-EAC-RemoveIcon.gif) icono quitar para eliminarlo. 

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a>Uso de PowerShell de Exchange Online Protection para administrar usuarios de correo

En esta sección se proporciona información sobre cómo agregar y administrar usuarios de correo mediante Windows PowerShell remoto.
  
### <a name="use-eop-powershell-to-add-a-mail-user"></a>Usar PowerShell de EOP para agregar un usuario de correo
  
En este ejemplo, se usa el cmdlet [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) para crear una cuenta de usuario habilitada para correo para Jeffrey Zeng en EOP con los siguientes detalles:
  
- El nombre es Jeffrey y el apellido es Zeng.

- El nombre es Jeffrey y el nombre para mostrar es Jeffrey Zeng.

- El alias es jeffreyz.

- La dirección de correo electrónico externa es jzeng@tailspintoys.com.

- El nombre de inicio de sesión de Office 365 es jeffreyz@contoso.onmicrosoft.com.

- La contraseña es Pa$$word1.

```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

Para comprobar que esto funcionó, ejecute el siguiente comando para mostrar información sobre el nuevo usuario de correo Jeffrey Zeng:
  
```Powershell
Get-User -Identity "Jeffrey Zeng"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a>Uso de PowerShell de EOP para editar las propiedades de un usuario de correo
  
Use los cmdlets [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) y [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) para ver o cambiar las propiedades de los usuarios de correo.
  
Este ejemplo establece la dirección de correo electrónico externa de Pilar Pinilla.
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

Este ejemplo establece la propiedad de la empresa para todos los usuarios de correo de Contoso.
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```
  
Para comprobar que esto funcionó, use el cmdlet [Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) para comprobar los cambios. (Tenga en cuenta que puede ver varias propiedades de varios contactos de correo).
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

En el ejemplo anterior, donde la propiedad Empresa estaba configurada para Contoso para todos los usuarios de correo, ejecute el siguiente comando para comprobar los cambios:
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> Este cmdlet usa un método de procesamiento por lotes que provoca un retraso en la propagación de unos minutos antes de que los resultados del cmdlet sean visibles.
  
### <a name="use-eop-powershell-to-remove-a-mail-user"></a>Usar PowerShell de EOP para quitar un usuario de correo
  
En este ejemplo se usa el cmdlet [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) para eliminar el usuario Jeffrey Zeng:
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 **Para comprobar que esto funcionó**
  
Para comprobar que esto funcionó, ejecute el cmdlet [Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) para comprobar que el usuario de correo ya no existe.
  
```Powershell
Get-Recipient Jeffrey | Format-List
```
