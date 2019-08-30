---
title: 'Exchange Online Protection '
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 70ab4af2-fec4-4886-8e12-27d348649204
description: Estas son algunas de las cosas que debe tener en cuenta antes de empezar a trabajar con EOP.
ms.openlocfilehash: c3e1df3d0016304a22f8411687118c3b4224a710
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676799"
---
# <a name="exchange-online-protection"></a>Exchange Online Protection

Este es el servicio de filtrado de correo electrónico hospedado de Microsoft Exchange Online Protection (EOP). A continuación, se detallan algunos aspectos que debe conocer antes de empezar a trabajar con EOP y usar este contenido:
  
- Para más información acerca de EOP, vea la [Descripción de servicio Protección en línea de Exchange](https://go.microsoft.com/fwlink/p/?LinkId=320619). Otros recursos útiles son [Información general de Exchange Online Protection](exchange-online-protection-overview.md), [Preguntas más frecuentes sobre EOP](eop-general-faq.md) y [Características de EOP](eop-features.md), así como la [página principal de Exchange Online Protection](https://go.microsoft.com/fwlink/?LinkId=279912).

- Para empezar a trabajar con EOP, los nuevos clientes deben ir a [Configurar un servicio de EOP](set-up-your-eop-service.md). En este tema se incluyen pasos que le ayudarán a configurar y a activar EOP.

- Si precisa más ayuda o desea compartir sus ideas, el [foro de EOP](https://go.microsoft.com/fwlink/?LinkId=285351) es un buen sitio para empezar.

## <a name="eop-help-for-administrators"></a>Ayuda de EOP para administradores

El contenido de la Ayuda para administradores de EOP consta de las siguientes categorías principales:
  
- [Exchange Online Protection Overview](exchange-online-protection-overview.md): presenta cómo funciona EOP y proporciona vínculos a información adicional.

- [Características de EOP](eop-features.md): proporciona una lista de las características que están disponibles en EOP.

- [Configurar el servicio de EOP](set-up-your-eop-service.md): proporciona los pasos para configurar el servicio de EOP y vínculos a información adicional.

- [Cambiar a EOP desde Google Postini, Barracuda Spam y virus firewall o Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): describe el proceso para cambiar a EOP desde otro producto de protección de correo electrónico.

- [Administrar destinatarios y grupos de roles de administrador en EOP](manage-recipients-and-admin-role-groups-in-eop.md): describe cómo administrar destinatarios y cómo asignar usuarios a grupos de roles de administración.

- [Flujo de correo en EOP](mail-flow-in-eop.md): describe cómo configurar escenarios de flujo de correo personalizados mediante conectores, cómo administrar dominios asociados con el servicio y cómo habilitar la característica de bloqueo perimetral basado en directorios (DBEB).

- [Best Practices for Configuring EOP](best-practices-for-configuring-eop.md): describe las opciones de configuración recomendadas para después de configurar y aprovisionar el servicio.

- [Directiva de mensajería y cumplimiento en EOP](messaging-policy-and-compliance-in-eop.md): describe cómo usar las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) para aplicar directivas y reglamentos específicos de la empresa, y cómo usar los informes de auditoría para realizar un seguimiento de los cambios de configuración en el servicio.

- [Protección contra correo electrónico no deseado y antimalware en Office 365](../anti-spam-and-anti-malware-protection.md): describe el filtrado de correo no deseado y el filtrado de malware y muestra cómo personalizarlos para satisfacer mejor las necesidades de su organización. También se describen las tareas que los administradores y los usuarios finales pueden realizar en los mensajes en cuarentena.

- [Informes y seguimiento de mensajes en Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): describe los informes y las herramientas de solución de problemas que están disponibles.

- [Centro de administración de Exchange en Exchange Online Protection ](../exchange-admin-center-in-exchange-online-protection-eop.md): describe cómo tener acceso y navegar por la interfaz de administración del centro de administración de Exchange (EAC) para administrar el servicio de EOP.

- [PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell): proporciona información sobre PowerShell remoto, que permite administrar el servicio EOP desde la línea de comandos.

- [Ayuda y soporte técnico para EOP](help-and-support-for-eop.md) Proporciona información sobre cómo obtener ayuda y soporte técnico.

## <a name="eop-help-for-end-users"></a>Ayuda de EOP para usuarios finales

El contenido de la Ayuda para asistir a los usuarios finales de EOP a administrar el correo no deseado incluye los siguientes temas:
  
- [Buscar y liberar mensajes en cuarentena como un usuario](../find-and-release-quarantined-messages-as-a-user.md): describe cómo los usuarios finales pueden buscar y publicar sus propios mensajes de correo no deseado en cuarentena en la interfaz de usuario de cuarentena de correo no deseado y, opcionalmente, informar de ellos como correo deseado a Microsoft.

- [Enviar mensajes de correo no deseado, mensajes de correo no deseado y suplantación de identidad a Microsoft para su análisis](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md): describe las distintas formas en que los usuarios finales pueden enviar mensajes de correo no deseado (correo no deseado) y mensajes que no son correo no deseado a Microsoft. En este tema se incluyen vínculos a las herramientas de informes disponibles en Microsoft Outlook y Outlook en la web (anteriormente conocido como Outlook Web App).

- [Enviar malware y no malware a Microsoft para su análisis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md): describe cómo los usuarios finales pueden enviar malware que ha superado los filtros o enviar un archivo que se identificó de forma incorrecta como malware.

- Los usuarios finales pueden agregar determinados usuarios o dominios a una lista de remitentes seguros o a una lista de remitentes bloqueados configurando su configuración de correo no deseado en Outlook o en Outlook en la Web. Tenga en cuenta que los mensajes que se envían de remitentes bloqueados se marcan como correo no deseado, no rechazados, lo que significa que se pueden recuperar de la carpeta de correo electrónico no deseado o cuarentena (en función de dónde haya configurado el servicio para enviar correo no deseado). Para obtener más información, vea [usar el complemento de mensajes de informe](https://support.office.com/article/addin-b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

- [Ayuda y soporte técnico para EOP](help-and-support-for-eop.md) Proporciona información sobre cómo obtener ayuda y soporte técnico.
