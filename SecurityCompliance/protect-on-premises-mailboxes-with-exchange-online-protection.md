---
title: Proteger los buzones locales con Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/1/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
description: Incluso si tiene previsto hospedar algunos o todos los buzones locales, aún puede proteger los buzones de correo con Exchange Online Protection (EOP). Para configurar conectores, su cuenta debe ser un administrador Global de Office 365, o un administrador de la compañía de Exchange (el grupo de roles de administración de la organización). Para obtener información acerca de cómo se relacionan con los permisos de Office 365 a los permisos de Exchange, consulte Asignación de roles de administrador en Office 365 operado por 21Vianet. Si todos los buzones de Exchange son locales, siga estos pasos para configurar el servicio EOP.
ms.openlocfilehash: 4751bb2183e61d292805d1799519644b77b08c2a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536847"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>Proteger los buzones locales con Exchange Online Protection

> [!NOTE]
> En este artículo sólo se aplica a Office 365 operado por 21Vianet en China. 
  
Incluso si tiene previsto hospedar algunos o todos los buzones locales, aún puede proteger los buzones de correo con Exchange Online Protection (EOP). Para configurar conectores, su cuenta debe ser un administrador Global de Office 365, o un administrador de la compañía de Exchange (el grupo de roles de administración de la organización). Para obtener información acerca de cómo se relacionan con los permisos de Office 365 a los permisos de Exchange, consulte [asignación de roles de administrador en Office 365 operado por 21Vianet](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac). Si todos los buzones de Exchange son locales, siga estos pasos para configurar el servicio EOP. 
  
## <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a>Paso 1: Usar el Centro de administración de Office 365 para agregar y comprobar el dominio

1. En el Centro de administración de Office 365, vaya a Instalación para agregar el dominio al servicio.
    
2.  Siga los pasos descritos en el portal para agregar los registros DNS correspondientes a su proveedor de hospedaje de DNS con el fin de comprobar la propiedad de dominio. 
    
> [!TIP]
> [Agregar un dominio y a los usuarios de Office 365 operado por 21Vianet](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78) y [crear registros DNS para Office 365 al administrar sus registros DNS](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b) son recursos útiles para hacer referencia al agregar su dominio al servicio y configurar DNS. 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Paso 2: Agregar a destinatarios y configurar el tipo de dominio

Antes de configurar el correo que circula hacia y desde el servicio EOP, se recomienda agregar los destinatarios al servicio. Hay varias maneras de hacerlo, tal y como se documenta en [Administrar usuarios de correo en EOP](https://go.microsoft.com/fwlink/?LinkId=506782). Además, si quiere habilitar el Bloqueo perimetral basado en directorios (DBEB) para aplicar la comprobación de destinatarios dentro del servicio después de agregarlos, debe establecer el tipo de dominio en Autoritativo. Para más información sobre DBEB, vea [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781).
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Paso 3: Usar el EAC para configurar el flujo de correo

Crear conectores en el centro de administración de Exchange (EAC) que permiten el flujo de correo entre los servidores de correo local y de elevación de privilegios. Para obtener instrucciones detalladas, consulte [Create necesario conectores para configurar el flujo de correo electrónico básica a través de elevación de privilegios](https://go.microsoft.com/fwlink/?LinkId=506780).
  
 ¿Cómo sabe si esta tarea funcionó? 
  
 Usar el analizador de conectividad remota para ejecutar una prueba que comprueba el flujo de correo entre el servicio y su entorno. Para obtener más información, vea la sección "Usar el analizador de conectividad remota para probar la entrega de correo electrónico" en el [flujo de correo con el analizador de conectividad remota de prueba](https://go.microsoft.com/fwlink/?LinkId=506784).
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Paso 4: Permitir el acceso SMTP entrante al puerto 25

Una vez configurado conectores, espere 72 horas para permitir la propagación de las actualizaciones de registro DNS. De este modo, restringir el tráfico entrante puerto 25 SMTP en sus servidores de correo o de firewall y acepten correo sólo de los centros de datos EOP, específicamente desde las direcciones IP enumeradas en [intervalos para Office 365 operado por 21Vianet de direcciones IP y URL de](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection). Esto protege su entorno local al limitar el ámbito de los mensajes entrantes que puede recibir. Además, si tiene una configuración en el servidor de correo que controlan las direcciones IP permitidas para conectar para la retransmisión de correo, actualizar esas opciones de configuración.
  
> [!TIP]
> Establezca la configuración en el servidor SMTP con un tiempo de espera de conexión de 60 segundos. La mayoría de las situaciones aceptan esta configuración, lo que permite algo de retraso en el caso de un mensaje enviado con datos adjuntos muy grandes, por ejemplo. 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Paso 5: Usar el Shell para asegurarse de que el correo no deseado se enrute a la carpeta de correo electrónico no deseado de cada usuario

Para asegurarse de que el correo electrónico de spam (no deseado) se enruta correctamente a la carpeta de correo electrónico no deseado de cada usuario, debe realizar un par de pasos de configuración. Los pasos se proporcionan en [asegurarse de que el correo no deseado se enrute a la carpeta de correo no deseado de cada usuario](https://go.microsoft.com/fwlink/?LinkId=506804). Si no desea mover los mensajes a la carpeta de correo no deseado de cada usuario, es posible que elija otra acción mediante la edición de las directivas de filtro de contenido en el centro de administración de Exchange. Para obtener más información, vea [Configuración de directivas de filtro de contenido](https://go.microsoft.com/fwlink/?LinkId=506805). 
  
## <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a>Paso 6: Usar el Centro de administración de Office 365 para apuntar el registro MX a EOP

Siga los pasos de configuración de dominio de Office 365 para actualizar el registro MX para su dominio, para que su correo electrónico entrante fluye a través de elevación de privilegios. Para obtener más información, puede hacer referencia vuelva a [crear registros DNS para Office 365 al administrar sus registros DNS](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b).
  
¿Cómo sabe si esta tarea funcionó?
  
 Usar el analizador de conectividad remota para ejecutar una prueba que comprueba el registro MX. Para obtener más información, vea la sección "Usar el analizador de conectividad remota para probar su registro MX y el conector de salida" en el [flujo de correo con el analizador de conectividad remota de prueba](https://go.microsoft.com/fwlink/?LinkId=506784). 
  
En este punto, ha comprobado la entrega del servicio para un conector local saliente configurado correctamente, y ha comprobado que su registro MX apunta a EOP. Ahora puede elegir ejecutar las siguientes pruebas adicionales para comprobar que un correo electrónico se entregará correctamente por el servicio a su entorno local:
  
- En Remote Connectivity Analyzer, haga clic en la pestaña **Office 365** y ejecute la prueba **Correo SMTP entrante** situada en **Pruebas de correo de Internet**.
    
- Envíe un mensaje de correo desde cualquier cuenta de correo electrónico basada en web a un destinatario de correo de su organización cuyo dominio coincida con el dominio que agregó al servicio. Confirme la entrega del mensaje al buzón de correo local mediante Microsoft Outlook u otro cliente de correo electrónico.
    
- Si quiere ejecutar una prueba de correo electrónico saliente, puede enviar un mensaje de correo electrónico de un usuario de su organización a una cuenta de correo electrónico basada en web y confirmar si se recibe el mensaje.
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Menos común: una configuración híbrida con buzones locales y en la nube

Si dispone de los buzones de correo Exchange local y uno o más buzones en la nube en Exchange Online, tiene una configuración *híbrida* . En una configuración híbrida, características como libre/ocupado uso compartido de calendarios y enrutamiento de correo funcionan conjuntamente en sus instalaciones y entornos de nube. Puede que tenga una configuración híbrida en su lugar, mientras que realizar la transición de buzones de correo a Exchange Online. Se configura un entorno híbrido diferente de protección de elevación de privilegios independiente. 
  
Es posible que elija un escenario híbrido de sacar partido de correo electrónico basada en la nube para la mayoría de los empleados. Puede hacer esto mientras que también hospeda algunos buzones locales; Por ejemplo, para el departamento legal. 
  
Una configuración híbrida puede ser compleja, pero tiene muchos beneficios. Para obtener más información acerca de cómo configurar escenarios híbridos con Exchange, consulte [características de implementación híbrida de configuración de Exchange con Office 365 operado por 21Vianet](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d).
  

