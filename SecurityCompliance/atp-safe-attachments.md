---
title: Datos adjuntos seguros ATP de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 01/08/2019
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
description: La característica de los datos adjuntos seguros proporciona comprobación de tiempo de clic de los datos adjuntos de correo electrónico. Utilizar datos adjuntos seguros para proteger la organización de las personas de archivos malintencionados enviar o recibir por correo electrónico.
ms.openlocfilehash: 85c1ec3e0126a155f863b9fef9ddb36b13d0b3fb
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769844"
---
# <a name="office-365-atp-safe-attachments"></a>Datos adjuntos seguros ATP de Office 365

## <a name="overview-of-office-365-atp-safe-attachments"></a>Información general de los datos adjuntos seguros ATP de Office 365

Datos adjuntos seguros de ATP (junto con los [Vínculos seguros ATP](atp-safe-links.md)) es parte de [La protección de amenaza avanzada de Office 365](office-365-atp.md) (ATP). La característica de los datos adjuntos seguros de ATP comprueba si los datos adjuntos de correo electrónico son malintencionados y, a continuación, realiza una acción para proteger su organización. La función de los datos adjuntos seguros de ATP protege a la organización de acuerdo con [las directivas de los datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md) que se han establecido por su Office 365 globales o los administradores de seguridad. 
  
Recientemente, protección de ATP se ha ampliado a los archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams. Para obtener más información, vea [Office 365 avanzada protección contra amenazas para SharePoint, OneDrive y los equipos de Microsoft](atp-for-spo-odb-and-teams.md).
       
## <a name="how-it-works"></a>Funcionamiento

La característica de los datos adjuntos seguros de ATP comprueba los datos adjuntos de correo electrónico para las personas de su organización. Cuando una directiva de datos adjuntos seguros de ATP es en contexto y alguien cubierto por que Directiva ve su correo electrónico en Office 365, se comprueban los datos adjuntos de correo electrónico y se toman las acciones adecuadas, en función de las directivas de los datos adjuntos seguros de ATP. Dependiendo de cómo se definen las directivas, las personas pueden continuar trabajando sin necesidad de conocer nunca que se enviaron archivos malintencionados.
  
Aquí hay dos ejemplos de datos adjuntos seguros de ATP en el trabajo.
  
- **Ejemplo 1: datos adjuntos de correo electrónico** Suponga que Lee recibe un mensaje de correo electrónico que tiene datos adjuntos. No es evidente para Lee si los datos adjuntos seguros o realmente contiene malware diseñado para robar las credenciales de usuario de Díaz. En la organización de Díaz, un administrador de seguridad está definida una directiva de datos adjuntos seguros de ATP hace unos pocos días. Con la característica de los datos adjuntos seguros de ATP, los datos adjuntos de correo electrónico se abre y probarse en un entorno virtual antes Lee lo recibe. Si los datos adjuntos se determinan como malintencionado, se quitará automáticamente. Si los datos adjuntos son seguros, se abrirá según lo esperado cuando Lee hace clic en él. 
    
- **En el ejemplo 2: archivo en SharePoint Online** Suponga que Jean recibió un archivo y carga en una biblioteca en SharePoint Online. Jean comparte el vínculo al archivo con el resto del equipo, no saber que el archivo es en realidad malintencionado. Afortunadamente, [ATP para SharePoint, OneDrive y los equipos de Microsoft](atp-for-spo-odb-and-teams.md) detecta el archivo malintencionado y lo bloquea. Unos días más tarde, Chris que se va a abrir el documento. Aunque Chris puede ver que el archivo se encuentra allí, Chris no se puede abrir o compartirlo, lo que impide el archivo malintencionado en equipo de Chris y otros usuarios. 
    
Datos adjuntos seguros de ATP que lleve a cabo el examen se coloque en la misma región donde residen los datos de Office 365. Para obtener más información acerca de la zona geográfica de centro de datos, vea [¿dónde están los datos que se encuentra?](https://products.office.com/where-is-your-data-located?geo=All) 

Las directivas de los datos adjuntos seguros de ATP se pueden aplicar a usuarios específicos o grupos de la organización o para todo el dominio. Además, las directivas de los datos adjuntos seguros de ATP pueden configurarse para usar datos adjuntos de marcador de posición mientras se están analizando datos adjuntos real. Para obtener más información, vea **[configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)**. 
  
## <a name="how-to-get-atp-safe-attachments"></a>Cómo obtener datos adjuntos seguros de ATP

La característica de los datos adjuntos seguros de ATP es parte de [La protección de amenaza avanzada de Office 365](office-365-atp.md). Las características de los datos adjuntos seguros de ATP aplican cuando:
  
- Se configuran las directivas de los datos adjuntos seguros de ATP. (Vea [configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)).
    
- Los usuarios han iniciado sesión en Office 365 mediante su cuenta de trabajo o escuela. (Vea [iniciar sesión en Office 365 o de Office](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)).
    
## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Cómo saber si la protección de los datos adjuntos seguros de ATP es en contexto

Es una buena manera de ver cómo funciona el servicio mediante la [visualización de informes de protección avanzada de amenaza](view-reports-for-atp.md).


[Las directivas de los datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md) debe definirse en orden para la protección de los datos adjuntos seguros de ATP estar en su lugar.   
  
La tabla siguiente describen algunos escenarios de ejemplo. En todos estos casos, se supone que la organización tiene una suscripción a Office 365 que incluye la protección contra amenazas de avanzada.
  
|**Escenario de ejemplo**|**¿Se aplica protección de los datos adjuntos seguros de ATP en este caso?**|
|:-----|:-----|
|Organización de Pat tiene E5 Enterprise de Office 365, pero nadie ha definido ninguna directiva para los datos adjuntos seguros de ATP todavía.  <br/> |No. Aunque la característica está disponible, debe definirse al menos una directiva de datos adjuntos seguros de ATP en orden para la protección de los datos adjuntos seguros de ATP estar en su lugar.  <br/> |
|Lee es un empleado del departamento de ventas de Contoso. Organización de Díaz tiene una directiva de datos adjuntos seguros de ATP en el lugar al que se aplica a los empleados de finanzas sólo.  <br/> |No. En este caso, los empleados de finanzas tendría la protección de los datos adjuntos seguros de ATP, pero otros empleados, incluido el departamento de ventas, podría no hasta que se definen las directivas que incluyan esos grupos.  <br/> |
|Ayer, un administrador de Office 365 en la organización de Jean establece una directiva de datos adjuntos seguros de ATP que se aplica a todos los empleados. Anteriormente en la actualidad, Jean recibió un mensaje de correo electrónico que incluye un archivo adjunto.  <br/> |Sí. En este ejemplo, Jean tiene una licencia para protección avanzada de amenaza y se ha definido una directiva de datos adjuntos seguros de ATP que incluye Jean. Normalmente tiene unos 30 minutos para una nueva directiva tener efecto en centros de datos; Dado que un día ha pasado en este caso, la directiva debe ser en vigor.  <br/> |
|Organización de Chris tiene E5 Enterprise de Office 365 con las directivas de los datos adjuntos seguros de ATP en contexto para todas las personas de la organización. Chris recibe un correo electrónico que tiene datos adjuntos y reenvía el mensaje a otras personas que están fuera de la organización.  <br/> |Protección de los datos adjuntos seguros de ATP es en lugar de los mensajes que recibe de Chris. Si las organizaciones de los destinatarios también tienen las directivas de los datos adjuntos seguros de ATP en su lugar, el mensaje que se reenvía Chris sería sujetos a dichas directivas cuando llegue el mensaje reenviado.  <br/> |
|Organización de Pablo tiene directivas de datos adjuntos seguros de ATP en su lugar, y se ha activado [ATP para SharePoint, OneDrive y los equipos de Microsoft](atp-for-spo-odb-and-teams.md) . Pablo se supone que todos los archivos de SharePoint Online se ha analizado y es seguro para abrir o descargar.<br/> |Protección de los datos adjuntos seguros de ATP está en su lugar según las directivas que se definen; Sin embargo, esto significa que se examinan todos los archivos en SharePoint Online, OneDrive para el negocio o Microsoft Teams. (Para obtener más información, vea [ATP para SharePoint, OneDrive y los equipos de Microsoft](atp-for-spo-odb-and-teams.md)).<br/> |
   
## <a name="submitting-files-for-malware-analysis"></a>Envío de archivos para el análisis de malware

- Si recibe un archivo que se va a solicitar a Microsoft para analizar, visite [Enviar un archivo para el análisis de malware](https://aka.ms/wdsi/submit).

- Si recibe un mensaje de correo electrónico (con o sin datos adjuntos) que desea enviar a Microsoft para su análisis, use el [complemento en el mensaje de informe](enable-the-report-message-add-in.md).
  
