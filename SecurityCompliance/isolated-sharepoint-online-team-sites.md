---
title: Sitios de grupo de SharePoint Online aislados
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 'Resumen: obtenga información sobre los usos de sitios de grupo de SharePoint Online aislados.'
ms.openlocfilehash: 17e6fffc72a366d2cbb2c96e2b6bc812d0670e94
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253928"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="e865f-103">Sitios de grupo de SharePoint Online aislados</span><span class="sxs-lookup"><span data-stu-id="e865f-103">Isolated SharePoint Online team sites</span></span>

 <span data-ttu-id="e865f-104">**Resumen:** obtenga información sobre los usos de sitios de grupo de SharePoint Online aislados.</span><span class="sxs-lookup"><span data-stu-id="e865f-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="e865f-p101">Los sitios de grupo de SharePoint Online son una forma sencilla de crear rápidamente un espacio para la colaboración en notas, documentos, artículos, calendarios y otros recursos en Microsoft Office 365. Los sitios de grupo de SharePoint Online se basan en un grupo de Office 365 y tienen un modelo de administración simplificado para permitir la colaboración abierta con un conjunto privado de miembros del grupo o con toda la organización. Un sitio de grupo predeterminado de SharePoint Online permite a los miembros del grupo de Office 365 invitar a otros usuarios y controlar la configuración de los permisos.</span><span class="sxs-lookup"><span data-stu-id="e865f-p101">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on an Office 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Office 365 group to invite other users and control permissions settings.</span></span>
  
<span data-ttu-id="e865f-p102">Pero, en algunos casos, puede que quiera crear un sitio de grupo de SharePoint Online para colaborar en el que los permisos del sitio se controlen de forma más estricta con pertenencia a grupos y niveles de permisos de SharePoint Online, que solo pueden controlar los administradores de SharePoint. Esto se denomina un sitio aislado, que está aislado para el conjunto de usuarios que colaboran, visualizan sus contenidos o administran el sitio. Puede que necesite usar un sitio aislado en estos casos:</span><span class="sxs-lookup"><span data-stu-id="e865f-p102">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators. We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site. You might need an isolated site for the following:</span></span>
  
- <span data-ttu-id="e865f-111">Un proyecto secreto en su organización.</span><span class="sxs-lookup"><span data-stu-id="e865f-111">A secret project within your organization.</span></span>
    
- <span data-ttu-id="e865f-112">La ubicación de propiedad intelectual altamente confidencial o valiosa para su organización.</span><span class="sxs-lookup"><span data-stu-id="e865f-112">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>
    
- <span data-ttu-id="e865f-113">Los recursos de una acción legal realizada por su organización o por la organización que sea objeto de esa acción legal.</span><span class="sxs-lookup"><span data-stu-id="e865f-113">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>
    
- <span data-ttu-id="e865f-114">Para compartir una suscripción de Office 365 entre varias organizaciones que se superpongan parcialmente, pero que, en su mayoría, existan como entidades empresariales separadas.</span><span class="sxs-lookup"><span data-stu-id="e865f-114">To share an Office 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>
    
<span data-ttu-id="e865f-115">Estos son los requisitos para un sitio aislado:</span><span class="sxs-lookup"><span data-stu-id="e865f-115">Here are the requirements of an isolated site:</span></span>
  
- <span data-ttu-id="e865f-116">Solo los administradores de SharePoint Online pueden administrar el sitio, como la pertenencia a grupos para el acceso al sitio y la configuración de permisos personalizados.</span><span class="sxs-lookup"><span data-stu-id="e865f-116">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>
    
- <span data-ttu-id="e865f-117">Los miembros del sitio no pueden invitar a otros miembros al sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="e865f-117">Members of the site cannot invite other members to the team site.</span></span>
    
- <span data-ttu-id="e865f-p103">Los usuarios que no sean miembros del sitio aislado no pueden solicitar acceso al sitio. Recibirán una página web de acceso denegado cuando intenten obtener acceso a cualquier dirección URL asociada con el sitio.</span><span class="sxs-lookup"><span data-stu-id="e865f-p103">Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>
    
<span data-ttu-id="e865f-p104">La ventaja de exigir un control de acceso centralizado y permisos personalizados por los administradores de SharePoint Online es que el sitio permanecerá aislado con el paso del tiempo. Por ejemplo, los miembros actuales no pueden, ya sea de forma intencionada o por error, invitar o configurar permisos personalizados para otros usuarios de la suscripción de Office 365 que no tendrían que ser miembros del sitio.</span><span class="sxs-lookup"><span data-stu-id="e865f-p104">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Office 365 subscription who should not be members of the site.</span></span>
  
<span data-ttu-id="e865f-122">Un sitio aislado se puede usar con otras características, como:</span><span class="sxs-lookup"><span data-stu-id="e865f-122">An isolated site can be used with other features, such as:</span></span>
  
- <span data-ttu-id="e865f-123">Information Rights Management, para garantizar que los recursos del sitio permanezcan cifrados, incluso si se descargan localmente y se cargan en otro sitio que esté disponible para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="e865f-123">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>
    
- <span data-ttu-id="e865f-124">Prevención de pérdida de datos para impedir que los usuarios envíen los recursos del sitio, como archivos, por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e865f-124">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="e865f-125">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e865f-125">Next steps</span></span>

<span data-ttu-id="e865f-126">Para probar un sitio de grupo de SharePoint Online aislado en una suscripción de prueba, vea las instrucciones paso a paso en [Entorno de desarrollo y pruebas en un sitio de grupo aislado de SharePoint Online](isolated-sharepoint-online-team-site-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e865f-126">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>
  
<span data-ttu-id="e865f-127">Cuando esté preparado para implementar un sitio de grupo de SharePoint Online aislado en producción, vea las consideraciones de diseño paso a paso en [Diseñar un sitio de grupo aislado de SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="e865f-127">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e865f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e865f-128">See Also</span></span>

[<span data-ttu-id="e865f-129">Diseñar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="e865f-129">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="e865f-130">Administrar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="e865f-130">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="e865f-131">Implementar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="e865f-131">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)


