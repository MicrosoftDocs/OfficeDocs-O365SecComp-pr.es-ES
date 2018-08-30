---
title: Informes de supervisión
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2a762db5-e1c9-4c09-aa8e-bef49ce97209
description: Usar informes de supervisión para ver qué mensajes de correo electrónico necesita cumplimiento revisar y que debe realizar.
ms.openlocfilehash: e18d083c0aad8be945c628516e593462da8e3898
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535794"
---
# <a name="supervision-reports"></a>Informes de supervisión

Definición las directivas de supervisión que las comunicaciones de la organización deben revisar para el cumplimiento y quién llevará a cabo las revisiones. Use los informes de supervisión para ver la actividad de revisión en el nivel de directiva y revisor. Para cada directiva, también puede ver las estadísticas de live en el estado actual de la actividad de revisión. [Obtenga más información acerca de las directivas de supervisión](configure-supervision-policies.md) . 
  
> [!NOTE]
> Uso de directivas de supervisión requiere una suscripción a Office 365 E5 para su organización. Si no tiene ese plan y desea probar supervisión, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Puede usar los informes de supervisión para:
  
- Compruebe que las directivas se funcionan según lo previsto. 
    
- Averigüe cuántos mensajes de correo electrónico que se identifican para su revisión.
    
- Averigüe cuántos mensajes de correo electrónico no son compatibles y cuáles están pasando la revisión. Esta información puede ayudarle a decidir si se debe ajustar con precisión las directivas o cambiar el número de revisores.
    
## <a name="view-the-supervision-report"></a>Ver el informe de supervisión

1. Inicie sesión en la [seguridad &amp; centro de cumplimiento](https://protection.office.com/) con las credenciales para una cuenta de administrador de la organización de Office 365 que tiene permisos para ver informes de supervisión.. 
    
2. Vaya a **informes** \> **panel**. Verá un widget de informes de supervisión y otros informes tiene acceso a.
    
3. Haga clic en el widget de **supervisión** para abrir la página de informe detallado. 
    
> [!NOTE]
> Si no puede tener acceso a la página de **informes** , compruebe que se encuentra un miembro del grupo de roles de revisión de supervisión, tal como se describe en [realizar supervisión disponible en su organización](configure-supervision-policies.md#SRavailable). Que se incluye en este rol grupo le permite crea y administrar supervisión directivas y ejecuta el informe. 
  
## <a name="how-to-use-the-report"></a>Cómo usar el informe

Cuando una directiva de supervisión identifica un correo electrónico para su revisión, el correo electrónico se entrega en la carpeta de supervisión del revisor en Outlook y Outlook web app. Este informe muestra el nombre de la directiva y el número de comunicaciones en cada etapa del proceso de revisión.
  
Utilice el informe para:
  
- Ver los datos para todas o directivas específicas.
    
- Ver los datos agrupados por tipo de etiqueta (como compatible, Questionable, etc.), el revisor o el tipo de mensaje.
    
- Exportar datos a un archivo CSV.
    
- Filtrar los datos según la fecha de actividad de revisión, tipo de etiqueta, revisor, tipo de mensaje.
    
Éste es un desglose de los valores que aparecen en la columna **tipo de etiqueta** . 
  
|**Tipo de etiqueta**|**¿Qué significa**|
|:-----|:-----|
|No se ha revisado  <br/> |El número de mensajes de correo electrónico que no se han revisado todavía. Estos mensajes de correo electrónico están en espera de revisión en la carpeta de supervisión del revisor de Outlook.  <br/> |
|Compatible con  <br/> |El número de mensajes de correo electrónico revisado y marcado como compatible. No es necesario realizar ninguna otra acción.  <br/> |
|Dudosos  <br/> |El número de mensajes de correo electrónico revisado y marca dudoso. Esto actúa como un indicador; otros revisores pueden ayudar a comprobar si un correo electrónico necesita investigación para cumplimiento de normas.  <br/> |
|No compatible (activo)  <br/> |El número de mensajes de correo electrónico que no son compatibles con que actualmente están investigar los revisores.  <br/> |
|No compatible (resuelto)  <br/> |El número de mensajes de correo electrónico que no son compatibles con que investigar y resuelven los revisores.  <br/> |
   
## <a name="more-details"></a>Obtener más detalles

- En primer lugar se deben aprovisionar las directivas de supervisión antes de que aparecen en este informe.
    
- Si se eliminan las directivas, aún se muestran datos históricos. Sin embargo, están indicados como "directiva inexistente", y no está disponible la función **de exportación** . 
    
- Si el informe no muestra los datos de forma predeterminada, podría ser debido a que el intervalo de fechas actual no tiene ningún dato que mostrar. En estos casos, utilice el control de **filtros** para cambiar el intervalo de fechas. 
    

