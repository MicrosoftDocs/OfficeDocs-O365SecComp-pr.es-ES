---
title: Configurar las directivas de seguros vínculos con Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 11/02/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
description: Configurar directivas de vínculos seguros para proteger la organización de vínculos malintencionados en archivos de Word, Excel, PowerPoint y Visio, así como en mensajes de correo electrónico.
ms.openlocfilehash: 2fce043aaf6e5e844415bd0caaaded8d30c18291
ms.sourcegitcommit: 147768bbe44c8c98c02fa29ae9d882cee4ec2d6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238462"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Configurar las directivas de seguros vínculos con Office 365 ATP

[Vínculos seguros ATP](atp-safe-links.md) , una característica de [Protección de amenaza avanzada de Office 365](office-365-atp.md) (ATP), puede ayudar a proteger su organización de vínculos malintencionados utilizados en suplantación de identidad y otros ataques. Si tiene el requisito [permisos asignados en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md), puede configurar las directivas de vínculos seguros de ATP para ayudar a garantizar que, cuando las personas, haga clic en direcciones web (URL), la organización está protegida. Las directivas de vínculos seguros ATP pueden configurarse para examinar las direcciones URL en correo electrónico y las direcciones URL en los documentos de Office.
  
[Las nuevas características se están agregando continuamente ATP](office-365-atp.md#new-features-are-continually-being-added-to-atp). Cuando se agregan nuevas características, debe realizar ajustes en las directivas de ATP seguros vínculos existentes.

## <a name="what-to-do"></a>Qué hacer 
  
1. [Revise los requisitos previos](#review-the-prerequisites).
    
2. [Revisar y editar la directiva de vínculos seguros ATP predeterminada que se aplica a todos los usuarios](#define-an-atp-safe-links-policy-that-applies-to-everyone). Por ejemplo, puede [Configurar la lista de direcciones URL bloqueada personalizada para vínculos seguros de ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).
    
3. [Agregar o editar las directivas de destinatarios de correo electrónico específica](#add-a-policy-for-specific-email-recipients), incluida la [configuración de la lista de direcciones URL "No reescritura" personalizada para vínculos seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
    
4. [Obtenga información acerca de las opciones de directiva de vínculos seguros de ATP](#learn-about-atp-safe-links-policy-options) (en este artículo), incluida la configuración para los cambios recientes
    
## <a name="step-1-review-the-prerequisites"></a>Paso 1: Revisar los requisitos previos

- Asegúrese de que la organización tiene [La protección de amenaza avanzada de Office 365](office-365-atp.md).
    
- Asegúrese de que tiene los permisos necesarios para definir o editar las directivas de ATP. Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).

- Asegúrese de que los clientes de Office están configurados para usar [Autenticación moderno](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (Esto es para la protección de vínculos seguros de ATP en documentos de Office).
    
- [Obtenga información acerca de las opciones de directiva de vínculos seguros de ATP](#learn-about-atp-safe-links-policy-options) (en este artículo). 

- Permitir hasta 30 minutos para la directiva de nueva o actualizada para propagarse a todos los centros de datos de Office 365.
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>Paso 2: Definir (o revisar) en la directiva de vínculos seguros de ATP que se aplica a todos los usuarios

Cuando tenga [La protección de amenaza avanzada de Office 365](office-365-atp.md), tendrá una directiva de vínculos seguros ATP predeterminada que se aplica a todas las personas de su organización. Asegúrese de revisar y, si es necesario, modificar la directiva predeterminada.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela. 
    
2. En la izquierda, en **administración de amenaza**, elija **directiva \> ** **Vínculos seguros**.
    
3. En la sección de **directivas que se aplican a toda la organización** , seleccione **predeterminado**y, a continuación, elija **Editar** (el botón Editar se parece a un lápiz). 
    
    ![Haga clic en Editar para editar la directiva predeterminada para la protección de vínculos seguros](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. En la sección **Bloquear las siguientes direcciones URL** , especifique uno o más direcciones URL en la que se desean impedir que los usuarios de la organización de visitar. (Vea [Configurar una lista de direcciones URL bloqueada personalizada con vínculos seguros ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md)).
    
5. En la sección de **configuración que se aplica a contenido excepto correo electrónico** , active (o desactive) las opciones que desea usar. (Se recomienda que seleccione todas las opciones). 
    
6. Elija **Guardar**.
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>Paso 3: Agregar (o editar) en las directivas de ATP seguros vínculos que se aplican a los destinatarios de correo electrónico específica

Después de haber revisado (o editar) la directiva de vínculos seguros ATP predeterminada que se aplica a todos los usuarios, el siguiente paso es definir directivas adicionales que se aplican a determinados destinatarios. Por ejemplo, puede especificar excepciones a la directiva predeterminada mediante la definición de una directiva adicional. 
  
1. Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela. 
    
2. En la izquierda, en **administración de amenaza**, elija la **Directiva**.
    
3. Elija **vínculos seguros**.
    
4. En la sección de **directivas que se aplican a determinados destinatarios** , elija **nuevo** (el botón nuevo se parece a un signo más ( **+**)).<br/>![Elija nuevo para agregar una directiva de vínculos seguros para los destinatarios de correo electrónico específica](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. Especifique el nombre, la descripción y la configuración de la directiva.<br/>**Ejemplo:** Para configurar una directiva no denominada "hacer clic directa a través de" que no se permiten a personas en un determinado grupo de la organización y haga clic en a través de un sitio Web específico sin protección de vínculos seguros ATP, podría especificar la siguiente configuración recomendada: 
    
  - En el cuadro **nombre** , no escriba haga clic en directo a través de.
    
  - En el cuadro **Descripción** , escriba una descripción como, impide que las personas en ciertos grupos de hacer clic en a través de un sitio Web sin necesidad de comprobación de vínculos seguros de ATP.
    
  - En la sección **Seleccione la acción** , elija **en**.
    
  - Seleccione **Utilizar datos adjuntos seguros para examinar el contenido descargable**.
    
  - Si esta opción está disponible, seleccione **Aplicar vínculos seguros a los mensajes enviados dentro de la organización**.
    
  - Seleccione **no permitir que el usuario haga clic en a través de a la dirección URL original**.
    
  - (Esto es opcional) En la sección **no de reescritura de las siguientes direcciones URL** , especifique una o más direcciones URL en la que se consideran seguros para su organización. (Consulte [Configurar una "No reescritura" las direcciones URL de lista personalizada con vínculos seguros ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))
    
  - En la sección **Aplicar a** , elija **el destinatario es un miembro de**y, a continuación, elija el grupo o grupos que desea incluir en la directiva. Elija **Agregar**y, a continuación, elija **Aceptar**.
    
6. Elija **Guardar**.
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>Paso 4: Información sobre las opciones de directiva de vínculos seguros de ATP

Como configurar o editar las directivas de vínculos seguros ATP, verá varias opciones disponibles. En caso de que se lo pregunte ¿cuáles son estas opciones, en la siguiente tabla se describe cada uno de ellos y su efecto. Recuerde que hay dos tipos principales de directivas de vínculos seguros de ATP para definir o editar:
- una [directiva predeterminada](#default-policy-options) que se aplica a todos los usuarios 
- [las directivas que se definen para destinatarios concretos](#policies-that-apply-to-specific-email-recipients) de adicionales 

### <a name="default-policy-options"></a>Opciones de directiva predeterminada

Opciones de directiva predeterminada se aplican a todas las personas de su organización.

|Esta opción  |Se obtiene este resultado  |
|---------|---------|
| **Bloquear las siguientes direcciones URL** <br/>    | Permite a su organización tengan una lista personalizada de direcciones URL que se bloquean automáticamente. Cuando los usuarios haga clic en una dirección URL en esta lista, se le lleva a una [página de advertencia](atp-safe-links-warning-pages.md) que explica por qué se bloqueó la dirección URL.<br/> Para obtener más información, vea [Set up una lista personalizada de direcciones URL bloqueada con vínculos seguros de ATP      |
| **Office 365 ProPlus, Office para iOS y Android** <br/>    | Cuando se selecciona esta opción, ATP vínculos seguros protección se aplica a las direcciones URL en los documentos que se abren en Office 365 ProPlus (Word, Excel y PowerPoint en Windows o Mac OS), documentos de Office en iOS o dispositivos Android, 2016 de Visio en Windows y Office Online (Word En línea en línea de PowerPoint, Excel Online proporciona y OneNote en línea), que el usuario ha iniciado sesión en Office 365. <br/><br/>Si ve sólo **2016 de Office en Windows**, a continuación, las actualizaciones de la característica no hayan alcanzado su entorno de Office 365 todavía (y se próximamente). Hasta entonces, la protección de vínculos seguros de ATP se aplica a Word 2016, 2016 de Excel, PowerPoint 2016 o 2016 de Visio que se ejecutan en Windows.            |
| **No realizar un seguimiento cuando los usuarios, haga clic en vínculos seguros de ATP** <br/>  | Cuando se selecciona esta opción, haga clic en datos de las direcciones URL en los documentos de Word, Excel, PowerPoint y Visio no se almacena.  <br/> |
|**No permita que los usuarios haga clic en a través de vínculos de seguros ATP a la dirección URL original** <br/> |Cuando se selecciona esta opción, los usuarios no pueden continuar más allá de una [página de advertencia](atp-safe-links-warning-pages.md) a una dirección URL que se determina que es malintencionado.  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>Directivas que se aplican a los destinatarios de correo electrónico específica

|Esta opción  |Se obtiene este resultado  |
|---------|---------|
|**Off** <br/> |No examina las direcciones URL en mensajes de correo electrónico.  <br/> Le permite definir una regla de excepción, como una regla que no examina las direcciones URL en mensajes de correo electrónico para un grupo específico de destinatarios.  <br/> |
|**En** <br/> |Vuelve a escribir las direcciones URL a los usuarios de la ruta a través de protección de vínculos seguros ATP cuando los usuarios, haga clic en las direcciones URL en mensajes de correo electrónico.  <br/> Comprueba una dirección URL cuando se hace clic en una lista de direcciones URL de dominios bloqueadas o malintencionadas.  <br/> |
|**Usar los datos adjuntos seguros para examinar el contenido descargable** <br/> |Cuando se selecciona esta opción, se examinan las direcciones URL que apuntan a contenido descargable.  <br/> |
|**Vínculos seguros se aplican a los mensajes enviados dentro de la organización** <br/> | Cuando esta opción está disponible y seleccionada, la protección de vínculos seguros de ATP se aplica a los mensajes enviados entre las personas de su organización, proporcionada las cuentas de correo electrónico se hospedan en Office 365 de correo electrónico.  <br/> |
|**No hacen el seguimiento de clics del usuario** <br/> |Cuando se selecciona esta opción, haga clic en datos de las direcciones URL en correo electrónico de los remitentes externos no se almacena. Haga clic en dirección URL de seguimiento de vínculos dentro de los mensajes de correo electrónico enviados dentro de la organización no se admite actualmente.  <br/> |
|**No permitir a los usuarios haga clic en a través de a la dirección URL original** <br/> |Cuando se selecciona esta opción, los usuarios no pueden continuar más allá de una [página de advertencia](atp-safe-links-warning-pages.md) a una dirección URL que se determina que es malintencionado.  <br/> |
|**No vuelva a escribir las siguientes direcciones URL** <br/> |Sale de las direcciones URL tal y como están. Mantiene una lista personalizada de direcciones URL seguras que no es necesario examinar si hay un grupo específico de destinatarios de correo electrónico de la organización.  Vea [Configurar una personalizado lista direcciones URL "No reescritura" using ATP seguros vínculos](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para obtener más información, incluidos los cambios recientes para admitir para comodín asteriscos (\*).<br/> |
   
## <a name="next-steps"></a>Pasos siguientes

Una vez que las directivas de vínculos seguros ATP, puede ver cómo funciona ATP para su organización mediante la visualización de informes. Vea los siguientes recursos para obtener más información:

- [Visualización de informes para la protección de amenaza avanzada de Office 365](view-reports-for-atp.md)

- [Use el explorador en la seguridad &amp; centro de cumplimiento](use-explorer-in-security-and-compliance.md) 