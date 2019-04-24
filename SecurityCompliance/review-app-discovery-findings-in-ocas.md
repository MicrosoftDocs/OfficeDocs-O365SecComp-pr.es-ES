---
title: Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: Revisar los informes de detección de aplicaciones en Office 365 Cloud App Security puede ayudarle a obtener más información sobre cómo los usuarios de su organización usan aplicaciones en la nube. Una vez que haya creado los informes de detección de aplicaciones con archivos de registro de los firewalls y servidores proxy, revise los resultados en el panel de detección de aplicaciones.
ms.openlocfilehash: f50ad372450b2a1404829eeb6f6964c1d954dccd
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264992"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a>Revisar los resultados de la detección de aplicaciones en Office 365 Cloud App Security
  
|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Siguientes pasos](#next-steps) <br/> |
   
El panel de detección en la nube funciona con los registros de tráfico web de la organización para proporcionar información detallada sobre el uso de aplicaciones en la nube. Si es administrador global, administrador de seguridad o lector de seguridad y su organización ha [creado informes de detección de aplicaciones en Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md), puede usar el panel de detección en la nube para conocer la forma en que los usuarios de su organización usan Office 365 y otras aplicaciones en la nube. (El panel de detección en la nube también se conoce como detección de aplicaciones de productividad).
  
 El panel de detección en la nube le permite ver información detallada sobre la forma en que los usuarios de su organización usan Office 365 y otras aplicaciones. 
  
![Se ha actualizado el panel de detección en la nube](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a>Ir al panel de detección en la nube

1. Vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.
    
2. Vaya al panel **Descubra** \> **detección en la nube**.
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a>Ver los usuarios principales, las direcciones IP, las aplicaciones y los niveles de riesgo

El panel de detección en la nube le ofrece una visión general de las aplicaciones que se usan con Office 365 en su organización, las alertas abiertas, los usuarios principales y los niveles de riesgo.
  
![Detección en la nube dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. En la pestaña **Panel** , mire el uso general de la aplicación de nube en su organización en la sección información general en la parte superior de la pantalla. 
    
2. Vea las **categorías de Office 365** para las aplicaciones que se usan en su organización. 
    
3. Mire el widget **aplicaciones** descubiertas para ver el uso de Office 365 y otras aplicaciones en esta vista. 
    
4. Mire el widget **principales usuarios** y **direcciones IP principales** para identificar a los usuarios de Office 365 y de la nube la mayor parte de su organización. 
    
5. Vea dónde las aplicaciones que usan los usuarios se encuentran en la ubicación geográfica con el mapa de ubicación de las **oficinas centrales de aplicaciones** . 
    
6. Por encima del área mapas, eche un vistazo a la puntuación de riesgo de las aplicaciones detectadas en la introducción a **los niveles de riesgo** . Puede ver los riesgos en los mismos grupos y categorías que usó en el área de **aplicaciones detectadas** . Por ejemplo, puede ver la cantidad de tráfico de cada agrupación de aplicaciones de riesgo alta, media o baja. 
    
## <a name="dive-deeper-into-the-information"></a>Profundizar más en la información

Puede usar detección en la nube para profundizar en las aplicaciones, subdominios, direcciones IP y usuarios.
  
1. En el panel detección en la nube, elija la pestaña **aplicaciones detectadas** . 
    
2. Use la sección Filtros para ver las aplicaciones por nombre, categoría, nivel de uso o fecha de última visualización.
    
3. En la lista de resultados, mantenga el mouse por un nombre de aplicación para mostrar el vínculo **Ver** subdominios.<br/> ![Mantener el mouse junto a una aplicación para mostrar un vínculo para ver los detalles de subdominio](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)<br/>Se mostrará información detallada sobre la aplicación seleccionada.
    
4. Para ver los detalles de las direcciones IP, seleccione la pestaña **direcciones IP** .<br/>![Detección en la nube muestra información detallada sobre las direcciones IP](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)<br/>En la lista de resultados, seleccione una dirección IP individual para ver información más detallada.
    
5. Para ver información detallada sobre los usuarios de Office 365 dentro de su organización, elija la pestaña **usuarios** .<br/>![Detección en la nube: información de los usuarios](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)
  
## <a name="exclude-entities"></a>Excluir entidades

Puede excluir determinados usuarios del sistema o direcciones IP para poder centrarse en información más específica.
  
1. Elija Configuración de **detección en la nube**. **** \>
    
2. Elija **excluir entidades**.
    
3. Elija **usuarios excluidos** o **direcciones IP excluidas**.
    
4. Especifique los usuarios o las direcciones IP y, en el cuadro **comentarios** , escriba información sobre los motivos por los que se excluyen los usuarios o las direcciones IP. 
    
5. Seleccione **Agregar**.
    
## <a name="next-steps"></a>Pasos siguientes

- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- [Crear informes de detección de aplicaciones](create-app-discovery-reports-in-ocas.md)
    
- Revisar las [actividades de uso de Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    

