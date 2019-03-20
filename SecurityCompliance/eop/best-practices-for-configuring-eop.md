---
title: Procedimientos recomendados para configurar EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Siga estos procedimientos recomendados para Exchange Online Protection (EOP) con el fin de evitar errores comunes de configuración y prepararse para usar esta característica sin problemas.
ms.openlocfilehash: e9bd83c8b38a20ae0ced4300648461c0cb135e4b
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693189"
---
# <a name="best-practices-for-configuring-eop"></a>Procedimientos recomendados para configurar EOP
  
Siga estos procedimientos recomendados para Exchange Online Protection (EOP) con el fin de evitar errores comunes de configuración y prepararse para usar esta característica sin problemas. Como norma general, se recomienda usar la configuración predeterminada. En este tema se supone que ya completó el proceso de configuración. Si no completó la configuración de EOP, vea [Configurar un servicio de EOP](set-up-your-eop-service.md).
  
## <a name="use-a-test-domain"></a>Usar un dominio de prueba

Recomendamos usar un dominio, subdominio o dominio de bajo volumen de prueba para probar las características del servicio antes de implementarlas en los dominios de producción de mayor volumen.
  
## <a name="synchronize-recipients"></a>Sincronizar destinatarios

Si su organización tiene cuentas de usuario existentes en un entorno local de Active Directory, puede sincronizar dichas cuentas con Azure Active Directory en la nube. Se recomienda usar la sincronización de directorios. Para más información sobre los beneficios de usar la sincronización de directorios y los pasos para configurarla, vea [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).
  
## <a name="spf-record-customization-to-help-prevent-spoofing"></a>Personalización del registro de SPF para impedir la suplantación de identidad

Cuando configuró EOP, agregó un registro de SPF (marco de directivas de remitente) para EOP a sus registros DNS. El registro de SPF ayuda a impedir la suplantación de identidad. Para obtener más información acerca de cómo un registro de SPF impide la suplantación de identidad y cómo puede Agregar las direcciones IP locales al registro de SPF, consulte [configurar SPF en Office 365 para evitar la suplantación de identidad](../set-up-spf-in-office-365-to-help-prevent-spoofing.md). 
  
## <a name="set-anti-spam-options"></a>Establecer opciones contra correo no deseado

Para administrar la configuración del filtro de conexión, agregue las direcciones IP a las listas de direcciones IP permitidas y de direcciones IP bloqueadas, o seleccione la opción **Habilitar lista segura**, que debería reducir el número de falsos positivos (correo válido que se clasifica como correo no deseado) que se recibe. Para obtener más información, vea [Configure the Connection Filter Policy](../configure-the-connection-filter-policy.md). Para obtener más información sobre configuración de correo no deseado que se aplica a toda la organización, consulte [Cómo ayudar a garantizar que un mensaje no se marque como correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=534224) o [Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](https://go.microsoft.com/fwlink/p/?LinkId=534225). Estos son útiles si tiene un control de nivel de administrador y desea impedir falsos positivos o falsos negativos.
  
Administre los filtros de contenido revisando y, opcionalmente, cambie la configuración predeterminada. Por ejemplo, puede cambiar la acción de qué ocurre con los mensajes detectados como correo no deseado. Si desea seguir un enfoque agresivo del filtrado de correo no deseado, puede configurar opciones avanzadas de filtrado de correo no deseado. Le recomendamos que Pruebe estas opciones primero antes de implementarlas en su entorno de producción (al activarlas) se recomienda que las organizaciones a las que les preocupa la suplantación de identidad (phishing) activen la opción **registro de SPF: error grave** . Para obtener más información, vea [configurar las directivas de filtro de correo no deseado](../configure-your-spam-filter-policies.md) y [Opciones avanzadas de filtrado de correo no deseado](../advanced-spam-filtering-asf-options.md).
  
> [!IMPORTANT]
> Si usa la acción de filtrado de contenido predeterminada, **mueva el mensaje a la carpeta correo no deseado**para asegurarse de que esta acción funcionará con los buzones locales, debe configurar las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) en su entorno local. servidores para detectar los encabezados de correo no deseado agregados por EOP. Para más información, consulte [Asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
Le recomendamos que revise las [preguntas más frecuentes sobre protección contra correo electrónico no deseado](../anti-spam-protection-faq.md), incluida la sección procedimientos recomendados de correo saliente, que le permitirá garantizar que el correo saliente se entregue.
  
Hay varias maneras de enviar falsos negativos (correo no deseado) y falsos positivos (no es correo no deseado) a Microsoft para que los analice. Para obtener más información, consulte [Enviar correo electrónico no deseado, mensajes sin correo no deseado y mensajes de suplantación de identidad a Microsoft para su análisis](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).
  
## <a name="set-anti-malware-options"></a>Establecer opciones antimalware

Revise y ajuste la configuración del filtro de malware en el Centro de administración de Exchange (EAC). Para obtener más información, vea [Configure anti-malware Policies](../configure-anti-malware-policies.md). También le recomendamos que lea información sobre otras preguntas frecuentes y respuestas relativas a la protección antimalware en nuestras [preguntas más frecuentes sobre protección contra malware ](../anti-malware-protection-faq-eop.md).
  
Si le preocupan los archivos ejecutables que contienen malware, puede crear una regla de flujo de correo de Exchange que bloquee los datos adjuntos de correo electrónico que tengan contenido ejecutable. Siga los pasos [que se describen en cómo reducir las amenazas de malware a través del bloqueo de datos adjuntos de archivos en Exchange Online Protection](https://support.microsoft.com/kb/2959596) para bloquear los archivos adjuntos a [mensajes en Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)que aparecen en usar reglas de flujo de correo.
  
Puede usar el filtro de tipos comunes de datos adjuntos en el EAC. Seleccione **protección** \> **filtros de malware**. Puede crear una regla de flujo de correo que bloquee todos los datos adjuntos de correo electrónico que tengan contenido ejecutable. 
  
Para una mayor protección, también le recomendamos usar reglas de flujo de correo para bloquear algunas o todas las extensiones siguientes: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh. Esto puede realizarse mediante la condición **La extensión de archivo de alguno de los datos adjuntos incluye estas palabras**. 
  
Los administradores y usuarios finales pueden enviar malware que logró pasar por los filtros o enviar un archivo que crean que se identificó incorrectamente como malware mediante su envío a Microsoft para su análisis. Para obtener más información, vea [Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md).
  
## <a name="create-mail-flow-rules"></a>Crear reglas de flujo de correo

Cree reglas de flujo de correo (también conocidas como reglas de transporte) o filtros personalizados para satisfacer sus necesidades empresariales.
  
Al implementar una regla nueva en producción, seleccione primero uno de los modos de prueba para ver su efecto. Cuando tenga la seguridad de que la regla funciona como se espera, cambie el modo de la regla a **Exigir**.
  
Al implementar reglas nuevas, considere la posibilidad de agregar la acción adicional de **Generar informe de incidentes** para supervisar la regla en acción. 
  
Si se encuentra en una configuración de implementación híbrida, con parte de la organización local y parte en Office 365, puede crear reglas que se apliquen a toda la organización. Para ello, use condiciones que estén disponibles tanto localmente como en Office 365. Si bien la mayoría de las condiciones están disponibles en ambas implementaciones, hay un pequeño conjunto que es específico de un escenario de implementación determinado. Obtenga más información en [reglas de flujo de correo (reglas de transporte) en Exchange Online](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).
  
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

Si le preocupan los archivos ejecutables que contienen malware, puede configurar directivas antimalware que bloqueen los datos adjuntos de correo electrónico que tengan contenido ejecutable. Siga los pasos descritos en [Configure anti-malware Policies](../configure-anti-malware-policies.md).
  
Para una mayor protección, también le recomendamos que bloquee algunas o todas las extensiones siguientes: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh.
  
## <a name="reporting-and-troubleshooting"></a>Notificación y solución de problemas

Solucionar problemas generales y tendencias mediante el uso de los informes del centro de administración. Para encontrar datos específicos en un punto único sobre un mensaje, use la herramienta de seguimiento de mensajes. Para más información sobre informes, vea [Informes y seguimiento de mensajes en Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Para más información sobre la herramienta de seguimiento de mensajes, vea [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx).
  
## <a name="for-more-information"></a>Para obtener más información

[Preguntas más frecuentes sobre EOP](eop-general-faq.md)
  
[Ayuda y soporte técnico para EOP](help-and-support-for-eop.md)
  
[Vídeos de introducción a EOP](videos-for-getting-started-with-eop.md)
  
[Cómo ayudar a garantizar que un mensaje no se marque como correo no deseado](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

