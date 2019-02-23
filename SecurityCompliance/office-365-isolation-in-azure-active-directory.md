---
title: Aislamiento y control de acceso de Office 365 en Azure Active Directory
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Resumen: funcionamiento del aislamiento y el control de acceso dentro de Azure Active Directory.'
ms.openlocfilehash: 45b48aef93b9cb146440de7f41f23a493e8565df
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220190"
---
# <a name="isolation-and-access-control-in-azure-active-directory"></a>Aislamiento y Control de acceso en Azure Active Directory

Azure Active Directory se diseñó para hospedar varios inquilinos de una forma muy segura mediante el aislamiento de datos lógicos. Un nivel de autorización controla el acceso a Azure Active Directory. Azure Active Directory aísla a los clientes en el uso de contenedores de inquilinos como límites de seguridad para proteger el contenido de un cliente de modo que los coinquilinos no puedan acceder al contenido ni verse comprometidos. La capa de autorización de Azure Active Directory realiza tres comprobaciones:
- ¿Está habilitada la entidad principal para obtener acceso al inquilino de Azure Active Directory?
- ¿Está habilitada la entidad principal para obtener acceso a los datos de este inquilino?
- ¿La entidad de identidad está autorizada en este inquilino para el tipo de acceso a datos solicitado?

Ninguna aplicación, usuario, servidor o servicio puede obtener acceso a Azure Active Directory sin la autenticación y el certificado correctos. Las solicitudes se rechazan si no van acompañadas de las credenciales correctas.

De hecho, Azure Active Directory hospeda cada inquilino en su propio contenedor protegido, con directivas y permisos para y en el contenedor que solo posee y administra el inquilino.
 
![Azure Container](media/office-365-isolation-azure-container.png)

El concepto de contenedores de inquilinos es profundamente ingranulado en el servicio de directorio en todas las capas, desde portales hasta almacenamiento persistente. Incluso cuando varios metadatos de inquilino de Azure Active Directory se almacenan en el mismo disco físico, no hay una relación entre los contenedores que no sean lo definido por el servicio de directorio, que a su vez viene dictado por el administrador de inquilinos. No puede haber conexiones directas con el almacenamiento de Azure Active Directory desde ninguna aplicación o servicio de solicitud sin pasar primero por el nivel de autorización.

En el ejemplo siguiente, contoso y Fabrikam tienen contenedores independientes dedicados y, aunque estos contenedores pueden compartir algunas de las infraestructuras subyacentes, como los servidores y el almacenamiento, permanecen separadas y aisladas entre sí y se canalizan mediante capas de autorización y control de acceso.
 
![Contenedores dedicados de Azure](media/office-365-isolation-azure-dedicated-containers.png)

Además, no hay ningún componente de la aplicación que se pueda ejecutar desde dentro de Azure Active Directory y no es posible que un inquilino infrinja forzosamente la integridad de otro inquilino, obtenga acceso a las claves de cifrado de otro inquilino o lea datos sin procesar del servidor.

De forma predeterminada, Azure Active Directory no permite todas las operaciones emitidas por identidades en otros inquilinos. Cada inquilino está aislado lógicamente dentro de Azure Active Directory a través de los controles de acceso basados en notificaciones. Las lecturas y escrituras de datos de directorio se limitan a contenedores de inquilinos y se canalizan mediante una capa de abstracción interna y una capa de control de acceso basado en roles (RBAC), que en conjunto aplican el inquilino como límite de seguridad. Todas las solicitudes de acceso a datos de directorio se procesan mediante estas capas y cada solicitud de acceso en Office 365 se controla con la lógica anterior.

Azure Active Directory tiene las particiones de Norteamérica, del gobierno de Estados Unidos, de la Unión Europea, de Alemania y de la World Wide. Un inquilino existe en una sola partición y las particiones pueden contener varios inquilinos. La información de particiones se abstrae de los usuarios. Una partición determinada (incluidos todos los inquilinos que contenga) se replica en varios centros de recursos. La partición de un inquilino se elige en función de las propiedades del espacio empresarial (por ejemplo, el código del país). Los secretos y otra información confidencial en cada partición se cifran con una clave dedicada. Las claves se generan automáticamente cuando se crea una partición nueva.

Las funciones del sistema de Azure Active Directory son una instancia única para cada sesión de usuario. Además, Azure Active Directory usa tecnologías de cifrado para proporcionar aislamiento de recursos del sistema compartidos en el nivel de red para evitar la transferencia de información no autorizada e inesperada.
