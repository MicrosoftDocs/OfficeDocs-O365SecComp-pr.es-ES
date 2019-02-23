---
title: Proteger aplicaciones con el Control de aplicaciones de acceso condicional de Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Detenga las infracciones y pérdidas en tiempo real con el control de aplicación de acceso condicional de seguridad de aplicación de Office 365 Cloud app.
ms.openlocfilehash: 23c4b29e86eb8ba92cfa8a544d6484965ec6372b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217090"
---
# <a name="protect-apps-with-office-365-cloud-app-security-conditional-access-app-control"></a>Proteger aplicaciones con el Control de aplicaciones de acceso condicional de Office 365 Cloud App Security

|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Siguiente paso](ocas-deploy-conditional-access-app-control.md) <br/> |[Empezar a usar](utilization-activities-for-ocas.md) <br/> |

En el lugar de trabajo de hoy en día, a menudo no es suficiente saber lo que ocurre en su entorno de nube después del hecho. Desea detener las infracciones y las pérdidas en tiempo real, antes de que los empleados pongan en riesgo sus datos y su organización de forma intencionada o inadvertida. Es importante permitir que los usuarios de la organización hagan la mayor parte de los servicios y las herramientas disponibles en las aplicaciones en la nube, y les permitan poner en funcionamiento sus propios dispositivos. Al mismo tiempo, necesita herramientas para ayudar a proteger su organización contra pérdidas de datos y el robo de datos en tiempo real. Junto con Azure Active Directory, Office 365 Cloud App Security ofrece estas capacidades en una experiencia holística e integrada con el control de aplicación de acceso condicional.

> [!IMPORTANT]
> para usar el Control de aplicación de acceso condicional de cloud app security, necesita una  [licencia de Azure Active directory P1](https://azure.microsoft.com/pricing/details/active-directory/)y una suscripción de seguridad de aplicación en [la nube de Office 365](office-365-cas-overview.md) activa.

## <a name="how-it-works"></a>Funcionamiento

El control de aplicación de acceso condicional usa una arquitectura de proxy inverso y se integra de forma exclusiva con el acceso condicional de Azure AD. El acceso condicional de Azure AD le permite exigir controles de acceso en las aplicaciones de la organización en función de determinadas condiciones. Las condiciones definen *quién* (usuario o grupo de usuarios) y a *qué* (qué aplicaciones de la nube) y a *dónde* (a qué ubicaciones y redes) se aplica una directiva de acceso condicional. Una vez que haya determinado las condiciones, puede enrutar a los usuarios a Office 365 Cloud App Security, donde puede proteger los datos con el control de la aplicación de acceso condicional mediante la aplicación de controles de acceso y de sesión.

El control de aplicación de acceso condicional permite que el acceso de la aplicación de usuario y las sesiones se supervisen y controlen en tiempo real en función de las directivas de acceso y de sesión. Las directivas de acceso y sesión se usan dentro del portal de Cloud App Security para refinar aún más los filtros y establecer las acciones que se van a realizar en un usuario. Con las directivas de acceso y de sesión, puede:

- **Bloquear en descarga**: puede bloquear la descarga de documentos confidenciales. Por ejemplo, en dispositivos no administrados.

- **Proteger al descargar**: en lugar de bloquear la descarga de documentos confidenciales, puede requerir que los documentos se protejan mediante cifrado en la descarga. Este cifrado comprueba que el documento está protegido y que el acceso de usuario se ha autenticado si los datos se descargan en un dispositivo que no es de confianza.

- **Supervisar sesiones de usuario de confianza baja**: los usuarios arriesgados se supervisan cuando inician sesión en las aplicaciones y sus acciones se registran desde dentro de la sesión. Puede investigar y analizar el comportamiento del usuario para comprender dónde y en qué condiciones, las directivas de sesión se deben aplicar en el futuro.

- **Bloquear acceso**: puede bloquear completamente el acceso a aplicaciones específicas para usuarios procedentes de dispositivos no administrados o de redes no corporativas.

- **Crear modo de solo lectura**: mediante la supervisión y el bloqueo de actividades personalizadas de la aplicación, puede crear un modo de solo lectura para aplicaciones específicas para usuarios específicos.

- **Restringir sesiones de usuario de redes no corporativas**: los usuarios que acceden a una aplicación protegida desde una ubicación que no forma parte de la red corporativa tienen permitido el acceso restringido. La descarga de materiales confidenciales está bloqueada o protegida.

### <a name="how-session-control-works"></a>Funcionamiento del control de sesión

La creación de una directiva de sesión con el control de aplicación de acceso condicional permite controlar las sesiones de usuario redirigiendo el usuario a través de un proxy inverso en lugar de hacerlo directamente a la aplicación. A partir de entonces, las solicitudes de usuario y las respuestas pasan por la seguridad de aplicaciones en la nube de Office 365 en lugar de directamente a la aplicación.

Para mantener al usuario dentro de la sesión, todas las direcciones URL relevantes, las secuencias de comandos Java y las cookies dentro de la sesión de la aplicación se reemplazan con las direcciones URL de seguridad de aplicaciones de nube de Office 365. Por ejemplo, si la aplicación devuelve una página con vínculos cuyos dominios terminan con myapp.com, el vínculo se reemplaza con dominios que terminan por algo similar a: myapp.com.us.cas.ms

Este método no requiere que instale nada en el dispositivo. Este método es ideal para supervisar sesiones desde dispositivos no administrados.

Una vez que se dirige una sesión a través de Office 365 Cloud App Security, se pueden realizar las siguientes acciones:

1. Inspeccionar el tráfico de las actividades de usuario

2. Mostrar las actividades identificadas en el registro de actividad de seguridad de aplicación de nube de Office 365

3. Guardar los registros de tráfico y analizarlos

4. Permitir que el administrador exporte los registros de tráfico

5. Aplicar directivas en la sesión

## <a name="managed-device-identification"></a>Identificación de dispositivos administrados

El control de aplicación de acceso condicional permite crear directivas que tienen en cuenta si un dispositivo se administra o no. Para identificar si un dispositivo se administra o no, la característica usa:

- Dispositivos compatibles

- Dispositivos Unidos a un dominio

- Implementación de certificados de cliente

### <a name="compliant-and-domain-joined-devices"></a>Dispositivos compatibles y Unidos a un dominio

El acceso condicional de Azure AD permite pasar directamente la información de dispositivos compatibles y Unidos a un dominio a Office 365 Cloud App Security. Desde allí, se puede desarrollar una directiva de acceso o una directiva de sesión que use el estado del dispositivo como filtro. Para obtener más información, vea [Introducción a la administración de dispositivos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).

### <a name="client-certificate-authenticated-devices"></a>Dispositivos autenticados del certificado de cliente

El mecanismo de identificación de dispositivos puede solicitar la autenticación de los dispositivos relevantes mediante certificados de cliente. Puede usar los certificados de cliente existentes que ya se han implementado en la organización o implementar nuevos certificados de cliente en los dispositivos administrados. A continuación, se usa la presencia de dichos certificados para establecer las directivas de acceso y de sesión. Para obtener información sobre cómo implementar certificados de cliente, consulte [deploy conditionAl Access App Control for Office 365 apps](ocas-deploy-conditional-access-app-control.md).

## <a name="supported-apps-and-clients"></a>Aplicaciones y clientes compatibles

El control de aplicaciones de acceso condicional para Office 365 admite las siguientes aplicaciones destacadas:

- Exchange Online (versión preliminar)

- OneDrive para la empresa (versión preliminar)

- Power BI (versión preliminar)

- SharePoint Online (versión preliminar)

- Microsoft Teams (versión preliminar)

- Yammer (versión preliminar)

Las aplicaciones adicionales se están continuamente en el control de la sesión.

## <a name="next-steps"></a>Pasos siguientes

- [Implementar el Control de aplicaciones de acceso condicional para las aplicaciones de Office 365](ocas-deploy-conditional-access-app-control.md)

- [Obtener información sobre las directivas de sesión en Office 365 Cloud App Security](ocas-session-policies.md)

- [Obtenga información sobre las directivas de acceso en Office 365 Cloud App Security](ocas-access-policies.md) 