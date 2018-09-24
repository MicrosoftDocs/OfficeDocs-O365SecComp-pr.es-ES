---
title: Habilite el complemento de mensajes de informe
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/28/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: Obtenga información sobre cómo habilitar el complemento en el mensaje de informe para Outlook y Outlook en el web, para usuarios individuales o de toda la organización.
ms.openlocfilehash: 68b70cdb138ad38216f188116e576a24304a3769
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972272"
---
# <a name="enable-the-report-message-add-in"></a>Habilite el complemento de mensajes de informe

El mensaje de informe complemento para Outlook permite que las personas que desea incorporar fácilmente clasificación incorrecta de correo electrónico, si seguros o malintencionado, Microsoft y sus filiales para el análisis. Microsoft utiliza estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico.
  
Si es un usuario individual, puede habilitar el complemento en el mensaje de informe para usted mismo. 
  
Si es un administrador de Exchange Online, puede habilitar el complemento en el mensaje de informe para su organización.
    
## <a name="get-the-report-message-add-in-for-yourself"></a>Obtener el mensaje de informe de complemento para usted mismo

1. Vaya a [https://store.office.com](https://store.office.com)y busque el complemento en el mensaje de informe.
    
2. Elija **obtenerlo ahora** (o **Agregar** ). 
    
3. Revise los términos de uso y política de privacidad. A continuación, elija **continuar**. 
    
4. Inicie sesión en su correo electrónico de Office 365 con su trabajo o cuenta school (para uso empresarial) o su cuenta de Microsoft (para uso personal).
    
Después de que el complemento está instalado y habilitado, verá los iconos siguientes: 

- En Outlook el icono tiene el siguiente aspecto: <br/> ![Icono informe de mensaje, complemento para Outlook](media/OutlookReportMessageIcon.png)<br/>
- En Outlook Web App el icono tiene el siguiente aspecto:<br/>![Outlook en el icono mensaje de informe de Web, complemento](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

  
Como un paso siguiente, obtenga información sobre cómo [usar el complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Obtener y habilitar el complemento en el mensaje de informe para la organización

> [!IMPORTANT]
> Debe ser un administrador de Exchange Online para realizar esta tarea.
  
1. Vaya a [https://portal.office.com](https://portal.office.com) e iniciar sesión con su cuenta de trabajo o escuela. 
    
2. Elija **administración** para ir al centro de administración. 
    
3. Elija **centros de administración** \> **Exchange** para ir al centro de administración de Exchange (EAC). 
    
4. Elija la **organización** \> **complementos**. 
    
5. Elija **+** \> **Agregar desde el almacén de Office**. 
    
6. Busca el mensaje de informe.
    
7. En la lista de **los resultados de la aplicación** , busque el **Mensaje de informe**y, a continuación, elija **obtenerlo ahora** (o **Agregar** ). 
    
8. Revise los términos de uso y política de privacidad. A continuación, elija **continuar**. 
    
    ![Haga clic en Continuar para aceptar los términos y la directiva de privacidad](media/3c813cd6-1601-4791-97dc-f8edbbd3fb6b.png)
  
9. En la pantalla de confirmación, elija **Sí**. 
    
10. Después de instalar el complemento en el mensaje de informe, debe habilitarlo. Para ello, siga estos pasos:
    
1. Volver a la CEF y actualice la ventana del explorador.
    
2. Elija la **organización** \> **complementos**. 
    
3. En la lista de complementos, seleccione **Informe de mensaje**. 
    
    ![En el EAC, puede habilitar el mensaje de informe complemento para Outlook](media/b496743c-55fa-4cdb-aa06-0b2a7aec6dab.png)
  
4. Elija **Editar**y seleccione una opción para habilitar el complemento. 
    
    ![Habilitar el complemento de mensaje de informe en el EAC](media/578b1b66-3620-4a8a-9819-1c9cc6836f37.png)
  
5. Elija **Guardar**. 
    
> [!TIP]
> Después de que el complemento está instalado y habilitado, las personas de su organización verán los iconos siguientes: 
  
A continuación, obtenga información sobre cómo [usar el complemento en el mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)y configurar una regla para ver los mensajes de correo electrónico ha informado.
  
### <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>Configurar una regla para obtener una copia de los mensajes de correo electrónico que notifica a los usuarios

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
  
[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  

