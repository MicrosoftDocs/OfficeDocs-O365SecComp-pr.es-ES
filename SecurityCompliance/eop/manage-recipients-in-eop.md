---
title: Administrar destinatarios en EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
description: Microsoft Exchange Online Protection (EOP) ofrece varias maneras de administrar los destinatarios de correo. Como administrador, puede realizar ciertas tareas de administración en el Centro de administración de Exchange (EAC) o utilizar Windows PowerShell y comprobar otras tareas de administración realizadas en el Centro de administración de Microsoft Office 365.
ms.openlocfilehash: 55b28dcb107df85052ff623f653eecaaf88c7bda
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341661"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="61bd0-104">Administrar destinatarios en EOP</span><span class="sxs-lookup"><span data-stu-id="61bd0-104">Manage recipients in EOP</span></span>

<span data-ttu-id="61bd0-p102">Microsoft Exchange Online Protection (EOP) ofrece varias maneras de administrar los destinatarios de correo. Como administrador, puede realizar ciertas tareas de administración en el Centro de administración de Exchange (EAC) o utilizar Windows PowerShell y comprobar otras tareas de administración realizadas en el Centro de administración de Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="61bd0-p102">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients. As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft Office 365 admin center.</span></span>
  
<span data-ttu-id="61bd0-107">EOP admite los siguientes tipos de destinatarios:</span><span class="sxs-lookup"><span data-stu-id="61bd0-107">EOP supports the following types of recipients:</span></span>
  
- <span data-ttu-id="61bd0-p103">**Usuarios de correo** Los usuarios de correo son destinatarios en los dominios administrados de EOP. Estos destinatarios tienen credenciales de inicio de sesión en la organización de Office 365, pero tienen direcciones de correo electrónico externas, lo que significa que los buzones de los destinatarios están fuera de la organización de la nube. Puede Agregar usuarios de correo para que puedan recibir correo y también puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para usuarios específicos. También puede asignar roles a los usuarios de correo de su organización; los usuarios con privilegios de grupo de roles de administración pueden obtener acceso al centro de administración de Exchange (EAC) y realizar ciertas tareas de administración. Para obtener más información sobre los roles de usuario y cómo asignar los roles de usuario en EOP, consulte [Manage admin role Group Permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="61bd0-p103">**Mail Users** Mail users are recipients in your EOP managed domains. These recipients have logon credentials in your Office 365 organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization. You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users. You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks. To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>
    
    <span data-ttu-id="61bd0-113">Para obtener más información sobre la administración de usuarios de correo en EOP, consulte [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="61bd0-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>
    
- <span data-ttu-id="61bd0-114">**Grupos** Los usuarios de correo se pueden agrupar en grupos de distribución o grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="61bd0-114">**Groups** Mail users can be grouped together into distribution groups or security groups.</span></span> 
    
    <span data-ttu-id="61bd0-115">Para obtener más información acerca de la administración de grupos en EOP, consulte [Administrar grupos en EOP](manage-groups-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="61bd0-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
    
<span data-ttu-id="61bd0-p104">¿Busca la versión de Exchange Online de este tema? Vea [Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx).</span><span class="sxs-lookup"><span data-stu-id="61bd0-p104">Looking for the Exchange Online version of this topic? See [Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx).</span></span>
  
<span data-ttu-id="61bd0-p105">¿Busca la versión de Exchange Server de este tema? Vea [Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx).</span><span class="sxs-lookup"><span data-stu-id="61bd0-p105">Looking for the Exchange Server version of this topic? See [Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx).</span></span>
  

