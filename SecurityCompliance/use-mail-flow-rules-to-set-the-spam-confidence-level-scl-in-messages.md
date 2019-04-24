---
title: Usar reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL)
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo establecer el SCL de los mensajes en Exchange Online Protection.
ms.openlocfilehash: e07b90ab1ab004c39ef36b2aa744ca87120c11fe
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263462"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>Usar reglas de flujo de correo para establecer el nivel de confianza contra correo no deseado (SCL)

Puede crear una regla de flujo de correo (también denominada regla de transporte) que establezca el nivel de confianza contra correo no deseado (SCL) de un mensaje de correo electrónico. El SCL es una medida de la probabilidad de que un mensaje sea correo no deseado. El correo no deseado son mensajes de correo electrónico no solicitados (y a menudo no deseados). El servicio realiza diferentes acciones en un mensaje según su clasificación SCL. Por ejemplo, tal vez desee evitar el filtrado de contenido de correo no deseado para los mensajes enviados por personas dentro de la organización porque confía en que un mensaje que envía internamente un colega no es correo no deseado. El uso de reglas de flujo de correo para establecer el valor de SCL de un mensaje le proporciona un mayor control para controlar el correo no deseado. 
  
 **¿Qué necesita saber antes de comenzar?**
  
- Tiempo estimado para finalizar este procedimiento: 10 minutos.
    
- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "reglas de flujo de correo" en [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) o [Feature Permissions in EOP](eop/feature-permissions-in-eop.md). 
    
- Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Métodos abreviados de teclado en el Centro de administración de Exchange**.
    
### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Para crear una regla de flujo de correo que establezca el SCL de un mensaje

1. En el Centro de administración de Exchange (EAC), elija **Flujo de correo** \> **Reglas**.
    
2. Elija **Nuevo**![Agregar icono](media/ITPro-EAC-AddIcon.gif) y seleccione **Crea una nueva regla**.
    
3. Especifique un nombre para la regla.
    
4. Elija **Más opciones** y, en **Aplicar esta regla si**, especifique una condición que desencadenará la acción que establecerá para esta regla (que es establecer el valor SCL).
    
    Por ejemplo, puede establecer que **El remitente** \> **es interno/externo** y, a continuación, en el cuadro de diálogo **seleccionar ubicación de remitente**, seleccionar **Dentro de la organización** y elegir **aceptar**.<br/>
    ![Seleccionar ubicación del remitente](media/EOP-ETR-SetSCL-1.jpg)
  
5. En **Hacer lo siguiente**, seleccione **Modificar propiedades del mensaje** \> **establecer el nivel de confianza de correo no deseado (SCL)**.
  
6. En el cuadro de diálogo **especificar SCL**, seleccione uno de los siguientes valores y elija **aceptar**:
    
  - **Omitir el filtrado de correo no deseado**: establece el SCL en -1, lo que significa que no se realizará el filtrado de contenido. 
    
  - **0-4**: cuando establece el SCL en uno de estos valores, el mensaje se pasará al filtro de contenido para su procesamiento adicional. 
    
  - **5, 6**: cuando se establece el SCL en uno de estos valores, se aplicará la acción especificada en **Correo no deseado** en las directivas del filtro de contenido aplicable. De forma predeterminada, la acción es enviar el mensaje a la carpeta de correo no deseado del destinatario. 
    
  - **7, -9**: cuando se establece el SCL en uno de estos valores, se aplicará la acción especificada en **Correo no deseado de confianza alta** en las directivas del filtro de contenido aplicable. De forma predeterminada, la acción es enviar el mensaje a la carpeta de correo no deseado del destinatario. 
    
    Para obtener más información acerca de cómo configurar las directivas de filtrado de contenido, vea [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md). Para obtener más información acerca de los valores de SCL en el servicio, vea [Niveles de confianza de correo no deseado](spam-confidence-levels.md).
    
7. Especifique propiedades adicionales para la regla y elija **Guardar**.
    
    > [!TIP]
    > Para obtener más información sobre las propiedades adicionales que puede seleccionar o especificar para esta regla, vea [usar el EAC para crear reglas de flujo de correo](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules). 
  
## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que este procedimiento funciona correctamente, envíe un mensaje de correo electrónico a una persona de su organización y compruebe que la acción que se realiza en el mensaje sea como se esperaba. Por ejemplo, si **establece el nivel de confianza de correo no deseado (SCL)** en **Omitir el filtrado de correo no deseado**, el mensaje debe enviarse a la bandeja de entrada del destinatario especificado. Sin embargo, si **establece el nivel de confianza de correo no deseado (SCL)** en **9** y la acción **Correo no deseado de confianza alta** para las directivas de filtro de contenido aplicables es mover el mensaje a la carpeta de correo no deseado, el mensaje debe enviarse a la carpeta de correo no deseado del destinatario especificado. 
  

