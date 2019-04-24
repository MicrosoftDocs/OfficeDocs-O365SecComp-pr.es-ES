---
title: Aplicar o quitar una directiva de eliminación de documentos de un sitio
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: Las organizaciones suelen estar sujetas a normas de cumplimiento, leyes u otras regulaciones que las obligan a conservar sus documentos durante un período de tiempo. Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal. Por esta razón, su organización puede haber creado una directiva de eliminación de documentos para el sitio como, por ejemplo, en el caso de que los documentos empresariales de carácter general deban eliminarse cinco años después de su creación.
ms.openlocfilehash: c00298a177ac405181ab2b2d9642b631e60a8a92
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243311"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="78efd-105">Aplicar o quitar una directiva de eliminación de documentos de un sitio</span><span class="sxs-lookup"><span data-stu-id="78efd-105">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="78efd-p102">Las organizaciones suelen estar sujetas a normas de cumplimiento, leyes u otras regulaciones que las obligan a conservar sus documentos durante un período de tiempo. Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal. Por esta razón, su organización puede haber creado una directiva de eliminación de documentos para el sitio como, por ejemplo, en el caso de que los documentos empresariales de carácter general deban eliminarse cinco años después de su creación.</span><span class="sxs-lookup"><span data-stu-id="78efd-p102">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time. However, retaining documents for longer than required can expose the organization to legal risk. For this reason, your organization may have created a document deletion policy for your site — for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="78efd-109">Dependiendo de la organización, una directiva de eliminación de documentos puede ser:</span><span class="sxs-lookup"><span data-stu-id="78efd-109">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="78efd-110">**Obligatorio** El propietario de un sitio no puede optar por una directiva obligatoria, que se aplica automáticamente al sitio.</span><span class="sxs-lookup"><span data-stu-id="78efd-110">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="78efd-111">**Predeterminada** Una directiva predeterminada se aplica automáticamente a un sitio, pero el propietario de dicho sitio puede:</span><span class="sxs-lookup"><span data-stu-id="78efd-111">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="78efd-112">Elegir otra directiva, si la hay.</span><span class="sxs-lookup"><span data-stu-id="78efd-112">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="78efd-113">Anular la directiva si no está relacionada con el contenido del sitio.</span><span class="sxs-lookup"><span data-stu-id="78efd-113">Opt out of the policy entirely if it is not relevant to the content in the site.</span></span>
    
- <span data-ttu-id="78efd-114">**Ni obligatoria ni predeterminada** En este caso, no se aplica ninguna directiva al sitio automáticamente, y el propietario debe aplicarla de forma manual.</span><span class="sxs-lookup"><span data-stu-id="78efd-114">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="78efd-p103">Una directiva de eliminación de documentos puede contener más de una regla; por ejemplo, una regla puede especificar que los documentos se deberán eliminar un año después de la creación y otra que la eliminación de documentos deberá tener lugar un año después de la última modificación. Si una directiva contiene más de una regla, puede seleccionar la que se ajuste mejor al sitio. La regla de eliminación se aplicará a todas las bibliotecas del sitio. Solo puede haber una directiva y una regla activas en un sitio al mismo tiempo. Al igual que ocurre con las directivas, es posible establecer una regla como predeterminada para que se aplique automáticamente al aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="78efd-p103">A document deletion policy may contain more than one rule — for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified. If a policy contains more than one rule, you can select the rule that best applies to your site. The delete rule will be applied to all libraries within the site. Only one policy and one rule can be active in a site at one time. Like a policy, a rule can be set as default, so that it is applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="78efd-p104">Por último, las directivas de eliminación de documentos son heredadas. Cuando se selecciona una directiva o regla para un sitio, todos los subsitios heredan esa selección, a menos que el propietario de un subsitio interrumpa la herencia seleccionando una directiva o regla distinta. Cuando seleccione una directiva o regla, tenga en cuenta el contenido de los subsitios del sitio.</span><span class="sxs-lookup"><span data-stu-id="78efd-p104">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="78efd-123">Ver las directivas de eliminación de documentos disponibles en una colección de sitios</span><span class="sxs-lookup"><span data-stu-id="78efd-123">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="78efd-p105">Su organización puede asignar distintas directivas a colecciones de sitios diferentes. En el nivel de colección de sitios, el propietario de una colección de sitios puede ver todas las directivas de eliminación de documentos disponibles para esa colección concreta. Las directivas pueden estar disponibles para la plantilla de la colección de sitios (y, por tanto, para todas las colecciones de sitios creadas a partir de esta plantilla) o para esta colección de sitios específica.</span><span class="sxs-lookup"><span data-stu-id="78efd-p105">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="78efd-127">En el sitio de nivel superior de la colección de sitios, en la esquina superior derecha, elija **configuración** del \> **sitio**[icono de engranaje].</span><span class="sxs-lookup"><span data-stu-id="78efd-127">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="78efd-128">En **directivas de eliminación de documentos**de administración \> de la colección de **sitios** .</span><span class="sxs-lookup"><span data-stu-id="78efd-128">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78efd-129">El vínculo **directivas de eliminación de documentos** no aparecerá a menos que se hayan asignado directivas a la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="78efd-129">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="78efd-130">Además, el vínculo no aparece inmediatamente después de que las directivas se hayan asignado al sitio: puede tardar hasta 24 horas desde el momento en que se asignan las directivas cuando aparece el vínculo **directivas de eliminación de documentos** .</span><span class="sxs-lookup"><span data-stu-id="78efd-130">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="78efd-131">En esta página, puede ver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="78efd-131">On this page you can view:</span></span>
    
  - <span data-ttu-id="78efd-p107">Las directivas asignadas actualmente y las reglas asociadas. Seleccione una directiva para ver las reglas en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="78efd-p107">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="78efd-134">Si existe una directiva predeterminada, se muestra **Sí** en la columna **Predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="78efd-134">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="78efd-135">Si la directiva se ha asignado como **Obligatoria**, se muestra un mensaje debajo de la lista.</span><span class="sxs-lookup"><span data-stu-id="78efd-135">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="78efd-p108">Esta lista es solo para consulta, para que el propietario de la colección de sitios pueda ver todas las directivas y reglas disponibles. Para aplicar una directiva, consulte la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="78efd-p108">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![Ver las directivas de eliminación de documentos asignadas a una colección de sitios](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="78efd-139">Aplicar o quitar una directiva de eliminación de documentos de un sitio</span><span class="sxs-lookup"><span data-stu-id="78efd-139">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="78efd-140">Como propietario del sitio o propietario de la colección de sitios, su organización puede haber creado directivas que puede aplicar al sitio o anular por completo.</span><span class="sxs-lookup"><span data-stu-id="78efd-140">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="78efd-141">En la esquina superior derecha, elija **configuración** del \> **sitio**[icono de engranaje].</span><span class="sxs-lookup"><span data-stu-id="78efd-141">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="78efd-142">En **directivas de eliminación de documentos**de administración \> del **sitio** .</span><span class="sxs-lookup"><span data-stu-id="78efd-142">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78efd-143">El vínculo **directivas de eliminación de documentos** no aparecerá a menos que se hayan asignado directivas a la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="78efd-143">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="78efd-144">Además, el vínculo no aparece inmediatamente después de que las directivas se hayan asignado al sitio: puede tardar hasta 24 horas desde el momento en que se asignan las directivas cuando aparece el vínculo **directivas de eliminación de documentos** .</span><span class="sxs-lookup"><span data-stu-id="78efd-144">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="78efd-145">Siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="78efd-145">Do one of the following:</span></span>
    
  - <span data-ttu-id="78efd-146">**Para aplicar una directiva** Seleccione una directiva \> Seleccione una regla en esa directiva \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="78efd-146">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="78efd-p110">Solo puede haber una directiva y una regla activas en un sitio al mismo tiempo. Su organización puede proporcionar varias directivas y reglas para elegir o solo una directiva o regla.</span><span class="sxs-lookup"><span data-stu-id="78efd-p110">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![Selección de la opción de Directiva](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="78efd-150">**Para dejar de participar en una directiva** Elija **no participar: Nota eliminar** \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="78efd-150">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="78efd-p111">Como propietario de un sitio, puede anular una directiva de eliminación de documentos si considera que la directiva no puede aplicarse al contenido del sitio. Sin embargo, no puede anular una directiva marcada como **Obligatoria**.</span><span class="sxs-lookup"><span data-stu-id="78efd-p111">As a site owner, you can opt out of a document deletion policy if you determine that the policy is not applicable to the content in your site. However, you cannot opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![Opción de cancelación](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="78efd-154">Las directivas de eliminación de documentos invalidan otras directivas</span><span class="sxs-lookup"><span data-stu-id="78efd-154">Document deletion policies override other policies</span></span>

<span data-ttu-id="78efd-155">Un sitio puede usar otras directivas para la retención y eliminación de contenido:</span><span class="sxs-lookup"><span data-stu-id="78efd-155">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="78efd-156">Directivas de tipo de contenido para la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="78efd-156">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="78efd-157">Directivas de administración de la información para una lista o biblioteca.</span><span class="sxs-lookup"><span data-stu-id="78efd-157">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="78efd-158">Si aplica una directiva de eliminación de documentos a un sitio que ya usa directivas de tipo de contenido o directivas de administración de información para una lista o biblioteca, dichas directivas se ignorarán mientras la directiva de eliminación de documentos esté activa.</span><span class="sxs-lookup"><span data-stu-id="78efd-158">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="78efd-159">Si se omiten otras directivas, verá el mensaje "el contenido de este sitio usa directivas de eliminación de documentos".</span><span class="sxs-lookup"><span data-stu-id="78efd-159">If other policies are ignored, you will see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="78efd-p113">Esto quiere decir que debe configurar un sitio de forma que solo utilice directivas creadas para contenido estructurado (directivas de administración de información y directivas de tipo de contenido) o contenido no estructurado (directivas de eliminación de documentos), pero no ambos. Si anula una directiva de eliminación de documentos, no se mostrará la advertencia y los demás tipos de directivas seguirán funcionando con normalidad.</span><span class="sxs-lookup"><span data-stu-id="78efd-p113">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both. If you opt out of a document deletion policy, the warning will not be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="78efd-162">Las directivas del sitio no se verán afectadas por las directivas de eliminación de documentos.</span><span class="sxs-lookup"><span data-stu-id="78efd-162">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="78efd-163">Determinar si se están ignorando las directivas de tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="78efd-163">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="78efd-164">Si el sitio estaba usando directivas de tipo de contenido y ahora ve este mensaje, esas directivas ya no se aplicarán.</span><span class="sxs-lookup"><span data-stu-id="78efd-164">If your site was using content type policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="78efd-165">Para restaurar las directivas de tipo de contenido, puede quitar la Directiva de eliminación de documentos del sitio, tal como se ha descrito anteriormente, si hay una opción de cancelación disponible.</span><span class="sxs-lookup"><span data-stu-id="78efd-165">To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="78efd-166">Si no existe la opción de no participar, la Directiva de eliminación de documentos es obligatoria y deberá ponerse en contacto con el responsable de cumplimiento de su organización.</span><span class="sxs-lookup"><span data-stu-id="78efd-166">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="78efd-167">En la esquina superior derecha, elija **configuración** del \> **sitio**[icono de engranaje].</span><span class="sxs-lookup"><span data-stu-id="78efd-167">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="78efd-168">En **plantillas de directiva de tipo de contenido**de administración \> de **sitio** .</span><span class="sxs-lookup"><span data-stu-id="78efd-168">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![ADVERTENCIA en el sitio de que se están usando directivas de eliminación de documentos](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="78efd-170">Determinar si se están ignorando las directivas de administración de información</span><span class="sxs-lookup"><span data-stu-id="78efd-170">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="78efd-171">Si el sitio estaba usando directivas de administración de la información y ahora ve este mensaje, esas directivas ya no se aplicarán.</span><span class="sxs-lookup"><span data-stu-id="78efd-171">If your site was using information management policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="78efd-172">Para restaurar las directivas de administración de la información, puede quitar la Directiva de eliminación de documentos del sitio, como se ha descrito anteriormente, si hay una opción de cancelación disponible.</span><span class="sxs-lookup"><span data-stu-id="78efd-172">To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="78efd-173">Si no existe la opción de no participar, la Directiva de eliminación de documentos es obligatoria y deberá ponerse en contacto con el responsable de cumplimiento de su organización.</span><span class="sxs-lookup"><span data-stu-id="78efd-173">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="78efd-174">Para una lista o biblioteca, en la biblioteca \> de la \> ficha **biblioteca** de la cinta de **Opciones Configuración** \> de la **Directiva** **permisos y** \> administración de información de administración.</span><span class="sxs-lookup"><span data-stu-id="78efd-174">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![ADVERTENCIA en el sitio de que se están usando directivas de eliminación de documentos](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="78efd-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="78efd-176">See also</span></span>

<span data-ttu-id="78efd-177">
  [Overview of document deletion policies](document-deletion-policies.md) (Información general sobre las directivas de eliminación de documentos)</span><span class="sxs-lookup"><span data-stu-id="78efd-177">[Overview of document deletion policies](document-deletion-policies.md)</span></span>
  
[<span data-ttu-id="78efd-178">Crear una directiva de eliminación de documentos</span><span class="sxs-lookup"><span data-stu-id="78efd-178">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

