---
title: Configurar las directivas de datos adJuntos seguros de Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection: M365-security-compliance
description: Definir directivas de datos adJuntos seguros para proteger a su organización de archivos malintencionados en el correo electrónico.
ms.openlocfilehash: dc3235dc8225a46ee28ea8bd0342721b4d55f4f0
ms.sourcegitcommit: 32cb896aef370764ec6e8f8278ebaf16f1c5ff37
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2019
ms.locfileid: "30123941"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Configurar las directivas de datos adJuntos seguros de Office 365 ATP

Los usuarios envían, reciben y comparten con regularidad datos adjuntos, como documentos, presentaciones, hojas de cálculo, etc. No siempre es fácil saber si los datos adjuntos son seguros o malintencionados solo mirando un mensaje de correo electrónico. Y lo último que desea es tener un dato malintencionado para llegar a través del cual se causan estragos en su organización. Afortunadamente, la [protección contra amenazas avanzada de Office 365](office-365-atp.md) (ATP) puede resultar útil. Puede configurar directivas de [datos adjuntos seguros de ATP](atp-safe-attachments.md) para ayudar a garantizar que su organización está protegida contra ataques de datos adjuntos de correo electrónico no seguro. 
  
## <a name="what-to-do"></a>Qué hacer 
  
1. [Revisión de los requisitos previos](#review-the-prerequisites)
    
2. [Configurar una directiva de datos adJuntos seguros de ATP](#set-up-an-atp-safe-attachments-policy)
    
3. [Obtener información sobre las opciones de directiva de datos adJuntos seguros de ATP](#learn-about-atp-safe-attachments-policy-options)
    
## <a name="step-1-review-the-prerequisites"></a>Paso 1: revisar los requisitos previos

- Asegúrese de que su organización tiene la [protección contra amenazas avanzada de Office 365](office-365-atp.md).
    
- Asegúrese de que tiene los permisos necesarios. Para definir (o editar) las directivas de ATP, debe tener asignado un rol apropiado. En la tabla siguiente se describen algunos ejemplos: <br>

    |Rol  |Dónde y cómo se asigna  |
    |---------|---------|
    |Administrador global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
    |Administrador de seguridad |Centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
    |Administración de la organización de Exchange Online |Centro de administración de[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
    Para obtener más información acerca de los roles y los permisos, consulte perMissions [in the Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

- [Obtener información sobre las opciones de directiva de datos adjuntos seguros de ATP](#learn-about-atp-safe-attachments-policy-options) (en este artículo). Algunas opciones, como las opciones supervisar o reemplazar, pueden dar lugar a un retraso de correo electrónico menor mientras se analizan los datos adjuntos. Para evitar retrasos en los mensajes, considere la posibilidad de usar la [entrega dinámica y la vista previa](dynamic-delivery-and-previewing.md).
    
- Espere hasta 30 minutos para que la directiva nueva o actualizada se extienda a todos los centros de seguridad de Office 365.
    
## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Paso 2: configurar (o editar) una directiva de datos adJuntos seguros de ATP
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa. 
    
2. en el centro de navegación &amp; izquierdo de Office 365 Security Compliance Center, en **administración de amenazas**, seleccione **directiva** \> de datos adjuntos **seguros**.
    
3. Si ve la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams**, le recomendamos que seleccione esta opción. Esto permitirá la [protección contra amenazas avanzada de office 365 para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) para el entorno de Office 365. 
    
4. Elija **nuevo** (el botón nuevo es similar a un signo más **+**()) para comenzar a crear la Directiva.
    
5. Especifique el nombre, la descripción y la configuración de la Directiva.<br/><br/>**Ejemplo:** Para configurar una directiva denominada "sin demoras" que entregue inmediatamente los mensajes de todos los usuarios y vuelva a adjuntar los datos adjuntos después de su examen, puede especificar la siguiente configuración: 
    
      - En el cuadro **nombre** , escriba sin retrasos.
    
      - En el cuadro **Descripción** , escriba una descripción como, entrega los mensajes inmediatamente y vuelve a adjuntar los datos adjuntos después del análisis.
    
      - En la sección respuesta, elija la opción de **entrega dinámica** . ([Obtenga más información sobre la vista previa y la entrega dinámica con datos adjuntos seguros de ATP](dynamic-delivery-and-previewing.md)).
    
      - En la sección **redirigir datos** adjuntos, seleccione la opción Habilitar redireccionamiento y escriba la dirección de correo electrónico de su administrador global de Office 365, administrador de seguridad o Analista de seguridad que investigará los datos adjuntos malintencionados. 
    
      - En la sección **aplicado a** , elija **el dominio del destinatario es**y, a continuación, seleccione su dominio. Elija **Agregar**y, después, haga clic en **Aceptar**.
    
6. Elija **Guardar**.
    
Considere la posibilidad de configurar varias directivas de datos adJuntos seguros de ATP para su organización. Estas directivas se aplicarán en el orden en que aparezcan en la página de **datos adjuntos seguros de ATP** . Una vez definida o modificada una directiva, permita al menos 30 minutos para que las directivas entren en vigor en los centros de recursos de Microsoft. 
  
## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Paso 3: información sobre las opciones de directiva de datos adJuntos seguros de ATP

A medida que configure las directivas de datos adJuntos seguros de ATP, podrá elegir entre varias opciones, como monitor, bloqueo, reemplazo, entrega dinámica, etc. En caso de que se haya preguntado sobre lo que hacen estas opciones, en la tabla siguiente se resumen cada uno de ellos y su efecto.
  
|**Opción**|**Efecto**|**Se usa cuando se desea:**|
|:-----|:-----|:-----|
|**Off** <br/> |No analiza los datos adjuntos en busca de malware  <br/> No retrasa la entrega de mensajes  <br/> |Desactivar el análisis para remitentes internos, escáneres, faxes o hosts inteligentes que solo enviarán datos adjuntos conocidos y buenos  <br/> Evitar retrasos innecesarios en el correo interno de enrutamiento  <br/> **Esta opción no se recomienda para la mayoría de los usuarios. Permite activar el análisis de datos adJuntos seguros de ATP para un grupo pequeño de remitentes internos.**           |
|**Monitor** <br/> |Entrega los mensajes con datos adjuntos y, a continuación, realiza un seguimiento de lo que ocurre con malware detectado  <br/> |Ver dónde se encuentra el malware detectado en su organización  <br/> |
|**Desbloquear** <br/> |Impide que se prosigan los mensajes con datos adjuntos de malware detectados  <br/> Envía mensajes con malware detectado a [cuarentena en Office 365](manage-quarantined-messages-and-files.md) donde un administrador o Analista de seguridad puede revisar y liberar (o eliminar) dichos mensajes  <br/> Bloquea los mensajes y datos adjuntos futuros de forma automática  <br/> |Proteger a su organización de ataques repetidos con los mismos datos adjuntos de malware  <br/> |
|**Reemplazar** <br/> |Quita los datos adjuntos de malware detectados  <br/> Notifica a los destinatarios que se han quitado datos adjuntos  <br/> Envía mensajes con malware detectado a [cuarentena en Office 365](manage-quarantined-messages-and-files.md) donde un administrador o Analista de seguridad puede revisar y liberar (o eliminar) dichos mensajes  <br/> |Elevar la visibilidad a los destinatarios que los datos adjuntos se quitaron debido al malware detectado  <br/> |
|**Entrega dinámica** <br/> |Entrega los mensajes inmediatamente  <br/> Reemplaza datos adjuntos con un archivo de marcador de posición hasta que se completa la búsqueda y, a continuación, vuelve a adjuntar los datos adjuntos si no se detecta malware  <br/> Incluye funciones de vista previa de datos adjuntos para la mayoría de los PDF y archivos de Office durante el examen  <br/> Envía mensajes con malware detectado a cuarentena donde un administrador o Analista de seguridad puede revisar y liberar (o eliminar) dichos mensajes  <br/> [Obtener información sobre la vista previa y la entrega dinámica con datos adJuntos seguros de ATP](dynamic-delivery-and-previewing.md) <br/> |Evitar retrasos en los mensajes al proteger a los destinatarios de archivos malintencionados  <br/> Permitir a los destinatarios obtener una vista previa de los datos adjuntos en modo seguro mientras se lleva a cabo el análisis  <br/> |
|**Habilitar redireccionamiento** <br/> |Se aplica cuando se elige la opción supervisar, bloquear o reemplazar  <br/> Envía datos adjuntos a una dirección de correo electrónico especificada en la que los administradores o analistas de seguridad pueden investigar  <br/> |Permitir que los administradores de seguridad y analistas investiguen datos adjuntos sospechosos  <br/> |
   
## <a name="next-steps"></a>Pasos siguientes

Una vez que se hayan implementado las directivas de datos adJuntos seguros de ATP, puede ver cómo está trabajando ATP para su organización consultando los informes. Vea los siguientes recursos para obtener más información:
- [Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)
- [Usar el explorador en el &amp; centro de seguridad y cumplimiento](use-explorer-in-security-and-compliance.md)

Manténgase al tanto de las nuevas características que llegarán a ATP. visite el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) y obtenga información sobre [las nuevas características que se agregan a ATP](office-365-atp.md#new-features-in-office-365-atp).
 