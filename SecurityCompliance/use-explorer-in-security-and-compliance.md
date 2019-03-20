---
title: Usar el explorador de amenazas en &amp; el centro de seguridad y cumplimiento
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Obtenga información sobre el explorador (también denominado explorador de amenazas) &amp; en el centro de seguridad y cumplimiento.
ms.openlocfilehash: 0c86792d8ed84b43b28bde31004dc95d2fa2b547
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693619"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>Usar el explorador de amenazas en &amp; el centro de seguridad y cumplimiento

Si su organización tiene [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)y dispone de los permisos necesarios, puede usar el explorador de amenazas para identificar y analizar las amenazas. Por ejemplo, puede identificar y eliminar correo electrónico malintencionado que se entregó, o ver malware detectado por las características de seguridad de Office 365. El explorador de amenazas (también conocido como explorador) es una herramienta eficaz casi en tiempo real para ayudar a los equipos de operaciones de seguridad a investigar y &amp; responder a amenazas en el centro de seguridad y cumplimiento.
  
![Ir al explorador de \> administración de amenazas](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Para usar el explorador, en el &amp; centro de seguridad y cumplimiento, vaya a **Threat Management** \> **Explorer**.

> [!IMPORTANT]
> Office 365 Threat Intelligence es ahora Office 365 plan de protección contra amenazas avanzada 2, junto con otras capacidades de protección contra amenazas. Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).
      
## <a name="explorer-overview"></a>Información general del explorador

El explorador muestra información sobre el malware y el phish sospechoso en el correo electrónico y los archivos de Office 365, así como otras amenazas de seguridad y riesgos para la organización. La primera vez que se abre el explorador, la vista predeterminada muestra las detecciones de malware de correo electrónico de los últimos 7 días. El explorador también puede mostrar características de protección de seguridad en Office 365, incluidos [vínculos seguros](atp-safe-links.md) y [datos adjuntos seguros](atp-safe-attachments.md) , y se puede modificar para mostrar los datos de los últimos 30 días. Si tiene un subcription de prueba para Office 365 Advanced Threat Protection Plan 2 u Office 365 E5, solo verá las detecciones y los datos de correo electrónico de los últimos 7 días.
  
![El explorador muestra información sobre el malware y los usuarios de destino](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
Use el menú Ver para cambiar la información que se muestra.
  
![Menú Ver del explorador](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
El explorador tiene varias capacidades de filtrado y consulta que le permiten profundizar en los detalles, como los usuarios de destino más importantes, las familias de malware principales, la tecnología de detección y mucho más. Cada tipo de informe ofrece varias formas de ver y explorar los datos.

> [!IMPORTANT]
> No use caracteres comodín, como un asterisco (*) o un signo de interrogación (?), con el explorador. Al buscar mensajes de correo electrónico en el campo asunto, el explorador realizará una coincidencia parcial y obtendrá resultados similares a una búsqueda con caracteres comodín.

## <a name="email--malware"></a>Malware \> de correo electrónico

Esta vista muestra los mensajes de correo electrónico identificados como que contienen malware.  

Permite ver la información del gráfico por la familia de código malintencionado, el dominio del remitente, la dirección IP del remitente, el estado de protección (acciones tomadas por las directivas y directivas de protección contra amenazas en Office 365) y la tecnología de detección (el modo en que se detectó el malware).  

![Ver datos sobre malware detectado](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

Debajo del gráfico, vea los detalles de las familias de malware principales, los usuarios de destino más importantes y más información sobre mensajes específicos. 

## <a name="email--phish"></a>Phishing \> de correo electrónico

Esta vista muestra los mensajes de correo electrónico identificados como intentos de suplantación de identidad.  

Ver información por dominio del remitente, IP del remitente y estado de protección (acciones tomadas por las características y directivas de protección contra amenazas en Office 365). 

![Ver datos sobre correo electrónico identificado como intentos de suplantación de identidad](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

Debajo del gráfico, vea más detalles sobre mensajes específicos. 

## <a name="email--user-reported"></a>Usuario \> de correo electrónico: informado

Esta vista muestra el correo electrónico que los usuarios han notificado como correo electrónico no deseado, no deseado o de suplantación de identidad.  

Ver información por tipo de informe (la determinación del usuario de que era correo no deseado, correo deseado o phish) y por razón de entrega (razones por las que el correo electrónico se redirigió a una ubicación específica, como una directiva de filtro de correo no deseado, una regla de flujo de correo, una lista de remitentes bloqueados, una lista de remitentes seguros, etc.).  

![Ver los datos de los usuarios de correo electrónico que se notifican como correo no deseado, correo deseado o phishing](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

Debajo del gráfico, vea más detalles sobre los mensajes de correo electrónico específicos, como la línea de asunto, la dirección IP del remitente, el usuario que notificó el mensaje como correo no deseado, correo deseado o phish, entre otros. 

## <a name="email--all-mail"></a>Enviar \> por correo electrónico todo el correo

En esta vista se muestra una vista general de la actividad de correo electrónico, incluido el correo electrónico identificado como malintencionado debido a suplantación de identidad (phishing) o malware, así como a todo el correo no malintencionado (correo electrónico normal, correo no deseado y correo masivo). 

> [!NOTE]
> Si recibe un error que lee **demasiados datos para mostrar**, agregue un filtro y, si es necesario, restrinja el intervalo de fechas que está viendo. 

Para aplicar un filtro, elija **remitente**, seleccione un elemento de la lista y, a continuación, haga clic en el botón actualizar. En nuestro ejemplo, utilizamos la **tecnología de detección** como filtro (hay varias opciones disponibles). Ver información por remitente, dominio del remitente, destinatarios, asunto, nombre de archivo de datos adjuntos, familia de malware, estado de protección (acciones llevadas a cabo por las directivas y características de protección contra amenazas en Office 365), la tecnología de detección (cómo se detectó el malware) y adicional. 

![Ver los datos sobre el correo electrónico detectado mediante la tecnología de detección](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

Debajo del gráfico, vea más detalles sobre los mensajes de correo electrónico específicos, como la línea de asunto, el destinatario, el remitente, el estado, etc. 

## <a name="content--malware"></a>Malware \> de contenido

Esta vista muestra los archivos que se identificaron como malintencionados con la protección contra amenazas avanzada de Office 365 en SharePoint Online, OneDrive para la empresa y Microsoft Teams.

Ver información por familia de malware, tecnología de detección (cómo se detectó el malware) y carga de trabajo (OneDrive, SharePoint o Teams). 

![Ver datos sobre malware detectado](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

Debajo del gráfico, vea más detalles sobre archivos específicos, como nombre de archivo de datos adjuntos, carga de trabajo, tamaño de archivo, quién modificó el archivo por última vez, etc. 
  
## <a name="new-click-to-filter-capabilities"></a>(Nueva) Capacidades de hacer clic y filtrar

Nuevo en el explorador es la capacidad de hacer clic para filtrar. Cuando se hace clic en un elemento de la leyenda, ese elemento se convierte en un filtro para el informe. Por ejemplo, supongamos que estamos viendo la vista de malware en el explorador:
  
![Ir al explorador de \> administración de amenazas](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Al hacer clic en **detonaCiones ATP** en este gráfico, se obtiene una vista similar a la siguiente: 
  
![El explorador está filtrado para mostrar solo los resultados de la detonación de ATO](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
En esta vista, ahora miramos los datos de los archivos que se han enumerado con datos adJuntos [seguros de ATP de Office 365](atp-safe-attachments.md). Debajo del gráfico, podemos ver los detalles sobre los mensajes de correo electrónico específicos que tienen datos adjuntos detectados por los datos adJuntos seguros de ATP.
  
![Detalles específicos sobre los mensajes de correo electrónico con datos adjuntos detectados](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
Al seleccionar uno o más elementos, se activa el menú **acciones** , que ofrece varias opciones entre las que elegir para los elementos seleccionados. 
  
![Al seleccionar un elemento, se activa el menú acciones](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
La capacidad de filtrar en un clic y navegar a detalles específicos puede ahorrarle mucho tiempo para la investigación de las amenazas.
  
## <a name="how-do-i-get-explorer"></a>¿Cómo se obtiene el explorador?

Explorer se incluye en el [plan 2 de la protección contra amenazas avanzada de Office 365](office-365-ti.md). 

Debe tener los permisos adecuados, como los que se han concedido a un administrador de seguridad o un lector de seguridad, para poder ver y usar el explorador. Para obtener más información, consulte perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).
  
## <a name="related-topics"></a>Temas relacionados

[Informes y opiniones en el centro de seguridad &amp; y cumplimiento de Office 365](reports-and-insights-in-security-and-compliance.md)
  
[Buscar e investigar correo electrónico malintencionado que se entregó (Office 365 Threat Invesitgation and Response)](investigate-malicious-email-that-was-delivered.md)
  
[Protección contra correo electrónico no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md)
  

