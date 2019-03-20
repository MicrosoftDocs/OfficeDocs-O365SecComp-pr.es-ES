---
title: Flujo de correo en EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/13/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: Como cliente de Exchange Online Protection (EOP), todos los mensajes enviados a su organización pasan a través de EOP antes de sus trabajadores los vean. Tanto si hospeda todos los buzones en la nube con Exchange Online, como si los hospeda localmente (lo que se denomina escenario independiente), quizás para continuar aprovechando las ventajas de la infraestructura existente, puede elegir cómo enrutar los mensajes que pasarán por EOP para procesarlos antes de que se enruten a los buzones de los trabajadores.
ms.openlocfilehash: b223efc62ff875ed345ce27a17263b3876829999
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2019
ms.locfileid: "30691719"
---
# <a name="mail-flow-in-eop"></a>Flujo de correo en EOP

Como cliente de Exchange Online Protection (EOP), todos los mensajes enviados a su organización pasan a través de EOP antes de sus trabajadores los vean. Tanto si hospeda todos los buzones en la nube con Exchange Online, como si los hospeda localmente (lo que se denomina escenario independiente), quizás para continuar aprovechando las ventajas de la infraestructura existente, puede elegir cómo enrutar los mensajes que pasarán por EOP para procesarlos antes de que se enruten a los buzones de los trabajadores.
  
Quizás quiera configurar un enrutamiento de correo personalizado para que su mensajería cumpla los requisitos de la empresa. Por ejemplo, se puede pasar todo el correo electrónico saliente a través de un dispositivo de filtrado de directivas. 
  
## <a name="working-with-messages-and-message-access-options"></a>Trabajar con mensajes y opciones de acceso de mensajes

EOP ofrece mucha flexibilidad para enrutar los mensajes. Los temas siguientes explican los pasos del proceso de flujo de correo.
  
[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx) Se describe la característica Bloqueo perimetral basado en directorios que permite rechazar los mensajes para los destinatarios no válidos en el perímetro de la red de servicio. 
  
[Ver o editar dominios administrados en EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describe cómo administrar dominios asociados con el servicio de EOP. 
  
Si agrega subdominios a la organización, el servicio de EOP también puede ayudarle a administrarlos. Para obtener más información sobre subdominios, vea [Enable Mail Flow for Subdomains in Exchange Online](http://technet.microsoft.com/library/4033a30a-f506-481c-8ef0-fd9a0508ae38.aspx).
  
[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx) presenta los conectores y muestra cómo usarlos para personalizar el enrutamiento de correo. Los escenarios incluyen garantizar una comunicación segura con una organización asociada y configurar un host inteligente. 
  
Para asegurarse de que el correo electrónico no deseado se enruta correctamente a la carpeta de correo electrónico no deseado de cada usuario, debe realizar un par de pasos de configuración. Se detallan [a continuación para asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Si no desea mover mensajes a la carpeta de correo electrónico no deseado de cada usuario, puede elegir otra acción editando las directivas de filtro de contenido en el centro de administración de Exchange. Para obtener más información, vea [Configurar las directivas de filtro de correo no deseado](../configure-your-spam-filter-policies.md).
  
## <a name="verify-mail-flow"></a>Comprobar el flujo de correo

Para comprobar que la configuración de EOP, incluida la configuración de conectores, esté funcionando correctamente, consulte la sección "¿Cómo sabe si esta tarea se ha completado correctamente?" en [Configurar un servicio de EOP](set-up-your-eop-service.md). 
  
[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx) proporciona instrucciones para probar que el flujo de correo está configurado correctamente. 
  

