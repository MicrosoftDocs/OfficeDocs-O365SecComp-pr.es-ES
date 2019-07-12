---
title: Envíos administrativos en Office 365 ATP
ms.author: brwilcox
author: briwilcox
manager: dansimp
ms.date: 07/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo enviar mensajes potencialmente peligrosos, direcciones URL y archivos a Microsoft.
ms.openlocfilehash: 6f7ea63cae4d7cafb0d1386b29d99101d290ef30
ms.sourcegitcommit: 9e2df36b05a2c93ce2629a7a5eda8f44159d114d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "35632230"
---
# <a name="admin-submissions-in-office-365-atp"></a>Envíos administrativos en Office 365 ATP

Ahora, los administradores pueden enviar correos electrónicos con el identificador de mensajes de red, las direcciones URL y los archivos para que Microsoft los analice en Office 365. La sección de Submissions actualizada todavía incluye mensajes de usuario que se han notificado. 

Al enviar un correo electrónico, recibirá información sobre las directivas que puedan haber permitido el correo entrante en su inquilino, así como el examen de las direcciones URL y los datos adjuntos del correo. Las directivas que pueden haber permitido un correo incluyen la lista de remitentes seguros de un usuario individual, así como directivas de nivel de inquilino, como reglas ETR. 


## <a name="how-to-submit-content"></a>Cómo enviar contenido

Para enviar contenido a Microsoft, haga clic en el botón **nuevo envío** en el lado superior izquierdo de la página envíos. Un control flotante en el lado derecho de la página aparece con la opción de enviar un correo electrónico, una dirección URL o un archivo. 

### <a name="email"></a>Correo electrónico
![Ejemplo de envío de correo electrónico](media/submission-flyout-email.PNG)
1. Para enviar un correo electrónico, seleccione **correo electrónico** y especifique el **identificador de mensaje de red** de correo electrónico o cargue el archivo de correo electrónico. 

2. Especifique el destinatario o los destinatarios con los que desea ejecutar la comprobación de la Directiva. La comprobación de la Directiva determinará si se ha omitido el análisis del correo electrónico debido a directivas de nivel de usuario o de inquilino. 

3. Especifique si el correo electrónico se debe haber bloqueado o no. Si el correo electrónico debe haberse bloqueado, especifique si debe haberse bloqueado como correo no deseado, suplantación de identidad (phishing) o malware. Si no está seguro de qué tipo puede ser, use su mejor criterio.  

* Si se ha omitido el filtro debido a las directivas tras el envío, verá información sobre esa Directiva.

* Si no se ha omitido el filtro debido a una o más directivas, el análisis se completará en varios minutos. Para ver más información sobre el envío, haga clic en el vínculo estado. Esto incluye los resultados de la comprobación de la Directiva y el veredicto de reescaneo. Nota Esto no ejecuta el correo electrónico a través de la pila de filtrado completo de ATP de Office 365, sino que ejecuta un nuevo análisis parcial en función de determinados atributos del correo, la dirección URL o el archivo. 

4. Haga clic en el botón **Enviar** .

### <a name="url"></a>URL
![Ejemplo de envío de correo electrónico](media/submission-url-flyout.png)
1. Para enviar una dirección URL, seleccione **dirección URL** en el control flotante. Escriba la dirección URL completa, incluido el protocolo (**https://**). 

* Si seleccionó **debería haber sido filtrada**, especifique si la dirección URL es phishing o malware.

2. Haga clic en el botón **Enviar** . 


### <a name="file"></a>File
![Ejemplo de envío de correo electrónico](media/submission-file-flyout.PNG)
1. Para enviar un archivo de **** selección de archivo desde el control flotante y cargar el archivo que desea examinar. 

2. Haga clic en el botón **Enviar** .


## <a name="related-topics"></a>Temas relacionados

[Plan 2 de protección contra amenazas avanzada de Office 365](office-365-ti.md)
  
[Protección contra amenazas en Office 365](protect-against-threats.md)
  
[Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)
  

