---
title: Suspender o restaurar una cuenta de usuario en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Con Office 365 en la nube seguridad de la aplicación, puede realizar las acciones de gobierno son suspender o quitar la suspensión de una cuenta de usuario. '
ms.openlocfilehash: 09d6ae870aa1a6b0a619ccf20f8cc19b392e23a8
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014852"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a>Suspender o restaurar una cuenta de usuario en Office 365 Cloud App Security

Administración avanzada de seguridad de Office 365 es ahora de seguridad de la aplicación de nube de Office 365.
  
|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Comenzar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |¡Están aquí!  <br/> [Pasos siguientes](suspend-or-restore-an-account-in-ocas.md#nextsteps) <br/> |
   
Suponga que recibe una alerta que se ha comprometido una de las cuentas de usuario de la organización para Office 365. O bien, suponga que ha recibido una alerta que indica que algo es incorrecto con una cuenta de usuario. Con la seguridad de la aplicación de nube de Office 365, puede suspender una cuenta de usuario y restaurarla más adelante después de haber investigar las alertas que reciba.
  
> [!NOTE]
> Seguridad de la aplicación de Office 365 en la nube está disponible en Office 365 Enterprise E5. Si su organización usa otra suscripción de Office 365 Enterprise, seguridad de la aplicación de nube de Office 365 puede adquirirse como un complemento. (Como administrador global, en el centro de administración de Office 365, elija **facturación** \> **Agregar suscripciones**.) Para obtener más información, vea [Descripción del servicio Office 365 plataforma: seguridad de Office 365 &amp; centro de cumplimiento](https://technet.microsoft.com/en-us/library/dn933793.aspx) y [comprar o editar un complemento de Office 365 para profesionales](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6). 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a>Para suspender una cuenta de usuario en la seguridad de la aplicación de nube de Office 365

Cuando se suspende una cuenta de usuario, se evita que el usuario de iniciar sesión de nuevo. Es la misma que la cuenta de usuario directamente en Office 365 para establecer el estado de inicio de sesión para el **Inicio de sesión bloqueado**de edición.
  
> [!NOTE]
> Si bloquea un usuario de inicio de sesión en Office 365, ya sea por ellos suspender o mediante la edición de su estado de inicio de sesión, tenga en cuenta que puede tardar una hora o lo surta efecto en todos los dispositivos y clientes ([Editar o cambiar un usuario en Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)) del usuario. Si el usuario ha iniciado sesión en Office 365, el bloque de surtirán efecto siempre que Office 365 requiere que inicien sesión nuevo. 
  
1. Como [administrador global o administrador de seguridad](permissions-in-the-security-and-compliance-center.md), vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela. (Esto le llevará a la seguridad &amp; centro de cumplimiento.) 
    
2. En la seguridad &amp; centro de cumplimiento, elija **alertas** \> **avanzada de administrar las alertas**.
    
3. Elija **Ir a la seguridad de la aplicación de Office 365 en la nube**.<br>![En la seguridad &amp; centro de cumplimiento, elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>
  
4. En la barra de navegación a través de la parte superior de la pantalla, elija **alertas**.
    
5. En la columna de la **alerta** , haga doble clic en una alerta que pertenece a una cuenta de usuario específica. 
    
6. En **las cuentas**, en la columna **estado** , elija configuración ![icono configuración](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **usuario Suspend**.
    
## <a name="to-restore-a-user-account"></a>Para restaurar una cuenta de usuario

Vea [restaurar un usuario en Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)
  
## <a name="next-steps"></a>Pasos siguientes

- [Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security](review-office-365-cas-alerts.md)
    
- [Administrar aplicaciones de OAuth con Office 365 Cloud App Security](manage-app-permissions-in-ocas.md)
    
- Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)
    

