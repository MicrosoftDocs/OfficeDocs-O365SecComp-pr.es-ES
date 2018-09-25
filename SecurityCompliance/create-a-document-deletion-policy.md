---
title: Crear una directiva de eliminación de documentos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 41b2ed73-eb8d-4429-945e-a8197894585a
description: Las organizaciones suelen necesitar conservar algunos documentos durante cierto período de tiempo para satisfacer el cumplimiento de ciertas normas legales u otras regulaciones. Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal.
ms.openlocfilehash: 6bf4c0604708608ad7af064f4b32b57d33208a39
ms.sourcegitcommit: ede6230c2df398dc0a633e8f32ee0bfede0d5142
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25002663"
---
# <a name="create-a-document-deletion-policy"></a><span data-ttu-id="4b47b-104">Crear una directiva de eliminación de documentos</span><span class="sxs-lookup"><span data-stu-id="4b47b-104">Create a document deletion policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b47b-p102">Más adelante, se recomienda usar una directiva de retención o etiquetas creadas en la seguridad &amp; centro de cumplimiento en lugar de una directiva de eliminación de documentos. Las directivas de eliminación de documentos seguirán funcionando codo con codo con las directivas de retención, pero si desea conservar o eliminar contenido en cualquier lugar en Office 365, se recomienda que use una directiva de retención. Para obtener más información, vea [utilizar una directiva de retención en lugar de estas características](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span><span class="sxs-lookup"><span data-stu-id="4b47b-p102">Moving forward, we recommend that you use a retention policy or labels created in the Security &amp; Compliance Center instead of a document deletion policy. Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy. For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span> 
  
<span data-ttu-id="4b47b-p103">Las organizaciones suelen necesitar conservar algunos documentos durante cierto período de tiempo para satisfacer el cumplimiento de ciertas normas legales u otras regulaciones. Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p103">Organizations are often required to retain documents for a certain period of time due to compliance, legal, or other regulations. However, retaining documents for longer than required can expose the organization to legal risk.</span></span>
  
<span data-ttu-id="4b47b-110">Con una directiva de eliminación de documentos, puede reducir proactivamente riesgo mediante la eliminación de documentos en un sitio después de un período de tiempo específico, por ejemplo, puede eliminar documentos de OneDrive de los usuarios para profesionales de sitios de cinco años después de que se crearon los documentos.</span><span class="sxs-lookup"><span data-stu-id="4b47b-110">With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span> 
  
<span data-ttu-id="4b47b-p104">Después de crear una directiva de eliminación de documentos, puede asignarla a una plantilla de colección de sitios, de forma que la directiva estará disponible para todas las colecciones de sitios creadas a partir de esa plantilla. También puede asignar una directiva a una colección de sitios determinada, lo que reemplaza a cualquier otra directiva que se haya asignado a la plantilla para esa colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p104">After you create a document deletion policy, you can assign it to a site collection template, so that the policy is available to all site collections created from that template. You can also assign a policy to a specific a site collection, which overrides any policies that may have been assigned to the template for that site collection.</span></span>
  
![Página de inicio de Centro de directivas de eliminación de documentos](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="policy-templates"></a><span data-ttu-id="4b47b-114">Plantillas de directiva</span><span class="sxs-lookup"><span data-stu-id="4b47b-114">Policy templates</span></span>

<span data-ttu-id="4b47b-p105">Puede crear una directiva de eliminación de documentos desde cero o puede usar una de las directivas de ejemplo. El Centro de directivas de cumplimiento de normas incluye directivas de ejemplo que puede usar tal cual, o bien puede usarlas como punto de partida y después cambiarles el nombre o modificarlas.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p105">You can create a document deletion policy from scratch, or you can use one of the sample policies. The Compliance Policy Center includes sample policies that you can use as is, or you can use them as a starting point and then rename or modify them.</span></span>
  
![Directivas de eliminación de documentos de muestra](media/IP-Sample-deletion-policies.png)
  
## <a name="examples-of-how-to-use-document-deletion-policies"></a><span data-ttu-id="4b47b-118">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4b47b-118">Examples of how to use document deletion policies</span></span>

<span data-ttu-id="4b47b-p106">Una colección de sitios o una plantilla de la colección de sitios puede tener uno más directivas de asignado a él, y cada una de dichas directivas puede tener una o varias reglas. Sin embargo, puede haber sólo una directiva que está activa por sitio, y puede haber sólo una regla de eliminación que está activa en cualquier momento para las bibliotecas dentro del sitio.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p106">A site collection or a site collection template can have one more policies assigned to it, and each of those policies can have one or more rules. However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![Diagrama con relación entre directivas](media/IP-Two-policies-four-rules.png)
  
<span data-ttu-id="4b47b-122">Además, puede seleccionar una directiva como obligatoria o predeterminada, y puede seleccionar una regla de eliminación como regla predeterminada:</span><span class="sxs-lookup"><span data-stu-id="4b47b-122">In addition, you can select a policy as mandatory or default, and you can select a deletion rule as a default rule:</span></span> 
  
- <span data-ttu-id="4b47b-p107">**Directiva de cumplimiento obligatorio** Cuando una directiva está marcada como obligatoria, sólo una directiva puede asignarse a la colección de sitios o la plantilla. La directiva debe estar marcada como predeterminada y se aplicará a todos los sitios. Los propietarios de sitios no se pueden anular la directiva.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p107">**Mandatory policy**When a policy is marked as mandatory, only one policy can be assigned to the site collection or template. The policy must be marked as default and will be applied to all sites. Site owners cannot opt out of the policy.</span></span>
    
- <span data-ttu-id="4b47b-126">**Directiva predeterminada** Cuando una directiva está establecida como predeterminada, la directiva es activa automáticamente en todos los sitios que se asigna a con ninguna acción requeridos por el propietario del sitio.</span><span class="sxs-lookup"><span data-stu-id="4b47b-126">**Default policy**When a policy is set as default, the policy is automatically active in all sites that it's assigned to with no action required by site owner.</span></span>
    
- <span data-ttu-id="4b47b-127">**Regla predeterminada** Cuando una regla de eliminación está establecida como predeterminada, se aplica automáticamente a todas las bibliotecas de los sitios que usan la directiva.</span><span class="sxs-lookup"><span data-stu-id="4b47b-127">**Default rule**When a deletion rule is set as default, it is automatically applied to all libraries in the sites that use the policy.</span></span>
    
<span data-ttu-id="4b47b-128">En los siguientes ejemplos se explica cuándo será conveniente usar una directiva obligatoria, o directivas y reglas predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="4b47b-128">The following examples explain when you might want to use a mandatory policy or default policies and rules.</span></span>
  
### <a name="example-1-apply-a-single-policy-with-a-single-rule-to-a-site-collection-template"></a><span data-ttu-id="4b47b-129">Ejemplo 1: aplicar una sola directiva con una sola regla a una plantilla de colección de sitios</span><span class="sxs-lookup"><span data-stu-id="4b47b-129">Example 1: Apply a single policy with a single rule to a site collection template</span></span>

<span data-ttu-id="4b47b-p108">Es posible que quiera aplicar una directiva de eliminación de documentos en una amplia gama de contenido no estructurado, como todos los sitios de OneDrive para la Empresa o todos los sitios de grupo. Si quiere asegurarse de que una sola directiva de eliminación de documentos está activa en todos los sitios creados a partir de una plantilla de colección de sitios, puede:</span><span class="sxs-lookup"><span data-stu-id="4b47b-p108">You may want to enforce a document deletion policy across a broad range of unstructured content, such as all OneDrive for Business sites or all team sites. If you want to ensure that a single document deletion policy is active in all sites created from a site collection template, you can:</span></span>
  
1. <span data-ttu-id="4b47b-132">Crear una única directiva con una sola regla de eliminación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b47b-132">Create a single policy with a single default deletion rule.</span></span>
    
2. <span data-ttu-id="4b47b-133">Establecer la directiva como obligatoria y predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b47b-133">Set the policy as mandatory and default.</span></span>
    
3. <span data-ttu-id="4b47b-134">Asignar la directiva a una plantilla de colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="4b47b-134">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="4b47b-p109">En este ejemplo, la regla de eliminación predeterminada se aplicará a todas las bibliotecas en todas las colecciones de sitios creadas a partir de la plantilla, y los propietarios de los sitios no podrán anular la directiva. Esta es la forma más sencilla de aplicar una directiva de eliminación de documentos de forma rígida y completa.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p109">In this example, the default deletion rule will be applied to all libraries in all site collections created from the template, and site owners cannot opt out of the policy. This is the simplest way to broadly and rigidly enforce a document deletion policy.</span></span>
  
![Diagrama con una sola directiva obligatoria](media/IP-Example-1-doc-deletion-policies.png)
  
### <a name="example-2-apply-a-single-policy-with-several-rules-to-a-site-collection-template"></a><span data-ttu-id="4b47b-138">Ejemplo 2: Aplicar una sola directiva con varias reglas a una plantilla de la colección de sitios</span><span class="sxs-lookup"><span data-stu-id="4b47b-138">Example 2: Apply a single policy with several rules to a site collection template</span></span>

<span data-ttu-id="4b47b-p110">Los propietarios de los sitios son los que mejor conocen el tipo de contenido que contienen sus sitios, por lo que puede optar por permitir que ellos elijan la regla de eliminación que mejor se aplique a su sitio. También es aconsejable permitir que los propietarios de sitios puedan anular una directiva completamente.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p110">Site owners often know best what type of content their site contains, so you may choose to allow site owners to select the deletion rule that best applies to their site. You may also want to allow site owners to opt out of a policy entirely.</span></span>
  
<span data-ttu-id="4b47b-p111">Podrá seguir creando y administrando las directivas centralmente. También puede seleccionar una directiva y una regla como predeterminadas, para que una directiva siempre esté en vigor hasta que el propietario del sitio elija otra o no participe en ella. Si quiere proporcionar dicha flexibilidad a los propietarios de los sitios, puede:</span><span class="sxs-lookup"><span data-stu-id="4b47b-p111">At the same time, you can still centrally create and manage the policies. You can also select one policy and rule as the default, so that a policy is always in effect until the site owner chooses a different one or opts out. If you want to provide such flexibility to site owners, you can:</span></span>
  
1. <span data-ttu-id="4b47b-143">Crear una sola directiva con varias reglas de eliminación y establecer una regla como predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b47b-143">Create a single policy with several deletion rules, and set one rule as the default.</span></span>
    
2. <span data-ttu-id="4b47b-144">Establecer la directiva como la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b47b-144">Set the policy as the default policy.</span></span>
    
3. <span data-ttu-id="4b47b-145">Asignar la directiva a una plantilla de colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="4b47b-145">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="4b47b-146">Los propietarios de los sitios pueden seleccionar una de las reglas de eliminación alternativas, anular la directiva, o no hacer nada y estar sujetos a la directiva y la regla predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="4b47b-146">Site owners can select one of the alternate deletion rules, opt out of the policy, or do nothing and be subject to the default policy and rule.</span></span>
  
![Diagrama con una directiva que tiene muchas reglas](media/IP-Example-2-doc-deletion-policies.png)
  
### <a name="example-3-apply-several-policies-with-one-or-more-rules-to-a-site-collection"></a><span data-ttu-id="4b47b-148">Ejemplo 3: aplicar varias directivas con una o varias reglas a una colección de sitios</span><span class="sxs-lookup"><span data-stu-id="4b47b-148">Example 3: Apply several policies with one or more rules to a site collection</span></span>

<span data-ttu-id="4b47b-p112">En este ejemplo se proporciona la máxima flexibilidad a los propietarios de sitios ya que podrán elegir entre varias directivas y, después de seleccionar una directiva, a menudo podrán elegir entre varias reglas. Una directiva y una regla se establecen como predeterminadas, de forma que una directiva siempre estará en vigor hasta que el propietario del sitio elija otra o no participe en ella. Tenga en cuenta que si no establece una directiva y una regla como predeterminadas, no habrá directivas ni reglas activas en las bibliotecas de documentos del sitio hasta que el propietario las elija y aplique.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p112">This example provides the maximum flexibility to site owners because they can choose from several policies, and after selecting a policy they can often choose from several rules. One policy and rule are set as default, so that a policy is always in effect until the site owner chooses a different one or opts out. Note that if you do not set a policy and rule as the default, then no policies or rules will be active for the document libraries in the site until the site owner takes action to select and apply them.</span></span>
  
<span data-ttu-id="4b47b-p113">A diferencia de lo que ocurre en los dos ejemplos anteriores, estas directivas se asignan a una colección de sitios específica, no a la plantilla de la colección de sitios. Esto significa que las directivas pueden personalizarse de forma más específica según el contenido de una colección de sitios determinada.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p113">Unlike the previous two examples, these policies are assigned to a specific site collection — not the site collection template. This means the policies can be more specifically tailored for the content in a specific site collection.</span></span>
  
<span data-ttu-id="4b47b-p114">Las directivas y las reglas se heredan. Los propietarios de los sitios pueden seleccionar una directiva y una regla para su sitio; de esta forma, todos los subsitios heredan la directiva del sitio primario. Sin embargo, un propietario de un subsitio puede interrumpir la herencia si selecciona otra directiva y otra regla, que a su vez se aplicarán a todos los subsitios hasta que se interrumpa la herencia de nuevo.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p114">Policies and rules are inherited. Site owners can select a policy and rule for their site, and all subsites inherit the policy from the parent. However, an owner of a subsite can break inheritance by selecting a different policy and rule, which in turn applies to all subsites until inheritance is broken again.</span></span>
  
<span data-ttu-id="4b47b-156">Para configurar este escenario, puede:</span><span class="sxs-lookup"><span data-stu-id="4b47b-156">To set up this scenario, you can:</span></span>
  
1. <span data-ttu-id="4b47b-157">Crear varias directivas que contengan una o varias reglas.</span><span class="sxs-lookup"><span data-stu-id="4b47b-157">Create several policies that each contains one or more rules.</span></span>
    
2. <span data-ttu-id="4b47b-158">Establecer una directiva y una regla como predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="4b47b-158">Set a policy and rule as the default.</span></span>
    
3. <span data-ttu-id="4b47b-159">Asignar las directivas a una colección de sitios especifica.</span><span class="sxs-lookup"><span data-stu-id="4b47b-159">Assign the policies to a specific site collection.</span></span>
    
<span data-ttu-id="4b47b-160">Además, las directivas y reglas se adaptan a una colección de sitios determinada, en la que los propietarios de los sitios podrán interrumpir la herencia si seleccionan la directiva y la regla que mejor se adapten a su sitio.</span><span class="sxs-lookup"><span data-stu-id="4b47b-160">In addition, the policies and rules are tailored to a specific site collection, where site owners can break inheritance by selecting the policy and rule that best applies to their site.</span></span>
  
![Diagrama con muchas directivas y reglas](media/IP-Example-3-doc-deletion-policies.png)
  
## <a name="create-a-document-deletion-policy"></a><span data-ttu-id="4b47b-162">Crear una directiva de eliminación de documentos</span><span class="sxs-lookup"><span data-stu-id="4b47b-162">Create a document deletion policy</span></span>

1. <span data-ttu-id="4b47b-p115">En la 365Security Office &amp; centro de cumplimiento, vaya a **administración de datos** \> **retención**. En **Eliminar**, haga clic en **administrar las directivas de eliminación de documentos de SharePoint Online y OneDrive para la empresa**. El centro de directiva de eliminación de documentos se abre en una nueva ficha de explorador.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p115">In the Office 365Security &amp; Compliance Center, navigate to **Data management** \> **Retention**. Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**. The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
    <span data-ttu-id="4b47b-p116">La primera vez que vaya desde la seguridad &amp; centro de cumplimiento al centro de directiva de eliminación de documentos, el centro de la directiva se crea automáticamente para usted. Como alternativa, puede crear manualmente el centro de directiva mediante la [creación de la colección de sitios](http://go.microsoft.com/fwlink/p/?LinkID=404342) y elija **Centro de cumplimiento de directivas** en la ficha de **empresa** .</span><span class="sxs-lookup"><span data-stu-id="4b47b-p116">The first time you navigate from the Security &amp; Compliance Center to the Document Deletion Policy Center, the policy center is automatically created for you. Alternatively, you can manually create the policy center by [creating the site collection](http://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab.</span></span> 
    
2. <span data-ttu-id="4b47b-168">Elija **las directivas de eliminación**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-168">Choose **Deletion Policies**.</span></span>
    
    ![Opción Directivas de eliminación](media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="4b47b-170">Elija **Elemento nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-170">Choose **new item**.</span></span>
    
4. <span data-ttu-id="4b47b-p117">Escriba un nombre y una descripción para la directiva. Los propietarios de los sitios pueden seleccionar una directiva para su sitio según el nombre y la descripción. Por lo tanto, incluya información suficiente para que elijan la directiva correcta.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p117">Enter a policy name and description. Site owners may be selecting a policy for their site based on this name and description, so include enough information for them to choose the correct policy.</span></span>
    
5. <span data-ttu-id="4b47b-173">Para crear una regla, elija **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-173">To create a rule, choose **New**.</span></span>
    
6. <span data-ttu-id="4b47b-174">Escriba un nombre y elija las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4b47b-174">Enter a name and choose the following options:</span></span>
    
  - <span data-ttu-id="4b47b-p118">Elija si la regla de forma permanente eliminar documentos o eliminarlos a la Papelera de reciclaje. La Papelera de reciclaje proporciona una red de seguridad de la segunda etapa antes de elimina permanentemente un elemento de un sitio. Para obtener más información acerca de la Papelera de reciclaje, vea [Vaciar la Papelera de reciclaje o restaurar los archivos](http://go.microsoft.com/fwlink/p/?LinkID=404348).</span><span class="sxs-lookup"><span data-stu-id="4b47b-p118">Choose whether the rule will permanently delete documents or delete them to the Recycle Bin. The Recycle Bin provides a second-stage safety net before an item is permanently deleted from a site. For more information about the Recycle Bin, see [Empty the Recycle Bin or restore your files](http://go.microsoft.com/fwlink/p/?LinkID=404348).</span></span>
    
  - <span data-ttu-id="4b47b-178">Elija si la fecha de eliminación se calcula a partir de la fecha en que se creó o la fecha en que se modificó por última vez un documento.</span><span class="sxs-lookup"><span data-stu-id="4b47b-178">Choose whether the deletion date is calculated from the date when a document was created or last modified.</span></span>
    
  - <span data-ttu-id="4b47b-179">Escriba un número de días, meses o años como el período de tiempo tras el cual se eliminará un documento.</span><span class="sxs-lookup"><span data-stu-id="4b47b-179">Enter a number of days, months, or years as the time period after which a document will be deleted.</span></span>
    
  - <span data-ttu-id="4b47b-p119">Elija si la regla es una regla predeterminada. La primera regla que cree se establece automáticamente como la regla predeterminada. Una regla predeterminada se aplica automáticamente a todas las bibliotecas de los sitios que usan la directiva.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p119">Choose whether the rule is a default rule. The first rule that you create is automatically set as the default rule. A default rule is automatically applied to all libraries in the sites that use the policy.</span></span>
    
![Página para nueva regla de eliminación](media/IP-New-deletion-rule.png)
  
7. <span data-ttu-id="4b47b-184">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-184">Click **Save**.</span></span>
    
8. <span data-ttu-id="4b47b-p120">Cree reglas adicionales si quiere que los propietarios de los sitios puedan elegir distintas reglas para aplicar a su sitio. La regla predeterminada, si la hay, se aplicará si el propietario del sitio no realiza ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p120">Create additional rules if you want site owners to be able to choose different rules to apply to their site. The default rule, if any, will be applied if the site owner takes no action.</span></span>
    
9. <span data-ttu-id="4b47b-187">Para quitar una regla de una directiva, seleccione la regla, haga clic en **Eliminar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-187">To remove a rule from a policy, select the rule, click **Delete**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4b47b-188">Si se elimina una regla y la directiva no contiene una regla predeterminada, no hay ninguna regla estará en vigor para esa directiva, en otras palabras, no hay documentos se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="4b47b-188">If you delete a rule, and the policy does not contain a default rule, then no rule will be in effect for that policy—in other words, no documents will be deleted.</span></span> 
  
![Mensaje de confirmación para eliminar regla de directiva](media/IP-Remove-rule-from-policy-message.png)
  
## <a name="assign-the-document-deletion-policy-to-a-site-collection-template"></a><span data-ttu-id="4b47b-190">Asignar la directiva de eliminación de documentos a una plantilla de colección de sitios</span><span class="sxs-lookup"><span data-stu-id="4b47b-190">Assign the document deletion policy to a site collection template</span></span>

<span data-ttu-id="4b47b-191">Al asignar una directiva a una plantilla de colección de sitios, hace que la directiva esté disponible para todas las colecciones de sitios creadas a partir de esa plantilla, tanto las existentes como las que se creen en el futuro.</span><span class="sxs-lookup"><span data-stu-id="4b47b-191">By assigning a policy to a site collection template, you make the policy available to all site collections created from that template, including both existing site collections and site collections created in the future.</span></span>
  
<span data-ttu-id="4b47b-p121">Es importante comprender que el período de tiempo especificado para un documento de directiva de eliminación significa el tiempo desde que el documento se ha creado o modificado, no el tiempo desde que se asignó la directiva. Cuando se asigna la directiva por primera vez, se evalúan todos los documentos en el sitio y, si se cumplen los criterios, se eliminará. Esto se aplica a todos los documentos existentes, no sólo nuevos documentos creados desde que se asignó la directiva.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p121">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned. When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted. This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="4b47b-p122">En la seguridad &amp; centro de cumplimiento, vaya a **administración de datos** \> **retención**. En **Eliminar**, haga clic en **administrar las directivas de eliminación de documentos de SharePoint Online y OneDrive para la empresa**. El centro de directiva de eliminación de documentos se abre en una nueva ficha de explorador.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p122">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**. Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**. The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="4b47b-198">Elija **Asignaciones de directivas para plantillas**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-198">Choose **Policy Assignments for Templates**.</span></span>
    
    ![Opción de asignaciones de directivas para plantillas](media/IP-Policy-Assignments-for-Templates-option.png)
  
3. <span data-ttu-id="4b47b-200">Elija **Elemento nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-200">Choose **new item**.</span></span>
    
4. <span data-ttu-id="4b47b-201">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b47b-201">Do one of the following:</span></span>
    
  - <span data-ttu-id="4b47b-202">Para asignar la directiva a una plantilla de colección de sitios como la plantilla Sitio de grupo, seleccione **Asignar a plantilla de colección de sitios** y, a continuación, seleccione la plantilla de colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="4b47b-202">To assign the policy to a site collection template such as the Team Site template, select **Assign to site collection template**, and then select the site collection template.</span></span>
    
  - <span data-ttu-id="4b47b-203">Para asignar la directiva a la unidad de uno de los usuarios para la empresa, elija **asignar a OneDrive para la plantilla de negocio**, resaltado a continuación.</span><span class="sxs-lookup"><span data-stu-id="4b47b-203">To assign the policy to users' One Drive for Business, choose **Assign to OneDrive for Business Template**, highlighted below.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4b47b-204">Cuando asigne una directiva a una plantilla de colección de sitios, dicha directiva estará disponible para las colecciones de sitios existentes creadas a partir de esa plantilla y para las que se creen en el futuro.</span><span class="sxs-lookup"><span data-stu-id="4b47b-204">When you assign a policy to a site collection template, that policy will be available both to existing site collections created from that template and to site collections created in the future.</span></span> 
  
![Página Seleccionar una plantilla con la opción OneDrive](media/IP-Choose-a-template.png)
  
5. <span data-ttu-id="4b47b-206">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-206">Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4b47b-p123">Cada plantilla puede tener un solo conjunto de directivas asignadas a ella. Si ve un error que indica que esta plantilla ya tiene directivas asignadas a ella, elija **Cancelar** \> **asignar a la colección de sitios** en el panel de navegación izquierdo \> seleccione una colección de sitios para ver y administrar el conjunto de directivas que ya están asignado.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p123">Each template can have only one set of policies assigned to it. If you see an error saying that this template already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** in the left navigation \> select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
6. <span data-ttu-id="4b47b-p124">Elija **Administrar directivas asignadas**, seleccione las directivas que desea asignar y, a continuación, elija si una directiva es la directiva predeterminada. Cuando se establece una directiva predeterminada, todos los sitios que se asigna automáticamente a la directiva tienen la directiva activa con ninguna acción requerida por el propietario del sitio.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p124">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy. When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![Página Agregar y administrar directivas](media/IP-Add-and-manage-policies-page.png)
  
7. <span data-ttu-id="4b47b-212">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-212">Click **Save**.</span></span>
    
8. <span data-ttu-id="4b47b-p125">Si quiere aplicar la directiva en todos los sitios sin permitir que los propietarios de sitios puedan anularla, elija **Marcar directiva como obligatoria**. Cuando establezca una directiva como obligatoria, solo podrá asignarse esa directiva a la plantilla de colección de sitios. La directiva también debe marcarse como predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p125">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection template. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="4b47b-216">Si esta opción está atenuada, elija **Administrar directivas asignadas** y asegúrese de que al menos una directiva esté asignada y establecida como predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b47b-216">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
9. <span data-ttu-id="4b47b-217">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-217">Click **Save**.</span></span>
    
## <a name="assign-the-document-deletion-policy-to-a-site-collection"></a><span data-ttu-id="4b47b-218">Asignar la directiva de eliminación de documentos a una colección de sitios</span><span class="sxs-lookup"><span data-stu-id="4b47b-218">Assign the document deletion policy to a site collection</span></span>

<span data-ttu-id="4b47b-p126">Al asignar una directiva a una colección de sitios determinada, hace que la directiva solo esté disponible para esa colección de sitios específica. Esto significa que las directivas se pueden adaptar según el contenido de la colección de sitios. Además, las directivas asignadas a una colección de sitios específica invalidará todas las directivas asignadas a la plantilla para esa colección de sitios. Por ejemplo, una directiva asignada a la colección de sitios del departamento de ventas (creada a partir de la plantilla Sitio de grupo) invalidará cualquier directiva asignada a la plantilla Sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p126">By assigning a policy to a specific site collection, you make the policy available only to that specific site collection. This means you can tailor policies more closely to the content in the site collection. Also, policies assigned to a specific site collection will override any policies that are assigned to the template for that site collection. For example, a policy assigned to the Sales Department site collection (created from the Team Site template) will override any policies assigned to the Team Site template.</span></span>
  
<span data-ttu-id="4b47b-p127">Es importante comprender que el período de tiempo especificado para un documento de directiva de eliminación significa el tiempo desde que el documento se ha creado o modificado, no el tiempo desde que se asignó la directiva. Cuando se asigna la directiva por primera vez, se evalúan todos los documentos en el sitio y, si se cumplen los criterios, se eliminará. Esto se aplica a todos los documentos existentes, no sólo nuevos documentos creados desde que se asignó la directiva.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p127">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned. When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted. This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="4b47b-p128">En la seguridad &amp; centro de cumplimiento, vaya a **administración de datos** \> **retención**. En **Eliminar**, elija **Administrar directivas de eliminación de documentos de SharePoint Online y OneDrive para la empresa**. El centro de directiva de eliminación de documentos se abre en una nueva ficha de explorador.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p128">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**. Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**. The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="4b47b-229">Elija **Asignaciones de directivas para colecciones de sitios**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-229">Choose **Policy Assignments for Site Collections**.</span></span>
    
    ![Opción de asignaciones de directivas para colecciones de sitios](media/IP-Policy-Assignments-for-Site-Collections-option.png)
  
3. <span data-ttu-id="4b47b-231">Elija **Elemento nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-231">Choose **new item**.</span></span>
    
4. <span data-ttu-id="4b47b-p129">Seleccione **Elija una colección de sitios**. Buscar por nombre o dirección URL de la colección de sitios, seleccione la colección de sitios y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p129">Choose **Choose a site collection**. Search for the site collection by name or URL, select the site collection and click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4b47b-p130">Cada colección de sitios puede tener un solo conjunto de directivas asignadas a ella. Si ve un error que indica que esta colección de sitios ya tiene directivas asignadas a ella, elija **Cancelar** \> **asignar a la colección de sitios** y seleccione una colección de sitios para ver y administrar el conjunto de directivas que ya están asignadas.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p130">Each site collection can have only one set of policies assigned to it. If you see an error saying that this site collection already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** and select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
![Página Seleccionar una colección de sitios](media/IP-Choose-a-site-collection-page.png)
  
5. <span data-ttu-id="4b47b-p131">Elija **Administrar directivas asignadas**, seleccione las directivas que desea asignar y, a continuación, elija si una directiva es la directiva predeterminada. Cuando se establece una directiva predeterminada, todos los sitios que se asigna automáticamente a la directiva tienen la directiva activa con ninguna acción requerida por el propietario del sitio.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p131">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy. When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![Página Agregar y administrar directivas](media/IP-Add-and-manage-policies-page.png)
  
6. <span data-ttu-id="4b47b-240">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-240">Click **Save**.</span></span>
    
7. <span data-ttu-id="4b47b-p132">Si quiere aplicar la directiva en todos los sitios sin permitir que los propietarios de sitios puedan anularla, elija **Marcar directiva como obligatoria**. Cuando establezca una directiva como obligatoria, solo podrá asignarse esa directiva a la colección de sitios. La directiva también debe marcarse como predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p132">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="4b47b-244">Si esta opción está atenuada, elija **Administrar directivas asignadas** y asegúrese de que al menos una directiva esté asignada y establecida como predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b47b-244">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
8. <span data-ttu-id="4b47b-245">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-245">Click **Save**.</span></span>
    
## <a name="delete-a-policy-assignment"></a><span data-ttu-id="4b47b-246">Eliminar una asignación de directivas</span><span class="sxs-lookup"><span data-stu-id="4b47b-246">Delete a policy assignment</span></span>

<span data-ttu-id="4b47b-247">Cuando se elimina una asignación, las directivas asignadas ya no se aplicarán a ninguno de los sitios de la colección de sitios o la plantilla de colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="4b47b-247">When you delete an assignment, the assigned policies will no longer apply to any sites in the site collection or site collection template.</span></span>
  
1. <span data-ttu-id="4b47b-p133">En la seguridad &amp; centro de cumplimiento, vaya a **administración de datos** \> **retención**. En **Eliminar**, elija **Administrar directivas de eliminación de documentos de SharePoint Online y OneDrive para la empresa**. El centro de directiva de eliminación de documentos se abre en una nueva ficha de explorador.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p133">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**. Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**. The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="4b47b-251">Elija **Asignaciones de directivas para plantillas** o **Asignaciones de directivas para colecciones de sitios**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-251">Choose either **Policy Assignments for Templates** or **Policy Assignments for Site Collections**.</span></span>
    
3. <span data-ttu-id="4b47b-252">Seleccione el elemento de asignación y haga clic en **Eliminar elemento**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-252">Select the assignment item and click **Delete Item**.</span></span>
    
    ![Comando Eliminar elemento para asignación de directiva](media/IP-Delete-policy-assignment.png)
  
## <a name="delete-a-policy"></a><span data-ttu-id="4b47b-254">Eliminar una directiva</span><span class="sxs-lookup"><span data-stu-id="4b47b-254">Delete a policy</span></span>

<span data-ttu-id="4b47b-p134">No se puede eliminar una directiva que está en uso. Antes de eliminar una directiva, primero debe eliminar todas las asignaciones para las colecciones de sitios y plantillas de colección de sitios que incluyen esa directiva, vea la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p134">You can't delete a policy that's in use. Before you can delete a policy, you first need to delete all assignments to site collections and site collection templates that include that policy—see the previous section.</span></span>
  
1. <span data-ttu-id="4b47b-p135">En la seguridad &amp; centro de cumplimiento \> elija **administración de datos** \> **retención** en el panel de navegación izquierdo \> en **Eliminar** \> **eliminación de un documento administrar directivas para SharePoint Online y OneDrive para la empresa**. El centro de directiva de eliminación de documentos se abre en una nueva ficha de explorador.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p135">In the Security &amp; Compliance Center \> choose **Data management** \> **Retention** in the left navigation \> under **Delete** \> **Manage document deletion policies for SharePoint Online and OneDrive for Business**. The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="4b47b-259">Elija \*\* las directivas de eliminación \*\*.</span><span class="sxs-lookup"><span data-stu-id="4b47b-259">Choose \*\* Deletion Policies \*\*.</span></span>
    
    ![Opción Directivas de eliminación](media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="4b47b-261">Seleccione la directiva.</span><span class="sxs-lookup"><span data-stu-id="4b47b-261">Select the policy.</span></span>
    
4. <span data-ttu-id="4b47b-262">En la cinta de opciones \> ficha **elementos** \> **Eliminar directiva**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-262">On the Ribbon \> **Items** tab \> **Remove Policy**.</span></span>
    
    ![Botón Quitar directiva en cinta](media/IP-Remove-Policy-button-on-Ribbon.png)
  
5. <span data-ttu-id="4b47b-p136">Si la directiva está en uso, se le pedirá si desea quitar la directiva de todas las colecciones de sitios donde se va a utilizar. Si está seguro, elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b47b-p136">If the policy is in use, you'll be asked if you want to remove the policy from all of the site collections where it's being used. If you're sure, choose **OK**.</span></span>
    
    ![Mensaje para confirmar eliminación de directiva](media/IP-Delete-policy-confirmation.png)
  
## <a name="see-also"></a><span data-ttu-id="4b47b-267">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b47b-267">See also</span></span>

[<span data-ttu-id="4b47b-268">Información general sobre las directivas de eliminación de documentos</span><span class="sxs-lookup"><span data-stu-id="4b47b-268">Overview of document deletion policies</span></span>](document-deletion-policies.md)

[<span data-ttu-id="4b47b-269">Aplicar o quitar una directiva de eliminación de documentos de un sitio</span><span class="sxs-lookup"><span data-stu-id="4b47b-269">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)
 

