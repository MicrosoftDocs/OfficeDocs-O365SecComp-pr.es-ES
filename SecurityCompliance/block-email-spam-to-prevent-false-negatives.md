---
title: Bloquear el correo no deseado con el filtro contra correo no deseado de Office 365 para evitar problemas de falsos negativos
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: da21c0b6-e8f0-4cc8-af2e-5029a9433d59
description: Sugerencias para configurar el filtro contra correo no deseado de Office 365 con el fin de bloquear el correo no deseado e impedir mensajes de falsos negativos. Un administrador usa el filtro de correo no deseado de Office 365 para impedir que se envíe correo no deseado a las bandejas de entrada de los usuarios.
ms.openlocfilehash: 3502215dba4097d0643501dd089ec3fe94575c87
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536088"
---
# <a name="block-email-spam-with-the-office-365-spam-filter-to-prevent-false-negative-issues"></a>Bloquear el correo no deseado con el filtro contra correo no deseado de Office 365 para evitar problemas de falsos negativos

Exchange Online Protection (EOP) es un servicio de filtrado de correo electrónico basado en la nube que protege a su organización contra el correo no deseado y el malware. Si tiene buzones en Office 365, ya están protegidos de forma predeterminada con EOP. 
  
Para garantizar que los mensajes de correo no deseado y correo masivo estén bloqueados, ajuste el filtro contra correo no deseado de Office 365. Esto ayudará a impedir el problema de falsos negativos, donde se permite que el correo no deseado llegue a la bandeja de entrada del usuario. Como administrador de Exchange Online o Exchange Online Protection (EOP), siga este procedimiento para ajustar el filtro contra correo no deseado de Office 365 e impedir que el correo no deseado se entregue en las bandejas de entrada de los usuarios.
  
## <a name="customize-the-office-365-anti-spam-filter-with-these-settings"></a>Personalizar el filtro contra correo no deseado de Office 365 con estas opciones de configuración

Un administrador puede usar varias opciones de configuración del filtro contra correo no deseado de Office 365 para impedir que el correo no deseado se envíe a las bandejas de entrada de los usuarios. El filtro contra correo no deseado de Office 365 se mejorará y podrá bloquear el correo no deseado e impedir mensajes de falsos negativos si usa las opciones que se indican aquí. En este contexto, un falso negativo hace referencia a mensajes masivos o de correo no deseado que se envían a la bandeja de entrada de un usuario.
  
### <a name="block-ip-addresses-with-a-connection-filter"></a>Bloquear direcciones IP con un filtro de conexión

Para personalizar el filtro contra correo no deseado de Office 365, agregue la dirección IP del remitente a la lista de direcciones IP bloqueadas del filtro de conexión:
  
1. Obtenga los encabezados del mensaje que quiere bloquear en su cliente de correo (como Outlook o Outlook Web App), como se describe en [Analizador de encabezados de mensaje](https://go.microsoft.com/fwlink/p/?LinkId=306583).
    
2. Busque la dirección IP después de la etiqueta CIP en el encabezado X-Forefront-Antispam-Report con el [Analizador de encabezados de mensaje](https://testconnectivity.microsoft.com/?tabid=mha) o de forma manual. 
    
3. Para agregar la dirección IP a la lista de direcciones IP bloqueadas, siga los pasos que se indican en “Usar el EAC para editar la directiva de filtro de conexión predeterminada” en [Configurar la directiva de filtro de conexiones](https://technet.microsoft.com/es-ES/library/jj200718%28v=exchg.150%29.aspx).
    
### <a name="block-bulk-mail-with-transport-rules-or-the-spam-filter"></a>Bloquear el correo masivo con regla de transporte o el filtro de correo no deseado

¿Es el correo no deseado principalmente correo masivo (por ejemplo, boletines o promociones)? Puede personalizar el filtro de correo no deseado en Office 365 si [usa reglas de transporte para filtrar de forma agresiva mensajes de correo masivo](https://technet.microsoft.com/es-ES/library/dn720438%28v=exchg.150%29.aspx) o activa la opción **Correo masivo** en las [Opciones avanzadas de filtrado de correo no deseado](https://technet.microsoft.com/es-ES/library/jj200750%28v=exchg.150%29.aspx) del filtro de correo no deseado. En el Centro de administración de Exchange, primero haga clic en **Protección** \> **Filtro de contenido** y, después, haga doble clic en la directiva de filtro que quiera ajustar. Haga clic en **Acciones de correo no deseado y correo masivo** para ajustar la configuración, como se muestra aquí. 
  
![Establecer el filtro de correo masivo en Exchange Online](media/a45095c2-269d-45b8-a76c-999b5e78da68.png)
  
### <a name="block-email-spam-using-spam-filter-block-lists"></a>Bloquear el correo no deseado con listas de bloqueados de filtro de correo no deseado

[Configure las directivas de filtro de correo no deseado](https://technet.microsoft.com/es-ES/library/jj200684%28v=exchg.150%29.aspx) para agregar la dirección del remitente a la lista de bloqueados del remitente o agregue el dominio a la lista de bloqueados del dominio en el filtro de correo no deseado. Los correos electrónicos de un remitente o dominio que se encuentre en la lista de bloqueados de filtro de correo no deseado se marcarán como correo no deseado. 
  
### <a name="advanced-spam-filtering-options"></a>Opciones avanzadas de filtrado de correo no deseado

[Configure las directivas de filtro de correo no deseado](https://technet.microsoft.com/es-ES/library/jj200684%28v=exchg.150%29.aspx) y active otras [Opciones avanzadas de filtrado de correo no deseado](https://technet.microsoft.com/es-ES/library/jj200750%28v=exchg.150%29.aspx).
  
Para obtener más información sobre otras opciones de configuración de correo no deseado que se aplican en toda la organización, vea [Impedir falsos positivos de correo electrónico marcado como correo no deseado con una lista segura u otras técnicas](prevent-email-from-being-marked-as-spam-0.md). Esto resulta útil si tiene control de nivel de administrador y quiere impedir falsos positivos.
  
## <a name="email-users-can-also-help-ensure-that-false-negative-and-email-spam-is-blocked-with-office-365-spam-filter"></a>Los usuarios de correo electrónico también pueden asegurarse de que los falsos negativos y el correo no deseado se bloqueen con un filtro contra correo no deseado de Office 365.

Facilitará los esfuerzos contra correo no deseado de Office 365 para impedir falsos negativos y correo masivo si pide a los usuarios que agreguen la dirección del remitente de correo no deseado a su lista de remitentes bloqueados en [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) o en [Outlook Web App](https://go.microsoft.com/fwlink/p/?LinkId=294862). En Outlook Web App, haga clic en **Configuración** \> **Opciones** \> **Bloquear o permitir** y, después, agregue la dirección a la lista de **remitentes bloqueados**, como se muestra aquí. 
  
![Bloquear un remitente en Outlook Web App](media/fdf51381-2527-4819-ac2a-5dff84d2a36d.png)
  
> [!NOTE]
> Para obtener más información sobre las listas de remitentes seguros, vea [Preguntas más frecuentes sobre listas de remitentes seguros y remitentes bloqueados](https://technet.microsoft.com/es-ES/library/dn133608%28v=exchg.150%29.aspx). 
  
Los párrafos anteriores de esta subsección solo son válidos para clientes que usen EOP como un servicio para proteger los sistemas de correo electrónico locales o como parte de una implementación híbrida de correo electrónico. Para obtener más información sobre EOP, vea la [Página principal de Exchange Online Protection](https://products.office.com/es-ES/exchange/exchange-email-security-spam-protection).
  
## <a name="eop-only-customers-set-up-the-office-365-spam-filter-to-block-email-spam"></a>Solo para clientes de EOP: Configurar el filtro contra correo no deseado de Office 365 para bloquear el correo no deseado

Solo para clientes de EOP con buzones locales: Si configura un filtro de correo no deseado para la acción predeterminada (Mover el mensaje a la carpeta de correo no deseado), siga los pasos indicados en “Asegurarse de que el correo no deseado se enrute a la carpeta Correo no deseado de cada usuario”. Intentamos facilitar esto al proporcionar comandos del Shell de administración de Exchange en un tema separado, así como un vínculo a información más general sobre cómo empezar a usar el Shell.
  
Para evitar falsos negativos de correo no deseado, sincronice la configuración del usuario con el servicio mediante la sincronización de directorios para asegurarse de que se respeten los remitentes bloqueados. Para obtener más información, vea “Usar la sincronización de directorios para administrar los usuarios de correo” en Administrar usuarios de correo en EOP.
  
## <a name="eop-only-customers-who-are-not-using-directory-synchronization"></a>Solo clientes de EOP que no usen la sincronización de directorios

El servicio EOP se diseñó para respetar las listas de remitentes bloqueados y seguros del usuario (si la información se compartió con el servicio). Si es cliente de EOP y usa Outlook, pero no configuró la sincronización de directorios para sincronizar los usuarios con Office 365, puede impedir que se entreguen los mensajes en las bandejas de entrada de los usuarios con los remitentes bloqueados. Pero puede que tenga que configurar algunas reglas de flujo del correo de Exchange en los casos siguientes:
  
- Si un mensaje pasa un filtrado de correo no deseado normal mediante EOP y, después, se entrega en un servidor Exchange local y EOP asigna un veredicto de correo no deseado de SCL 1-4 (correo deseado), la lista de remitentes bloqueados local de los usuarios invalidará el veredicto de filtro de correo no deseado de EOP y lo entregará en la carpeta Correo no deseado.
    
- Si, en EOP, una regla de flujo del correo de Exchange asigna un SCL de -1 a un mensaje o la dirección IP WHEL dominio se encuentra en la lista de permitidos, el valor de SCL se propagará al servidor Exchange local mediante conectores. En este caso, no se exigirá el uso de la lista de remitentes bloqueados del usuario. Para cambiar esto, puede crear una regla de flujo del correo local que establezca el valor de SCL en 0. Esto hará que Outlook exija el uso de la lista de remitentes bloqueados local del usuario.
    
**Para configurar una regla de flujo del correo con el fin de impedir que se entreguen mensajes en la bandeja de entrada de los usuarios con la lista de remitentes bloqueados**
  
1. Abra el Shell de administración de Exchange del servidor local. Para obtener información sobre cómo abrir el Shell en la organización de Exchange local, vea [Abrir el Shell de administración de Exchange](https://technet.microsoft.com/library/dd638134%28v=exchg.160%29.aspx).
    
2. Ejecute este comando para enrutar los mensajes de correo no deseado filtrados por contenido a la carpeta Correo no deseado para actualizar el valor de SCL en todos los mensajes marcados con SCL -1:
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SCL:-1" -SetSCL 0
  ```

    Como el valor de SCL es 0 en el servidor Exchange local, el correo deseado se entregará en las bandejas de entrada de los usuarios, pero se permitirá que la lista de remitentes bloqueados local de los usuarios los envíe a la carpeta Correo no deseado. Si usa una cuarentena de correo no deseado en EOP, aún es posible que los remitentes que se encuentren en la lista segura del usuario se identifiquen como correo no deseado y se envíen a la cuarentena. Si usa la carpeta Correo no deseado en el buzón local, esto permitirá la entrega en la bandeja de entrada para los remitentes seguros.

> [!WARNING]
> Si usa una regla de flujo del correo para cambiar el valor de SCL a 0 (o a cualquier valor distinto de -1), se aplicarán en el mensaje todas las opciones de correo no deseado de Outlook. Esto quiere decir que se respetarán las listas seguras y de bloqueados, pero los mensajes que no tengan direcciones en las listas de remitentes seguros o bloqueados podrían marcarse como correo no deseado al procesar el filtro de correo no deseado del lado cliente. Si quiere que Outlook procese las listas seguras y de bloqueados, pero no usa el filtro de correo no deseado de lado cliente, necesita establecer la opción en “Sin filtrado automático” en Opciones de correo no deseado de Outlook. “Sin filtrado automático” es la opción predeterminada en las versiones más recientes de Outlook, pero necesita confirmar que se aplicó esta opción para asegurarse de que el filtro de correo no deseado de lado cliente no se aplique en los mensajes. Como administrador, puede exigir que se deshabilite el filtrado de correo no deseado de Outlook si sigue las instrucciones que se indican en [Outlook: Configuración de directiva para deshabilitar la interfaz de usuario de correo no deseado y el mecanismo de filtrado](https://support.microsoft.com/es-ES/kb/2180568).
  
## <a name="see-also"></a>Vea también
<a name="BKMK_please_comment"> </a>

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)
  
[Impedir falsos positivos de correo electrónico marcado como correo no deseado con una lista segura u otras técnicas](prevent-email-from-being-marked-as-spam-0.md)
  

