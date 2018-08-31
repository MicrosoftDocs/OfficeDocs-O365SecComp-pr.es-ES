---
title: RGPD de uso compartido de archivos local
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: ''
localization_priority: Priority
description: Obtenga información sobre cómo cumplir los requisitos de RGPD en el uso compartido de archivos de Windows Server local.
ms.openlocfilehash: 29f79f05f4b23656e3262b717e4fa24d80d9d470
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272455"
---
# <a name="gdpr-for-on-premises-windows-server-file-shares"></a><span data-ttu-id="46a87-103">RGPD para uso compartido de archivos de Windows Server local.</span><span class="sxs-lookup"><span data-stu-id="46a87-103">GDPR for on-premises Windows Server file shares</span></span>

<span data-ttu-id="46a87-104">El método recomendado básico para el uso compartido de archivos es:</span><span class="sxs-lookup"><span data-stu-id="46a87-104">The basic recommended approach for file shares is:</span></span>

-   <span data-ttu-id="46a87-105">Use Azure Information Protection para etiquetar los datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="46a87-105">Use Azure Information Protection to label sensitive data.</span></span>

-   <span data-ttu-id="46a87-106">Use el escáner de Azure Information Protection para buscar datos.</span><span class="sxs-lookup"><span data-stu-id="46a87-106">Use Azure Information Protection scanner to find data.</span></span>

<span data-ttu-id="46a87-107">El enfoque recomendado para el uso compartido de archivos incluye estos pasos:</span><span class="sxs-lookup"><span data-stu-id="46a87-107">The recommended approach for files shares includes these steps:</span></span>

1.  <span data-ttu-id="46a87-108">**Instale y configure el escáner de Azure Information Protection.**</span><span class="sxs-lookup"><span data-stu-id="46a87-108">**Install and configure Azure Information Protection scanner.**</span></span>

    -   <span data-ttu-id="46a87-109">Decida qué tipos de datos confidenciales quiere usar.</span><span class="sxs-lookup"><span data-stu-id="46a87-109">Decide which sensitive data types to use.</span></span>

    -   <span data-ttu-id="46a87-110">Especifique las carpetas locales y los recursos compartidos de red que se van a usar.</span><span class="sxs-lookup"><span data-stu-id="46a87-110">Specify local folders and network shares to use.</span></span>

2.  <span data-ttu-id="46a87-111">**Complete un ciclo de detección.**</span><span class="sxs-lookup"><span data-stu-id="46a87-111">**Complete a discovery cycle.**</span></span>

    -   <span data-ttu-id="46a87-112">Ejecute el escáner en el modo de detección y valide los resultados.</span><span class="sxs-lookup"><span data-stu-id="46a87-112">Run the scanner in discovery mode and validate the findings.</span></span>

    -   <span data-ttu-id="46a87-113">Si es necesario, optimice las condiciones y los tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="46a87-113">If needed, optimize the conditions and sensitive information types.</span></span>

    -   <span data-ttu-id="46a87-114">Evalúe el impacto esperado de aplicar etiquetas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="46a87-114">Assess the expected impact of automatically applying labels.</span></span>

3.  <span data-ttu-id="46a87-115">**Ejecute el analizador de Azure Information Protection para aplicar etiquetas a los documentos necesarios**.</span><span class="sxs-lookup"><span data-stu-id="46a87-115">**Run the Azure Information Protection scanner to apply labels to qualifying documents**.</span></span>

4.  <span data-ttu-id="46a87-116">**Para obtener protección:**</span><span class="sxs-lookup"><span data-stu-id="46a87-116">**For protection:**</span></span>

    -   <span data-ttu-id="46a87-117">Configure las reglas de prevención de pérdida de datos de Exchange para proteger los documentos con la etiqueta que desee.</span><span class="sxs-lookup"><span data-stu-id="46a87-117">Configure Exchange data loss prevention rules to protect documents with the desired label.</span></span>

    -   <span data-ttu-id="46a87-118">Asegúrese de usar permisos para limitar quién puede obtener acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="46a87-118">Be sure to use permissions to limit who can access files.</span></span>

5.  <span data-ttu-id="46a87-119">**Para supervisar, integre los registros de Windows Server con una herramienta SIEM.**</span><span class="sxs-lookup"><span data-stu-id="46a87-119">**For monitoring, integrate Windows Server logs with a SIEM tool.**</span></span>

    -   <span data-ttu-id="46a87-p101">Para buscar datos personales para solicitudes de datos personales, utilice el escáner de Azure Information Protection. También puede configurar la búsqueda de SharePoint Server para rastrear el uso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="46a87-p101">To find personal data for data subject requests, use Azure Information Protection scanner. You can also configure SharePoint Server search to crawl file shares.</span></span>

<span data-ttu-id="46a87-122">Para obtener más información sobre cómo usar el escáner de Azure Information Protection para buscar y etiquetar datos personales, vea el Kit de herramientas de detección de datos de RGPD de Microsoft en [http://aka.ms/gdprpartners](<http://aka.ms/gdprpartners>).</span><span class="sxs-lookup"><span data-stu-id="46a87-122">For more information on using Azure Information Protection scanner to find and label personal data, see the Microsoft GDPR Data Discovery Toolkit at [http://aka.ms/gdprpartners](<http://aka.ms/gdprpartners>).</span></span>

<span data-ttu-id="46a87-p102">Para obtener información sobre cómo configurar el escáner para buscar condiciones y usar los tipos de información confidencial prevención de pérdida de datos (DLP) de Office 365, consulte [Configuración de las condiciones para la clasificación automática y recomendada en Azure Information Protection](https://docs.microsoft.com/es-ES/information-protection/deploy-use/configure-policy-classification). Tenga en cuenta que los nuevos tipos de información confidencial de Office 365 no estarán disponibles inmediatamente para su uso con el escáner y que los tipos de información confidencial personalizados no pueden usarse con este.</span><span class="sxs-lookup"><span data-stu-id="46a87-p102">For information on configuring the scanner for conditions and using the Office 365 data loss prevention (DLP) sensitive information types, see [How to configure conditions for automatic and recommended classification for Azure Information Protection](https://docs.microsoft.com/es-ES/information-protection/deploy-use/configure-policy-classification). Note that new Office 365 sensitive information types will not be immediately available to use with the scanner and custom sensitive information types cannot be used with the scanner.</span></span>
