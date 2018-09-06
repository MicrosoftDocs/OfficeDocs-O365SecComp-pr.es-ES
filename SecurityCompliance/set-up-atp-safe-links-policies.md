---
title: Configurar las directivas de seguros vínculos con Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
description: Configurar directivas de vínculos seguros para proteger la organización de vínculos malintencionados en archivos de Word, Excel, PowerPoint y Visio, así como en mensajes de correo electrónico.
ms.openlocfilehash: 01ba394053e2da137d5adafa4799040507ab4270
ms.sourcegitcommit: f8cc2c7bad31d04c99a8eca5e0f8fad72494087a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "23848090"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Configurar las directivas de seguros vínculos con Office 365 ATP

[Vínculos seguros ATP](atp-safe-links.md) , una característica de [Protección de amenaza avanzada de Office 365](office-365-atp.md) (ATP), puede ayudar a proteger su organización de vínculos malintencionados utilizados en suplantación de identidad y otros ataques. Si tiene el requisito [permisos asignados en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md), puede configurar las directivas de vínculos seguros de ATP para ayudar a garantizar que, cuando las personas, haga clic en direcciones web (URL), la organización está protegida. Las directivas de vínculos seguros ATP pueden configurarse para examinar las direcciones URL en correo electrónico y las direcciones URL en los documentos de Office.
  
Las nuevas características se están agregando continuamente a los vínculos seguros ATP:
  
- En las últimas de 2017 octubre, protección de vínculos seguros de ATP se ha ampliado para aplicar a las direcciones URL en correo electrónico, así como las direcciones URL en los documentos de Office 365 ProPlus, como Word, Excel, PowerPoint en Windows y en dispositivos Android, iOS y los archivos de Visio en Windows.
    
- A partir de marzo de 2018, protección de vínculos seguros de ATP se ha ampliado para aplicar a correo electrónico enviado entre las personas de una organización.
    
- A partir de las últimas de 2018 de marzo, protección de vínculos seguros de ATP se ha ampliado para aplicar a las direcciones URL en Office Online (en línea de Word, Excel Online, Online de PowerPoint y OneNote en línea) y Office 365 ProPlus en Mac OS.
    
- A partir de mayo de 2018, [páginas de advertencia](atp-safe-links-warning-pages.md) se actualizan con una nueva combinación de colores, más detalles y la capacidad para seguir a un sitio a pesar de las recomendaciones determinadas. 

Cuando se agregan nuevas características, debe realizar ajustes en las directivas de ATP seguros vínculos existentes.

## <a name="what-to-do"></a>Qué hacer 
  
1. [Revise los requisitos previos](#review-the-prerequisites).
    
2. [Revisar y editar la directiva de vínculos seguros ATP predeterminada que se aplica a todos los usuarios](#define-an-atp-safe-links-policy-that-applies-to-everyone). Por ejemplo, puede [Configurar la lista de direcciones URL bloqueada personalizada para vínculos seguros de ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).
    
3. [Agregar una directiva de destinatarios de correo electrónico específica](#add-a-policy-for-specific-email-recipients), incluida la [configuración de la lista de direcciones URL "No reescritura" personalizada para vínculos seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
    
4. [Obtenga información acerca de las opciones de directiva de vínculos seguros de ATP](#learn-about-atp-safe-links-policy-options) (en este artículo), incluida la configuración para los cambios recientes
    
## <a name="review-the-prerequisites"></a>Revise los requisitos previos

- Asegúrese de que la organización tiene [La protección de amenaza avanzada de Office 365](office-365-atp.md).
    
- Asegúrese de que tiene los permisos necesarios para definir o editar las directivas de ATP. Vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).
    
- [Obtenga información acerca de las opciones de directiva de vínculos seguros de ATP](#learn-about-atp-safe-links-policy-options) (en este artículo). 

- Asegúrese de que los clientes de Office están configurados para usar [Autenticación moderno](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).
    
- Permitir hasta 30 minutos para la directiva de nueva o actualizada para propagarse a todos los centros de datos de Office 365.
    
## <a name="define-an-atp-safe-links-policy-that-applies-to-everyone"></a>Definir una directiva de vínculos seguros de ATP que se aplica a todos los usuarios

Cuando haya avanzado de protección contra amenazas en Office 365 Enterprise, tendrá una directiva de vínculos seguros ATP predeterminada que se aplica a todas las personas de su organización. Puede editar la directiva en la seguridad &amp; centro de cumplimiento o el centro de administración de Exchange. **Se recomienda usar la seguridad &amp; centro de cumplimiento para revisar o modificar cualquiera de las directivas de ATP**.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela. 
    
2. En la izquierda, en **administración de amenaza**, elija **directiva \> ** **Vínculos seguros**.
    
3. En la sección de **directivas que se aplican a toda la organización** , seleccione **predeterminado**y, a continuación, elija **Editar** (el botón Editar se parece a un lápiz). 
    
    ![Haga clic en Editar para editar la directiva predeterminada para la protección de vínculos seguros](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. En la sección **Bloquear las siguientes direcciones URL** , especifique uno o más direcciones URL en la que se desean impedir que los usuarios de la organización de visitar. (Vea [Configurar una lista de direcciones URL bloqueada personalizada con vínculos seguros ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md)).
    
5. En la sección de **configuración que se aplica a contenido excepto correo electrónico** , active (o desactive) las opciones que desea usar. (Se recomienda que seleccione todas las opciones). 
    
6. Elija **Guardar**.
    
## <a name="add-a-policy-for-specific-email-recipients"></a>Agregar una directiva de destinatarios de correo electrónico específicos

Después de haber revisado la directiva para todos los usuarios, considere la posibilidad de definir directivas adicionales para grupos específicos de destinatarios de correo electrónico. Esto le permite especificar excepciones a la directiva predeterminada. Puede agregar las directivas de uso de la seguridad &amp; centro de cumplimiento (recomendado) o el centro de administración de Exchange. **Se recomienda usar la seguridad &amp; centro de cumplimiento para revisar o modificar cualquiera de las directivas de ATP**.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela. 
    
2. En la izquierda, en **administración de amenaza**, elija la **Directiva**.
    
3. Elija **vínculos seguros**.
    
4. En la sección de **directivas que se aplican a determinados destinatarios** , elija **nuevo** (el botón nuevo se parece a un signo más ( **+**)).
    
    ![Elija nuevo para agregar una directiva de vínculos seguros para los destinatarios de correo electrónico específica](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. Especifique el nombre, la descripción y la configuración de la directiva.
    
    **Ejemplo:** Para configurar una directiva no denominada "hacer clic directa a través de" que no se permiten a personas en un determinado grupo de la organización y haga clic en a través de un sitio Web específico sin protección de vínculos seguros ATP, podría especificar la siguiente configuración recomendada: 
    
  - En el cuadro **nombre** , no escriba haga clic en directo a través de.
    
  - En el cuadro **Descripción** , escriba una descripción como, impide que las personas en ciertos grupos de hacer clic en a través de un sitio Web sin necesidad de comprobación de vínculos seguros de ATP.
    
  - En la sección **Seleccione la acción** , elija **en**.
    
  - Seleccione **Utilizar datos adjuntos seguros para examinar el contenido descargable**.
    
  - Si esta opción está disponible, seleccione **Aplicar vínculos seguros a los mensajes enviados dentro de la organización**.
    
  - Seleccione **no permitir que el usuario haga clic en a través de a la dirección URL original**.
    
  - (Esto es opcional) En la sección **no de reescritura de las siguientes direcciones URL** , especifique una o más direcciones URL en la que se consideran seguros para su organización. (Consulte [Configurar una "No reescritura" las direcciones URL de lista personalizada con vínculos seguros ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))
    
  - En la sección **Aplicar a** , elija **el destinatario es un miembro de**y, a continuación, elija el grupo o grupos que desea incluir en la directiva. Elija **Agregar**y, a continuación, elija **Aceptar**.
    
6. Elija **Guardar**.
    
## <a name="learn-about-atp-safe-links-policy-options"></a>Obtenga información acerca de las opciones de directiva de vínculos seguros de ATP

Como configurar o editar una directiva de vínculos seguros ATP, verá varias opciones disponibles. En caso de que se lo pregunte ¿cuáles son estas opciones, en la siguiente tabla se describe cada uno de ellos y su efecto. Tenga en cuenta que existen dos tipos principales de directivas para definir o editar: una directiva predeterminada que se aplica a todos los usuarios y las directivas adicionales que se definen para destinatarios concretos.
  
|**Para esta directiva**|**Esta opción**|**Se obtiene este resultado**|
|:-----|:-----|:-----|
|Predeterminado (una vez definido, la directiva predeterminada se aplica a todas las personas de la organización)  <br/> |**Bloquear las siguientes direcciones URL** <br/> |Permite a su organización tengan una lista personalizada de direcciones URL que se bloquean automáticamente. Cuando los usuarios haga clic en una dirección URL en esta lista, se le lleva a una [página de advertencia](atp-safe-links-warning-pages.md) que explica por qué se bloqueó la dirección URL.<br/> Consulte [Configurar una lista personalizada de direcciones URL bloqueada mediante ATP seguros vínculos](set-up-a-custom-blocked-urls-list-wtih-atp.md) para obtener más detalles, como la compatibilidad con recién agregado hasta tres asteriscos comodín (\*).  <br/> |
|Predeterminada  <br/> |**Office 365 ProPlus, Office para iOS y Android** <br/> |Cuando se selecciona esta opción, ATP vínculos seguros protección se aplica a las direcciones URL en los documentos que se abren en Office 365 ProPlus (Word, Excel y PowerPoint en Windows o Mac OS), documentos de Office en iOS o dispositivos Android, 2016 de Visio en Windows y Office Online (Word En línea en línea de PowerPoint, Excel Online proporciona y OneNote en línea), que el usuario ha iniciado sesión en Office 365. </br></br>Si ve sólo **2016 de Office en Windows**, a continuación, las actualizaciones de la característica no hayan alcanzado su entorno de Office 365 todavía (y se próximamente). Hasta entonces, la protección de vínculos seguros de ATP se aplica a Word 2016, 2016 de Excel, PowerPoint 2016 o 2016 de Visio que se ejecutan en Windows.           |
|Predeterminada  <br/> |**No realizar un seguimiento cuando los usuarios, haga clic en vínculos seguros de ATP** <br/> |Cuando se selecciona esta opción, haga clic en datos de las direcciones URL en los documentos de Word, Excel, PowerPoint y Visio no se almacena.  <br/> |
|Predeterminada  <br/> |**No permita que los usuarios haga clic en a través de vínculos de seguros ATP a la dirección URL original** <br/> |Cuando se selecciona esta opción, los usuarios no pueden continuar más allá de una [página de advertencia](atp-safe-links-warning-pages.md) a una dirección URL que se determina que es malintencionado.  <br/> |
|Una directiva creada para los destinatarios de correo electrónico específica  <br/> |**Off** <br/> |No examina las direcciones URL en mensajes de correo electrónico.  <br/> Le permite definir una regla de excepción, como una regla que no examina las direcciones URL en mensajes de correo electrónico para un grupo específico de destinatarios.  <br/> |
|Una directiva creada para los destinatarios de correo electrónico específica  <br/> |**En** <br/> |Vuelve a escribir las direcciones URL a los usuarios de la ruta a través de protección de vínculos seguros ATP cuando los usuarios, haga clic en las direcciones URL en mensajes de correo electrónico.  <br/> Comprueba una dirección URL cuando se hace clic en una lista de direcciones URL de dominios bloqueadas o malintencionadas.  <br/> |
|Una directiva creada para los destinatarios de correo electrónico específica  <br/> |**Usar los datos adjuntos seguros para examinar el contenido descargable** <br/> |Cuando se selecciona esta opción, se examinan las direcciones URL que apuntan a contenido descargable.  <br/> |
|Una directiva creada para los destinatarios de correo electrónico específica  <br/> |**Vínculos seguros se aplican a los mensajes enviados dentro de la organización** <br/> | Cuando esta opción está disponible y seleccionada, la protección de vínculos seguros de ATP se aplica a los mensajes enviados entre las personas de su organización, proporcionada las cuentas de correo electrónico se hospedan en Office 365 de correo electrónico.  <br/> |
|Una directiva creada para los destinatarios de correo electrónico específica  <br/> |**No hacen el seguimiento de clics del usuario** <br/> |Cuando se selecciona esta opción, haga clic en datos de las direcciones URL en correo electrónico de los remitentes externos no se almacena. Haga clic en dirección URL de seguimiento de vínculos dentro de los mensajes de correo electrónico enviados dentro de la organización no se admite actualmente.  <br/> |
|Una directiva creada para los destinatarios de correo electrónico específica  <br/> |**No permitir a los usuarios haga clic en a través de a la dirección URL original** <br/> |Cuando se selecciona esta opción, los usuarios no pueden continuar más allá de una [página de advertencia](atp-safe-links-warning-pages.md) a una dirección URL que se determina que es malintencionado.  <br/> |
|Una directiva creada para los destinatarios de correo electrónico específica  <br/> |**No vuelva a escribir las siguientes direcciones URL** <br/> |Sale de las direcciones URL tal y como están. Mantiene una lista personalizada de direcciones URL seguras que no es necesario examinar si hay un grupo específico de destinatarios de correo electrónico de la organización.  Vea [Configurar una personalizado lista direcciones URL "No reescritura" using ATP seguros vínculos](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para obtener más información, incluidos los cambios recientes para admitir para comodín asteriscos (\*).<br/> |
   
## <a name="related-topics"></a>Temas relacionados

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[Vínculos de ATP seguros en Office 365](atp-safe-links.md)
  
[Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md)
  
[Configurar una lista de direcciones URL bloqueada personalizada con vínculos seguros de ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md)
  
[Configurar una personalizada lista las direcciones URL "No reescritura" con vínculos seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
  
[Ver los informes de protección contra amenazas de avanzada](view-reports-for-atp.md)

[Los permisos de la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md)
  

