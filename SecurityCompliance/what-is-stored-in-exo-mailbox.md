---
title: Contenido almacenado en buzones de correo de Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Los datos producidos por las aplicaciones basadas en la nube en Office 365 se almacenan en el buzón de correo de un usuario de Exchange online en la nube de Microsoft.
ms.openlocfilehash: d2d126d28a9b92962af7637610282e99e7685594
ms.sourcegitcommit: ecc823c2a4f1465114cf1d3a4630e31c47779ddc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2019
ms.locfileid: "35079404"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Contenido almacenado en buzones de correo de Exchange Online

Un buzón de Exchange Online se usa principalmente para almacenar elementos relacionados con el correo electrónico, como mensajes, elementos de calendario, tareas y notas. Pero esto cambia a medida que más aplicaciones de Office 365 basadas en la nube también almacenan sus datos en el buzón de un usuario. Una de las ventajas de almacenar datos en un buzón es que puede usar las herramientas de búsqueda en búsqueda de contenido, eDiscovery, eDiscovery avanzado e investigaciones de datos para buscar, ver y exportar los datos de estas aplicaciones basadas en la nube. Los datos de algunas de estas aplicaciones se almacenan en carpetas ocultas que se encuentran en un subárbol de mensajes no interpersonales (no IPM) en el buzón. Esto significa que los datos se ocultan de la vista del usuario cuando usan Outlook u otros clientes de correo para tener acceso a su buzón.

En la siguiente tabla se enumeran las aplicaciones de Office 365 que almacenan datos en un buzón basado en la nube. La tabla también describe el tipo de contenido que cada aplicación almacena.

|Aplicación de Office 365  |Descripción  |
|:---------|:---------|
|Formularios     <br/> |Los formularios (almacenados como un archivo PDF) y las respuestas a un formulario (almacenado en un archivo CSV) se adjuntan a los mensajes de correo electrónico y se almacenan en una carpeta oculta en el buzón del usuario que creó el formulario. Al exportar contenido de formularios en un archivo PST, estos datos se encuentran en la carpeta **ApplicationDataRoot** en una subcarpeta denominada con el siguiente globalmente identificado (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.        <br/> |
|Grupos de Office 365    <br/>|  Los mensajes de correo electrónico, los elementos de calendario, los contactos (personas), las notas y las tareas se almacenan en el buzón de correo asociado con un grupo de Office 365.       <br/> |
|Outlook/Exchange Online<br/>|  Los mensajes de correo electrónico, los elementos de calendario, los contactos (personas), las notas y las tareas se almacenan en el buzón de un usuario.       <br/> |
|Contactos    <br/> |  Los contactos de la aplicación contactos (que son los mismos contactos que los que son accesibles en Outlook) se almacenan en el buzón de un usuario.      <br/> |
|Programación de clases     <br/> |   Los planes creados en el programa de clases se almacenan en el buzón del grupo de Office 365 correspondiente que se aprovisiona cuando se crea un plan nuevo. El alias para el buzón de grupo es el nombre del plan.      <br/> |
|Skype Empresarial    <br/>  | Las conversaciones en Skype empresarial se almacenan en la carpeta Historial de conversaciones en el buzón de un usuario. Si el buzón de un participante de una reunión de Skype se coloca en retención por juicio o se asigna a una directiva de retención, los archivos adjuntos a una reunión se conservan en el buzón de participantes.         <br/> |
|Sway     <br/> |  Los sways se almacenan como un archivo HTML que se adjunta a un mensaje de correo electrónico y se almacenan en una carpeta oculta en el buzón del usuario que creó el Sway. Al exportar contenido de Sway en un archivo PST, estos datos se encuentran en la carpeta **ApplicationDataRoot** en una subcarpeta denominada con el siguiente GUID) **905fcf26-4eb7-48A0-9ff0-8dcc7194b5ba**.       <br/> |
|Tareas    <br/> |  Las tareas de la aplicación tareas (que son las mismas tareas que las que son accesibles en Outlook) se almacenan en el buzón de un usuario.       <br/> |
|Teams    <br/>  |Las conversaciones que forman parte de un canal de Microsoft Teams se almacenan en el buzón de correo que está asociado al equipo. Las conversaciones que forman parte de la lista de chats en Microsoft Teams (también llamadas *1 x N chats*) se almacenan en el buzón de los usuarios que participan en el chat. Además, la información de Resumen de las reuniones y las llamadas en un canal de Microsoft Teams se almacena en los buzones de correo de los usuarios que marcaron la reunión o la llamada. <br/> | 
|To-Do  <br/> | Las tareas ( ** llamadas tareas que se guardan en listas de tareas pendientes) en la aplicación de tareas se almacenan en el buzón de un usuario.        <br/> |
||||

> [!NOTE]
> En este momento, si se coloca una retención en un buzón (mediante retenciones en la exhibición de documentos electrónicos y en casos de eDiscovery avanzados), el contenido de los formularios y de Sway no se conservará en la retención. 