---
title: Administrar destinatarios en EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
description: Microsoft Exchange Online Protection (EOP) ofrece varias maneras de administrar los destinatarios de correo. Como administrador, puede realizar ciertas tareas de administración dentro del centro de administración de Exchange (EAC) o mediante Windows PowerShell remoto y comprobar otras tareas de administración realizadas en el centro de administración de Microsoft 365.
ms.openlocfilehash: 1d9436cf02538ab5c69e0e68d20eda1af5b0a5cd
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2019
ms.locfileid: "30691689"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="9417d-104">Administrar destinatarios en EOP</span><span class="sxs-lookup"><span data-stu-id="9417d-104">Manage recipients in EOP</span></span>

<span data-ttu-id="9417d-105">Microsoft Exchange Online Protection (EOP) ofrece varias maneras de administrar los destinatarios de correo.</span><span class="sxs-lookup"><span data-stu-id="9417d-105">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients.</span></span> <span data-ttu-id="9417d-106">Como administrador, puede realizar ciertas tareas de administración dentro del centro de administración de Exchange (EAC) o mediante Windows PowerShell remoto y comprobar otras tareas de administración realizadas en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9417d-106">As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="9417d-107">EOP admite los siguientes tipos de destinatarios:</span><span class="sxs-lookup"><span data-stu-id="9417d-107">EOP supports the following types of recipients:</span></span>
  
- <span data-ttu-id="9417d-108">**Usuarios de correo** Los usuarios de correo son los destinatarios que hay en sus dominios administrados de EOP.</span><span class="sxs-lookup"><span data-stu-id="9417d-108">**Mail Users** Mail users are recipients in your EOP managed domains.</span></span> <span data-ttu-id="9417d-109">Estos destinatarios disponen de las credenciales de inicio de sesión de su organización Office 365 pero tienen direcciones de correo electrónico externas, lo que significa que los buzones de los destinatarios están ubicados fuera de su organización basada en la nube.</span><span class="sxs-lookup"><span data-stu-id="9417d-109">These recipients have logon credentials in your Office 365 organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization.</span></span> <span data-ttu-id="9417d-110">Puede Agregar usuarios de correo para que puedan recibir correo y también puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="9417d-110">You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users.</span></span> <span data-ttu-id="9417d-111">Además puede asignar roles a los usuarios de correo de su organización; los usuarios con privilegios de grupo de funciones de administración pueden acceder al Centro de administración de Exchange (EAC) y realizar determinadas tareas de administración.</span><span class="sxs-lookup"><span data-stu-id="9417d-111">You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks.</span></span> <span data-ttu-id="9417d-112">Para obtener más información sobre los roles de usuario y cómo asignar los roles de usuario en EOP, consulte [Manage admin role Group Permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="9417d-112">To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>
    
    <span data-ttu-id="9417d-113">Para obtener más información sobre la administración de usuarios de correo en EOP, consulte [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="9417d-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>
    
- <span data-ttu-id="9417d-114">**Grupos** Los usuarios de correo se pueden agrupar en grupos de distribución o grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9417d-114">**Groups** Mail users can be grouped together into distribution groups or security groups.</span></span> 
    
    <span data-ttu-id="9417d-115">Para obtener más información acerca de la administración de grupos en EOP, consulte [Administrar grupos en EOP](manage-groups-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="9417d-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
    
<span data-ttu-id="9417d-p104">¿Busca la versión de Exchange Online de este tema? Vea [Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx).</span><span class="sxs-lookup"><span data-stu-id="9417d-p104">Looking for the Exchange Online version of this topic? See [Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx).</span></span>
  
<span data-ttu-id="9417d-p105">¿Busca la versión de Exchange Server de este tema? Vea [Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx).</span><span class="sxs-lookup"><span data-stu-id="9417d-p105">Looking for the Exchange Server version of this topic? See [Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx).</span></span>
  

