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
# <a name="protect-apps-with-office-365-cloud-app-security-conditional-access-app-control"></a><span data-ttu-id="d398f-103">Proteger aplicaciones con el Control de aplicaciones de acceso condicional de Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d398f-103">Protect apps with Office 365 Cloud App Security Conditional Access App Control</span></span>

|<span data-ttu-id="d398f-104">Evaluación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d398f-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="d398f-105">Planeación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d398f-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="d398f-106">Implementación \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d398f-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="d398f-107">Uso \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="d398f-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="d398f-108">Empezar a evaluar</span><span class="sxs-lookup"><span data-stu-id="d398f-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="d398f-109">Empezar a planear</span><span class="sxs-lookup"><span data-stu-id="d398f-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="d398f-110">Ya está aquí.</span><span class="sxs-lookup"><span data-stu-id="d398f-110">You are here!</span></span>  <br/> [<span data-ttu-id="d398f-111">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="d398f-111">Next step</span></span>](ocas-deploy-conditional-access-app-control.md) <br/> |[<span data-ttu-id="d398f-112">Empezar a usar</span><span class="sxs-lookup"><span data-stu-id="d398f-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="d398f-p101">En el lugar de trabajo de hoy en día, a menudo no es suficiente saber lo que ocurre en su entorno de nube después del hecho. Desea detener las infracciones y las pérdidas en tiempo real, antes de que los empleados pongan en riesgo sus datos y su organización de forma intencionada o inadvertida. Es importante permitir que los usuarios de la organización hagan la mayor parte de los servicios y las herramientas disponibles en las aplicaciones en la nube, y les permitan poner en funcionamiento sus propios dispositivos. Al mismo tiempo, necesita herramientas para ayudar a proteger su organización contra pérdidas de datos y el robo de datos en tiempo real. Junto con Azure Active Directory, Office 365 Cloud App Security ofrece estas capacidades en una experiencia holística e integrada con el control de aplicación de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="d398f-p101">In today’s workplace, it’s often not enough to know what’s happening in your cloud environment after the fact. You want to stop breaches and leaks in real time, before employees intentionally or inadvertently put your data and your organization at risk. It's important to enable users in your organization to make the most of the services and tools available to them in cloud apps, and let them bring their own devices to work. At the same time, you need tools to help protect your organization from data leaks, and data theft, in real time. Together with Azure Active Directory, Office 365 Cloud App Security delivers these capabilities in a holistic and integrated experience with Conditional Access App Control.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d398f-118">para usar el Control de aplicación de acceso condicional de cloud app security, necesita una  [licencia de Azure Active directory P1](https://azure.microsoft.com/pricing/details/active-directory/)y una suscripción de seguridad de aplicación en [la nube de Office 365](office-365-cas-overview.md) activa.</span><span class="sxs-lookup"><span data-stu-id="d398f-118">To use Cloud App Security Conditional Access App Control, you need an [Azure Active Directory P1 license](https://azure.microsoft.com/pricing/details/active-directory/) and an active [Office 365 Cloud App Security](office-365-cas-overview.md) subscription.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="d398f-119">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="d398f-119">How it works</span></span>

<span data-ttu-id="d398f-p102">El control de aplicación de acceso condicional usa una arquitectura de proxy inverso y se integra de forma exclusiva con el acceso condicional de Azure AD. El acceso condicional de Azure AD le permite exigir controles de acceso en las aplicaciones de la organización en función de determinadas condiciones. Las condiciones definen *quién* (usuario o grupo de usuarios) y a *qué* (qué aplicaciones de la nube) y a *dónde* (a qué ubicaciones y redes) se aplica una directiva de acceso condicional. Una vez que haya determinado las condiciones, puede enrutar a los usuarios a Office 365 Cloud App Security, donde puede proteger los datos con el control de la aplicación de acceso condicional mediante la aplicación de controles de acceso y de sesión.</span><span class="sxs-lookup"><span data-stu-id="d398f-p102">Conditional Access App Control uses a reverse proxy architecture and is uniquely integrated with Azure AD conditional access. Azure AD conditional access allows you to enforce access controls on your organization’s apps based on certain conditions. The conditions define *who* (user or group of users) and *what* (which cloud apps) and *where* (which locations and networks) a conditional access policy is applied to. After you’ve determined the conditions, you can route users to Office 365 Cloud App Security where you can protect data with Conditional Access App Control by applying access and session controls.</span></span>

<span data-ttu-id="d398f-p103">El control de aplicación de acceso condicional permite que el acceso de la aplicación de usuario y las sesiones se supervisen y controlen en tiempo real en función de las directivas de acceso y de sesión. Las directivas de acceso y sesión se usan dentro del portal de Cloud App Security para refinar aún más los filtros y establecer las acciones que se van a realizar en un usuario. Con las directivas de acceso y de sesión, puede:</span><span class="sxs-lookup"><span data-stu-id="d398f-p103">Conditional Access App Control enables user app access and sessions to be monitored and controlled in real time based on access and session policies. Access and session policies are used within the Cloud App Security portal to further refine filters and set actions to be taken on a user. With the access and session policies, you can:</span></span>

- <span data-ttu-id="d398f-p104">**Bloquear en descarga**: puede bloquear la descarga de documentos confidenciales. Por ejemplo, en dispositivos no administrados.</span><span class="sxs-lookup"><span data-stu-id="d398f-p104">**Block on download**: You can block the download of sensitive documents. For example, on unmanaged devices.</span></span>

- <span data-ttu-id="d398f-p105">**Proteger al descargar**: en lugar de bloquear la descarga de documentos confidenciales, puede requerir que los documentos se protejan mediante cifrado en la descarga. Este cifrado comprueba que el documento está protegido y que el acceso de usuario se ha autenticado si los datos se descargan en un dispositivo que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="d398f-p105">**Protect on download**: Instead of blocking the download of sensitive documents, you can require documents to be protected via encryption on download. This encryption makes sure the document is protected and user access is authenticated if the data is downloaded to an untrusted device.</span></span>

- <span data-ttu-id="d398f-p106">**Supervisar sesiones de usuario de confianza baja**: los usuarios arriesgados se supervisan cuando inician sesión en las aplicaciones y sus acciones se registran desde dentro de la sesión. Puede investigar y analizar el comportamiento del usuario para comprender dónde y en qué condiciones, las directivas de sesión se deben aplicar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="d398f-p106">**Monitor low-trust user sessions**: Risky users are monitored when they sign into apps and their actions are logged from within the session. You can investigate and analyze user behavior to understand where, and under what conditions, session policies should be applied in the future.</span></span>

- <span data-ttu-id="d398f-133">**Bloquear acceso**: puede bloquear completamente el acceso a aplicaciones específicas para usuarios procedentes de dispositivos no administrados o de redes no corporativas.</span><span class="sxs-lookup"><span data-stu-id="d398f-133">**Block access**: You can completely block access to specific apps for users coming from unmanaged devices or from non-corporate networks.</span></span>

- <span data-ttu-id="d398f-134">**Crear modo de solo lectura**: mediante la supervisión y el bloqueo de actividades personalizadas de la aplicación, puede crear un modo de solo lectura para aplicaciones específicas para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="d398f-134">**Create read-only mode**: By monitoring and blocking custom in-app activities, you can create a read-only mode to specific apps for specific users.</span></span>

- <span data-ttu-id="d398f-p107">**Restringir sesiones de usuario de redes no corporativas**: los usuarios que acceden a una aplicación protegida desde una ubicación que no forma parte de la red corporativa tienen permitido el acceso restringido. La descarga de materiales confidenciales está bloqueada o protegida.</span><span class="sxs-lookup"><span data-stu-id="d398f-p107">**Restrict user sessions from non-corporate networks**: Users accessing a protected app from a location that isn't part of your corporate network are allowed restricted access. The download of sensitive materials is blocked or protected.</span></span>

### <a name="how-session-control-works"></a><span data-ttu-id="d398f-137">Funcionamiento del control de sesión</span><span class="sxs-lookup"><span data-stu-id="d398f-137">How session control works</span></span>

<span data-ttu-id="d398f-p108">La creación de una directiva de sesión con el control de aplicación de acceso condicional permite controlar las sesiones de usuario redirigiendo el usuario a través de un proxy inverso en lugar de hacerlo directamente a la aplicación. A partir de entonces, las solicitudes de usuario y las respuestas pasan por la seguridad de aplicaciones en la nube de Office 365 en lugar de directamente a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d398f-p108">Creating a session policy with Conditional Access App Control enables you to control user sessions by redirecting the user through a reverse proxy instead of directly to the app. From then on, user requests and responses go through Office 365 Cloud App Security rather than directly to the app.</span></span>

<span data-ttu-id="d398f-p109">Para mantener al usuario dentro de la sesión, todas las direcciones URL relevantes, las secuencias de comandos Java y las cookies dentro de la sesión de la aplicación se reemplazan con las direcciones URL de seguridad de aplicaciones de nube de Office 365. Por ejemplo, si la aplicación devuelve una página con vínculos cuyos dominios terminan con myapp.com, el vínculo se reemplaza con dominios que terminan por algo similar a: myapp.com.us.cas.ms</span><span class="sxs-lookup"><span data-stu-id="d398f-p109">To keep the user within the session, all the relevant URLs, Java scripts, and cookies within the app session are replaced with Office 365 Cloud App Security URLs. For example, if the app returns a page with links whose domains end with myapp.com, the link is replaced with domains ending with something like: myapp.com.us.cas.ms</span></span>

<span data-ttu-id="d398f-p110">Este método no requiere que instale nada en el dispositivo. Este método es ideal para supervisar sesiones desde dispositivos no administrados.</span><span class="sxs-lookup"><span data-stu-id="d398f-p110">This method doesn't require you to install anything on the device. This method is ideal when monitoring sessions from unmanaged devices.</span></span>

<span data-ttu-id="d398f-144">Una vez que se dirige una sesión a través de Office 365 Cloud App Security, se pueden realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d398f-144">After a session is directed through Office 365 Cloud App Security, the following actions can be done:</span></span>

1. <span data-ttu-id="d398f-145">Inspeccionar el tráfico de las actividades de usuario</span><span class="sxs-lookup"><span data-stu-id="d398f-145">Inspect the traffic for user activities</span></span>

2. <span data-ttu-id="d398f-146">Mostrar las actividades identificadas en el registro de actividad de seguridad de aplicación de nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="d398f-146">Display the identified activities in the Office 365 Cloud App Security Activity log</span></span>

3. <span data-ttu-id="d398f-147">Guardar los registros de tráfico y analizarlos</span><span class="sxs-lookup"><span data-stu-id="d398f-147">Save the traffic logs and analyze them</span></span>

4. <span data-ttu-id="d398f-148">Permitir que el administrador exporte los registros de tráfico</span><span class="sxs-lookup"><span data-stu-id="d398f-148">Enable the admin to export the traffic logs</span></span>

5. <span data-ttu-id="d398f-149">Aplicar directivas en la sesión</span><span class="sxs-lookup"><span data-stu-id="d398f-149">Enforce policies on the session</span></span>

## <a name="managed-device-identification"></a><span data-ttu-id="d398f-150">Identificación de dispositivos administrados</span><span class="sxs-lookup"><span data-stu-id="d398f-150">Managed device identification</span></span>

<span data-ttu-id="d398f-p111">El control de aplicación de acceso condicional permite crear directivas que tienen en cuenta si un dispositivo se administra o no. Para identificar si un dispositivo se administra o no, la característica usa:</span><span class="sxs-lookup"><span data-stu-id="d398f-p111">Conditional Access App Control enables you to create policies that take into account whether a device is managed or not. To identify whether a device is managed or not, the feature uses:</span></span>

- <span data-ttu-id="d398f-153">Dispositivos compatibles</span><span class="sxs-lookup"><span data-stu-id="d398f-153">Compliant devices</span></span>

- <span data-ttu-id="d398f-154">Dispositivos Unidos a un dominio</span><span class="sxs-lookup"><span data-stu-id="d398f-154">Domain-joined devices</span></span>

- <span data-ttu-id="d398f-155">Implementación de certificados de cliente</span><span class="sxs-lookup"><span data-stu-id="d398f-155">Client certificates deployment</span></span>

### <a name="compliant-and-domain-joined-devices"></a><span data-ttu-id="d398f-156">Dispositivos compatibles y Unidos a un dominio</span><span class="sxs-lookup"><span data-stu-id="d398f-156">Compliant and domain-joined devices</span></span>

<span data-ttu-id="d398f-p112">El acceso condicional de Azure AD permite pasar directamente la información de dispositivos compatibles y Unidos a un dominio a Office 365 Cloud App Security. Desde allí, se puede desarrollar una directiva de acceso o una directiva de sesión que use el estado del dispositivo como filtro. Para obtener más información, vea [Introducción a la administración de dispositivos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="d398f-p112">Azure AD conditional access enables compliant and domain-joined device information to be passed directly to Office 365 Cloud App Security. From there, an access policy or a session policy can be developed that uses device state as a filter. For more information, see the [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>

### <a name="client-certificate-authenticated-devices"></a><span data-ttu-id="d398f-160">Dispositivos autenticados del certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="d398f-160">Client-certificate authenticated devices</span></span>

<span data-ttu-id="d398f-p113">El mecanismo de identificación de dispositivos puede solicitar la autenticación de los dispositivos relevantes mediante certificados de cliente. Puede usar los certificados de cliente existentes que ya se han implementado en la organización o implementar nuevos certificados de cliente en los dispositivos administrados. A continuación, se usa la presencia de dichos certificados para establecer las directivas de acceso y de sesión. Para obtener información sobre cómo implementar certificados de cliente, consulte [deploy conditionAl Access App Control for Office 365 apps](ocas-deploy-conditional-access-app-control.md).</span><span class="sxs-lookup"><span data-stu-id="d398f-p113">The device identification mechanism can request authentication from relevant devices using client certificates. You can either use existing client certificates already deployed in your organization or roll out new client certificates to managed devices. You then use the presence of those certificates to set access and session policies. For information on how to deploy client certificates see [Deploy Conditional Access App Control for Office 365 apps](ocas-deploy-conditional-access-app-control.md).</span></span>

## <a name="supported-apps-and-clients"></a><span data-ttu-id="d398f-165">Aplicaciones y clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="d398f-165">Supported apps and clients</span></span>

<span data-ttu-id="d398f-166">El control de aplicaciones de acceso condicional para Office 365 admite las siguientes aplicaciones destacadas:</span><span class="sxs-lookup"><span data-stu-id="d398f-166">Conditional Access App Control for Office 365 supports the following featured apps:</span></span>

- <span data-ttu-id="d398f-167">Exchange Online (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d398f-167">Exchange Online (preview)</span></span>

- <span data-ttu-id="d398f-168">OneDrive para la empresa (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d398f-168">OneDrive for Business (preview)</span></span>

- <span data-ttu-id="d398f-169">Power BI (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d398f-169">Power BI (preview)</span></span>

- <span data-ttu-id="d398f-170">SharePoint Online (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d398f-170">SharePoint Online (preview)</span></span>

- <span data-ttu-id="d398f-171">Microsoft Teams (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d398f-171">Microsoft Teams (preview)</span></span>

- <span data-ttu-id="d398f-172">Yammer (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d398f-172">Yammer (preview)</span></span>

<span data-ttu-id="d398f-173">Las aplicaciones adicionales se están continuamente en el control de la sesión.</span><span class="sxs-lookup"><span data-stu-id="d398f-173">Additional apps are being continuously on-boarded to session control.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d398f-174">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d398f-174">Next steps</span></span>

- [<span data-ttu-id="d398f-175">Implementar el Control de aplicaciones de acceso condicional para las aplicaciones de Office 365</span><span class="sxs-lookup"><span data-stu-id="d398f-175">Deploy Conditional Access App Control for Office 365 apps</span></span>](ocas-deploy-conditional-access-app-control.md)

- [<span data-ttu-id="d398f-176">Obtener información sobre las directivas de sesión en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d398f-176">Learn about session policies in Office 365 Cloud App Security</span></span>](ocas-session-policies.md)

- [<span data-ttu-id="d398f-177">Obtenga información sobre las directivas de acceso en Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d398f-177">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md) 