---
title: Puntuación segura de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: ¿Alguna vez se ha preguntado cómo proteger su organización realmente en Office 365? La puntuación segura está aquí para ayudar. La puntuación segura analiza la seguridad de la organización en función de las actividades habituales y la configuración de seguridad de Office 365 y asigna una puntuación.
ms.openlocfilehash: cf272869981dd73e1ceb4bd7180cc16acaed0516
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2019
ms.locfileid: "29992364"
---
# <a name="office-365-secure-score"></a>Puntuación segura de Office 365

**Resumen** ¿Alguna vez se ha preguntado cómo proteger su organización realmente en Office 365? La puntuación segura está aquí para ayudar. La puntuación segura analiza la seguridad de la organización en función de las actividades habituales y la configuración de seguridad de Office 365 y asigna una puntuación. Lea este artículo para obtener información general sobre la puntuación segura y cómo usarla.
  
## <a name="how-to-get-to-secure-score"></a>Cómo obtener una puntuación segura

Si su organización tiene una suscripción que incluye [office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 business](https://docs.microsoft.com/microsoft-365/business/)o Office 365 Business Premium, y tiene los [permisos necesarios](#required-permissions), puede ver la puntuación segura de su organización visitando [https://securescore.office.com](https://securescore.office.com). 

Como alternativa, puede visitar el centro de seguridad & cumplimiento ([https://protection.office.com](https://protection.office.com)), donde encontrará un widget de puntuación segura que le proporcionará el resultado actual.

![Widget de calificación segura](media/SecureScoreWidget-o365.png)

El widget incluye un vínculo a su panel de calificaciones seguras.

![Panel de calificaciones seguras](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a>Funcionamiento

La puntuación segura determina qué servicios de Office 365 está usando (como OneDrive, SharePoint y Exchange), a continuación, compara la configuración y las actividades con una línea base establecida por Microsoft. Obtendrá una puntuación según el grado de alineación de la organización con los procedimientos recomendados de seguridad. También obtendrá recomendaciones sobre los pasos que puede realizar para mejorar la puntuación de su organización. 
  
![Cola de acciones en la herramienta de puntuación segura de Office 365](media/SecureScore-ActionsToTake.png)
  
Puntuación segura calcula la puntuación en función de los servicios adquiridos. Por ejemplo, si solo compró un plan de Exchange Online, no recibirá ninguna de las características de seguridad de SharePoint Online. El denominador de la puntuación es la suma de todas las líneas de base de los controles que se aplican a los productos adquiridos. El numerador es la suma de todos los controles para los que ha completado, o parcialmente, las acciones para completar ese control.

ExPanda una acción para obtener información sobre los pasos que se deben seguir, las amenazas a las que se va a proteger y cuántos puntos aumentará la puntuación una vez que se sigue la recomendación.
  
![Acción expandida en la herramienta de puntuación segura de Office 365](media/SecureScore-DetailedActionToTake.png)
  
Para ver el impacto de las acciones en la seguridad de la organización, seleccione la ficha **analizador de puntuación** y revise el historial. 
  
![Ficha analizador de puntuación de la herramienta de puntuación segura de Office 365](media/SecureScore-ScoreAnalyzer-7days.png)
  
Debajo del gráfico, verá una lista de calificaciones y acciones por categoría. 
  
![Gráfico en la ficha analizador de puntuaciones que muestra un punto de datos seleccionado](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
Las acciones etiquetadas como **[no puntuadas]** son las que se pueden realizar para la organización, pero porque no están conectadas a la puntuación segura, no se puntuan.  

En la página **analizador de puntuación** , haga clic en un punto de datos para un día específico y, a continuación, desplácese hacia abajo para ver las acciones completadas y incompletas de ese día para averiguar qué ha cambiado. La puntuación se calcula una vez al día (alrededor de 1:00 A.M. PST). Si realiza un cambio en una acción medida, la puntuación se actualizará automáticamente el día siguiente. Tarda hasta 48 horas en reflejarse un cambio en su puntuación.

La puntuación segura no expresa una medida absoluta de la probabilidad de que se infrinja. Expresa en qué medida ha adoptado características que pueden compensar el riesgo de infringirse. Ningún servicio puede garantizar que no se infrinja y la calificación segura no se debe interpretar como garantía de ningún modo.
 
## <a name="how-secure-score-helps"></a>Cómo ayuda la puntuación segura

Con la puntuación segura, puede ayudar a mejorar la postura de seguridad de su organización mediante las características de seguridad integradas en Office 365 (muchas de las cuales ya compró pero podrían no tener en cuenta). Obtener más información sobre estas características puede ayudarle a tener la tranquilidad de que está llevando a cabo los pasos correctos para proteger su organización de las amenazas.
  
Pero no solo tiene que tomar nuestra palabra. Los clientes que usan la puntuación segura han observado su puntuación en cinco veces mayor que los clientes que no la usan. (El aumento de la puntuación se corresponde con las características de seguridad que se usan en sus organizaciones).
  
> [!NOTE]
> La puntuación segura no expresa una medida absoluta de la probabilidad de que se infrinja. Expresa la medida en que ha adoptado los controles que pueden compensar el riesgo de infringirse. Ningún servicio puede garantizar que no se infrinja y la puntuación segura no se debe interpretar como garantía de ningún modo. 
  
## <a name="required-permissions"></a>Permisos necesarios

Para poder ver y usar el panel de calificaciones seguras, debe tener asignado uno de los siguientes roles en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles):
- Administrador global
- Administrador de facturación
- Administrador de usuarios
- Administrador de contraseñas
- Administrador de seguridad
- Lector de seguridad
- Administrador de Exchange
- Administrador de SharePoint

 Los usuarios a los que no se les ha asignado un rol de administrador no podrán tener acceso a la puntuación segura.

## <a name="related-topics"></a>Temas relacionados

[Introducción al panel de seguridad](security-dashboard.md)

[¿Qué suscripción tengo?](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)
