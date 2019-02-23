---
title: Threat management in the Office 365 Security &amp; Compliance Center
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0a73d5fa-b2c8-43e7-9ed4-61f0552b1c98
description: Use la administración de amenazas para ayudar a controlar y administrar el acceso de dispositivos móviles a los datos de la organización, proteger la organización contra la pérdida de datos y ayudar a proteger los mensajes entrantes y salientes del software malintencionado y el correo no deseado. También se usa la administración de amenazas para proteger la reputación del dominio y para determinar si los remitentes se falsifican de su dominio de una mala parte de las cuentas.
ms.openlocfilehash: 30083c1e030921598d950afbedc78acab2a24910
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221170"
---
# <a name="threat-management-in-the-office-365-security-amp-compliance-center"></a>Threat management in the Office 365 Security &amp; Compliance Center

Use la administración de amenazas para ayudar a controlar y administrar el acceso de dispositivos móviles a los datos de la organización, proteger la organización contra la pérdida de datos y ayudar a proteger los mensajes entrantes y salientes del software malintencionado y el correo no deseado. También se usa la administración de amenazas para proteger la reputación del dominio y para determinar si los remitentes se falsifican de su dominio de una mala parte de las cuentas.
  
## <a name="how-to-view-and-use-threat-management-in-the-security-amp-compliance-center"></a>Cómo ver y usar la administración de amenazas en el &amp; centro de seguridad y cumplimiento

En Office 365, use el centro &amp; de seguridad y cumplimiento para administrar las amenazas de su organización.
  
 **Para ir directamente al centro de &amp; seguridad y cumplimiento:**
  
1. Vaya a [https://protection.office.com](https://protection.office.com).

2. Inicie sesión en Office 365 con su cuenta profesional o educativa.

3. En el panel izquierdo, seleccione **Administración de amenazas**.

    ![Menú de administración &amp; de amenazas del centro de seguridad y cumplimiento de Office 365](media/dca29ff2-ad6d-4c27-becb-b5947268d55a.png)
  
 **Para ir al centro de &amp; seguridad y cumplimiento mediante el iniciador de aplicaciones de Office 365:**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Seleccione el iniciador ![de aplicaciones el icono del iniciador](media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) de aplicaciones en Office 365 en la esquina superior izquierda y, a continuación, seleccione el icono **seguridad &amp; y cumplimiento** . 

3. En el panel izquierdo, seleccione **Administración de amenazas**.

## <a name="about-threat-management-in-office-365"></a>Acerca de la administración de amenazas en Office 365

Estas opciones están disponibles en **Administración de amenazas** en el &amp; centro de seguridad y cumplimiento.
  
Todavía estamos implementando la administración de amenazas para el &amp; centro de seguridad y cumplimiento, por lo que es posible que no vea todos estos todavía, o que vea más de las opciones que se muestran aquí. Durante la ejecución, algunos de ellos, por ejemplo, el antimalware, DKIM y otros, seguirán disponibles a través del centro de administración de Exchange (EAC) durante un período de tiempo limitado.

En algunos casos, hay pequeñas diferencias entre el EAC y las implementaciones &amp; del centro de cumplimiento de seguridad. Por ejemplo, los caracteres admitidos para filtros de correo no deseado son diferentes entre las dos plataformas. Se proporcionan artículos que proporcionan más información sobre las diferencias específicas cuando se producen.
  
|**Herramienta**|**Descripción**|
|:-----|:-----|
|**Panel, explorador de amenazas e incidentes** <br/> |Una vez habilitados, estos paneles le permiten administrar Office 365 Analytics y la inteligencia de amenazas. Para obtener más información, vea información [General sobre la inteligencia sobre amenazas de Office 365](office-365-ti.md).<br/> |
|**Filtrado de correo** <br/> |Ajuste y supervisión de la configuración que ayuda a evitar el correo no deseado en Office 365. Cree listas permitir o bloquear, determine quién suplanta su dominio y por qué, y configure y vea las directivas de filtro de correo no deseado. Para obtener más información, consulte [protección contra correo no deseado de correo electrónico de Office 365](anti-spam-protection.md).<br/> También puede configurar una directiva para comprobar que los usuarios no envían correo no deseado. Esto puede ocurrir, por ejemplo, si el equipo de un usuario se infecta con malware que está programado para enviar mensajes de correo electrónico. Para saber cómo puede evitar el correo no deseado saliente, consulte [Configure the Outbound spam Policy](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx).<br/> Si actualmente tiene un problema con el correo no deseado, puede usar el [solucionador de problemas de correo no deseado y de malware](https://configure.office.com/Scenario.aspx?sid=73).           |
|**Antimalware** <br/> |Protege contra virus y spyware que viajan hacia o desde su organización en Office 365. Los virus son programas de software malintencionado que, cuando se ejecutan, se replican por sí mismos y modifican otros programas y datos en el equipo. Los virus se propagan por el equipo en busca de que los programas infecten y también se compartan desde un equipo a otro, a menudo a través del correo electrónico. El spyware recopila su información personal, como la información de inicio de sesión, y la envía de vuelta a su autor. Para empezar a configurar las directivas antimalware, vea [Configure anti-malware Policies](https://technet.microsoft.com/library/jj200745%28v=exchg.150%29.aspx).<br/> Si actualmente tiene un problema con malware, puede usar el solucionador de [problemas de correo no deseado y de malware](https://configure.office.com/Scenario.aspx?sid=73).           |
|**DKIM** <br/> |Destinado a los administradores de Office 365 más avanzados, pero disponible para todos los clientes de Office 365, DomainKeys Identified Mail (DKIM) ayuda a garantizar que otros sistemas de correo confían en los mensajes que se envían desde Office 365. DKIM hace esto agregando una firma digital única a los mensajes de correo electrónico que envía desde su organización. Sistemas de correo electrónico que reciben correo electrónico de puede usar esta firma digital para ayudarle a determinar si el correo electrónico es legítimo.<br/> No se preocupe si los detalles de cómo funciona esto parece complicado, ya que el valor predeterminado que se configura en Office 365 debería funcionar para la mayoría de las organizaciones. Si no configura DKIM, Office 365 usa su directiva predeterminada y las claves que crea para habilitar DKIM para el dominio. Además, si deshabilita la firma DKIM, después de un período de tiempo, Office 365 automáticamente habilita la directiva predeterminada de Office 365 para su dominio.<br/> Si lo desea, puede ver esta página en el centro de &amp; seguridad y cumplimiento y ver si las firmas DKIM están habilitadas actualmente para su dominio y puede ver la última vez que las claves de cifrado usadas por Office 365 se han rotado. También puede girar las claves manualmente.<br/> **Importante.** DKIM es sólo una técnica de autenticación de correo electrónico que usa Office 365. Para ser más efectivo, DKIM se usa junto con otras técnicas admitidas, como el marco de directivas de remitente (SPF) y la autenticación de mensajes basada en el dominio, la creación de informes y la conformidad (DMARC). Juntas, estas tecnologías de autenticación basadas en dominio ayudan a evitar el correo no deseado y la suplantación de identidad.<br/>  Antes de realizar cambios en DKIM mediante el &amp; centro de seguridad y cumplimiento, se sienta cómodo con la tecnología y el modo en que funciona. Para empezar, vea más [información sobre los conceptos básicos: más formas de evitar el correo no deseado en Office 365](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365).           |
|**Datos adjuntos seguros**<br/>|[Datos adjuntos seguros](atp-safe-attachments.md) forma parte de la protección contra amenazas avanzada. Cuando está habilitado, los archivos adjuntos de correo electrónico se abren en un entorno aislado y especial que es independiente de Office 365 antes de que se envíen a los buzones de correo de los destinatarios. Los datos adJuntos seguros están diseñados para ayudar a detectar datos adjuntos malintencionados incluso antes de que las firmas antivirus estén disponibles. Para obtener más información, consulte [datos adjuntos seguros en Office 365](atp-safe-attachments.md).<br/> |
|**Vínculos seguros** <br/> |[Vínculos seguros](atp-safe-links.md) forma parte de la protección contra amenazas avanzada. Vínculos seguros Ayude a evitar que los usuarios envíen direcciones URL en el correo electrónico o en documentos de Office que apunten a sitios web que se reconocen como malintencionados. Para obtener más información, consulte [vínculos seguros en Office 365](atp-safe-links.md).<br/> |
|**Cuarentena**<br/>|Configure la [cuarentena](http://go.microsoft.com/fwlink/p/?LinkID=809005) para los mensajes de correo electrónico entrantes en Office 365 donde los mensajes que se han filtrado como correo no deseado, en masa, de suplantación de identidad y de malware se pueden conservar para una revisión posterior. Tanto los usuarios como los administradores pueden trabajar con los mensajes en cuarentena. Los usuarios pueden trabajar en cuarentena solo con sus propios mensajes filtrados. Los administradores pueden buscar y administrar los mensajes en cuarentena para todos los usuarios.<br/> |
|**Amenazas avanzadas** <br/> |Vea el [Informe de estado de protección contra amenazas](https://support.office.com/article/View-the-reports-for-Advanced-Threat-Protection-E47E838C-D99E-4C0B-B9AA-E66C4FAE902F#advancedthreats) para ver información sobre el contenido malintencionado encontrado y bloqueado por Exchange Online Protection y la protección contra amenazas avanzada.  <br/> |
