---
title: Puntuación segura de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/25/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: ¿Se ha preguntado cómo proteger su organización es realmente en Office 365? Puntuación seguro está aquí para ayudar a. Puntuación seguro analiza la seguridad de su organización en función de sus actividades normales y la configuración de seguridad en Office 365 y asigna una puntuación.
ms.openlocfilehash: bc0379e40b09e63e5fded1b1a289d40c306def91
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29559093"
---
# <a name="office-365-secure-score"></a>Puntuación segura de Office 365

**Resumen** ¿Se ha preguntado cómo proteger su organización es realmente en Office 365? Puntuación seguro está aquí para ayudar a. Puntuación seguro analiza la seguridad de su organización en función de sus actividades normales y la configuración de seguridad en Office 365 y asigna una puntuación. Lea este artículo para obtener una visión general de puntuación de seguro y cómo puede usarlo.
  
## <a name="how-to-get-to-secure-score"></a>Cómo llegar a la puntuación de seguro

Si su organización tiene una suscripción que incluye [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/)o Premium de negocio de Office 365 y, si tiene los [permisos necesarios](#required-permissions), puede ver la puntuación seguro de su organización visitando [https://securescore.office.com](https://securescore.office.com). 

Como alternativa, puede visitar el centro de cumplimiento de seguridad & ([https://protection.office.com](https://protection.office.com)), donde encontrará un widget de puntuación seguro que se proporciona con su calificación actual.

![Widget de puntuación seguro](media/SecureScoreWidget-o365.png)

El widget incluye un vínculo al panel puntuación seguro.

![Panel de puntuación seguro](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a>Funcionamiento

Puntuación seguro determina qué servicios de Office 365 está usando (por ejemplo, OneDrive, SharePoint y Exchange), a continuación, se comparan las configuraciones y las actividades de una línea de base establecida por Microsoft. Obtendrá una puntuación en función de cómo bien alineada a la organización es con procedimientos recomendados de seguridad. También obtendrá recomendaciones en los pasos que puede realizar para mejorar la puntuación de su organización. 
  
![Cola de acciones de la herramienta de Office 365 seguro puntuación](media/SecureScore-ActionsToTake.png)
  
Puntuación de seguro calcula la puntuación basada en los servicios que ha comprado. Por ejemplo, si ha comprado solo un plan de Exchange Online, no se tuvo para características de seguridad de SharePoint Online. El denominador de la puntuación es la suma de todas las líneas de base para los controles que se aplican a los productos que ha comprado. El numerador es la suma de todos los controles para los que completado o parcialmente completado, las acciones para cumplir con ese control.

Expanda una acción para obtener información sobre qué pasos que deben seguirse, protegen las amenazas que le ayudará desde y el número de puntos que aumentará su puntuación una vez seguir la recomendación.
  
![Acción expandida en la herramienta de Office 365 seguro puntuación](media/SecureScore-DetailedActionToTake.png)
  
Para ver el impacto de sus acciones en la seguridad de su organización, seleccione la ficha **Del analizador de puntuación** y revisar el historial. 
  
![Ficha de puntuación del analizador de la herramienta de Office 365 seguro puntuación](media/SecureScore-ScoreAnalyzer-7days.png)
  
Debajo del gráfico, verá una lista de acciones y las puntuaciones por categoría. 
  
![En la ficha del analizador de puntuación que muestra un punto de datos seleccionado de gráfico](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
Acciones que están etiquetadas como **[No una puntuación]** son los que se puede realizar para su organización, pero debido a que no están conectados a la puntuación de seguro, no se cuentan.  

En la página **Analizador de puntuación** , haga clic en un punto de datos para un día específico, a continuación, desplácese hacia abajo para ver las acciones completadas e incompletas para ese día para averiguar qué ha cambiado. La puntuación se calcula una vez al día (aproximadamente 1:00 AM PST). Si realiza un cambio en una acción medida, la puntuación actualizará automáticamente el día siguiente. Se tardan hasta 48 horas para que un cambio se refleja en su puntuación.

Puntuación seguro no express una medida absoluta de cómo es probable que van a obtener tipo de brecha. Expresa la medida a la que han adoptado las características que pueden desplazar el riesgo de que se pueda infringir. No hay ningún servicio puede garantizar que va a no ser tipo de brecha y la puntuación de seguro no se debe interpretar como una garantía de ninguna forma.
 
## <a name="how-secure-score-helps"></a>Cómo ayuda proteger puntuación

Con la puntuación de seguro, puede ayudar a mejorar la posición de seguridad de su organización mediante el uso de las características de seguridad integradas en Office 365 (muchas de las cuales ya adquirido pero es posible que no tenga). Aprender más acerca de estas características puede ayudar a su tranquilidad de que va a llevar los pasos adecuados para proteger su organización contra las amenazas.
  
Pero no sólo nuestra palabra de él. Los clientes que usen puntuación seguro han visto sus puntuación aumentar cinco veces mayor que los clientes que no son lo utilizan. (El aumento en su puntuación se corresponde con las características de seguridad que se usan en las organizaciones).
  
> [!NOTE]
> Puntuación seguro no express una medida absoluta de cómo es probable que van a obtener tipo de brecha. Expresa la medida a la que han adoptado los controles que pueden desplazar el riesgo de que se pueda infringir. Ningún servicio puede garantizar que no se pueda infringir y puntuación seguro no se debe interpretar como una garantía de ninguna forma. 
  
## <a name="required-permissions"></a>Permisos necesarios

Para poder ver y usar el panel de puntuación seguro, debe asignar uno de los siguientes roles en Azure Active Directory:
- Administrador global
- Administrador de facturación
- Administrador de usuarios
- Administrador de contraseñas
- Administrador de seguridad
- Lector de seguridad
- Administrador de Exchange
- Administrador de SharePoint

 Los usuarios que no están asignados a un rol de administrador no podrán tener acceso a la puntuación de seguro.

## <a name="related-topics"></a>Temas relacionados

[Información general del panel de seguridad](security-dashboard.md)

[¿Qué suscripción tengo?](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)