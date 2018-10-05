---
title: Habilite el complemento de mensajes de informe
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/04/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: Obtenga información sobre cómo habilitar el complemento en el mensaje de informe para Outlook y Outlook en el web, para usuarios individuales o de toda la organización.
ms.openlocfilehash: 2eb12bd14f92e2d4ee26fbef817578d32e737b85
ms.sourcegitcommit: e14dec9bed0c0009acbc1f1cb80b4d0794ad5739
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2018
ms.locfileid: "25435097"
---
# <a name="enable-the-report-message-add-in"></a>Habilite el complemento de mensajes de informe

El mensaje de informe complemento para Outlook permite que las personas que desea incorporar fácilmente clasificación incorrecta de correo electrónico, si seguros o malintencionado, Microsoft y sus filiales para el análisis. Microsoft utiliza estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico. Además, si su organización usa servicios de Microsoft Cloud que incluyen [La protección de amenaza avanzada de Office 365](office-365-atp.md) o [Información sobre amenazas](office-365-ti.md), el complemento en el mensaje de informe proporciona el equipo de seguridad de su organización con información útil Puede usar para revisar y actualizar las directivas de seguridad. 

Por ejemplo, suponga que las personas son informes una gran cantidad de mensajes como suplantación de identidad. Superficies de esta información en el [Panel de seguridad](security-dashboard.md) y otros informes. Equipo de seguridad de su organización puede usar esta información como una indicación de que las directivas contra suplantación de identidad es posible que deba actualizarse. O bien, si las personas informa de una gran cantidad de mensajes que se han marcado como correo no deseado como no deseado mediante el uso del complemento en el mensaje de informe, equipo de seguridad de su organización es posible que necesite ajustar [las directivas contra correo no deseadas](configure-the-anti-spam-policies.md).  
  
Si es un usuario individual, se puede [Habilitar el complemento en el mensaje de informe para usted mismo](#get-the-report-message-add-in-for-yourself). 
  
Si es un administrador de Exchange Online, se puede [Habilitar el complemento en el mensaje de informe para la organización](#get-and-enable-the-report-message-add-in-for-your-organization).
    
## <a name="get-the-report-message-add-in-for-yourself"></a>Obtener el mensaje de informe de complemento para usted mismo

1. En el [almacén de Office](https://appsource.microsoft.com/product/office/WA104381180?src=office), recibe el mensaje de informe de complemento.
    
2. Elija **obtener TI ahora**.<br/>![Notificar mensaje: obtenerlo ahora](media/ReportMessageGETITNOW.png)<br/> 
    
3. Revise los términos de uso y política de privacidad. A continuación, elija **continuar**. 
    
4. Inicie sesión en su correo electrónico de Office 365 con su trabajo o cuenta school (para uso empresarial) o su cuenta de Microsoft (para uso personal).
    

Después de que el complemento está instalado y habilitado, verá los iconos siguientes: 

- En Outlook el icono tiene el siguiente aspecto: <br/> ![Icono informe de mensaje, complemento para Outlook](media/OutlookReportMessageIcon.png)<br/>
- En Outlook Web App el icono tiene el siguiente aspecto:<br/>![Outlook en el icono mensaje de informe de Web, complemento](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

Como un paso siguiente, obtenga información sobre cómo [usar el complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Obtener y habilitar el complemento en el mensaje de informe para la organización

> [!IMPORTANT]
> Debe ser un administrador global de Office 365 o un administrador de Exchange Online para llevar a cabo esta tarea.

1. Vaya a [https://portal.office.com](https://portal.office.com) e iniciar sesión con su cuenta de trabajo o escuela. 
    
2. Elija **administración** para ir al centro de administración. 
    
3. Elija **centros de administración** \> **Exchange** para ir al centro de administración de Exchange (EAC). 
    
4. Elija la **organización** \> **complementos**. 
    
5. Elija **+**  >  **Agregar desde el almacén de Office**.<br/>![Elija Agregar desde el almacén de Office](media/EAC-Org-AddFromOfficeStore.png)<br/>Se abrirá la tienda de Office en el explorador web.
    
6. Busca el mensaje de informe.<br/>![Busca el mensaje de informe](media/ReportMessageSearchOfficeStore.png)<br/>
    
7. En la lista de **aplicaciones** , seleccione **Informe de mensaje**y, a continuación, elija **Obtener TI ahora**.<br/>![Elija GET TI ahora](media/ReportMessageGETITNOW.png)<br/> 
    
8. Revise los términos de uso y política de privacidad. A continuación, elija **continuar**. 
    
    ![Haga clic en Continuar para aceptar los términos y la directiva de privacidad](media/ReportMessageTermsAndConditions.png)
  
9. Se abre un Asistente para ayudarle a configurar la información de la revisión de complemento de mensaje de informe y elija **siguiente** para continuar.<br/>![Mensaje complemento Asistente para informes para Office 365](media/ReportMessageAdminInstallUI.png)<br/> 

10. Especificar la configuración predeterminada que desee que los usuarios tengan para el complemento en el mensaje de informe.<br/>![Especificar la configuración predeterminada para el complemento en el mensaje de informe](media/ReportMessageUserOptionsAdminsSet.png)<br/>
    
11. Especificar quién obtiene el mensaje de informe de complemento. <br/>![Especificar quién obtiene el mensaje de informe de complemento](media/ReportMessageChooseWhoGetsItAdminSettings.png)<br/>

12. Elija **Guardar**.

Dependiendo de lo que seleccionada utilizando al asistente, las personas de su organización tendrán el mensaje de informe complemento disponible. Las personas de su organización verán los iconos siguientes: 

- En Outlook el icono tiene el siguiente aspecto: <br/> ![Icono informe de mensaje, complemento para Outlook](media/OutlookReportMessageIcon.png)<br/>
- En Outlook Web App el icono tiene el siguiente aspecto:<br/>![Outlook en el icono mensaje de informe de Web, complemento](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>


A continuación, obtenga información sobre cómo [usar el complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)y configurar una regla para ver los mensajes de correo electrónico ha informado.

## <a name="review-or-edit-the-default-settings-for-the-report-message-add-in"></a>Revisar o modificar la configuración predeterminada para el complemento en el mensaje de informe

Puede revisar y modificar la configuración predeterminada para el complemento de mensaje de informe mediante el centro de administración. 

> [!IMPORTANT]
> Debe ser un administrador global de Office 365 o un administrador de Exchange Online para llevar a cabo esta tarea.
    
1. Si sólo ha instalado el complemento en el mensaje de informe para su organización, ya estará en la página Servicios & complementos. De lo contrario, vaya [aquí](https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns) e iniciar sesión con su cuenta de trabajo o escuela para Office 365.

2. Buscar **Mensaje de informe**y, a continuación, selecciónelo.<br/>![Servicios y complementos para Office 365](media/ReportMessage-o365servicesaddins.png)<br/> 
    
3. Se abre un panel que muestra la configuración que se han seleccionado para el complemento en el mensaje de informe durante la implementación.<br/>![Configuración para el complemento en el mensaje de informe](media/ReportMessage-reviewaddinsettings.png)<br/> 

4. Revise y si es necesario, modificar la configuración para el complemento en el mensaje de informe y, a continuación, guarde los cambios.
    
  
## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>Configurar una regla para obtener una copia de los mensajes de correo electrónico que notifica a los usuarios

> [!IMPORTANT]
> Debe ser un administrador de Exchange Online para realizar esta tarea.
  
Puede configurar una regla para obtener una copia de los mensajes de correo electrónico que notifica a los usuarios de la organización. Para ello, después de haber descargado y habilitado el complemento en el mensaje de informe para la organización.
  
1. En el EAC, seleccione el **flujo de correo** \> **reglas**. 
    
2. Elija **+** \> **crear una nueva regla**. 
    
3. En el cuadro **nombre** , escriba un nombre, como los envíos.
    
4. En la lista **aplicar esta regla si** , elija **la dirección del destinatario incluye …**. 
    
5. En la pantalla **especificar palabras o frases** , agregue junk@office365.microsoft.com y phish@office365.microsoft.com y, a continuación, elija **Aceptar**. 
    
    ![Especificar las direcciones de correo electrónico no deseado y phishing para la regla](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)
  
6. En la lista **haga lo siguiente...** , elija **CCO del mensaje a...**. 
    
7. Agregar un administrador global, Administrador de seguridad o lector de seguridad que debe recibir una copia de cada mensaje de correo electrónico que informan de las personas a Microsoft y, a continuación, elija **Aceptar**. 
    
    ![Agregar un administrador global o de seguridad para recibir una copia de cada mensaje conocida](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)
  
8. Seleccione **esta regla con nivel de gravedad de auditoría**y elija **medio**. 
    
9. En **Elegir un modo para esta regla**, haga clic en **Aplicar**. 
    
    ![Configurar una regla para obtener una copia de cada mensaje conocida](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)
  
10. Elija **Guardar**. 
    
Con esta regla en su lugar, siempre que una persona de su organización notifica un mensaje de correo electrónico mediante el complemento de mensaje de informe, el administrador global, Administrador de seguridad o lector de seguridad recibirá una copia de ese mensaje. Puede habilitar esta información le permite configurar o ajustar las directivas, como las directivas de [Office 365 ATP seguros vínculos](atp-safe-links.md) . 
  
## <a name="related-topics"></a>Temas relacionados

[Use el complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[Ver los informes de seguridad de correo electrónico de la seguridad &amp; centro de cumplimiento](view-email-security-reports.md)

[Visualización de informes para la protección de amenaza avanzada de Office 365](view-reports-for-atp.md)

[Use el explorador en la seguridad &amp; centro de cumplimiento](use-explorer-in-security-and-compliance.md)
  

