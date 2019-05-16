---
title: Proteger la información
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/26/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Página de aterrizaje para proteger la información
ms.openlocfilehash: 696684778604f4259166bdc3059944285833cba1
ms.sourcegitcommit: 4eb4ca899adcf4d86501530f875eb49af8cdaeb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2019
ms.locfileid: "34083183"
---
# <a name="protect-information"></a>Proteger la información

Microsoft 365 y Office 365 incluyen capacidades que se pueden aplicar a tipos específicos de datos para proteger la información.


|**Función**|**Más información**|
|:-----|:-----|
|[Etiquetas de confidencialidad](sensitivity-labels.md) <br/> |Con las etiquetas de confidencialidad puede clasificar y ayudar a proteger el contenido confidencial. Las opciones de protección incluyen etiquetas, marcas de agua y cifrado. Las etiquetas de confidencialidad usan Azure Information Protection. Si está usando las etiquetas de Azure Information Protection, por ahora le recomendamos que Evite crear nuevas etiquetas en otros centros de administración hasta que haya completado la migración. Consulte [migración de Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-migrate-labels). <br/> Las [etiquetas de retención](retention-policies.md) son distintas de las etiquetas de confidencialidad. Las etiquetas de retención le ayudan a conservar o eliminar el contenido en función de las directivas que defina. Estos ayudan a las organizaciones a cumplir las normativas del sector y las directivas internas.|
|[Prevención de pérdida de datos](data-loss-prevention-policies.md) Supervisor  <br/> |Con las directivas de DLP, puede identificar, supervisar y proteger automáticamente la información confidencial en Office 365. Las directivas de prevención de pérdida de datos pueden usar las etiquetas de confidencialidad y los tipos de información confidencial para identificar información confidencial. <br/> |
|[Tipos de información confidencial](what-the-sensitive-information-types-look-for.md) <br/> |Microsoft 365 incluye muchos tipos de información confidencial listos para que pueda usarlos en las directivas de DLP y para la clasificación automática con etiquetas de confidencialidad y retención. Los tipos de información confidencial también se pueden usar con el [escáner de Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner) para clasificar y proteger los archivos de forma local. Los tipos de información confidencial definen cómo el proceso automatizado reconoce determinados tipos de información, como los números de servicio de mantenimiento y los números de tarjetas de crédito.   <br/> |
|[Cifrado de mensajes de Office 365](ome.md) OME  <br/> |Con el cifrado de mensajes de Office 365, su organización puede enviar y recibir mensajes de correo electrónico cifrados entre usuarios de dentro y fuera de la organización. El cifrado de mensajes de Office 365 funciona con Outlook.com, Yahoo!, gmail y otros servicios de correo electrónico. El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios deseados puedan ver el contenido de los mensajes. <br/> |
|[Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/)<br/> |Azure Information Protection (a veces conocido como AIP) ayuda a una organización a clasificar, etiquetar y, de manera opcional, proteger los documentos y los correos electrónicos. Los administradores pueden aplicar etiquetas automáticamente mediante la definición de reglas y condiciones. Los usuarios pueden aplicar manualmente etiquetas a los archivos y el correo. También puede proporcionar recomendaciones a los usuarios sobre cuándo se deben aplicar las etiquetas.<br/> Si utiliza etiquetas de confidencialidad o cifrado de mensajes de Office, ya está usando las capacidades de clasificación y protección. Si todavía no ha migrado las etiquetas de Azure Information Protection a Office 365, continúe administrarlas en Azure Information Protection.  <br/>Puede ejecutar el analizador local de [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner) para clasificar y proteger los archivos de Windows Server, los recursos compartidos de red y las bibliotecas y los sitios de SharePoint Server. Esto puede ser un primer paso hacia la identificación de datos para migrar a Office 365.
|Azure Information Protection con la clave de cifrado administrada por el cliente <br/> |Algunas organizaciones tienen una necesidad empresarial o un requisito de cumplimiento para mantener el control de una clave de cifrado. Esta opción es poco frecuente. Azure Information Protection permite a las organizaciones introducir su propia clave (BYOK) en el servicio. Para obtener más información, consulte [traer su propia clave (BYOK) para Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/byok-price-restrictions). Se ofrece otra opción más compleja para los clientes que tienen que conservar una clave de cifrado en local, lo que se conoce como mantener su propia clave (HYOK).  Para obtener más información, vea [retener su propia clave (HYOK) para Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-adrms-restrictions). <br/> |
    

