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
ms.openlocfilehash: d7a1f4c281a50a8a835acd848f2c1c0d0407bcf1
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676531"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Cambiar a EOP desde Google Postini, Barracuda Spam y Virus Firewall o Cisco IronPort

 El objetivo de este tema consiste en proporcionar los detalles sobre el proceso para cambiar a Protección en línea de Exchange (EOP) desde una aplicación de higiene de correo electrónico local o desde un servicio de protección basado en la nube, así como suministrar los recursos de ayuda necesarios para comenzar. Existen muchas soluciones de filtrado de correo no deseado, aunque el proceso para cambiar a EOP es similar en la mayoría de los casos.
  
Si no está familiarizado con EOP y desea leer una introducción sobre sus características antes de decidir si quiere cambiar, comience con el tema de [información general de Exchange Online Protection](exchange-online-protection-overview.md) .
  
Antes de cambiarse a EOP, es importante que piense si desea hospedar los buzones de correo protegidos por EOP en la nube, con Exchange Online, de forma local o en un escenario híbrido. (Por "híbrido" se entiende que algunos buzones de correo están hospedados de forma local y otros en Exchange Online). Los pasos de configuración necesarios para cada uno de estos escenarios de hospedaje (en la nube, en local o híbrido) pueden ser diferentes. Estas son algunas consideraciones que le pueden ayudar a elegir la implementación adecuada:
  
- **Protección de EOP con buzones de correo locales**: este escenario es adecuado si tiene una infraestructura de hospedaje de correo existente que desea usar o si tiene requisitos empresariales para mantener los buzones de correo locales y desea la protección de correo electrónico basada en la nube de EOP. . En [Cambiar a EOP independiente](#switch-to-eop-standalone) se describe este escenario con más detalle.

- **Protección de EOP con buzones de Exchange Online**: este escenario es el adecuado si desea que la protección de EOP y todos los buzones de correo estén hospedados en la nube. Además, le ayudará a reducir la complejidad, ya que no es necesario mantener servidores de mensajería locales. Este escenario se describe en [Cambiar a Exchange Online](#switch-to-exchange-online).

- **Protección de EOP con buzones de correo híbridos**: es posible que quiera buzones de correo en la nube, pero necesita mantener los buzones de correo de algunos usuarios de forma local. Elija este escenario si desea hospedar algunos buzones de correo en local y otros en Exchange Online. En [Cambiar a una solución híbrida](#switch-to-a-hybrid-solution) se describe este escenario.

## <a name="switch-to-eop-standalone"></a>Cambiar a EOP independiente

Si actualmente hospeda sus buzones de correo en local y usa una aplicación de protección local o un servicio de protección de mensajería en la nube, puede cambiar a EOP para beneficiarse de sus características de protección y disponibilidad. Para configurar EOP en un escenario independiente, es decir, para hospedar los buzones de correo de forma local y usar EOP para proteger el correo electrónico, siga los pasos detallados en [Configurar un servicio de EOP](set-up-your-eop-service.md). En este tema se describen los pasos que hay que seguir para configurar la protección EOP. Entre ellos se incluye registrarse, agregar el dominio y configurar el flujo del correo con conectores.
  
## <a name="switch-to-exchange-online"></a>Cambiar a Exchange Online

Si tiene una aplicación local que protege los buzones de correo locales, puede que le interese pasar a la protección EOP y a buzones hospedados en la nube de Exchange Online a fin de beneficiarse de las características de protección y de mensajería en la nube de Office 365. Para comenzar, regístrese en Office 365 y agregue su dominio. En este escenario, no es necesario que configure conectores, puesto que no existe un enrutamiento a buzones de correo locales. Comience en la [página de inicio de Office 365](https://www.microsoft.com/office365/online-software.aspx). Introducción a [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=275407) proporciona recursos para familiarizarse con sus características.
  
Durante el proceso de instalación de Office 365, podrá crear los usuarios de buzones de correo basados en la nube.
  
## <a name="switch-to-a-hybrid-solution"></a>Cambiar a una solución híbrida

Puede que desee mover solo una parte de los buzones de correo a la nube debido a los requisitos de su compañía o a consideraciones reglamentarias. Al implementar un escenario híbrido, los buzones de correo se pueden mover a la nube en función de las necesidades del negocio. La migración a un escenario híbrido con la protección EOP resulta más complicada que cambiar a un escenario en la nube. No obstante, Microsoft ofrece diversos recursos y un completo soporte para escenarios híbridos a fin de facilitar la conversión.
  
El mejor punto de partida, si está pensando en una implementación híbrida, son las implementaciones híbridas de [Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid). Además, es importante comprender las diversas formas de enrutar el correo en un escenario híbrido. [Enrutamiento de transporte en las implementaciones híbridas de Exchange](https://docs.microsoft.com/exchange/transport-routing) explica cada tipo, por lo que puede elegir el mejor escenario de enrutamiento en función de los requisitos empresariales.
  
## <a name="migration-planning"></a>Diseño de la migración

Cuando decida cambiar a EOP, asegúrese de considerar las siguientes áreas:
  
- **Reglas de filtros personalizados**: Si tiene un filtro personalizado o reglas de directiva de negocio para detectar correo no deseado específico, le recomendamos que pruebe EOP con la configuración predeterminada durante un período, antes de migrar las reglas. EOP ofrece protección contra correo no deseado a nivel empresarial con la configuración predeterminada, por lo que quizá no sea necesario migrar todas sus reglas a EOP. Evidentemente, si tiene reglas que ejecutan ciertas directivas empresariales personalizadas, podrá crearlas. [Reglas de flujo de correo (reglas de transporte) en Exchange Online Protection](mail-flow-rules-transport-rules-0.md) proporciona instrucciones detalladas para crear reglas de flujo de correo en EOP.

- Listas de direcciones IP **permitidas y bloqueadas**: Si tiene listas de admitidos y de bloqueo por usuario, deje transtenerse algún tiempo para copiar las listas a EOP como parte del proceso de configuración. Para obtener más información acerca de las listas de IP admitidas y de IP bloqueadas, consulte [Configure the Connection Filter Policy](../configure-the-connection-filter-policy.md).

- **Comunicación segura**: Si tiene un partner que requiere mensajería cifrada, le recomendamos que configure esto en el centro de administración de Exchange. Para configurar este escenario, vea [set up Connectors for Secure Mail Flow with a Partner Organization](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).

> [!TIP]
> Al cambiar de una aplicación local a EOP, se puede dejar la aplicación o un servidor para que realice las comprobaciones de reglas de negocio. Por ejemplo, si el dispositivo realiza un filtrado personalizado en el correo saliente y desea que siga haciéndolo, puede configurar EOP para enviar correo directamente al dispositivo para un filtrado adicional, antes de que se enrute a Internet.
