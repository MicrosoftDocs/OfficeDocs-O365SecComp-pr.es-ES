---
title: Configurar las directivas de Office 365 ATP los datos adjuntos seguros
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
description: Definir directivas de los datos adjuntos seguros para proteger su organización desde archivos malintencionados en el correo electrónico.
ms.openlocfilehash: 7c2bcfd1d9faad48cb8852b066f544abd1fb6ace
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706074"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Configurar las directivas de Office 365 ATP los datos adjuntos seguros

Personas con regularidad envían, recibir y compartir datos adjuntos, como documentos, presentaciones, hojas de cálculo y mucho más. No siempre es fácil saber si un archivo adjunto es seguro o malintencionado solo con mirar un mensaje de correo electrónico. Y lo último que desea es un archivo adjunto malintencionado obtener a través de, causando estragos para su organización. Afortunadamente, puede ayudar a [La protección de amenaza avanzada de Office 365](office-365-atp.md) (ATP). Puede configurar las directivas de [Los datos adjuntos seguros de ATP](atp-safe-attachments.md) para ayudar a garantizar que la organización está protegida frente a ataques por los datos adjuntos de correo electrónico no seguros. 
  
## <a name="what-to-do"></a>Qué hacer 
  
1. [Revise los requisitos previos](#review-the-prerequisites)
    
2. [Establecer una directiva de datos adjuntos seguros de ATP](#set-up-an-atp-safe-attachments-policy)
    
3. [Obtenga información acerca de las opciones de directiva de los datos adjuntos seguros de ATP](#learn-about-atp-safe-attachments-policy-options)
    
## <a name="step-1-review-the-prerequisites"></a>Paso 1: Revisar los requisitos previos

- Asegúrese de que la organización tiene [La protección de amenaza avanzada de Office 365](office-365-atp.md).
    
- Asegúrese de tener el requisito [permisos para la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).
    
- [Obtenga información acerca de las opciones de directiva de los datos adjuntos seguros de ATP](#learn-about-atp-safe-attachments-policy-options) (en este artículo). Algunas opciones, como las opciones de Monitor o reemplazar, pueden provocar un retraso secundario de correo electrónico mientras se examinan los datos adjuntos. Para evitar retrasos de mensaje, considere el uso de [la entrega dinámica y obtener una vista previa](dynamic-delivery-and-previewing.md).
    
- Permitir hasta 30 minutos para la directiva de nueva o actualizada para propagarse a todos los centros de datos de Office 365.
    
## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Paso 2: Configurar una directiva de datos adjuntos seguros de ATP (o editar)
  
1. Como administrador global o administrador de seguridad, vaya a [https://security.microsoft.com](https://security.microsoft.com) y el inicio de sesión con la cuenta de trabajo o escuela. 
    
2. En la seguridad de Office 365 &amp; centro de cumplimiento, en el panel de navegación izquierdo, en **administración de amenaza**, elija **Directiva** \> **Los datos adjuntos seguros**.
    
3. Si ve **Activar ATP para SharePoint, OneDrive y los equipos de Microsoft**, se recomienda que seleccione esta opción. Esto permitirá que [Office 365 avanzada protección contra amenazas para SharePoint, OneDrive y los equipos de Microsoft](atp-for-spo-odb-and-teams.md) para su entorno de Office 365. 
    
4. Elija **nuevo** (el botón nuevo se parece a un signo más ( **+**)) para empezar a crear la directiva.
    
5. Especifique el nombre, la descripción y la configuración de la directiva.<br/><br/>**Ejemplo:** Para configurar una directiva no denominada "retrasos" que entrega los mensajes de todos los usuarios inmediatamente y, a continuación, vuelve a adjuntar datos adjuntos después de que estén digitalizar, es posible que especifique las siguientes opciones: 
    
      - En el cuadro **nombre** , no escriba retrasos.
    
      - En el cuadro **Descripción** , escriba una descripción como, entrega los mensajes inmediatamente y vuelve a adjuntar datos adjuntos después de la digitalización.
    
      - En la sección respuesta, elija la opción de **Entrega dinámica** . ([Obtenga más información acerca de la entrega dinámica y obtener una vista previa con datos adjuntos seguros de ATP](dynamic-delivery-and-previewing.md)).
    
      - En la sección **redirigir datos adjuntos** , seleccione la opción para habilitar el redireccionamiento y escriba la dirección de correo electrónico del administrador global, Administrador de seguridad o analista de seguridad que va a investigar datos adjuntos malintencionados de Office 365. 
    
      - En la sección **Aplicar a** , elija la opción **es el dominio de destinatario**y, a continuación, seleccione su dominio. Elija **Agregar**y, a continuación, elija **Aceptar**.
    
6. Elija **Guardar**.
    
Considere la posibilidad de configurar varias directivas de datos adjuntos seguros de ATP para su organización. Estas directivas se aplicarán en el orden en que aparecen en la página **Datos adjuntos seguros de ATP** . Después de haberse definida o editar una directiva, permitir al menos 30 minutos para que las directivas surtan efecto a lo largo de centros de datos de Microsoft. 
  
## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Paso 3: Obtenga información acerca de las opciones de directiva de los datos adjuntos seguros de ATP

Como configurar las directivas de los datos adjuntos seguros de ATP, elegir entre muchas opciones, incluido el Monitor, bloquear, reemplazar, entrega dinámica y así sucesivamente. En caso de que se está preguntando qué hacer estas opciones, la tabla siguiente resume cada uno de ellos y su efecto.
  
|**Opción**|**Efecto**|**Usar cuando desea:**|
|:-----|:-----|:-----|
|**Off** <br/> |No examina los datos adjuntos de malware  <br/> Retraso de no entrega de mensajes  <br/> |Desactivar el examen de remitentes internos, escáneres, faxes o hosts inteligentes que sólo va a enviar los datos adjuntos conocidos y de buenos  <br/> Evitar retrasos innecesarios en enrutamiento de correo interno  <br/> **Esta opción no se recomienda para la mayoría de los usuarios. Permite que desactive el análisis de los datos adjuntos seguros de ATP para un pequeño grupo de remitentes internos.**           |
|**Monitor** <br/> |Entrega los mensajes con datos adjuntos y, a continuación, realiza un seguimiento de lo que sucede con malware detectado  <br/> |Vea donde se ha detectado malware se coloca en la organización  <br/> |
|**Bloque** <br/> |Impide que los mensajes con datos adjuntos se ha detectado malware desde continuar  <br/> Envía los mensajes con malware detectado en [cuarentena en Office 365](manage-quarantined-messages-and-files.md) donde un administrador de seguridad o analista puede revisar y de la versión (o eliminar) esos mensajes  <br/> Bloquea los datos adjuntos y mensajes futuros automáticamente  <br/> |Proteger su organización frente a ataques repetidos con los mismos datos adjuntos de malware  <br/> |
|**Reemplazar** <br/> |Quita detecta los datos adjuntos de malware  <br/> Notifica a los destinatarios que se han quitado datos adjuntos  <br/> Envía los mensajes con malware detectado en [cuarentena en Office 365](manage-quarantined-messages-and-files.md) donde un administrador de seguridad o analista puede revisar y de la versión (o eliminar) esos mensajes  <br/> |Elevar visibilidad a los destinatarios que se han quitado datos adjuntos a causa de malware detectado  <br/> |
|**Entrega dinámica** <br/> |Entrega los mensajes inmediatamente  <br/> Reemplaza los datos adjuntos con un archivo de marcador de posición hasta que el examen se ha completado y, a continuación, vuelve a adjuntar los datos adjuntos si no se detecta ninguna malware  <br/> Incluye los datos adjuntos que se obtiene una vista previa de las capacidades para la mayoría de los archivos PDF y Office archivos durante la exploración  <br/> Envía los mensajes con malware detectado a cuarentena donde un administrador de seguridad o analista puede revisar y de la versión (o eliminar) esos mensajes  <br/> [Obtenga información sobre la entrega dinámica y obtener una vista previa con datos adjuntos seguros de ATP](dynamic-delivery-and-previewing.md) <br/> |Evitar retrasos de mensaje al tiempo que protege los destinatarios de archivos malintencionados  <br/> Habilitar destinatarios obtener una vista previa de datos adjuntos en modo seguro mientras el examen está produciendo  <br/> |
|**Habilitar la redirección** <br/> |Se aplica cuando se elige la opción de Monitor, bloquear o reemplazar  <br/> Envía los datos adjuntos a una dirección de correo electrónico especificada donde pueden investigar los administradores de seguridad o los analistas  <br/> |Permiten a los administradores de seguridad y los analistas de investigación datos adjuntos sospechosos  <br/> |
   
## <a name="next-steps"></a>Pasos siguientes

Una vez que las directivas de los datos adjuntos seguros de ATP, puede ver cómo funciona ATP para su organización mediante la visualización de informes. Vea los siguientes recursos para obtener más información:
- [Visualización de informes para la protección de amenaza avanzada de Office 365](view-reports-for-atp.md)
- [Use el explorador en la seguridad &amp; centro de cumplimiento](use-explorer-in-security-and-compliance.md)
 