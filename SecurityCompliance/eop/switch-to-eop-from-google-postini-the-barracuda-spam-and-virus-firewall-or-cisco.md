---
title: Cambiar a EOP desde Google Postini, Barracuda Spam y Virus Firewall o Cisco IronPort
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
description: El objetivo de este tema consiste en proporcionar los detalles sobre el proceso para cambiar a Protección en línea de Exchange (EOP) desde una aplicación de higiene de correo electrónico local o desde un servicio de protección basado en la nube, así como suministrar los recursos de ayuda necesarios para comenzar.
ms.openlocfilehash: 7e91c8b4d93d6d7aee55283e52bef92748fc49e1
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154583"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Cambiar a EOP desde Google Postini, Barracuda Spam y Virus Firewall o Cisco IronPort

 El objetivo de este tema consiste en proporcionar los detalles sobre el proceso para cambiar a Protección en línea de Exchange (EOP) desde una aplicación de higiene de correo electrónico local o desde un servicio de protección basado en la nube, así como suministrar los recursos de ayuda necesarios para comenzar. Existen muchas soluciones de filtrado de correo no deseado, aunque el proceso para cambiar a EOP es similar en la mayoría de los casos.
  
Si es la primera vez que usa EOP y desea leer una introducción sobre sus características antes de decidir si cambiarse o no, empiece por [Información general de Exchange Online Protection](exchange-online-protection-overview.md) en TechNet. 
  
Antes de cambiarse a EOP, es importante que piense si desea hospedar los buzones de correo protegidos por EOP en la nube, con Exchange Online, de forma local o en un escenario híbrido. (Por "híbrido" se entiende que algunos buzones de correo están hospedados de forma local y otros en Exchange Online). Los pasos de configuración necesarios para cada uno de estos escenarios de hospedaje (en la nube, en local o híbrido) pueden ser diferentes. Estas son algunas consideraciones que le pueden ayudar a elegir la implementación adecuada:
  
- **Protección EOP con buzones de correo locales** Este escenario resulta conveniente si ya cuenta con una infraestructura de hospedaje de correo que desea aprovechar, o bien debe mantener los buzones de correo en local por los requisitos de su compañía y desea implementar la protección de correo basada en la nube de EOP. En [Cambiar a EOP independiente](#switch-to-eop-standalone) se describe este escenario con más detalle. 
    
- **Protección EOP con buzones de correo de Exchange Online** Este escenario es ideal si desea hospedar la protección EOP y todos los buzones de correo en la nube. Además, le ayudará a reducir la complejidad, ya que no es necesario mantener servidores de mensajería locales. Este escenario se describe en [Cambiar a Exchange Online](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md#BKMK_SwitchEXO). 
    
- **Protección EOP con buzones de correo híbridos** Puede que desee implementar buzones de correo en la nube, pero debe mantener los buzones de algunos usuarios de forma local. Elija este escenario si desea hospedar algunos buzones de correo en local y otros en Exchange Online. En [Cambiar a una solución híbrida](#switch-to-a-hybrid-solution) se describe este escenario. 
    
## <a name="switch-to-eop-standalone"></a>Cambiar a EOP independiente

Si actualmente hospeda sus buzones de correo en local y usa una aplicación de protección local o un servicio de protección de mensajería en la nube, puede cambiar a EOP para beneficiarse de sus características de protección y disponibilidad. Para configurar EOP en un escenario independiente, es decir, para hospedar los buzones de correo de forma local y usar EOP para proteger el correo electrónico, siga los pasos detallados en [Configurar un servicio de EOP](set-up-your-eop-service.md). En este tema se describen los pasos que hay que seguir para configurar la protección EOP. Entre ellos se incluye registrarse, agregar el dominio y configurar el flujo del correo con conectores.
  
## <a name="switch-to-exchange-online"></a>Cambiar a Exchange Online
<a name="BKMK_SwitchEXO"> </a>

Si tiene una aplicación local que protege los buzones de correo locales, puede que le interese pasar a la protección EOP y a buzones hospedados en la nube de Exchange Online a fin de beneficiarse de las características de protección y de mensajería en la nube de Office 365. Para comenzar, regístrese en Office 365 y agregue su dominio. En este escenario, no es necesario que configure conectores, puesto que no existe un enrutamiento a buzones de correo locales. Comience en la [página de inicio de Office 365](https://www.microsoft.com/en-us/office365/online-software.aspx). (En [Introducción a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=275407) se proporcionan recursos para familiarizarse con las características). 
  
Durante el proceso de instalación de Office 365, podrá crear los usuarios de buzones de correo basados en la nube.
  
## <a name="switch-to-a-hybrid-solution"></a>Cambiar a una solución híbrida
<a name="BKMK_SwitchHybrid"> </a>

Puede que desee mover solo una parte de los buzones de correo a la nube debido a los requisitos de su compañía o a consideraciones reglamentarias. Al implementar un escenario híbrido, los buzones de correo se pueden mover a la nube en función de las necesidades del negocio. La migración a un escenario híbrido con la protección EOP resulta más complicada que cambiar a un escenario en la nube. No obstante, Microsoft ofrece diversos recursos y un completo soporte para escenarios híbridos a fin de facilitar la conversión.
  
Si está pensando en implementar una configuración híbrida, la mejor referencia para comenzar la encontrará en [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx). Además, es importante comprender las diversas formas de enrutar el correo en un escenario híbrido. En [Transport Routing in Exchange 2013 Hybrid Deployments](http://technet.microsoft.com/library/36c2cea3-2e2f-40ac-88bd-7e1b6bd27828.aspx) se explica cada uno de los tipos, para que pueda elegir el mejor escenario de enrutamiento en función de sus necesidades de negocio. 
  
## <a name="migration-planning"></a>Planeación de la migración
<a name="sectionSection3"> </a>

Cuando decida cambiar a EOP, asegúrese de considerar las siguientes áreas:
  
- **Reglas de filtrado personalizadas** Si tiene reglas de directivas empresariales o de filtrado personalizadas para detectar correo no deseado específico, se recomienda que pruebe EOP con la configuración predeterminada durante un período antes de migrar sus propias reglas. EOP ofrece protección contra correo no deseado a nivel empresarial con la configuración predeterminada, por lo que quizá no sea necesario migrar todas sus reglas a EOP. Evidentemente, si tiene reglas que ejecutan ciertas directivas empresariales personalizadas, podrá crearlas. [Reglas de flujo de correo (reglas de transporte) en Exchange Online Protection](mail-flow-rules-transport-rules-0.md) proporciona instrucciones detalladas para crear reglas de flujo de correo en EOP. 
    
- **Listas de direcciones IP permitidas y bloqueadas** Si tiene listas de permitidos y bloqueados por usuario, deje cierto tiempo para copiarlas a EOP como parte del proceso de instalación. Para obtener más información acerca de las listas de IP admitidas y de IP bloqueadas, consulte [Configure the Connection Filter Policy](../configure-the-connection-filter-policy.md).
    
- **Comunicación segura** Si tiene un socio que necesita que se cifren los mensajes, se recomienda que realice las configuraciones convenientes en el centro de administración de Exchange. Para configurar este escenario, consulte [Create connectors for a secure mail channel using transport layer security (TLS)](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx).
    
> [!TIP]
> Al cambiar de una aplicación local a EOP, se puede dejar la aplicación o un servidor para que realice las comprobaciones de reglas de negocio. Por ejemplo, si la aplicación realiza el filtrado personalizado del correo saliente y desea que lo siga haciendo, puede configurar EOP para que envíe el correo directamente a la aplicación a fin de realizar un filtrado adicional antes de que se enrute a Internet. En [Exchange Online Protection Connectors - Outbound Smart Host Scenario](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx) se muestra cómo configurar el flujo del correo en este caso. 
  

