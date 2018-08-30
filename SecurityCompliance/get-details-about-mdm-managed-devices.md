---
title: Obtener detalles acerca de los dispositivos administrados por Mobile Device Management (MDM) para Office 365
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MBS150
- MET150
ms.assetid: 5602963c-a1f2-4c21-afb9-f66cd7dca1f0
description: En este artículo se muestra cómo usar Windows PowerShell para obtener detalles sobre los dispositivos de la organización que ha configurado para la administración de dispositivos móviles para Office 365.
ms.openlocfilehash: 2e406d3583e7892531b7c74bef0db374672956c7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272535"
---
# <a name="get-details-about-devices-managed-by-mobile-device-management-mdm-for-office-365"></a>Obtener detalles acerca de los dispositivos administrados por Mobile Device Management (MDM) para Office 365

En este artículo se muestra cómo usar Windows PowerShell para obtener detalles sobre los dispositivos de la organización que ha configurado para la administración de dispositivos móviles para Office 365. 
  
## <a name="what-device-details-can-i-get"></a>¿Qué detalles del dispositivo se debe obtener?

Éste es un desglose.
  
|**Detalle**|**Qué buscar en PowerShell**|
|:-----|:-----|
|Dispositivo está [inscrito en MDM para Office 365](enroll-your-mobile-device.md) <br/> |El valor del parámetro *isManaged* es:  <br/> **True** = dispositivo está inscrito.  <br/> **False** = no está inscrito el dispositivo.  <br/> |
|Dispositivo es compatible con las [directivas de seguridad de dispositivo](https://go.microsoft.com/fwlink/?linkid=615144) <br/> |El valor del parámetro *isCompliant* es:  <br/> **True** = es compatible con las directivas de dispositivo.  <br/> **False** = no es compatible con las directivas de dispositivo.  <br/> |
   
![Flujo que muestra los valores de parámetro AAD Shell para si se inscriben dispositivos y reclamación](media/647b70f4-f886-41ef-8bff-04773a1da278.png)
  
> [!NOTE]
> Los comandos y las secuencias de comandos en este artículo también devolverá obtener información detallada sobre todos los dispositivos que son administrados por [Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune). 
  
## <a name="before-you-begin"></a>Antes de empezar

Hay algunas cosas que necesitará para configurado para ejecutar los comandos y las secuencias de comandos que se describen en este artículo.
  
### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Paso 1: Descargar e instalar Azure Active Directory módulo para Windows PowerShell

Para obtener más información sobre estos pasos, vea [Connect to Office 365 PowerShell](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell).
  
1. Vaya a [Microsoft Asistente en línea de servicios de inicio de sesión para RTWl de profesionales de TI](https://www.microsoft.com/en-us/download/details.aspx?id=41950) y haga clic en **Descargar** para Ayudante para el inicio de sesión de Microsoft Online Services. 
    
2. Instale el Módulo Microsoft Azure Active Directory para Windows PowerShell siguiendo estos pasos:
    
    1. Abra un símbolo del sistema de PowerShell con permisos de administrador.
        
    2. Ejecute el `Install-Module MSOnline` comando.
        
    3. Si se le pida instalar el proveedor de NuGet, escriba `Y` y presione ENTRAR.
        
    4. Si se le pida instalar el módulo de PSGallery, escriba `Y` y presione ENTRAR.
        
    5. Después de la instalación, cierre la ventana de comandos de PowerShell.
    
### <a name="step-2-connect-to-your-office-365-subscription"></a>Paso 2: Conectarse a la suscripción de Office 365

1. En el Windows Azure Active Directory módulo para Windows PowerShell, ejecute el siguiente comando.</br>  
  `$UserCredential = Get-Credential`

2. En el cuadro de diálogo **Solicitud de credenciales de Windows PowerShell** , escriba el nombre de usuario y la contraseña de su cuenta de administrador global de Office 365 y, a continuación, haga clic en **Aceptar**.
    
3. Ejecute el siguiente comando.</br>
    `
  Connect-MsolService -Credential $UserCredential
  `

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Paso 3: Compruebe que se encuentra capaz de ejecutar scripts de PowerShell

> [!NOTE]
> Puede omitir este paso si ya está configurado para ejecutar scripts de PowerShell. 
  
Para ejecutar la secuencia de comandos **Get-MsolUserDeviceComplianceStatus.ps1** , debe habilitar la ejecución de scripts de PowerShell. 
  
1. Desde el escritorio de Windows, haga clic en **Inicio**y, a continuación, escriba Windows PowerShell. Haga clic con el botón secundario del mouse en **Windows PowerShell**y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. Ejecute el siguiente comando.</br>
  `Set-ExecutionPolicy RemoteSigned`

3. Cuando se le solicite, escriba `Y` y, a continuación, presione ENTRAR. 
    
## <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>Ejecute el cmdlet Get-MsolDevice para mostrar detalles para todos los dispositivos de la organización

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.
    
2. Ejecute el siguiente comando.</br>
  ```
  Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
  ```

Para obtener más ejemplos, vea [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).
  
## <a name="run-a-script-to-get-device-details"></a>Ejecutar un script para obtener detalles del dispositivo

### <a name="first-save-the-script-to-your-computer"></a>En primer lugar, guarde la secuencia de comandos en el equipo

1. Copie y pegue el siguiente texto en el Bloc de notas.</br> 
  ```
  param (
      [PSObject[]]$users = @(),
      [Switch]$export,
      [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
      [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
  [System.Collections.IDictionary]$script:schema = @{
      
      DeviceId = ''
      DeviceOSType = ''
      DeviceOSVersion = ''
      DeviceTrustLevel = ''
      DisplayName = ''
      IsCompliant = ''
      IsManaged = ''
      ApproximateLastLogonTimestamp = ''
      DeviceObjectId = ''    
      RegisteredOwnerUpn = ''
      RegisteredOwnerObjectId = ''
      RegisteredOwnerDisplayName = ''
  }
  function createResultObject
  {
      [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
      return $resultObject
  }
  If ($users.Count -eq 0)
  {
      $users = Get-MsolUser
  }
  [PSObject[]]$result = foreach ($u in $users)
  {
      
      [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
      foreach ($d in $devices)
      {
          [PSObject]$deviceResult = createResultObject
          $deviceResult.DeviceId = $d.DeviceId 
          $deviceResult.DeviceOSType = $d.DeviceOSType 
          $deviceResult.DeviceOSVersion = $d.DeviceOSVersion 
          $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
          $deviceResult.DisplayName = $d.DisplayName
          $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
          $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
          $deviceResult.DeviceObjectId = $d.ObjectId
          $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
          $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
          $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
          $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
          $deviceResult
      }
  }
  If ($export)
  {
      $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
  }
  Else
  {
      $result
  }
  
  ```

2. Guardar como un archivo de secuencia de comandos de Windows PowerShell mediante el uso de la extensión de archivo **. ps1**. </br>Ejemplo:</br> `Get-MsolUserDeviceComplianceStatus.ps1`.
    
### <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Ejecute el script para obtener información del dispositivo para una única cuenta de usuario

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.
    
2. Navegue a la carpeta donde guardó la secuencia de comandos. Por ejemplo, si guardó a C:\PS-Scripts, ejecutaría el comando siguiente.</br>
    `cd C:\PS-Scripts`

3. Ejecute el siguiente comando para identificar al usuario que desea obtener detalles del dispositivo. En este ejemplo se obtienen los detalles para bar@example.com.</br>
  ```
  $u = Get-MsolUser -UserPrincipalName bar@example.com
  ```

4. Ejecute el siguiente comando para iniciar la secuencia de comandos.</br>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

En el escritorio de Windows, se exporta la información como un archivo CSV. Puede usar los parámetros adicionales para especificar el nombre de archivo y ruta de acceso de la CSV.
  
### <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Ejecute el script para obtener información del dispositivo para un grupo de usuarios

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.
    
2. Navegue a la carpeta donde guardó la secuencia de comandos. Por ejemplo, si guardó a C:\PS-Scripts, ejecutaría el comando siguiente.</br>
  `cd C:\PS-Scripts`

3. Ejecute el comando siguiente para identificar el grupo que desea obtener detalles del dispositivo. En este ejemplo se obtienen los detalles para los usuarios del grupo FinanceStaff.</br>
  ```
  $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
  ```

4. Ejecute el siguiente comando para iniciar la secuencia de comandos.</br>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

En el escritorio de Windows, se exporta la información como un archivo CSV. Puede usar los parámetros adicionales para especificar el nombre de archivo y ruta de acceso de la CSV.
  
## <a name="more-info"></a>Más información

[Información general de MDM para Office 365](overview-of-mdm.md)
  
[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)
  

