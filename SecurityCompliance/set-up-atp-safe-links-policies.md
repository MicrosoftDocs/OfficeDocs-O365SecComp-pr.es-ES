---
title: Configurar directivas de vínculos seguros de Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection: M365-security-compliance
description: Configure las directivas de vínculos seguros para proteger a su organización de vínculos malintencionados en archivos de Word, Excel, PowerPoint y Visio, así como en mensajes de correo electrónico.
ms.openlocfilehash: db7da9d6ce2d2f2503585c0cde89f2b2626e2afa
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220170"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Configurar directivas de vínculos seguros de Office 365 ATP

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales. Si es un usuario doméstico que busca información sobre vínculos seguros en Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

[Vínculos seguros ATP](atp-safe-links.md), una característica de la [protección contra amenazas avanzada](office-365-atp.md) (atp) de Office 365, puede ayudar a proteger su organización de vínculos malintencionados usados en suplantación de identidad (phishing) y otros ataques. Si dispone de los [permisos necesarios para el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md), puede configurar directivas de vínculos seguros de ATP para ayudar a garantizar que cuando los usuarios hagan clic en direcciones web (URL), su organización esté protegida. Las directivas de vínculos seguros de ATP se pueden configurar para analizar direcciones URL en correo electrónico y direcciones URL en documentos de Office.
  
[Las nuevas características se agregan continuamente a ATP](office-365-atp.md#new-features-in-office-365-atp). A medida que se agreguen nuevas características, es posible que deba realizar ajustes en las directivas de vínculos seguros de ATP existentes.

## <a name="what-to-do"></a>Qué hacer 
  
1. [Revise los requisitos previos](#review-the-prerequisites).
    
2. [Revise y edite la directiva predeterminada de vínculos seguros de ATP que se aplica a todos los usuarios](#define-an-atp-safe-links-policy-that-applies-to-everyone). Por ejemplo, puede [configurar la lista de direcciones URL bloqueadas personalizadas para vínculos seguros ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).
    
3. [Agregar o editar directivas para destinatarios de correo electrónico específicos](#add-a-policy-for-specific-email-recipients), incluida [la configuración de la lista de direcciones URL "no reescribir" personalizadas para vínculos seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
    
4. [Obtener información sobre las opciones de directiva de vínculos seguros de ATP](#learn-about-atp-safe-links-policy-options) (en este artículo), incluida la configuración de cambios recientes.
    
## <a name="step-1-review-the-prerequisites"></a>Paso 1: revisar los requisitos previos

- Asegúrese de que su organización tiene la [protección contra amenazas avanzada de Office 365](office-365-atp.md).
    
- Asegúrese de que tiene los permisos necesarios. Para definir (o editar) las directivas de ATP, debe tener asignado un rol apropiado. En la tabla siguiente se describen algunos ejemplos: <br>

    |Rol  |Dónde y cómo se asigna  |
    |---------|---------|
    |Administrador global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
    |Administrador de seguridad |Centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
    |Administración de la organización de Exchange Online |Centro de administración de[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

    Para obtener más información acerca de los roles y los permisos, consulte perMissions [in the Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Asegúrese de que los clientes de Office estén configurados para usar la [autenticación moderna](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (esto es para la protección de vínculos seguros de ATP en documentos de Office).
    
- [Obtener información sobre las opciones de directiva de vínculos seguros de ATP](#learn-about-atp-safe-links-policy-options) (en este artículo). 

- Espere hasta 30 minutos para que la directiva nueva o actualizada se extienda a todos los centros de seguridad de Office 365.
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>Paso 2: definir (o revisar) la Directiva de vínculos seguros de ATP que se aplica a todos los usuarios

Cuando tenga la [protección contra amenazas avanzada de Office 365](office-365-atp.md), tendrá una directiva predeterminada de vínculos seguros de ATP que se aplica a todos los usuarios de la organización. Asegúrese de revisar y, si es necesario, modifique la directiva predeterminada.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa. 
    
2. En el panel de navegación izquierdo, en **Administración de amenazas**, elija **vínculos seguros**de **directiva \> ** .
    
3. En la sección **directivas que se aplican a toda la organización** , seleccione predeterminado y, a continuación, elija **Editar** (el botón Editar **es**similar a un lápiz).<br/>![Haga clic en Editar para editar la directiva predeterminada para protección de vínculos seguros](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. En la sección **bloquear las siguientes direcciones URL** , especifique una o más direcciones URL en las que desee impedir que los usuarios de la organización puedan visitar. (Consulte [configurar una lista de direcciones URL bloqueadas personalizadas mediante vínculos seguros de ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md)).
    
5. En la sección **configuración que se aplica a los contenidos excepto el correo electrónico** , active (o desactive) las opciones que desee usar. (Le recomendamos que seleccione todas las opciones). 
    
6. Elija **Guardar**.
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>Paso 3: agregar (o editar) directivas de vínculos seguros de ATP que se aplican a destinatarios de correo electrónico específicos

Una vez que haya revisado (o editado) la directiva predeterminada de vínculos seguros de ATP que se aplica a todos los usuarios, el siguiente paso consiste en definir directivas adicionales que se aplicarán a destinatarios específicos. Por ejemplo, puede especificar excepciones a su directiva predeterminada definiendo una directiva adicional. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa. 
    
2. En el panel de navegación izquierdo, en **Administración de amenazas**, elija **Directiva**.
    
3. Elija **vínculos seguros**.
    
4. En la sección **directivas que se aplican a destinatarios específicos** , elija **nuevo** (el botón nuevo es similar a un **+** signo más ()).<br/>![Elija nuevo para agregar una directiva de vínculos seguros para destinatarios de correo electrónico específicos](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. Especifique el nombre, la descripción y la configuración de la directiva.<br/>**Ejemplo:** Para configurar una directiva denominada "no hay clic directo a través de" que no permite a los usuarios de un grupo determinado de su organización hacer clic a través de un sitio web específico sin protección de vínculos seguros de ATP, puede especificar la siguiente configuración recomendada: 
    
  - En el cuadro **nombre** , escriba sin clic directo.
    
  - En el cuadro **Descripción** , escriba una descripción como, para evitar que los usuarios de determinados grupos puedan hacer clic en un sitio web sin verificación de vínculos seguros de ATP.
    
  - En la sección **seleccionar la acción** , elija **activado**.
    
  - Seleccione **usar datos adjuntos seguros para analizar contenido**descargable.
    
  - Si esta opción está disponible, seleccione **aplicar vínculos seguros a los mensajes enviados dentro de la organización**.
    
  - Seleccione no permitir que el **usuario haga clic a través de la dirección URL original**.
    
  - (Opcional) En la sección no **reescribir las siguientes direcciones URL** , especifique una o más direcciones URL que se consideren seguras para su organización. (Consulte [configurar una lista de direcciones URL personalizadas "no reescribir" mediante vínculos seguros ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))
    
  - En la sección **aplicado a** , elija **el destinatario es miembro de**y, a continuación, elija el grupo o los grupos que desea incluir en la Directiva. Elija **Agregar**y, después, haga clic en **Aceptar**.
    
6. Elija **Guardar**.
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>Paso 4: información sobre las opciones de directiva de vínculos seguros de ATP

Al configurar o editar las directivas de vínculos seguros de ATP, verá que hay varias opciones disponibles. En caso de que se pregunte Cuáles son estas opciones, en la tabla siguiente se describe cada una de ellas y su efecto. Recuerde que hay dos tipos principales de directivas de vínculos seguros de ATP que debe definir o editar:
- una [directiva predeterminada](#default-policy-options) que se aplica a todos los usuarios 
- [directivas adicionales que se definen para destinatarios específicos](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>Opciones de directivas preDeterminadas

Las opciones de directiva preDeterminadas se aplican a todos los usuarios de la organización.

|Esta opción  |Se obtiene este resultado  |
|---------|---------|
| **Bloquear las siguientes direcciones URL** <br/>    | Permite a su organización tener una lista personalizada de direcciones URL que se bloquean automáticamente. Cuando los usuarios hagan clic en una dirección URL de esta lista, se les redirigirá a una [Página de advertencia](atp-safe-links-warning-pages.md) que explica por qué se bloquea la dirección URL.<br/> Para obtener más información, consulte [configurar una lista de direcciones URL bloqueadas personalizadas mediante vínculos seguros de ATP      |
| **Office 365 proPlus, Office para iOS y Android** <br/>    | Cuando se selecciona esta opción, la protección de vínculos seguros de ATP se aplica a las direcciones URL de los documentos abiertos en Office 365 proPlus (Word, Excel y PowerPoint en Windows o Mac OS), documentos de Office en iOS o dispositivos Android, Visio 2016 en Windows y Office Online (Word Online, PowerPoint online, Excel online y OneNote online), siempre que el usuario haya iniciado sesión en Office 365. <br/><br/>Si ve solo **office 2016 en Windows**, las actualizaciones de características no han llegado a su entorno de Office 365 todavía (y estarán disponibles próximamente). Hasta entonces, la protección de vínculos seguros de ATP se aplica a Word 2016, Excel 2016, PowerPoint 2016 o Visio 2016 que se ejecutan en Windows.            |
| **No hacer un seguimiento cuando los usuarios hacen clic en ATP vínculos seguros** <br/>  | Cuando se selecciona esta opción, no se almacenan los datos de direcciones URL en los documentos de Word, Excel, PowerPoint y Visio.  <br/> |
|**No permitir que los usuarios haga clic en los vínculos seguros ATP a la dirección URL original** <br/> |Cuando se selecciona esta opción, los usuarios no pueden continuar después de una [Página de advertencia](atp-safe-links-warning-pages.md) en una dirección URL que se determina como malintencionada.  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>Directivas que se aplican a destinatarios de correo electrónico específicos

|Esta opción  |Se obtiene este resultado  |
|---------|---------|
|**Off** <br/> |No examina direcciones URL en mensajes de correo electrónico.  <br/> Permite definir una regla de excepción, como una regla que no examina direcciones URL en mensajes de correo electrónico para un grupo específico de destinatarios.  <br/> |
|**De** <br/> |Reescribe las direcciones URL para enrutar a los usuarios a través de la protección de vínculos seguros ATP cuando los usuarios hacen clic en direcciones URL en mensajes de correo electrónico.  <br/> Comprueba una dirección URL al hacer clic en una lista de direcciones URL malintencionadas o bloqueadas.  <br/> |
|**Usar datos adJuntos seguros para analizar contenido descargable** <br/> |Cuando se selecciona esta opción, se examinan las direcciones URL que apuntan al contenido descargable.  <br/> |
|**Aplicar vínculos seguros a los mensajes enviados dentro de la organización** <br/> | Cuando esta opción está disponible y seleccionada, la protección de vínculos seguros de ATP se aplica a los mensajes de correo electrónico enviados entre las personas de su organización, siempre que las cuentas de correo electrónico se hospeden en Office 365.  <br/> |
|**No hacer un seguimiento de los clics del usuario** <br/> |Cuando se selecciona esta opción, no se almacenan los datos de las direcciones URL del correo electrónico de remitentes externos. Dirección URL haga clic en seguimiento para los vínculos de los mensajes de correo electrónico enviados dentro de la organización actualmente no se admite.  <br/> |
|**No permitir que los usuarios hagan clic a través de la dirección URL original** <br/> |Cuando se selecciona esta opción, los usuarios no pueden continuar después de una [Página de advertencia](atp-safe-links-warning-pages.md) en una dirección URL que se determina como malintencionada.  <br/> |
|**No volver a escribir las siguientes direcciones URL** <br/> |Deja las direcciones URL tal y como están. Mantiene una lista personalizada de direcciones URL seguras que no necesitan análisis para un grupo específico de destinatarios de correo electrónico de la organización.  Consulte [configurar una lista de direcciones URL personalizadas "no reescribir" mediante vínculos seguros ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para obtener más información, incluidos los cambios recientes para la compatibilidad con asteriscos comodín (\*).<br/> |
   
## <a name="next-steps"></a>Pasos siguientes

Una vez que se hayan implementado las directivas de vínculos seguros de ATP, podrá ver cómo ATP está trabajando para sus orgnization consultando los informes. Vea los siguientes recursos para obtener más información:

- [Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)

- [Usar el explorador en el &amp; centro de seguridad y cumplimiento](use-explorer-in-security-and-compliance.md)

Manténgase al tanto de las nuevas características que llegarán a ATP. visite el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) y obtenga información sobre [las nuevas características que se agregan a ATP](office-365-atp.md#new-features-in-office-365-atp).