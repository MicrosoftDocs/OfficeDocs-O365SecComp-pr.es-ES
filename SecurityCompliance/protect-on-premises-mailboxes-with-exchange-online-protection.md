---
title: Proteger buzones locales con Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/1/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
description: Incluso si planea hospedar algunos o todos los buzones de correo locales, aún puede proteger los buzones con Exchange Online Protection (EOP). Para configurar conectores, la cuenta debe ser un administrador global de Office 365 o un administrador de la compañía de Exchange (el grupo de roles de administración de la organización). Para obtener información sobre cómo se relacionan los permisos de Office 365 con los permisos de Exchange, consulte asignación de roles de administrador en Office 365 operado por 21Vianet. Si todos los buzones de Exchange son locales, siga estos pasos para configurar el servicio de EOP.
ms.openlocfilehash: 40fb5471a084cf245d9aef7f7b2b88effb5c4a83
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276040"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>Proteger buzones locales con Exchange Online Protection

> [!NOTE]
> Este artículo solo se aplica a Office 365 operado por 21Vianet en China. 
  
Incluso si planea hospedar algunos o todos los buzones de correo locales, aún puede proteger los buzones con Exchange Online Protection (EOP). Para configurar conectores, la cuenta debe ser un administrador global de Office 365 o un administrador de la compañía de Exchange (el grupo de roles de administración de la organización). Para obtener información sobre cómo se relacionan los permisos de Office 365 con los permisos de Exchange, consulte [asignación de roles de administrador en Office 365 operado por 21Vianet](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac). Si todos los buzones de Exchange son locales, siga estos pasos para configurar el servicio de EOP. 
  
## <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a>Paso 1: Usar el Centro de administración de Office 365 para agregar y comprobar el dominio

1. En el Centro de administración de Office 365, vaya a Instalación para agregar el dominio al servicio.
    
2.  Siga los pasos del portal para agregar los registros DNS aplicables a su proveedor de host DNS para comprobar la propiedad del dominio. 
    
> [!TIP]
> [Agregue el dominio y los usuarios a office 365 operado por 21Vianet](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78) y [cree registros dns para Office 365 cuando administre los registros DNS](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b) son recursos útiles para hacer referencia a medida que agrega el dominio al servicio y configura el DNS. 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Paso 2: agregar destinatarios y configurar el tipo de dominio

Antes de configurar el correo que circula hacia y desde el servicio EOP, se recomienda agregar los destinatarios al servicio. Hay varias maneras de hacerlo, tal y como se documenta en [Administrar usuarios de correo en EOP](https://go.microsoft.com/fwlink/?LinkId=506782). Además, si quiere habilitar el Bloqueo perimetral basado en directorios (DBEB) para aplicar la comprobación de destinatarios dentro del servicio después de agregarlos, debe establecer el tipo de dominio en Autoritativo. Para más información sobre DBEB, vea [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781).
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Paso 3: Usar el EAC para configurar el flujo de correo

Cree conectores en el centro de administración de Exchange (EAC) que permitan el flujo de correo entre EOP y los servidores de correo locales. Para obtener instrucciones detalladas, consulte [crear conectores necesarios para configurar el flujo de correo electrónico básico a través de EOP](https://go.microsoft.com/fwlink/?LinkId=506780).
  
 ¿Cómo sabe si esta tarea funcionó? 
  
 Use el analizador de conectividad remota para ejecutar una prueba que compruebe el flujo de correo entre el servicio y su entorno. Para obtener más información, vea la sección "usar el analizador de conectividad remota para probar la entrega de correo electrónico" en [Test mail Flow with the Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784).
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Paso 4: Permitir el acceso SMTP entrante al puerto 25

Después de configurar los conectores, espere 72 horas para permitir la propagación de las actualizaciones de registros DNS. A continuación, restrinja el tráfico SMTP de entrada-25 entrante en el firewall o los servidores de correo para aceptar correo solo de los centros de recursos de EOP, específicamente de las direcciones IP que aparecen en [direcciones URL e intervalos de direcciones IP para Office 365 operado por 21Vianet](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection). Esto protege su entorno local limitando el ámbito de los mensajes entrantes que puede recibir. Además, si tiene configuraciones en su servidor de correo que controlan las direcciones IP permitidas para conectarse para la retransmisión de correo, actualice también esa configuración.
  
> [!TIP]
> Establezca la configuración en el servidor SMTP con un tiempo de espera de conexión de 60 segundos. La mayoría de las situaciones aceptan esta configuración, lo que permite algo de retraso en el caso de un mensaje enviado con datos adjuntos muy grandes, por ejemplo. 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Paso 5: Usar el Shell para asegurarse de que el correo no deseado se enrute a la carpeta de correo electrónico no deseado de cada usuario

Para asegurarse de que el correo electrónico no deseado se enruta correctamente a la carpeta de correo electrónico no deseado de cada usuario, debe realizar un par de pasos de configuración. Los pasos se proporcionan [para asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](https://go.microsoft.com/fwlink/?LinkId=506804). Si no desea mover mensajes a la carpeta de correo no deseado de cada usuario, puede elegir otra acción si modifica las directivas de filtro de contenido en el centro de administración de Exchange. Para obtener más información, vea [Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805). 
  
## <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a>Paso 6: Usar el Centro de administración de Office 365 para apuntar el registro MX a EOP

Siga los pasos de configuración del dominio de Office 365 para actualizar el registro MX de su dominio, de modo que el correo electrónico entrante fluya a través de EOP. Para obtener más información, puede hacer referencia de nuevo a [crear registros DNS para Office 365 cuando administre los registros DNS](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b).
  
¿Cómo sabe si esta tarea funcionó?
  
 Use el analizador de conectividad remota para ejecutar una prueba que compruebe el registro MX. Para obtener más información, vea la sección "usar el analizador de conectividad remota para probar el registro MX y el conector saliente" en [probar el flujo de correo con el analizador de conectividad remota](https://go.microsoft.com/fwlink/?LinkId=506784). 
  
En este punto, ha comprobado la entrega del servicio para un conector local saliente configurado correctamente, y ha comprobado que su registro MX apunta a EOP. Ahora puede elegir ejecutar las siguientes pruebas adicionales para comprobar que un correo electrónico se entregará correctamente por el servicio a su entorno local:
  
- En Remote Connectivity Analyzer, haga clic en la pestaña **Office 365** y ejecute la prueba **Correo SMTP entrante** situada en **Pruebas de correo de Internet**.
    
- Envíe un mensaje de correo desde cualquier cuenta de correo electrónico basada en web a un destinatario de correo de su organización cuyo dominio coincida con el dominio que agregó al servicio. Confirme la entrega del mensaje al buzón de correo local mediante Microsoft Outlook u otro cliente de correo electrónico.
    
- Si quiere ejecutar una prueba de correo electrónico saliente, puede enviar un mensaje de correo electrónico de un usuario de su organización a una cuenta de correo electrónico basada en web y confirmar si se recibe el mensaje.
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Menos común: una configuración híbrida con buzones de correo locales y en la nube

Si tiene buzones de Exchange local y uno o más buzones en la nube en Exchange Online, tiene una configuración *híbrida* . En una configuración híbrida, características como el uso compartido del calendario de disponibilidad y el enrutamiento de correo funcionan en conjunto en entornos locales y en la nube. Es posible que tenga una instalación híbrida en su ubicación mientras realiza la transición de los buzones a Exchange Online. Un entorno híbrido se configura de forma diferente a la protección independiente de EOP. 
  
Puede elegir un escenario híbrido para aprovechar el correo electrónico basado en la nube para la mayoría de los empleados. Puede hacer esto mientras hospeda también algunos buzones de correo locales; por ejemplo, para el departamento legal. 
  
Una configuración híbrida puede ser compleja, pero tiene muchas ventajas. Para obtener más información sobre la configuración de escenarios híbridos con Exchange, vea [configurIng Exchange Hybrid Deployment Features with Office 365 operated by 21Vianet](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d).
  

