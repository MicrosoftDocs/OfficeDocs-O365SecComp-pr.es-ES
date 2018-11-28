---
title: Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: Revisión de informes de detección de aplicaciones en administración avanzada de seguridad le ayudarán a obtener más información acerca de cómo las personas de su organización utilizan aplicaciones de nube. Después de crear informes de detección de aplicación con archivos de registro de los firewalls y servidores proxy, revise los resultados en el panel de la detección de la aplicación.
ms.openlocfilehash: ddf3826f5aac9d3c837cf66f1b97b4650df70f32
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706264"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a>Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security
  
|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Comenzar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |¡Están aquí!  <br/> [Pasos siguientes](#next-steps) <br/> |
   
El panel de detección de la nube funciona con registros de tráfico web de la organización para proporcionar información detallada sobre el uso de la aplicación en la nube. Si usted es un administrador global, Administrador de seguridad o lector de seguridad y su organización tiene [creado informes de detección de aplicaciones en la seguridad de la aplicación de nube de Office 365](create-app-discovery-reports-in-ocas.md), puede usar el panel de detección en la nube para comprender mejor cómo de personas en su organización está usando Office 365 y otras aplicaciones en la nube. (El panel de detección de la nube también conocido como está detección de aplicaciones de productividad).
  
 **A partir de marzo 2018, el panel de detección de la nube tiene nuevas características** que hacen que sea más fácil ver información detallada acerca de cómo las personas de su organización están usando Office 365 y otras aplicaciones. 
  
![Se ha actualizado el panel detección de nube](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a>Vaya al panel de detección de la nube

1. Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela para Office 365. (Esto le llevará a la seguridad &amp; centro de cumplimiento.) 
    
2. En la seguridad &amp; centro de cumplimiento, elija **alertas** \> **avanzada de administrar las alertas**.<br/>(Si no está habilitado aún seguridad de la aplicación de nube de Office 365, y debe ser un administrador global, [activar la seguridad de la aplicación de nube de Office 365](turn-on-office-365-cas.md).)
    
3. Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.
    
4. Vaya a **descubrir** \> **panel de detección de la nube**.
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a>Vea sus usuarios principales, direcciones IP, aplicaciones y niveles de riesgo

El panel de detección de la nube le ofrece una introducción de un vistazo a las aplicaciones que se usan con Office 365 en su organización, cualquier alertas abiertas, superior a los usuarios y niveles de riesgo.
  
![Dashboaard de detección de la nube](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. En la ficha de **panel** , examine el uso de aplicación en la nube global en la organización en la sección información general en la parte superior de la pantalla. 
    
2. Ver las **categorías de Office 365** para las aplicaciones que se usan en su organización. 
    
3. Examine el widget **Discovered aplicaciones** para ver el uso de Office 365 y otras aplicaciones en esta vista. 
    
4. Examine el widget **superior a los usuarios** y **las direcciones IP de la parte superior** para identificar aquellos que usar Office 365 y en la nube de aplicaciones en la mayor parte de la organización. 
    
5. Vea dónde están las aplicaciones que usan las personas por ubicación geográfica mediante el uso de la asignación de **ubicación de sedes centrales de aplicaciones** . 
    
6. Sobre el área de mapas, eche un vistazo en la puntuación de riesgo de las aplicaciones descubiertas en la información general de **los niveles de riesgo** . Puede mirar los riesgos por los mismos grupos y categorías que se usaron en el área de **aplicaciones Discovered** . Por ejemplo, puede ver es la cantidad de tráfico en cada agrupación de aplicaciones de riesgo alto, medio o bajo. 
    
## <a name="dive-deeper-into-the-information"></a>Profundizan en la información

Puede usar la detección en la nube para Eche un vistazo más profundo de aplicaciones, subdominios, direcciones IP y los usuarios.
  
1. En el panel de la detección de la nube, elija la ficha **Discovered aplicaciones** . 
    
2. Use la sección filtros para ver aplicaciones por nombre, categoría, el nivel de uso o última fecha visto.
    
3. En la lista de resultados, pase el ratón por un nombre de la aplicación para mostrar el vínculo **Ver subdominios** .<br/> ![Mantenga el mouse junto a una aplicación para mostrar un vínculo para ver los detalles de subdominio](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)<br/>Aparecerá información detallada sobre la aplicación seleccionada.
    
4. Para ver detalles acerca de las direcciones IP, elija la pestaña **direcciones IP** .<br/>![Detección de la nube muestra información detallada acerca de las direcciones IP](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)<br/>En la lista de resultados, seleccione una dirección IP individual para ver información más detallada.
    
5. Para ver detalles acerca de los usuarios de Office 365 dentro de la organización, elija la pestaña de **los usuarios** .<br/>![Detección de nube - información de los usuarios](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)
  
## <a name="exclude-entities"></a>Excluir las entidades

Puede excluir determinados usuarios del sistema o las direcciones IP con el fin de centrarse en información más específica.
  
1. Elija **configuración** \> **configuración de detección de la nube**.
    
2. Elija **excluir las entidades**.
    
3. Elija **los usuarios excluidos** o **direcciones IP excluidos**.
    
4. Especificar los usuarios o las direcciones IP y, en el cuadro **comentarios** , escriba información acerca de por qué se van a excluir los usuarios o direcciones IP. 
    
5. Elija **Agregar**.
    
## <a name="next-steps"></a>Pasos siguientes

- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- [Crear informes de detección de aplicaciones](create-app-discovery-reports-in-ocas.md)
    
- Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)
    

