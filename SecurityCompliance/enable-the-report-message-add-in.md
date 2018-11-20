---
title: Habilite el complemento de mensajes de informe
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/19/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: Obtenga información sobre cómo habilitar el complemento en el mensaje de informe para Outlook y Outlook en el web, para usuarios individuales o de toda la organización.
ms.openlocfilehash: a62e3e6250d2eccd2109a71f994713e2dd1b262e
ms.sourcegitcommit: 6669b7aae26965145e85d9613d3091bf389f000b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2018
ms.locfileid: "26618926"
---
# <a name="enable-the-report-message-add-in"></a>Habilite el complemento de mensajes de informe

## <a name="overview"></a>Información general

El mensaje de informe complemento para Outlook y Outlook en el Web permite que las personas que desea incorporar fácilmente clasificación incorrecta de correo electrónico, si seguros o malintencionado, Microsoft y sus filiales para el análisis. Microsoft utiliza estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico. Además, si su organización usa [Protección de amenaza avanzada de Office 365](office-365-atp.md) o [Información sobre amenazas de Office 365](office-365-ti.md), el complemento en el mensaje de informe proporciona equipo de seguridad de su organización con información útil que puedan usar para revisar y actualizar directivas de seguridad. 

Por ejemplo, suponga que las personas son informes una gran cantidad de mensajes como suplantación de identidad. Superficies de esta información en el [Panel de seguridad](security-dashboard.md) y otros informes. Equipo de seguridad de su organización puede usar esta información como una indicación de que las directivas contra suplantación de identidad es posible que deba actualizarse. O bien, si las personas informa de una gran cantidad de mensajes que se han marcado como correo no deseado como no deseado mediante el uso del complemento en el mensaje de informe, equipo de seguridad de su organización es posible que necesite ajustar [las directivas contra correo no deseadas](configure-the-anti-spam-policies.md). 

El complemento en el mensaje de informe funciona con la suscripción de Office 365 y los siguientes productos:
 - Outlook en la Web
 - Outlook 2013 SP1
 - Outlook 2016
 - Outlook 2016 para Mac
 - Outlook incluido con Office 365 ProPlus
  
Si es un usuario individual, se puede [Habilitar el complemento en el mensaje de informe para usted mismo](#get-the-report-message-add-in-for-yourself). 
  
Si usted es un administrador global de Office 365 o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, se puede [Habilitar el complemento en el mensaje de informe para la organización](#get-and-enable-the-report-message-add-in-for-your-organization). El complemento del mensaje de informe ahora está disponible a través de la [Implementación centralizado](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).
    
## <a name="get-the-report-message-add-in-for-yourself"></a>Obtener el mensaje de informe de complemento para usted mismo

1. En [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), busque el [complemento en el mensaje de informe](https://appsource.microsoft.com/product/office/wa104381180).
    
2. Elija **obtener TI ahora**.<br/>![Notificar mensaje: obtenerlo ahora](media/ReportMessageGETITNOW.png)<br/> 
    
3. Revise los términos de uso y política de privacidad. A continuación, elija **continuar**. 
    
4. Inicie sesión en su correo electrónico de Office 365 con su trabajo o cuenta school (para uso empresarial) o su cuenta de Microsoft (para uso personal).
    
Después de que el complemento está instalado y habilitado, verá los iconos siguientes: 

- En Outlook el icono tiene el siguiente aspecto: <br/> ![Icono informe de mensaje, complemento para Outlook](media/OutlookReportMessageIcon.png)<br/>
- En Outlook Web App el icono tiene el siguiente aspecto:<br/>![Outlook en el icono mensaje de informe de Web, complemento](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

Como un paso siguiente, obtenga información sobre cómo [usar el complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Obtener y habilitar el complemento en el mensaje de informe para la organización

> [!IMPORTANT]
> Debe ser un administrador global de Office 365 o un administrador de Exchange Online para llevar a cabo esta tarea. Además, Exchange debe configurarse para usar la autenticación de OAuth para obtener más información, vea [requisitos de Exchange (centralizado de implementación de complementos)](https://docs.microsoft.com/en-us/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements). 

1. Vaya a la [página de complementos y servicios](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) en el nuevo centro de administración de Microsoft 365.<br/>![Página de servicios y complementos en el nuevo centro de administración de Microsoft 365](media/ServicesAddInsPageNewM365AdminCenter.png)<br/> 
    
2. Elija **+ implementar Add-in**.<br/>![Elija implementar complemento](media/ServicesAddIns-ChooseDeployAddIn.png)<br/> 
    
3. En la pantalla nuevo complemento, revise la información y, a continuación, elija **siguiente**.<br/>![Detalles del complemento nuevo](media/NewAddInScreen1.png)<br/>
    
4. Seleccione **Agregar un complemento de la tienda de Office**y, a continuación, elija **siguiente**.<br/>![Agregar un nuevo complemento](media/NewAddInScreen2.png)<br/> 
    
5. Búsqueda de mensaje de informe y en la lista de resultados, junto al complemento mensaje de informe, elija Agregar.<br/>![Buscar mensajes de informe y, a continuación, elija Agregar](media/NewAddInScreen3.png)<br/>
    
6. En la pantalla del mensaje del informe, revise la información y, a continuación, elija **siguiente**.<br/>![Detalles del informe de mensaje](media/ReportMessageAdd-InNewScreen4.png)<br/>

7. Especificar la configuración predeterminada del usuario para Outlook y, a continuación, elija **siguiente**.<br/>![Informe de configuración de mensaje predeterminada para Outlook](media/ReportMessageOptionsScreen5.png)<br/>

8. Especificar quién obtiene el mensaje de informe complemento y, a continuación, elija **Guardar**. <br/>![Que obtiene el mensaje de informe de complemento](media/ReportMessageOptionsScreen6.png)<br/>

> [!TIP]
> Se recomienda [Configurar una regla para obtener una copia de los mensajes de correo electrónico que notifica a los usuarios](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)

Dependiendo de lo que seleccionada utilizando al asistente, las personas de su organización tendrán el [complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) disponibles. Las personas de su organización verán los iconos siguientes: 

- En Outlook el icono tiene el siguiente aspecto: <br/> ![Icono informe de mensaje, complemento para Outlook](media/OutlookReportMessageIcon.png)<br/>
- En Outlook Web App el icono tiene el siguiente aspecto:<br/>![Outlook en el icono mensaje de informe de Web, complemento](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>Configurar una regla para obtener una copia de los mensajes de correo electrónico que notifica a los usuarios

> [!IMPORTANT]
> Debe ser un administrador de Exchange Online para realizar esta tarea.
  
Puede configurar una regla para obtener una copia de los mensajes de correo electrónico que notifica a los usuarios de la organización. Para ello, después de haber descargado y habilitado el complemento en el mensaje de informe para la organización.
  
1. En el EAC, seleccione el **flujo de correo** \> **reglas**. 
    
2. Elija **+** \> **crear una nueva regla**. 
    
3. En el cuadro **nombre** , escriba un nombre, como los envíos.
    
4. En la lista **aplicar esta regla si** , elija **la dirección del destinatario incluye …**. 
    
5. En la pantalla **especificar palabras o frases** , agregue `junk@office365.microsoft.com` y `phish@office365.microsoft.com`y, a continuación, elija **Aceptar**.<br/>![Especificar las direcciones de correo electrónico no deseado y phishing para la regla](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)<br/>
  
6. En la lista **haga lo siguiente...** , elija **CCO del mensaje a...**. 
    
7. Agregar un administrador global, Administrador de seguridad o lector de seguridad que debe recibir una copia de cada mensaje de correo electrónico que informan de las personas a Microsoft y, a continuación, elija **Aceptar**.<br/>![Agregar un administrador global o de seguridad para recibir una copia de cada mensaje conocida](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)<br/>
  
8. Seleccione **esta regla con nivel de gravedad de auditoría**y elija **medio**. 
    
9. En **Elegir un modo para esta regla**, haga clic en **Aplicar**.<br/>![Configurar una regla para obtener una copia de cada mensaje conocida](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)<br/>
  
10. Elija **Guardar**. 
    
Con esta regla en su lugar, siempre que una persona de su organización notifica un mensaje de correo electrónico mediante el complemento de mensaje de informe, el administrador global, Administrador de seguridad o lector de seguridad recibirá una copia de ese mensaje. Puede habilitar esta información le permite configurar o ajustar las directivas, como las directivas de [Office 365 ATP seguros vínculos](atp-safe-links.md) . 

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Revisar o modificar la configuración para el complemento en el mensaje de informe

Puede revisar y modificar la configuración predeterminada para el informe de mensaje complemento en la [página Servicios & Add-Ins](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns). 

> [!IMPORTANT]
> Debe ser un administrador global de Office 365 o un administrador de Exchange Online para llevar a cabo esta tarea.
    
1. Vaya a la [página de complementos y servicios](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) en el nuevo centro de administración de Microsoft 365.<br/>![Página de servicios y complementos en el nuevo centro de administración de Microsoft 365](media/ServicesAddInsPageNewM365AdminCenter.png)<br/>

2. Busque y seleccione el complemento del mensaje de informe.<br/>![Busque y seleccione el complemento en el mensaje de informe](media/FindReportMessageAddIn.png)<br/> 
    
3. En la pantalla de mensaje de informe, revisar y editar la configuración según corresponda para su organización.<br/>![Configuración para el complemento en el mensaje de informe](media/EditReportMessageAddIn.png)<br/> 

## <a name="learn-how-to-use-the-report-message-add-in"></a>Obtenga información sobre cómo usar el complemento en el mensaje de informe

Cómo [usar el complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
  
## <a name="related-topics"></a>Temas relacionados

[Use el complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[Ver los informes de seguridad de correo electrónico de la seguridad &amp; centro de cumplimiento](view-email-security-reports.md)

[Visualización de informes para la protección de amenaza avanzada de Office 365](view-reports-for-atp.md)

[Use el explorador en la seguridad &amp; centro de cumplimiento](use-explorer-in-security-and-compliance.md)
  

