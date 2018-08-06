---
title: Procedimientos recomendados para configurar EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Siga estos procedimientos recomendados para Exchange Online Protection (EOP) con el fin de evitar errores comunes de configuración y prepararse para usar esta característica sin problemas.
ms.openlocfilehash: ef58e2cd5a3ffdbbeb02124442c355974d174073
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027277"
---
# <a name="best-practices-for-configuring-eop"></a>Procedimientos recomendados para configurar EOP
  
Siga estos procedimientos recomendados para Exchange Online Protection (EOP) con el fin de evitar errores comunes de configuración y prepararse para usar esta característica sin problemas. Como norma general, se recomienda usar la configuración predeterminada. En este tema se supone que ya completó el proceso de configuración. Si no completó la configuración de EOP, vea [Configurar un servicio de EOP](set-up-your-eop-service.md).
  
## <a name="use-a-test-domain"></a>Usar un dominio de prueba

Recomendamos usar un dominio, subdominio o dominio de bajo volumen de prueba para probar las características del servicio antes de implementarlas en los dominios de producción de mayor volumen.
  
## <a name="synchronize-recipients"></a>Sincronizar destinatarios

Si su organización tiene cuentas de usuario existentes en un entorno local de Active Directory, puede sincronizar dichas cuentas con Azure Active Directory en la nube. Se recomienda usar la sincronización de directorios. Para más información sobre los beneficios de usar la sincronización de directorios y los pasos para configurarla, vea [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).
  
## <a name="spf-record-customization-to-help-prevent-spoofing"></a>Personalización del registro de SPF para impedir la suplantación de identidad

Al configurar EOP, agregó un registro de SPF (marco de directivas de remitentes) para EOP a sus registros DNS. El registro SPF ayuda a evitar la suplantación de identidad. Para obtener más información acerca de cómo evita la suplantación de un registro SPF y cómo se pueden agregar las direcciones IP local para el registro de SPF, consulte [Set up SPF en Office 365 para ayudar a evitar la suplantación de identidad](../set-up-spf-in-office-365-to-help-prevent-spoofing.md). 
  
## <a name="set-anti-spam-options"></a>Establecer opciones contra correo no deseado

Administrar la conexión de configuración del filtro mediante la adición de las direcciones IP a las listas de direcciones IP bloqueadas y direcciones IP permitidas y seleccionando la opción de **Habilitar la lista de seguros** , que debe reducir el número de falsos positivos (correo correcto que se clasifica como correo no deseado) recibe. Encontrará más información en [Configurar la directiva de filtro de conexión](../configure-the-connection-filter-policy.md). Para obtener más configuración de correo no deseado que se aplica a toda la organización, eche un vistazo de [cómo ayudar a garantizar que no se marcó un mensaje como correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=534224) o [correo electrónico de bloqueo de correo no deseado con el filtro de spam de Office 365 para evitar problemas de negativos es false](https://go.microsoft.com/fwlink/p/?LinkId=534225). Estos son útiles si tiene control de nivel de administrador y desea impedir que falsos positivos o negativos falsos.
  
Administrar los filtros de contenido mediante la revisión y, opcionalmente, cambiar la configuración predeterminada. Por ejemplo, puede cambiar la acción de lo que ocurre con los mensajes detectados como correo no deseado. Si desea seguir un enfoque agresivo para el filtrado de correo no deseado, puede configurar opciones de filtrado de spam avanzado. Se recomienda probar estas opciones en primer lugar antes implementarlos en el entorno de producción (activando ellos) se recomienda que las organizaciones que se preocupan por suplantación de identidad para convertir la **registro SPF: error** opción. Encontrará más información en la [configuración de sus directivas de filtro de correo no deseado](../configure-your-spam-filter-policies.md) y [Opciones de filtrado avanzadas correo no deseado](../advanced-spam-filtering-asf-options.md).
  
> [!IMPORTANT]
> Si usa la acción de filtro de contenido de forma predeterminada, **mover el mensaje a la carpeta correo no deseado**, con el fin de garantizar que esta acción funciona con buzones locales, debe configurar reglas de flujo de correo de Exchange, también denominadas reglas de transporte, en sus instalaciones servidores para detectar los encabezados de spam agregados por elevación de privilegios. Para obtener información detallada, vea [Asegúrese de que el correo no deseado se enrute a la carpeta de correo no deseado de cada usuario](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
Le recomendamos que revise la [protección contra correo no deseado preguntas más frecuentes](../anti-spam-protection-faq.md), incluidas la salida postal sección sobre procedimientos recomendados, que le ayudará a asegurarse de que el correo saliente se entrega.
  
Puede enviar (correo no deseado) de falsos negativos y falsos positivos (que no sean el correo no deseado) a Microsoft para su análisis de varias maneras. Para obtener información detallada, vea [enviar spam, no spam y los mensajes de estafas de suplantación de identidad a Microsoft para su análisis](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).
  
## <a name="set-anti-malware-options"></a>Establecer opciones antimalware

Revisar y ajustar las opciones de filtro de malware en el center(EAC) de administración de Exchange. Encontrará más información en [Configure anti-malware policies](../configure-anti-malware-policies.md). También se recomienda la lectura sobre otras preguntas más frecuentes y respuestas relativas a la protección contra malware en nuestra [protección Anti-malware preguntas más frecuentes ](../anti-malware-protection-faq-eop.md).
  
Si le preocupan los archivos ejecutables que contienen malware, puede crear una regla de flujo de correo de Exchange que bloquee los datos adjuntos de correo electrónico que tengan contenido ejecutable. Siga los pasos descritos en el tema[Cómo reducir las amenazas de malware a través del bloqueo de datos adjuntos de los archivos en Exchange Online Protection](https://support.microsoft.com/kb/2959596) para bloquear los tipos de archivos que aparecen en "Tipos de archivo ejecutables admitidos para la inspección de reglas de transporte" en [Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx).
  
Puede usar el filtro de tipos comunes de datos adjuntos en el EAC. Seleccione **protección** \> **filtros de malware**. Puede crear una regla de flujo de correo de Exchange, también denominada regla de transporte, que bloquea los datos adjuntos de correo electrónico que tengan contenido ejecutable. 
  
Para una mayor protección, también le recomendamos usar reglas de flujo de correo para bloquear algunas o todas las extensiones siguientes: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh. Esto puede realizarse mediante la condición **La extensión de archivo de alguno de los datos adjuntos incluye estas palabras**. 
  
Los administradores y usuarios finales pueden enviar malware que logró pasar por los filtros o enviar un archivo que crean que se identificó incorrectamente como malware mediante su envío a Microsoft para su análisis. Para obtener más información, vea [Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md).
  
## <a name="create-mail-flow-rules"></a>Crear reglas de flujo de correo

Cree reglas de flujo de correo, también denominadas reglas de transporte o filtros personalizados, según sus necesidades empresariales.
  
Al implementar una regla nueva en producción, seleccione primero uno de los modos de prueba para ver su efecto. Cuando tenga la seguridad de que la regla funciona como se espera, cambie el modo de la regla a **Exigir**.
  
Al implementar reglas nuevas, considere la posibilidad de agregar la acción adicional de **Generar informe de incidentes** para supervisar la regla en acción. 
  
Si se encuentra en una configuración de implementación híbrida, con parte de la organización local y parte en Office 365, puede crear reglas que se apliquen a toda la organización. Para ello, use condiciones que estén disponibles tanto localmente como en Office 365. Si bien la mayoría de las condiciones están disponibles en ambas implementaciones, hay un pequeño conjunto que es específico de un escenario de implementación determinado. Para más información, vea [Mail flow or Transport rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).
  
Si quiere inspeccionar los archivos adjuntos de correo electrónico de los mensajes en tránsito dentro de su organización, puede hacerlo mediante reglas de flujo de correo. Después, puede actuar en los mensajes inspeccionados en función del contenido o de las características de esos datos adjuntos. Obtenga más información en [Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx).
  
### <a name="phishing-and-spoofing-prevention"></a>Suplantación de identidad (phishing) y prevención de suplantación

Puede mejorar la protección contra suplantación de identidad (anti-phishing) si detecta el momento en que la información personal sale de la organización en un correo electrónico. Por ejemplo, puede usar las siguientes expresiones regulares en las reglas de flujo de correo para detectar la transmisión de datos financieros personales o información que puede poner en riesgo la privacidad:
  
- \d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d (Visa MasterCard)
    
- \d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d (American Express)
    
- \d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d (cualquier número de 16 dígitos)
    
- \d\d\d\-\d\d\-\d\d\d\d (números de la Seguridad Social)
    
El éxito de las campañas de correo no deseado y de suplantación de identidad también puede reducirse mediante el bloqueo de mensajes de correo electrónico malintencionados entrantes que parecen haber sido enviados desde su propio dominio. Por ejemplo, puede crear una regla de flujo de correo que rechace los mensajes de su dominio de empresa enviados al mismo dominio de empresa para bloquear este tipo de falsificación del remitente.
  
> [!CAUTION]
> Se recomienda crear esta regla de rechazo solo cuando exista la certeza de que no se envía desde Internet ningún correo legítimo desde su dominio a su servidor de correo. Esto puede ocurrir, por ejemplo, cuando un usuario de la organización envía un mensaje a un destinatario externo y, posteriormente, se reenvía a otro destinatario de la organización. 
  
### <a name="extension-blocking"></a>Bloqueo de extensiones

Si le preocupa de archivos ejecutables que contienen código malintencionado, puede configurar directivas antimalware para bloquear todos los datos adjuntos de correo electrónico que tiene contenido ejecutable. Siga los pasos descritos en [Configure anti-malware policies](../configure-anti-malware-policies.md).
  
Para una mayor protección, también le recomendamos que bloquee algunas o todas las extensiones siguientes: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh.
  
## <a name="reporting-and-troubleshooting"></a>Notificación y solución de problemas

Use los informes del centro de administración de Office 365 para solucionar problemas generales y detectar tendencias. Para encontrar datos específicos en un punto único sobre un mensaje, use la herramienta de seguimiento de mensajes. Para más información sobre informes, vea [Informes y seguimiento de mensajes en Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Para más información sobre la herramienta de seguimiento de mensajes, vea [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx).
  
## <a name="for-more-information"></a>Más información

[Preguntas más frecuentes sobre EOP](eop-general-faq.md)
  
[Ayuda y soporte técnico para EOP](help-and-support-for-eop.md)
  
[Vídeos de introducción a EOP](videos-for-getting-started-with-eop.md)
  
[Cómo ayudar a garantizar que un mensaje no se marque como correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

