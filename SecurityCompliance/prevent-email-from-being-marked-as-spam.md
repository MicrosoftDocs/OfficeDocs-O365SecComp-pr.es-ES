---
title: Evitar que el correo electrónico real se marque como correo no deseado en Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 34823bbc-a3e3-4949-ba42-97c73997eeed
description: Obtenga información sobre cómo separar el correo electrónico real del correo no deseado y evitar que se marque como correo no deseado en Office 365.
ms.openlocfilehash: d092dc0a1a222f51f48102eb8c07e8e6051aa1bd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535818"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a>Evitar que el correo electrónico real se marque como correo no deseado en Office 365

 **¿Se está marcando el correo electrónico real como correo no deseado en Office 365? Siga este procedimiento.**
  
Exchange Online Protection (EOP) intenta filtrar el correo no deseado y mantener la bandeja de entrada libre de contenido que los usuarios no quieran ver. Pero, a veces, EOP filtra mensajes que sí quieren ver los usuarios.
  
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a>Determinar el motivo por el que un mensaje se marcó como correo no deseado

Muchos de los problemas relacionados con el correo no deseado en Office 365 pueden solucionarse si se [analizan los encabezados de mensaje de correo electrónico](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) y se determina cuál fue el problema. Si ve un encabezado de mensaje llamado X-Forefront-Antispam-Report que contiene la cadena SFV:NSPM, quiere decir que Exchange Online Protection (EOP) analizó el mensaje y determinó que era correo no deseado. En ese caso, es muy recomendable que [use el complemento Denunciar mensaje](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) para ayudarnos a mejorar nuestros filtros. Si no ve este valor en los encabezados, puede que no se realizara un análisis de correo no deseado del mensaje, o bien se produjo un problema de configuración que causó que el mensaje se clasificara de forma incorrecta como correo no deseado. Obtenga [más información sobre los encabezados de mensaje contra correo no deseado](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).
  
En el encabezado, busque los siguientes encabezados y valores.
  
### <a name="x-forefront-antispam-report"></a>X-Forefront-Antispam-Report

- **SFV:BLK** Indica que el mensaje se marcó como correo no deseado porque la dirección de envío se encuentra en la lista de remitentes bloqueados del destinatario. 
    
- **SFV:SKS** Indica que el mensaje se marcó como correo no deseado antes del filtro de contenido. Esto puede ocurrir debido a una regla de transporte que marque el mensaje como correo no deseado. Ejecute un seguimiento de mensajes para ver si se desencadenó una regla de transporte que pudiera establecer un nivel de confianza contra correo no deseado (SCL) alto. 
    
- **SFV:SKB** Indica que el mensaje se marcó como correo no deseado porque coincidía con una lista de bloqueados en la directiva de filtro contra correo no deseado. 
    
- **SFV:BULK** Indica que el valor de nivel de quejas masivas (BCL) que se encuentran en el encabezado X-Microsoft-Antispam está por encima del umbral de correo masivo que se estableció para el filtro de contenido. El correo masivo es el correo electrónico al que puede que los usuarios se suscribieran, pero se sigue considerando correo no deseado. En el encabezado de mensaje, busque la propiedad BCL (nivel de confianza en masa) en el encabezado X-Microsoft-Antispam. Si el valor de BCL es inferior al umbral establecido en el filtro de correo no deseado, puede ajustar el umbral para que, en su lugar, marque estos tipos de mensajes masivos como correo no deseado. Diferentes usuarios tienen distintas tolerancias y preferencias para la [administración del correo masivo](https://blogs.msdn.microsoft.com/tzink/2014/08/25/different-levels-of-bulk-mail-filtering-in-office-365/). Puede crear distintas directivas o reglas para diferentes preferencias de usuario.
    
- **CAT:SPOOF** o **CAT:PHISH** Indica que el mensaje parece suplantado, lo que significa que el origen del mensaje no se puede validar y podría ser sospechoso. Si es válido, el remitente tendrá que asegurarse de que tiene una configuración correcta de los registros SPF y DKIM. Para obtener más información, vea el encabezado Authentication-Results. Aunque puede resultar difícil conseguir que todos los remitentes usen métodos de autenticación de correo electrónico adecuados, omitir estas comprobaciones puede ser muy peligroso y se considera una de las principales causas de peligro. 
    
### <a name="x-customspam"></a>X-CustomSpam

- La presencia de este encabezado indica que el mensaje se marcó como correo no deseado porque una de las [opciones avanzadas contra correo no deseado está habilitada](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) en el filtro de correo no deseado. A menos que necesite estas características, le recomendamos que use la configuración predeterminada. 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a>Soluciones para otras causas de recibir demasiado correo no deseado

Para funcionar correctamente, Exchange Online Protection (EOP) necesita que los administradores completen algunas tareas. Si no es el administrador de su espacio empresarial de Office 365 y recibe demasiado correo no deseado, le recomendamos que trabaje con su administrador en relación con estas tareas. De lo contrario, puede ir directamente a la sección para usuarios.
  
### <a name="for-admins"></a>Para administradores

- **Apuntar los registros DNS a Office 365** Para que EOP proporcione protección, los registros DNS del agente de intercambio de correo (MX) de todos los dominios tienen que apuntar a Office 365 (y únicamente a Office 365). Si los registros MX no apuntan a Office 365, EOP no proporcionará el filtrado de correo no deseado para los usuarios. Si quiere usar otro servicio o dispositivo para proporcionar filtrado de correo no deseado para su dominio, puede deshabilitar la protección contra correo no deseado en EOP. Para hacerlo, cree una regla de transporte que establezca el valor de SCL en -1. Si posteriormente decide usar EOP, asegúrese de quitar esta regla de transporte. 
    
- **Deshabilitar el filtro SmartScreen en Outlook** Si los usuarios usan el cliente para equipo de escritorio de Outlook, tendrán que deshabilitar la función de filtro SmartScreen, que se considera descontinuada. Si está habilitada, puede causar falsos positivos. Esto no es necesario si se ejecuta una versión actualizada del cliente de Outlook para equipo de escritorio. 
    
- **Activar el complemento Denunciar mensaje para los usuarios** Es muy recomendable que [habilite el complemento Denunciar mensaje para los usuarios](enable-the-report-message-add-in.md). Como administrador, es posible que también pueda ver los comentarios que los usuarios envían y usar cualquier patrón para ajustar la configuración que pueda estar causando problemas.
    
- **Permitir un remitente de forma inmediata** Si necesita permitir un remitente de forma inmediata, es muy recomendable que **SOLO permita una dirección IP de remitente específica**. Como alternativa, puede permitir un remitente y, además, asegurarse de que este supere una comprobación de autenticación, como SPF o DKIM; para hacerlo, cree una regla de transporte que examine **tanto** el dominio del remitente como un encabezado Authentication-Results correcto. 
    
### <a name="for-users"></a>Para usuarios

- **Denunciar correo no deseado a Microsoft** Informe de los mensajes de correo no deseado a Microsoft con el [complemento Denunciar mensaje](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Además, también puede enviar un mensaje a junk@office365.microsoft.com y adjuntar uno o más mensajes al informe.
    
    **Importante** Si no reenvía los mensajes como datos adjuntos, [no se incluirán los encabezados y no podremos mejorar](https://blogs.msdn.microsoft.com/tzink/2017/11/30/when-creating-support-tickets-about-spam-be-sure-to-include-message-headers/) el filtrado de correo no deseado en Office 365. 
    
- **Agregar un remitente a la lista de permitidos (usar con moderación)** Como último recurso, puede [Bloquear o permitir (configuración de correo electrónico no deseado)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). Si lo hace, tenga en cuenta que podría permitirse un intento de suplantación de identidad (phishing) dirigido en su bandeja de entrada.
    

