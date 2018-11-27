---
title: Use el explorador en la seguridad &amp; centro de cumplimiento
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
description: Obtenga información sobre el explorador (también denominado Explorador de amenaza) en la seguridad &amp; centro de cumplimiento.
ms.openlocfilehash: 1b3088028651b445d890333a25804902843d915d
ms.sourcegitcommit: 7f45890ecfa5e15575df4e3ebe472a8dd8d99112
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674925"
---
# <a name="use-explorer-in-the-security-amp-compliance-center"></a>Use el explorador en la seguridad &amp; centro de cumplimiento

Si su organización tiene [Información sobre amenazas de Office 365](office-365-ti.md), y tiene los permisos necesarios, puede usar el explorador para identificar y analizar las amenazas. Por ejemplo, puede identificar y eliminar el correo electrónico malintencionado que se entregó o vea malware que se capturó mediante las características de seguridad de Office 365. Explorer (también denominada Explorador de amenaza) es un potente cerca de informe en tiempo real en la seguridad &amp; centro de cumplimiento.
  
![Vaya a administración de amenaza \> Explorer](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Para usar el explorador, en la seguridad &amp; centro de cumplimiento, vaya a **administración de amenazas** \> **Explorer**.
      
## <a name="explorer-overview"></a>Introducción al explorador

El explorador muestra información sobre malware sospechoso en el correo electrónico y los archivos de Office 365, así como otras amenazas de seguridad y riesgos para la organización. La primera vez que se abre el explorador, la vista predeterminada muestra las detecciones de malware de antivirus para los últimos 7 días. El explorador también puede mostrar seguridad características de protección en Office 365, incluidos [Vínculos seguros](atp-safe-links.md) y [Los datos adjuntos seguros](atp-safe-attachments.md) y se puede modificar para mostrar los datos de los últimos 30 días.
  
![El explorador muestra información acerca de los principales de malware y los usuarios de destino](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
Use el menú Ver para cambiar la información que se muestra.
  
![El menú Ver para el explorador](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
El explorador tiene varias filtrado y consultar las funcionalidades que permiten explorar en profundidad detalles, como la parte superior había destinada a los usuarios, las familias de malware superior y más. Cada tipo de informe ofrece una variedad de posibilidades para ver y explorar datos.

> [!IMPORTANT]
> No utilice caracteres comodín, como un asterisco (*) o un signo de interrogación (?), con el explorador. Al buscar en el campo Asunto de los mensajes de correo electrónico, el explorador realizará parciales resultados de coincidencia y rendimiento similares a una búsqueda con caracteres comodín.

## <a name="email--malware"></a>Correo electrónico \> Malware

Esta vista muestra los mensajes de correo electrónico identificados como que contiene el malware.  

Ver la información en el gráfico por familia de código malintencionado, dominio del remitente, IP del remitente, el estado de protección (acciones realizadas por sus características de protección de amenaza y directivas en Office 365) y tecnología de detección (cómo se detectó el malware).  

![Ver datos sobre malware detectado](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

Debajo del gráfico, ver detalles acerca de las familias de malware superior, parte superior había destinada a los usuarios y obtener más detalles acerca de los mensajes específicos. 

## <a name="email--phish"></a>Correo electrónico \> phishing

Esta vista muestra los mensajes de correo electrónico identificados como los intentos de suplantación de identidad.  

Ver la información de dominio del remitente, IP del remitente y el estado de protección (acciones realizadas por sus características de protección de amenaza y directivas en Office 365). 

![Ver los datos de correo electrónico que se identificó como intentos de suplantación de identidad](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

Debajo del gráfico, ver más detalles acerca de los mensajes específicos. 

## <a name="email--user-reported"></a>Correo electrónico \> indicado por el usuario

Esta vista muestra el correo electrónico que los usuarios han informado como no deseado, no correo no deseado o correo electrónico de suplantación de identidad.  

Ver la información por tipo de informe (determinación de la del usuario que el correo electrónico es correo no deseado, no no deseado o phishing) y por el motivo de la entrega (motivos de por qué salió el correo electrónico a una ubicación específica, como una directiva de filtro de spam, una regla de flujo de correo, una lista de remitentes bloqueados, una lista de remitentes seguros, etcetera.).  

![Datos de vista acerca de los usuarios de correo electrónico enviados como correo no deseado, no no deseado o suplantación de identidad](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

Debajo del gráfico, ver más detalles acerca de los mensajes de correo electrónico específica, como la línea de asunto, la dirección IP del remitente, el usuario que envió el mensaje como correo no deseado, no no deseado, o phishing y mucho más. 

## <a name="email--all-mail"></a>Correo electrónico \> todo el correo

Este vistas muestra una vista de total de actividad de correo electrónico, correo electrónico, con identificado como malintencionados de vencimiento para la suplantación de identidad o malware, además de todo el correo que no sean malintencionado (correo electrónico normal, correo no deseado y correo masivo). 

> [!NOTE]
> Si recibe un error que lee **demasiado cantidad de datos para mostrar**, agregue un filtro y, si es necesario, restringir el intervalo de fechas que se está viendo. 

Para aplicar un filtro, elija **remitente**, seleccione un elemento en la lista y, a continuación, haga clic en el botón Actualizar. En nuestro ejemplo, hemos usado la **tecnología de detección** como un filtro (hay varias opciones disponibles). Ver la información de remitente, dominio del remitente, los destinatarios, asunto, nombre de archivo de datos adjuntos, familia de código malintencionado, el estado de protección (acciones realizadas por sus características de protección de amenaza y directivas en Office 365), tecnología de detección (cómo se detectó el malware), y más. 

![Ver los datos de correo electrónico detectado por tecnología de detección](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

Debajo del gráfico, ver más detalles acerca de los mensajes de correo electrónico específica, por ejemplo, la línea de asunto, destinatario, remitente, estado y así sucesivamente. 

## <a name="content--malware"></a>Contenido \> Malware

Esta vista muestra los archivos que se han identificado como malintencionados en SharePoint Online, OneDrive para la empresa y Microsoft Teams.

Ver la información por malware, detección tecnología de la familia (cómo se detectó el malware) y carga de trabajo (OneDrive, SharePoint o equipos). 

![Ver datos sobre malware detectado](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

Debajo del gráfico, ver más detalles acerca de los archivos específicos, como el nombre del archivo adjunto, carga de trabajo, el tamaño de archivo que se modificó por última vez el archivo y mucho más. 
  
## <a name="new-click-to-filter-capabilities"></a>(Nuevo)! Haga clic en para filtrar capacidades

El explorador es la capacidad de hacer clic para filtrar. A partir de las últimas de 2018 mayo, al hacer clic en un elemento de la leyenda, que el elemento se convierte en un filtro para el informe. Por ejemplo, suponga que buscamos en la vista de Malware en el explorador:
  
![Vaya a administración de amenaza \> Explorer](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Al hacer clic en **Detonación ATP** en los resultados de este gráfico en una vista como esta: 
  
![Explorador de filtrado para mostrar sólo los resultados de detonación ATO](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
En esta vista, ahora observamos datos para los archivos que se han detonated por [Office 365 ATP los datos adjuntos seguros](atp-safe-attachments.md). Debajo del gráfico, podemos ver detalles acerca de los mensajes de correo electrónico específica que tenían datos adjuntos que se han detectado por los datos adjuntos seguros de ATP.
  
![Detalles específicos acerca de los mensajes de correo electrónico con datos adjuntos detectados](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
Al seleccionar uno o varios elementos, activa el menú **acciones** , que ofrece varias opciones desde el que se elija para los elementos seleccionados. 
  
![Al seleccionar un elemento, activa el menú Acciones](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
La capacidad de filtrar en un clic y desplazarse por los detalles específicos puede guardar una gran cantidad de tiempo en investigar las amenazas.
  
## <a name="how-do-i-get-explorer"></a>¿Cómo se puede obtener el explorador?

El explorador se incluye en la [Información sobre amenazas de Office 365](office-365-ti.md). 

Debe tener los permisos adecuados, como los concedidos a un administrador de seguridad o el lector de seguridad, a fin de ver y usar el explorador. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).
  
## <a name="related-topics"></a>Temas relacionados

[Informes y conocimientos en la seguridad de Office 365 &amp; centro de cumplimiento](reports-and-insights-in-security-and-compliance.md)
  
[Buscar e investigar el correo electrónico malintencionado que se entregó (Office 365 información sobre amenazas)](investigate-malicious-email-that-was-delivered.md)
  
[Protección contra correo electrónico no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md)
  

