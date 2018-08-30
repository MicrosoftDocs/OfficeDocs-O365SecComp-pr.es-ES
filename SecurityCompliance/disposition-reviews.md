---
title: Introducción a las revisiones de disposición
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d0c6095b-bfee-4906-a2c7-89c2d7f411c1
description: Cuando se crea una etiqueta que se conserva el contenido en Office 365, puede desencadenar una revisión de disposición al final del período de retención.
ms.openlocfilehash: c0a2933f597c9b314ac4ce2e72de9619fac90082
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013724"
---
# <a name="overview-of-disposition-reviews"></a><span data-ttu-id="99802-103">Introducción a las revisiones de disposición</span><span class="sxs-lookup"><span data-stu-id="99802-103">Overview of disposition reviews</span></span>

<span data-ttu-id="99802-p101">Cuando el contenido llega al final de su período de retención, existen varias razones por qué es posible que desee revisar dicho contenido para decidir si se puede eliminar sin ningún riesgo ("eliminado"). Por ejemplo, es posible que necesite:</span><span class="sxs-lookup"><span data-stu-id="99802-p101">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed"). For example, you might need to:</span></span>
  
- <span data-ttu-id="99802-106">Suspender la eliminación ("disposición") de contenido relevante en caso de litigio o una auditoría.</span><span class="sxs-lookup"><span data-stu-id="99802-106">Suspend the deletion ("disposition") of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="99802-107">Quitar el contenido de la lista de disposición para almacenar en un archivo, si dicho contenido tiene investigación o valor histórico.</span><span class="sxs-lookup"><span data-stu-id="99802-107">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="99802-108">Asignar un período de retención diferente para el contenido, si la directiva original era una solución temporal o provisional.</span><span class="sxs-lookup"><span data-stu-id="99802-108">Assign a different retention period to the content, if the original policy was a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="99802-109">Devolver el contenido a los clientes o transferir a otra organización.</span><span class="sxs-lookup"><span data-stu-id="99802-109">Return the content to clients or transfer it to another organization.</span></span>
    
<span data-ttu-id="99802-p102">Cuando se crea una etiqueta que se conserva el contenido en Office 365, puede desencadenar una revisión de disposición al final del período de retención. En una revisión de disposición:</span><span class="sxs-lookup"><span data-stu-id="99802-p102">When you create a label that retains content in Office 365, you can choose to trigger a disposition review at the end of the retention period. In a disposition review:</span></span>
  
- <span data-ttu-id="99802-p103">Las personas que elija reciben una notificación de correo electrónico que tienen contenido para revisar. Estos revisores pueden ser usuarios individuales, distribución o grupos de seguridad o grupos de Office 365. Tenga en cuenta que las notificaciones se envían de forma semanal.</span><span class="sxs-lookup"><span data-stu-id="99802-p103">The people you choose receive an email notification that they have content to review. These reviewers can be individual users, distribution or security groups, or Office 365 groups. Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="99802-115">Los revisores vaya a la página de **disposición** en la seguridad &amp; centro de cumplimiento para revisar el contenido.</span><span class="sxs-lookup"><span data-stu-id="99802-115">The reviewers go to the **Disposition** page in the Security &amp; Compliance Center to review the content.</span></span> 
    
- <span data-ttu-id="99802-116">Para cada documento, el revisor puede:</span><span class="sxs-lookup"><span data-stu-id="99802-116">For each document, the reviewer can:</span></span>
    
  - <span data-ttu-id="99802-117">Aplicar una etiqueta diferente.</span><span class="sxs-lookup"><span data-stu-id="99802-117">Apply a different label.</span></span>
    
  - <span data-ttu-id="99802-118">Ampliar su período de retención.</span><span class="sxs-lookup"><span data-stu-id="99802-118">Extend its retention period.</span></span>
    
  - <span data-ttu-id="99802-119">Eliminarlo de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="99802-119">Permanently delete it.</span></span>
    
- <span data-ttu-id="99802-120">Los revisores pueden ver disposiciones pendientes o históricas y exportar esa lista como un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="99802-120">Reviewers can view either pending or historical dispositions, and export that list as a .csv file.</span></span>
    
<span data-ttu-id="99802-121">Tenga en cuenta que disposición revisiones requieren una suscripción a Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="99802-121">Note that disposition reviews require an Office 365 Enterprise E5 subscription.</span></span>
  
<span data-ttu-id="99802-p104">Una revisión de disposición puede incluir contenido en los buzones de Exchange, los sitios de SharePoint, OneDrive cuentas y grupos de Office 365. En espera de una revisión de disposición en esas ubicaciones de contenido se elimina después de que un revisor elige eliminar permanentemente el contenido.</span><span class="sxs-lookup"><span data-stu-id="99802-p104">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Office 365 groups. Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>
  
![Página de disposición](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a><span data-ttu-id="99802-125">Configuración de la revisión de disposición mediante la creación de una etiqueta</span><span class="sxs-lookup"><span data-stu-id="99802-125">Setting up the disposition review by creating a label</span></span>

<span data-ttu-id="99802-p105">Este es el flujo de trabajo básico para la configuración de una revisión de disposición. Tenga en cuenta que este flujo de muestra una etiqueta que se va a publicar y, a continuación, se aplica manualmente por un usuario; como alternativa, una etiqueta que desencadena una revisión de disposición puede ser automático aplicada al contenido.</span><span class="sxs-lookup"><span data-stu-id="99802-p105">This is the basic workflow for setting up a disposition review. Note that this flow shows a label being published and then manually applied by a user; alternatively, a label that triggers a disposition review can be auto-applied to content.</span></span>
  
![Gráfico que muestra el flujo del funcionamiento de disposición](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="99802-p106">Una revisión de disposición es una opción cuando se crea una etiqueta en Office 365. Tenga en cuenta que esta opción no está disponible en una directiva de retención, pero solo en una etiqueta con la configuración de retención.</span><span class="sxs-lookup"><span data-stu-id="99802-p106">A disposition review is an option when you create a label in Office 365. Note that this option is not available in a retention policy but only in a label with retention settings.</span></span>
  
<span data-ttu-id="99802-131">Para obtener más información acerca de las etiquetas, vea [información general de las etiquetas](labels.md).</span><span class="sxs-lookup"><span data-stu-id="99802-131">For more information about labels, see [Overview of labels](labels.md).</span></span>
  
![Configuración de retención de una etiqueta](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a><span data-ttu-id="99802-133">Eliminación de contenido</span><span class="sxs-lookup"><span data-stu-id="99802-133">Disposing content</span></span>

<span data-ttu-id="99802-p107">Cuando un revisor recibe una notificación por correo electrónico que el contenido está listo para revisar, pueden ir a la página de **disposición** en la seguridad &amp; centro de cumplimiento y seleccionados uno o varios elementos. El revisor puede, a continuación:</span><span class="sxs-lookup"><span data-stu-id="99802-p107">When a reviewer is notified by email that content is ready to review, they can go to the **Disposition** page in the Security &amp; Compliance Center and select one or more items. The reviewer can then:</span></span> 
  
- <span data-ttu-id="99802-136">Aplicar una etiqueta diferente.</span><span class="sxs-lookup"><span data-stu-id="99802-136">Apply a different label.</span></span>
    
- <span data-ttu-id="99802-137">Ampliar el período de retención.</span><span class="sxs-lookup"><span data-stu-id="99802-137">Extend the retention period.</span></span>
    
- <span data-ttu-id="99802-138">Eliminar permanentemente el elemento.</span><span class="sxs-lookup"><span data-stu-id="99802-138">Permanently delete the item.</span></span>
    
<span data-ttu-id="99802-p108">Un revisor puede usar el vínculo para ver el documento en su ubicación original, si el revisor tiene permisos para esa ubicación. Durante una revisión de disposición, el contenido nunca se mueve desde su ubicación original y no se eliminen nunca hasta que el revisor elige hacerlo.</span><span class="sxs-lookup"><span data-stu-id="99802-p108">A reviewer can use the link to view the document in its original location, if the reviewer has permissions for that location. During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>
  
<span data-ttu-id="99802-p109">Tenga en cuenta que las notificaciones de correo electrónico se envían automáticamente a los revisores de forma semanal. Por lo tanto, cuando el contenido llega al final de su período de retención, puede tardar hasta siete días para los revisores reciben la notificación de correo electrónico que el contenido está esperando su disposición.</span><span class="sxs-lookup"><span data-stu-id="99802-p109">Note that the email notifications are sent automatically to reviewers on a weekly basis. Therefore, when content reaches the end of its retention period, it may take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="99802-p110">Tenga en cuenta también que todas las acciones de disposición se auditan. Para asegurarse de esto, debe activar la auditoría de al menos un día antes de la primera acción de disposición - para obtener más información, vea [Buscar en el registro de auditoría de la seguridad de Office 365 &amp; centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="99802-p110">Also note that all disposition actions are audited. To ensure this, you must turn on auditing at least one day prior to the first disposition action - for more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 
  
![Opciones de eliminación de un documento](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a><span data-ttu-id="99802-146">Permisos para la disposición</span><span class="sxs-lookup"><span data-stu-id="99802-146">Permissions for disposition</span></span>

<span data-ttu-id="99802-p111">Para obtener acceso a la página de **disposición** , los revisores deben ser miembros de la **Administración de la eliminación** y el rol de **Los registros de auditoría con permiso de vista** . Se recomienda crear un nuevo grupo de rol denominado revisores de disposición, adición de estas dos funciones a ese grupo de roles y, a continuación, agregar miembros al grupo de funciones.</span><span class="sxs-lookup"><span data-stu-id="99802-p111">To get access to the **Disposition** page, reviewers must be members of the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="99802-149">Para obtener más información, vea [dar a los usuarios acceso a la seguridad de Office 365 &amp; centro de cumplimiento](grant-access-to-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="99802-149">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md)</span></span>
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="99802-150">¿Cuánto tiempo hasta que el contenido eliminado se elimina de manera permanente</span><span class="sxs-lookup"><span data-stu-id="99802-150">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="99802-p112">En espera de una revisión de disposición de contenido se elimina después de que un revisor elige eliminar permanentemente el contenido. Cuando el revisor elige esta opción, el contenido en el sitio de SharePoint o la cuenta de OneDrive, pasa a ser candidato para el proceso de limpieza estándar que se describen en esta sección: [funcionamiento con contenido en lugar de una directiva de retención](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="99802-p112">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content. When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in this section: [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
<span data-ttu-id="99802-153">Esto significa:</span><span class="sxs-lookup"><span data-stu-id="99802-153">This means that:</span></span>
  
- <span data-ttu-id="99802-p113">El contenido en una biblioteca de documentos estará mueve a la primera etapa Papelera de reciclaje **dentro de 7 días** de disposición y, a continuación, elimina permanentemente **93 días** después de que. La Papelera de reciclaje no se indiza por la búsqueda y, por tanto, su contenido no está disponible para una exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="99802-p113">Content in a document library will be moved to the first-stage Recycle Bin **within 7 days** of disposition, and then permanently deleted **93 days** after that. The Recycle Bin is not indexed by search and therefore its contents are not available to an eDiscovery hold.</span></span> 
    
- <span data-ttu-id="99802-156">El contenido de la suspensión de conservación biblioteca quedará permanentemente eliminado **dentro de 7 días** de disposición.</span><span class="sxs-lookup"><span data-stu-id="99802-156">Content in the Preservation Hold library will be permanently deleted **within 7 days** of disposition.</span></span> 
    
## <a name="view-pending-and-completed-dispositions"></a><span data-ttu-id="99802-157">Ver pendientes y disposiciones completados</span><span class="sxs-lookup"><span data-stu-id="99802-157">View pending and completed dispositions</span></span>

<span data-ttu-id="99802-158">En la página de **eliminación** de la seguridad &amp; centro de cumplimiento, puede ver disposiciones pendientes y completadas:</span><span class="sxs-lookup"><span data-stu-id="99802-158">On the **Disposition** page of the Security &amp; Compliance Center, you can view both pending and completed dispositions:</span></span> 
  
- <span data-ttu-id="99802-p114">Disposiciones **pendiente** han alcanzado el final de su período de retención y requieren una revisión de disposición. Después de revisar cada elemento, decidir si desea aplicar una etiqueta diferente a ella, ampliar su período de retención o eliminarlo de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="99802-p114">**Pending** dispositions have reached the end of their retention period and require a disposition review. After reviewing each item, decide if you want to apply a different label to it, extend its retention period, or permanently delete it.</span></span> 
    
- <span data-ttu-id="99802-p115">Disposiciones **completado** se han aprobado para su eliminación durante una revisión de disposición y ahora están en el proceso que se va a eliminar de forma permanente. Elementos que han tenido una etiqueta diferente aplicado o su período de retención extendido como parte de una revisión no aparecerá aquí.</span><span class="sxs-lookup"><span data-stu-id="99802-p115">**Completed** dispositions were approved for deletion during a disposition review and are now in the process of being permanently deleted. Items that had a different label applied or their retention period extended as part of a review won't appear here.</span></span> 
    
### <a name="filter-the-disposition-views"></a><span data-ttu-id="99802-163">Filtrar las vistas de disposición</span><span class="sxs-lookup"><span data-stu-id="99802-163">Filter the disposition views</span></span>

<span data-ttu-id="99802-p116">Puede filtrar estas vistas por intervalo de tiempo o de etiqueta. Para pendientes disposiciones, el intervalo de tiempo se basa en la fecha de caducidad. Para disposiciones históricas, el intervalo de tiempo se basa en la fecha de eliminación.</span><span class="sxs-lookup"><span data-stu-id="99802-p116">You can filter these views by label or time range. For pending dispositions, the time range is based on the expiry date. For historical dispositions, the time range is based on the deletion date.</span></span>
  
![Opciones de filtro en la página de disposición](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a><span data-ttu-id="99802-168">Exportar los elementos de disposición</span><span class="sxs-lookup"><span data-stu-id="99802-168">Export the disposition items</span></span>

<span data-ttu-id="99802-169">Además, puede exportar los elementos en la vista como un archivo .csv que se puede abrir en Excel.</span><span class="sxs-lookup"><span data-stu-id="99802-169">In addition, you can export the items in either view as a .csv file that you can open in Excel.</span></span>
  
![Datos de disposición exportado en Excel](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

