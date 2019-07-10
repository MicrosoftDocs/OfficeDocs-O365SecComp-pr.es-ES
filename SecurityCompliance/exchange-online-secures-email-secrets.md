---
title: Cómo Exchange Online protege su información confidencial de correo electrónico
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Además del centro de confianza de Office 365, que proporciona información de seguridad, privacidad y cumplimiento para Office 365, es posible que quiera saber cómo Office 365 ayuda a proteger secretos que proporcione en sus centros de datos. Usamos una tecnología denominada administrador de claves distribuidas (DKM).
ms.openlocfilehash: 8350785968c68b22c58be17ec68d94ff908c95d9
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599436"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="95906-104">Cómo Exchange Online protege su información confidencial de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="95906-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="95906-105">Este artículo describe cómo Microsoft protege su información confidencial de correo electrónico en sus centros de datos.</span><span class="sxs-lookup"><span data-stu-id="95906-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="95906-106">¿Cómo se protege la información confidencial proporcionada por el usuario?</span><span class="sxs-lookup"><span data-stu-id="95906-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="95906-107">Además del centro de confianza de Office 365, que proporciona [información de seguridad, privacidad y cumplimiento para office 365](https://go.microsoft.com/fwlink/?linkid=874644), es posible que quiera saber cómo Office 365 ayuda a proteger secretos que proporcione en sus centros de datos.</span><span class="sxs-lookup"><span data-stu-id="95906-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](https://go.microsoft.com/fwlink/?linkid=874644), you might want to know how Office 365 helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="95906-108">Usamos una tecnología denominada administrador de claves distribuidas (DKM).</span><span class="sxs-lookup"><span data-stu-id="95906-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="95906-109">[Administrador de claves distribuidas](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) es una funcionalidad del lado cliente que usa un conjunto de claves secretas para cifrar y descifrar información.</span><span class="sxs-lookup"><span data-stu-id="95906-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="95906-110">Solo los miembros de un grupo de seguridad específico de los Servicios de dominio de Active Directory pueden tener acceso a dichas claves para descifrar los datos cifrados por el DKM.</span><span class="sxs-lookup"><span data-stu-id="95906-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="95906-111">En Exchange Online, solo determinadas cuentas de servicio bajo las cuales se ejecutan procesos de Exchange forman parte del grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="95906-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="95906-112">Como parte del procedimiento operativo estándar en el centro de datos, ningún humano tiene credenciales que forman parte de este grupo de seguridad y, por lo tanto, nadie tiene acceso a las claves que pueden descifrar la información confidencial.</span><span class="sxs-lookup"><span data-stu-id="95906-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="95906-p104">Para depuración, solución de problemas o fines de auditoria, un administrador del centro de datos debe solicitar acceso con privilegios elevados para obtener credenciales temporales que forman parte del grupo de seguridad. Este proceso requiere varios niveles de aprobación legal. Si se concede acceso, toda la actividad se registra y se audita. Además, solo se otorga acceso durante un determinado intervalo de tiempo, que caduca automáticamente una vez concluido.</span><span class="sxs-lookup"><span data-stu-id="95906-p104">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group. This process requires multiple levels of legal approval. If access is granted, all activity is logged and audited. In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="95906-117">Para brindar protección adicional, la tecnología del DKM incluye sustitución de claves y archivado automáticos.</span><span class="sxs-lookup"><span data-stu-id="95906-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="95906-118">Esto también garantiza el acceso al contenido anterior sin tener que recurrir a la misma clave de forma indefinida.</span><span class="sxs-lookup"><span data-stu-id="95906-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="95906-119">¿De qué forma Exchange Online usa el DKM?</span><span class="sxs-lookup"><span data-stu-id="95906-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="95906-120">Microsoft usa el [Administrador de claves distribuidas](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) para cifrar sus secretos en los centros de seguridad de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="95906-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="95906-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="95906-121">For example:</span></span>
  
- <span data-ttu-id="95906-122">Credenciales de la cuenta de correo electrónico para cuentas conectadas.</span><span class="sxs-lookup"><span data-stu-id="95906-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="95906-123">Las cuentas conectadas son cuentas de terceros, como hotmail, gmail y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="95906-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="95906-124">cuentas de correo.</span><span class="sxs-lookup"><span data-stu-id="95906-124">mail accounts.</span></span>
    
- <span data-ttu-id="95906-125">Clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="95906-125">Customer key.</span></span> <span data-ttu-id="95906-126">Si usa la [clave de cliente en Office 365](controlling-your-data-using-customer-key.md), usará [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) para proteger sus secretos.</span><span class="sxs-lookup"><span data-stu-id="95906-126">If you are using [Customer Key in Office 365](controlling-your-data-using-customer-key.md), you'll use [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="95906-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="95906-127">Related topics</span></span>

[<span data-ttu-id="95906-128">Cifrado en Office 365</span><span class="sxs-lookup"><span data-stu-id="95906-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="95906-129">Información de referencia técnica sobre el cifrado en Office 365</span><span class="sxs-lookup"><span data-stu-id="95906-129">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="95906-130">Garantía del servicio en el centro de &amp; seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="95906-130">Service assurance in the Office 365 Security &amp; Compliance Center</span></span>](https://go.microsoft.com/fwlink/?linkid=874645)
  

