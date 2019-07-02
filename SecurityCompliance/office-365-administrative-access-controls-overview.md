---
title: Controles de acceso administrativo en Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Resumen: información general sobre los controles de acceso administrativo de Office 365 y la categorización de datos.'
ms.openlocfilehash: 38519fe4e9c05e3468ac3f9f6367c096fb64d195
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520700"
---
# <a name="administrative-access-controls-in-office-365"></a><span data-ttu-id="db034-103">Controles de acceso administrativo en Office 365</span><span class="sxs-lookup"><span data-stu-id="db034-103">Administrative Access Controls in Office 365</span></span> 

<span data-ttu-id="db034-104">Microsoft ha invertido mucho en sistemas y controles que automatizan la mayoría de las operaciones de Office 365 mientras limitan de forma intencionada el acceso al contenido del cliente por parte de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db034-104">Microsoft has invested heavily in systems and controls that automate most Office 365 operations while intentionally limiting access to customer content by Microsoft.</span></span> <span data-ttu-id="db034-105">Los seres humanos rigen el servicio y el software opera el servicio.</span><span class="sxs-lookup"><span data-stu-id="db034-105">Humans govern the service, and software operates the service.</span></span> <span data-ttu-id="db034-106">Esto permite que Microsoft administre Office 365 a escala y administre los riesgos de las amenazas internas para el contenido de los clientes.</span><span class="sxs-lookup"><span data-stu-id="db034-106">This enables Microsoft to manage Office 365 at scale and manage the risks of internal threats to customer content.</span></span>

<span data-ttu-id="db034-107">De forma predeterminada, los ingenieros de Microsoft tienen privilegios administrativos que no tienen ningún derecho de acceso permanente al contenido del cliente en Office 365.</span><span class="sxs-lookup"><span data-stu-id="db034-107">By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Office 365.</span></span> <span data-ttu-id="db034-108">Un ingeniero de Microsoft puede tener un acceso limitado, auditado y seguro al contenido de un cliente durante un período de tiempo limitado.</span><span class="sxs-lookup"><span data-stu-id="db034-108">A Microsoft engineer can have limited, audited, and secured access to a customer's content for a limited amount of time.</span></span> <span data-ttu-id="db034-109">El acceso solo es necesario para las operaciones de servicio y solo cuando lo aprueba un miembro de la administración Senior de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db034-109">Access is only when necessary for service operations and only when approved by a member of Microsoft senior management.</span></span> <span data-ttu-id="db034-110">Para los clientes con licencia de caja de caja de clientes, el cliente proporciona la aprobación de acceso a su contenido hospedado en Office 365.</span><span class="sxs-lookup"><span data-stu-id="db034-110">For Customer Lockbox licensed customers, the customer provides access approval to their content hosted on Office 365.</span></span>

<span data-ttu-id="db034-111">Microsoft proporciona servicios en línea con varios formularios de entrega de nube:</span><span class="sxs-lookup"><span data-stu-id="db034-111">Microsoft provides online services using multiple forms of cloud delivery:</span></span>

- <span data-ttu-id="db034-112">**Nubes públicas:** Incluye versiones de varios inquilinos de Office 365, Azure y otros servicios hospedados en Norteamérica, Sudamérica, Europa, Asia, Australia, etc.</span><span class="sxs-lookup"><span data-stu-id="db034-112">**Public Clouds:** Includes multi-tenant versions of Office 365, Azure, and other services hosted in North America, South America, Europe, Asia, Australia, etc.</span></span>
- <span data-ttu-id="db034-113">**Nubes nacionales:** Incluye todas las nubes soberanos y de terceros operadas fuera de los Estados Unidos (excepto las que se han mencionado anteriormente), como Office 365 en China (operado por 21Vianet) y Office 365 en Alemania (operado por Microsoft, pero bajo un modelo en el que se confía en los datos en alemán; Deutsche Telekom, controla y supervisa el acceso de Microsoft a los datos de los clientes y los sistemas que contienen datos del cliente).</span><span class="sxs-lookup"><span data-stu-id="db034-113">**National Clouds:** Includes all sovereign and third party-operated clouds outside of the United States (except ones noted previously), such as Office 365 in China (operated by 21Vianet), and Office 365 in Germany (operated by Microsoft, but under a model in which a German data trustee, Deutsche Telekom, controls and monitors Microsoft's access to Customer Data and systems that contain Customer Data).</span></span>
- <span data-ttu-id="db034-114">**Nubes gubernamentales:** Incluye los servicios de Office 365 y Azure que están disponibles para los clientes del gobierno de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="db034-114">**Government Clouds:** Includes Office 365 and Azure services that are available to United States government customers.</span></span>

<span data-ttu-id="db034-115">A efectos de este artículo, los servicios de Office 365 incluyen:</span><span class="sxs-lookup"><span data-stu-id="db034-115">For purposes of this article, Office 365 services include:</span></span>

- [<span data-ttu-id="db034-116">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="db034-116">Exchange Online</span></span>](https://docs.microsoft.com/Exchange/exchange-online)
- [<span data-ttu-id="db034-117">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="db034-117">Exchange Online Protection</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [<span data-ttu-id="db034-118">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="db034-118">SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [<span data-ttu-id="db034-119">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="db034-119">OneDrive for Business</span></span>](https://docs.microsoft.com/OneDrive/onedrive)
- [<span data-ttu-id="db034-120">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="db034-120">Skype for Business</span></span>](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [<span data-ttu-id="db034-121">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db034-121">Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [<span data-ttu-id="db034-122">Yammer</span><span class="sxs-lookup"><span data-stu-id="db034-122">Yammer</span></span>](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="office-365-access-controls"></a><span data-ttu-id="db034-123">Controles de acceso de Office 365</span><span class="sxs-lookup"><span data-stu-id="db034-123">Office 365 Access Controls</span></span>

<span data-ttu-id="db034-124">Para fines de control de acceso, Microsoft clasifica los datos de Office 365 como datos de cliente u otros tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="db034-124">For access control purposes, Microsoft categorizes Office 365 data as Customer data or other types of data.</span></span>

### <a name="customer-data"></a><span data-ttu-id="db034-125">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="db034-125">Customer data</span></span>

<span data-ttu-id="db034-126">Los datos de los clientes son todos los datos proporcionados por o en nombre de un cliente cuando se usan los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="db034-126">Customer data is all data provided by or on behalf of a customer when using Office 365 services.</span></span> <span data-ttu-id="db034-127">Se trata de contenido de cliente que se crea o carga directamente con los usuarios de Office 365, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="db034-127">This is customer content directly created or uploaded by Office 365 users, including:</span></span>

- <span data-ttu-id="db034-128">Mensajes de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="db034-128">Emails</span></span>
- <span data-ttu-id="db034-129">Contenido de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="db034-129">SharePoint Online content</span></span>
- <span data-ttu-id="db034-130">Mensajes instantáneos</span><span class="sxs-lookup"><span data-stu-id="db034-130">Instant messages</span></span>
- <span data-ttu-id="db034-131">Elementos de calendario</span><span class="sxs-lookup"><span data-stu-id="db034-131">Calendar items</span></span>
- <span data-ttu-id="db034-132">Documents</span><span class="sxs-lookup"><span data-stu-id="db034-132">Documents</span></span>
- <span data-ttu-id="db034-133">Contactos</span><span class="sxs-lookup"><span data-stu-id="db034-133">Contacts</span></span>
- <span data-ttu-id="db034-134">Información de identificación del usuario final (EUII) (datos que son únicos para un usuario o que son vinculables a un usuario individual pero que no incluyen contenido del cliente).</span><span class="sxs-lookup"><span data-stu-id="db034-134">End-user identifiable information (EUII) (data that is unique to a user or that is linkable to an individual user but does not include customer content).</span></span>

### <a name="other-types-of-data"></a><span data-ttu-id="db034-135">Otros tipos de datos</span><span class="sxs-lookup"><span data-stu-id="db034-135">Other types of data</span></span>

<span data-ttu-id="db034-136">Otros tipos de datos son:</span><span class="sxs-lookup"><span data-stu-id="db034-136">Other types of data include:</span></span>

- <span data-ttu-id="db034-137">**Datos de la cuenta:** Incluye datos administrativos (información proporcionada por los administradores cuando registran o compran servicios) y datos de pago (información sobre instrumentos de pago, como detalles de la tarjeta de crédito).</span><span class="sxs-lookup"><span data-stu-id="db034-137">**Account data:** Includes administrative data (information provided by administrators when they sign-up or purchase services), and payment data (information about payment instruments, such as credit card details).</span></span>
- <span data-ttu-id="db034-138">**Información de identificación organizativa:** Incluye datos que se usan para identificar un espacio empresarial, datos de uso y no vinculables a un usuario individual o incluidos en el contenido del cliente.</span><span class="sxs-lookup"><span data-stu-id="db034-138">**Organizationally identifiable information:** Includes data used to identify a tenant, usage data, and not linkable to an individual user or included in customer content.</span></span>
- <span data-ttu-id="db034-139">**Metadatos del sistema:** Incluye registros de servicios que contienen opciones de configuración, estado del sistema, direcciones IP de Microsoft e información técnica sobre suscripciones e inquilinos.</span><span class="sxs-lookup"><span data-stu-id="db034-139">**System metadata:** Includes service logs that contain configuration settings, system status, Microsoft IP addresses, and technical information about subscriptions and tenants.</span></span>

<span data-ttu-id="db034-140">Microsoft ha establecido mecanismos de control de acceso para garantizar que nadie tenga acceso no aprobado a datos de clientes o a datos de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="db034-140">Microsoft has established access control mechanisms to ensure that no one has unapproved access to Customer Data or access control data.</span></span> <span data-ttu-id="db034-141">Los datos de control de acceso administran el acceso a otros tipos de datos o funciones dentro del entorno, incluidos el acceso al contenido del cliente o la EUII, las contraseñas de Microsoft, los certificados de seguridad y otros datos relacionados con la autenticación.</span><span class="sxs-lookup"><span data-stu-id="db034-141">Access control data manages access to other types of data or functions within the environment, including access to customer content or EUII, Microsoft passwords, security certificates, and other authentication-related data.</span></span> <span data-ttu-id="db034-142">Los mecanismos de control de acceso también protegen contra el acceso físico, lógico o remoto no aprobado al entorno de producción de Office 365.</span><span class="sxs-lookup"><span data-stu-id="db034-142">Access control mechanisms also guard against unapproved physical, logical, or remote access to the Office 365 production environment.</span></span>

<span data-ttu-id="db034-143">Microsoft usa tres categorías de controles de acceso para Office de operaciones 365:</span><span class="sxs-lookup"><span data-stu-id="db034-143">There are three categories of access controls used by Microsoft for operating Office 365:</span></span>

- <span data-ttu-id="db034-144">Controles de aislamiento</span><span class="sxs-lookup"><span data-stu-id="db034-144">Isolation Controls</span></span>
- <span data-ttu-id="db034-145">Controles de personal</span><span class="sxs-lookup"><span data-stu-id="db034-145">Personnel Controls</span></span>
- <span data-ttu-id="db034-146">Controles de tecnología</span><span class="sxs-lookup"><span data-stu-id="db034-146">Technology Controls</span></span>

<span data-ttu-id="db034-147">Cuando se combinan, estos controles ayudan a evitar y detectar acciones malintencionadas en Office 365.</span><span class="sxs-lookup"><span data-stu-id="db034-147">When combined, these controls help prevent and detect malicious actions in Office 365.</span></span> <span data-ttu-id="db034-148">Además de los controles de aislamiento, personal y tecnología que usa Microsoft, hay una cuarta categoría de controles: los implementados por los clientes.</span><span class="sxs-lookup"><span data-stu-id="db034-148">In addition to the isolation, personnel, and technology controls used by Microsoft, there is a fourth category of controls: those implemented by customers.</span></span>

<span data-ttu-id="db034-149">Office 365 permite administrar los datos de la misma manera que los datos se administran en entornos locales.</span><span class="sxs-lookup"><span data-stu-id="db034-149">Office 365 allows you to manage data the same way data is managed in on-premises environments.</span></span> <span data-ttu-id="db034-150">La persona que registra una organización para Office 365 se convierte automáticamente en un administrador global.</span><span class="sxs-lookup"><span data-stu-id="db034-150">The person who signs up an organization for Office 365 automatically becomes a global administrator.</span></span> <span data-ttu-id="db034-151">El administrador global tiene acceso a todas las características de los portales de administración y puede:</span><span class="sxs-lookup"><span data-stu-id="db034-151">The global admin has access to all features in Management Portals and can:</span></span>

- <span data-ttu-id="db034-152">Crear o editar usuarios</span><span class="sxs-lookup"><span data-stu-id="db034-152">Create or edit users</span></span>
- <span data-ttu-id="db034-153">Asignar roles de administrador a otros</span><span class="sxs-lookup"><span data-stu-id="db034-153">Assign admin roles to others</span></span>
- <span data-ttu-id="db034-154">Restablecer contraseñas de usuario</span><span class="sxs-lookup"><span data-stu-id="db034-154">Reset user passwords</span></span>
- <span data-ttu-id="db034-155">Administrar licencias de usuario</span><span class="sxs-lookup"><span data-stu-id="db034-155">Manage user licenses</span></span>
- <span data-ttu-id="db034-156">Administrar dominios</span><span class="sxs-lookup"><span data-stu-id="db034-156">Manage domains</span></span>
- <span data-ttu-id="db034-157">Aprobar solicitudes de caja de caja de cliente</span><span class="sxs-lookup"><span data-stu-id="db034-157">Approve Customer Lockbox requests</span></span>

<span data-ttu-id="db034-158">Se recomienda que cada organización configure al menos dos cuentas de administrador.</span><span class="sxs-lookup"><span data-stu-id="db034-158">We recommend that each organization configure at least two admin accounts.</span></span> <span data-ttu-id="db034-159">Para grandes organizaciones empresariales, recomendamos cuentas de administrador especializadas que atienden diferentes funciones.</span><span class="sxs-lookup"><span data-stu-id="db034-159">For large enterprise organizations, we recommend specialized admin accounts that serve different functions.</span></span>

<span data-ttu-id="db034-160">Para obtener información acerca de la asignación de roles y permisos de administrador, vea [asignar roles de administrador en Office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) y [acerca de Office 365 roles de administrador](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).</span><span class="sxs-lookup"><span data-stu-id="db034-160">For information about assigning admin roles and permissions, see [Assigning admin roles in Office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) and [About Office 365 admin roles](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).</span></span>

## <a name="related-links"></a><span data-ttu-id="db034-161">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="db034-161">Related Links</span></span>

- [<span data-ttu-id="db034-162">Controles de aislamiento</span><span class="sxs-lookup"><span data-stu-id="db034-162">Isolation Controls</span></span>](office-365-isolation-controls.md)
- [<span data-ttu-id="db034-163">Controles de personal</span><span class="sxs-lookup"><span data-stu-id="db034-163">Personnel Controls</span></span>](office-365-personnel-controls.md)
- [<span data-ttu-id="db034-164">Controles de tecnología</span><span class="sxs-lookup"><span data-stu-id="db034-164">Technology Controls</span></span>](office-365-technology-controls.md)
- [<span data-ttu-id="db034-165">Auditoría y supervisión de controles de acceso</span><span class="sxs-lookup"><span data-stu-id="db034-165">Monitoring and Auditing Access Controls</span></span>](office-365-monitoring-and-auditing-access-controls.md)
- [<span data-ttu-id="db034-166">Controles de acceso de Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="db034-166">Yammer Enterprise Access Controls</span></span>](office-365-yammer-enterprise-access-controls.md)