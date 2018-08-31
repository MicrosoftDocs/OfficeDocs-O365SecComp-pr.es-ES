---
title: Aplicar o quitar una directiva de eliminación de documentos de un sitio
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: Las organizaciones suelen estar sujetas a normas de cumplimiento, leyes u otras regulaciones que las obligan a conservar sus documentos durante un período de tiempo. Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal. Por esta razón, su organización puede haber creado una directiva de eliminación de documentos para el sitio como, por ejemplo, en el caso de que los documentos empresariales de carácter general deban eliminarse cinco años después de su creación.
ms.openlocfilehash: abee0da7adfba6f653743d503f8b30770ee93c40
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536607"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="28c63-105">Aplicar o quitar una directiva de eliminación de documentos de un sitio</span><span class="sxs-lookup"><span data-stu-id="28c63-105">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="28c63-p102">Las organizaciones suelen estar sujetas a normas de cumplimiento, leyes u otras regulaciones que las obligan a conservar sus documentos durante un período de tiempo. Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal. Por esta razón, su organización puede haber creado una directiva de eliminación de documentos para el sitio como, por ejemplo, en el caso de que los documentos empresariales de carácter general deban eliminarse cinco años después de su creación.</span><span class="sxs-lookup"><span data-stu-id="28c63-p102">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time. However, retaining documents for longer than required can expose the organization to legal risk. For this reason, your organization may have created a document deletion policy for your site — for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="28c63-109">Dependiendo de la organización, una directiva de eliminación de documentos puede ser:</span><span class="sxs-lookup"><span data-stu-id="28c63-109">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="28c63-110">**Obligatorio** Propietario de un sitio no puede anular una directiva obligatoria, que se aplica automáticamente al sitio.</span><span class="sxs-lookup"><span data-stu-id="28c63-110">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="28c63-111">**Predeterminada** Una directiva predeterminada se aplica automáticamente a un sitio, pero el propietario de dicho sitio puede:</span><span class="sxs-lookup"><span data-stu-id="28c63-111">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="28c63-112">Elegir otra directiva, si la hay.</span><span class="sxs-lookup"><span data-stu-id="28c63-112">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="28c63-113">Anular la directiva si no está relacionada con el contenido del sitio.</span><span class="sxs-lookup"><span data-stu-id="28c63-113">Opt out of the policy entirely if it is not relevant to the content in the site.</span></span>
    
- <span data-ttu-id="28c63-114">**Ni obligatoria ni predeterminada** En este caso, no se aplica ninguna directiva al sitio automáticamente, y el propietario debe aplicarla de forma manual.</span><span class="sxs-lookup"><span data-stu-id="28c63-114">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="28c63-p103">Una directiva de eliminación de documentos puede contener más de una regla; por ejemplo, una regla puede especificar que los documentos se deberán eliminar un año después de la creación y otra que la eliminación de documentos deberá tener lugar un año después de la última modificación. Si una directiva contiene más de una regla, puede seleccionar la que se ajuste mejor al sitio. La regla de eliminación se aplicará a todas las bibliotecas del sitio. Solo puede haber una directiva y una regla activas en un sitio al mismo tiempo. Al igual que ocurre con las directivas, es posible establecer una regla como predeterminada para que se aplique automáticamente al aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="28c63-p103">A document deletion policy may contain more than one rule — for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified. If a policy contains more than one rule, you can select the rule that best applies to your site. The delete rule will be applied to all libraries within the site. Only one policy and one rule can be active in a site at one time. Like a policy, a rule can be set as default, so that it is applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="28c63-p104">Por último, las directivas de eliminación de documentos son heredadas. Cuando se selecciona una directiva o regla para un sitio, todos los subsitios heredan esa selección, a menos que el propietario de un subsitio interrumpa la herencia seleccionando una directiva o regla distinta. Cuando seleccione una directiva o regla, tenga en cuenta el contenido de los subsitios del sitio.</span><span class="sxs-lookup"><span data-stu-id="28c63-p104">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="28c63-123">Ver las directivas de eliminación de documentos disponibles en una colección de sitios</span><span class="sxs-lookup"><span data-stu-id="28c63-123">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="28c63-p105">Su organización puede asignar distintas directivas a colecciones de sitios diferentes. En el nivel de colección de sitios, el propietario de una colección de sitios puede ver todas las directivas de eliminación de documentos disponibles para esa colección concreta. Las directivas pueden estar disponibles para la plantilla de la colección de sitios (y, por tanto, para todas las colecciones de sitios creadas a partir de esta plantilla) o para esta colección de sitios específica.</span><span class="sxs-lookup"><span data-stu-id="28c63-p105">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="28c63-127">En el sitio de nivel superior en la colección de sitios, en la esquina superior derecha, elija **configuración** [icono de engranaje] \> **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="28c63-127">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="28c63-128">En **administración de colección de sitios** \> **directivas de eliminación de documentos**.</span><span class="sxs-lookup"><span data-stu-id="28c63-128">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="28c63-p106">El vínculo de **Las directivas de eliminación de documentos** no aparecerá a menos que las directivas se han asignado a la colección de sitios. Además, el vínculo no aparece inmediatamente después de que las directivas se han asignado al sitio, puede demorar hasta 24 horas desde cuando las directivas se asignan a cuando aparece el vínculo de **Las directivas de eliminación de documentos** .</span><span class="sxs-lookup"><span data-stu-id="28c63-p106">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection. Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="28c63-131">En esta página, puede ver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="28c63-131">On this page you can view:</span></span>
    
  - <span data-ttu-id="28c63-p107">Las directivas asignadas actualmente y las reglas asociadas. Seleccione una directiva para ver las reglas en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="28c63-p107">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="28c63-134">Si existe una directiva predeterminada, se muestra **Sí** en la columna **Predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="28c63-134">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="28c63-135">Si la directiva se ha asignado como **Obligatoria**, se muestra un mensaje debajo de la lista.</span><span class="sxs-lookup"><span data-stu-id="28c63-135">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="28c63-p108">Esta lista es solo para consulta, para que el propietario de la colección de sitios pueda ver todas las directivas y reglas disponibles. Para aplicar una directiva, consulte la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="28c63-p108">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![Ver las directivas de eliminación de documentos asignadas a una colección de sitios](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="28c63-139">Aplicar o quitar una directiva de eliminación de documentos de un sitio</span><span class="sxs-lookup"><span data-stu-id="28c63-139">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="28c63-140">Como propietario del sitio o propietario de la colección de sitios, su organización puede haber creado directivas que puede aplicar al sitio o anular por completo.</span><span class="sxs-lookup"><span data-stu-id="28c63-140">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="28c63-141">En la esquina superior derecha, elija **configuración** [icono de engranaje] \> **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="28c63-141">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="28c63-142">En **administración de sitios** \> **directivas de eliminación de documentos**.</span><span class="sxs-lookup"><span data-stu-id="28c63-142">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="28c63-p109">El vínculo de **Las directivas de eliminación de documentos** no aparecerá a menos que las directivas se han asignado a la colección de sitios. Además, el vínculo no aparece inmediatamente después de que las directivas se han asignado al sitio, puede demorar hasta 24 horas desde cuando las directivas se asignan a cuando aparece el vínculo de **Las directivas de eliminación de documentos** .</span><span class="sxs-lookup"><span data-stu-id="28c63-p109">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection. Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="28c63-145">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="28c63-145">Do one of the following:</span></span>
    
  - <span data-ttu-id="28c63-146">**Para aplicar una directiva** Seleccione una directiva de \> seleccione una regla en esa directiva \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="28c63-146">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="28c63-p110">Solo puede haber una directiva y una regla activas en un sitio al mismo tiempo. Su organización puede proporcionar varias directivas y reglas para elegir o solo una directiva o regla.</span><span class="sxs-lookup"><span data-stu-id="28c63-p110">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![Seleccione la opción de directiva](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="28c63-150">**Para anular una directiva** Elija **voluntaria: tenga en cuenta eliminar** \> **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="28c63-150">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="28c63-p111">Como propietario de un sitio, puede anular una directiva de eliminación de documentos si considera que la directiva no puede aplicarse al contenido del sitio. Sin embargo, no puede anular una directiva marcada como **Obligatoria**.</span><span class="sxs-lookup"><span data-stu-id="28c63-p111">As a site owner, you can opt out of a document deletion policy if you determine that the policy is not applicable to the content in your site. However, you cannot opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![Opción alta de salida](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="28c63-154">Las directivas de eliminación de documentos invalidan otras directivas</span><span class="sxs-lookup"><span data-stu-id="28c63-154">Document deletion policies override other policies</span></span>

<span data-ttu-id="28c63-155">Un sitio puede usar otras directivas para la retención y eliminación de contenido:</span><span class="sxs-lookup"><span data-stu-id="28c63-155">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="28c63-156">Directivas de tipo de contenido para la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="28c63-156">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="28c63-157">Directivas de administración de la información para una lista o biblioteca.</span><span class="sxs-lookup"><span data-stu-id="28c63-157">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="28c63-p112">Si se aplica una directiva de eliminación de documentos a un sitio que ya usa las directivas de tipo de contenido o las directivas de administración de información para una lista o biblioteca, dichas directivas se omiten mientras la directiva de eliminación de documentos se encuentra en vigor. Si se omiten las otras directivas, verá el mensaje "El contenido de este sitio usa las directivas de eliminación de documentos".</span><span class="sxs-lookup"><span data-stu-id="28c63-p112">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect. If other policies are ignored, you will see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="28c63-p113">Esto quiere decir que debe configurar un sitio de forma que solo utilice directivas creadas para contenido estructurado (directivas de administración de información y directivas de tipo de contenido) o contenido no estructurado (directivas de eliminación de documentos), pero no ambos. Si anula una directiva de eliminación de documentos, no se mostrará la advertencia y los demás tipos de directivas seguirán funcionando con normalidad.</span><span class="sxs-lookup"><span data-stu-id="28c63-p113">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both. If you opt out of a document deletion policy, the warning will not be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="28c63-162">Las directivas del sitio no se verán afectadas por las directivas de eliminación de documentos.</span><span class="sxs-lookup"><span data-stu-id="28c63-162">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="28c63-163">Determinar si se están ignorando las directivas de tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="28c63-163">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="28c63-p114">Si el sitio estaba en uso las directivas de tipo de contenido y ver ahora este mensaje, esas directivas ya no están en vigor. Para restaurar las directivas de tipo de contenido, puede quitar la directiva de eliminación de documentos de su sitio, tal y como se ha descrito anteriormente, si hay una opción de anular. Si no hay ninguna opción para excluir, la directiva de eliminación de documentos es obligatoria y debe ponerse en contacto con el responsable de cumplimiento de normas en su organización.</span><span class="sxs-lookup"><span data-stu-id="28c63-p114">If your site was using content type policies and you now see this message, those policies are no longer in effect. To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available. If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="28c63-167">En la esquina superior derecha, elija **configuración** [icono de engranaje] \> **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="28c63-167">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="28c63-168">En **administración de sitios** \> **plantillas de directiva de tipo de contenido**.</span><span class="sxs-lookup"><span data-stu-id="28c63-168">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![Advertencia en el sitio que se usan las directivas de eliminación de documentos](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="28c63-170">Determinar si se están ignorando las directivas de administración de información</span><span class="sxs-lookup"><span data-stu-id="28c63-170">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="28c63-p115">Si el sitio estaba en uso las directivas de administración de información y ahora verá este mensaje, esas directivas ya no están en vigor. Para restaurar las directivas de administración de información, puede quitar la directiva de eliminación de documentos de su sitio, tal y como se ha descrito anteriormente, si hay una opción de anular. Si no hay ninguna opción para excluir, la directiva de eliminación de documentos es obligatoria y debe ponerse en contacto con el responsable de cumplimiento de normas en su organización.</span><span class="sxs-lookup"><span data-stu-id="28c63-p115">If your site was using information management policies and you now see this message, those policies are no longer in effect. To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available. If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="28c63-174">Para una lista o biblioteca, en la cinta de opciones \> ficha **biblioteca** \> **Configuración de la biblioteca** \> en **permisos y administración** \> **Configuración de directiva de administración de información**.</span><span class="sxs-lookup"><span data-stu-id="28c63-174">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![Advertencia en el sitio que se usan las directivas de eliminación de documentos](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="28c63-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="28c63-176">See also</span></span>

[<span data-ttu-id="28c63-177">Información general sobre las directivas de eliminación de documentos</span><span class="sxs-lookup"><span data-stu-id="28c63-177">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="28c63-178">Crear una directiva de eliminación de documentos</span><span class="sxs-lookup"><span data-stu-id="28c63-178">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

