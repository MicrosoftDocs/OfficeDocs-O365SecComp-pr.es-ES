---
title: 'Purga automática cero horas: protección contra correo no deseado y malware'
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/9/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: Purgar cero horas automático (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con el correo no deseado o malware que ya se han entregado a las bandejas de entrada de los usuarios y, a continuación, representa el contenido malintencionado inocua. ZAP ¿cómo esto depende del tipo de contenido malintencionado detectado.
ms.openlocfilehash: dc8901dc7c1db5b323ccbeee610647b8a302fcb3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535800"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Purga automática cero horas: protección contra correo no deseado y malware

Purgar cero horas automático (ZAP) es una característica de protección de correo electrónico que detecta los mensajes con el correo no deseado o malware que ya se han entregado a las bandejas de entrada de los usuarios y, a continuación, representa el contenido malintencionado inocua. ZAP ¿cómo esto depende del tipo de contenido malintencionado detectado.
  
ZAP está disponible con el valor predeterminado de Exchange Online Protection que se incluye con cualquier suscripción de Office 365 que contiene los buzones de Exchange Online.
  
## <a name="how-does-zap-work"></a>¿Cómo funciona ZAP?

Las firmas de motor y malware contra correo no deseadas en las actualizaciones de Office 365 en tiempo real de manera diaria. Sin embargo, los usuarios aún es posible que obtenga malintencionados mensajes entregados a sus bandejas de entrada para una variedad de motivos, incluso cuando el contenido se weaponized en un momento después de que se ha entregado primero a los usuarios. ELIMINAR direcciones esto mediante la supervisión de forma continua las actualizaciones a las firmas de correo no deseado y malware de Office 365, y puede, por tanto, buscar y quitar mensajes entregados ya en las bandejas de entrada. Para el correo que ya se ha identificado como correo no deseado, ZAP mueve los mensajes no leídos a la carpeta de correo electrónico no deseado del usuario. Para recién detectado malware, ZAP quita los datos adjuntos de mensaje de correo electrónico, independientemente de si el correo se ha leído o no. Es true para los mensajes que se han clasificado incorrectamente como malintencionados al revés.
  
La acción ZAP es transparente para el usuario del buzón, navegará no se notifica que el correo se ha movido.
  
Permitir listas, [reglas de flujo de correo](https://go.microsoft.com/fwlink/p/?LinkId=722755)y las reglas de usuario final o filtros adicionales tienen prioridad sobre ZAP.
  
 **En este artículo:**
  
> [Establecer la directiva de filtro de spam](zero-hour-auto-purge.md#BK_SetSpam)
    
> [Vea si ZAP mueve el mensaje](zero-hour-auto-purge.md#BK_DidZAPMove)
    
> [Deshabilitar ZAP](zero-hour-auto-purge.md#BK_Posh)
    
> [Preguntas más frecuentes](zero-hour-auto-purge.md#BK_FAQ)
    
## <a name="working-with-zap"></a>Trabajar con ZAP

ZAP está activado de forma predeterminada, pero es necesario para asegurarse de que un par de condiciones se cumplen:
  
- Directiva de filtro de spam se establece para [mover el mensaje a la carpeta correo no deseado](zero-hour-auto-purge.md#BK_SetSpam).
    
    También puede crear una nueva directiva de filtro de spam que sólo se aplica a un conjunto de usuarios si no desea que todos los buzones que se filtran por ZAP.
    
- El usuario [opciones \> correo electrónico no deseado](https://support.office.com/article/068FA430-F8D7-4518-A8DA-8BC74958F05F).
    
Si desea [ver si ZAP mueve el mensaje](zero-hour-auto-purge.md#BK_DidZAPMove), puede usar la herramienta de seguimiento de mensaje de Exchange Online.
  
Los administradores también pueden [Deshabilitar ZAP](zero-hour-auto-purge.md#BK_Posh) mediante el uso de PowerShell. 
  
 **Para establecer la directiva de filtro de spam**
  
1. Inicie sesión en el [Where iniciar sesión en Office 365 para profesionales](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) y elija **protección** \> **filtro de spam**. 
    
    ![En el EAC, elija protección y, a continuación, filtro de correo no deseado](media/0463c879-63fa-4a6c-9b03-e980d5ef3954.PNG)
  
2. Elegir la directiva de filtro que desea ajustar, o bien seleccionar **Agregar**![icono Agregar](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) para crear una nueva. 
    
    En la captura de pantalla anterior, la directiva se denomina "Predeterminado", pero si crea directivas de filtro de correo no deseado adicional puede proporcionar un nombre diferente. También puede aplicar la directiva a sólo un conjunto limitado de usuarios.
    
3. En la ventana Directiva, elija **acciones de correo no deseado y masiva**y asegúrese de que el **Spam** se establece en **Mover mensaje a la carpeta correo no deseado**. 
    
    Si decide **Guardar** en este momento, la directiva se aplica a su inquilino de Office 365. 
    
    ![Conjunto de acciones de correo no deseado y masiva a Mpve mensaje a la carpeta correo no deseado](media/4332cfb3-89e1-48ba-8da8-9286f2fa1089.PNG)
  
4. Si ha creado una nueva directiva, y que desea aplicar la directiva a sólo un conjunto de usuarios, desplácese hasta la sección **Aplicada a** en la ventana de filtro de la directiva y en los controles de menú elegir los **destinatarios**, **dominio**o **las pertenencias a grupos** ¿desea aplicar la directiva. También puede establecer excepciones y condiciones adicionales. 
    
    ![En la sección aplicado a elegir los destinatarios](media/19ca10db-c0f4-432c-b3de-ad4101a23de6.PNG)
  
    Elija **Guardar** para aplicar la directiva a los usuarios seleccionados. 
    
 **Para ver si ZAP mueve el mensaje**
  
- Puede usar [Buscar y corregir problemas de entrega de correo electrónico como un Office 365 para profesionales admin](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6) para determinar si el mensaje se ha movido por ZAP: 
    
    Busque el texto "cero horas automático purgar (ZAP)" en los detalles de seguimiento para identificar un mensaje que se ha movido por ZAP.
    
 **Para deshabilitar ZAP**
  
- Si desea deshabilitar eliminar para el inquilino de Office 365, o un conjunto de usuarios, use el parámetro **ZapEnabled** de [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet de elevación de privilegios.
    
    En el siguiente ejemplo, ZAP está deshabilitado para una directiva de filtro de contenido denominada "Prueba".
    
||
|:-----|
|
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

|
   
## <a name="faq"></a>Preguntas más frecuentes
<a name="BK_FAQ"> </a>

 **¿Qué ocurre si un mensaje legítimo se mueve a la carpeta correo electrónico no deseado?**
  
Debe seguir el proceso de generación de informes normal de falsos positivos. La única razón se pasaría el mensaje de la Bandeja de entrada a la carpeta correo electrónico no deseado sería debido a que el servicio ha determinado que el mensaje es correo no deseado o malintencionado.
  
 **¿Qué ocurre si utilizo la cuarentena de Office 365 en lugar de la carpeta de correo electrónico no deseado?**
  
ZAP no mover los mensajes en cuarentena desde la Bandeja de entrada en este momento.
  
 **¿Qué ocurre si tiene una regla de flujo de correo personalizado (bloquear o permitir regla)?**
  
Las reglas creadas por administradores (reglas de flujo de correo) o las reglas de bloqueo y permitir tiene prioridad. Este tipo de mensajes se excluye de los criterios de la característica.
  
## <a name="related-topics"></a>Temas relacionados
<a name="BK_FAQ"> </a>

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)
  
[Bloquear el correo no deseado con el filtro de correo no deseado de Office 365 para evitar problemas de negativos falsos](block-email-spam-to-prevent-false-negatives.md)
  

