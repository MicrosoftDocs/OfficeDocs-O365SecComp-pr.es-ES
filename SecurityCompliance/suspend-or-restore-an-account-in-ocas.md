---
title: Suspender o restaurar una cuenta de usuario en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Con Office 365 Cloud App Security, las acciones de gobierno que puede realizar son suspender o anular la suspensión de una cuenta de usuario. '
ms.openlocfilehash: 10da1385f850fadf077b4e3f9e3a00e9e4629fdd
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862452"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a>Suspender o restaurar una cuenta de usuario en Office 365 Cloud App Security

|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Siguientes pasos](#next-steps)<br/> |
   
SuPongamos que recibe una alerta de que una de las cuentas de usuario de su organización para Office 365 ha estado en peligro. O bien, supongamos que ha recibido una alerta que indica que hay algún error en una cuenta de usuario. Con Office 365 Cloud App Security, puede suspender una cuenta de usuario y restaurarla más tarde una vez que haya investigado las alertas que recibe.
  
> [!NOTE]
> Office 365 Cloud App Security está disponible en Office 365 Enterprise E5. Si su organización usa otra suscripción de Office 365 Enterprise, Office 365 Cloud App Security puede adquirirse como un complemento. (como administrador global, en el centro de administración de Office 365, elija **facturación** \> **Add**subscriptions). Para obtener más información, consulte [office 365 Platform Service Description: office &amp; 365 Security Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) y [comprar o editar un complemento para Office 365 para empresas](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6). 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a>Para suspender una cuenta de usuario en Office 365 Cloud App Security

Al suspender una cuenta de usuario, se impide que el usuario inicie sesión de nuevo. Es lo mismo que editar la cuenta de usuario directamente en Office 365 para establecer el estado de inicio de sesión para **iniciar sesión bloqueado**.
  
> [!NOTE]
> Si impide que un usuario inicie sesión en Office 365, ya sea suspendiendo los cambios o editando su estado de inicio de sesión, tenga en cuenta que puede tardar una hora o para que surtan efecto en todos los clientes y dispositivos del usuario ([Editar o cambiar un usuario en Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)). Si el usuario ha iniciado sesión en Office 365, el bloque entrará en vigor siempre que Office 365 lo requiera volver a iniciar sesión. 
  
1. Como [administrador global o administrador de seguridad](permissions-in-the-security-and-compliance-center.md), vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa. (Esto le llevará al centro de &amp; seguridad y cumplimiento). 
    
2. En el centro &amp; de seguridad y cumplimiento, elija **alertas** \> **Administrar alertas avanzadas**.
    
3. Elija **ir a Office 365 Cloud App Security**.<br>![En el centro &amp; de seguridad y cumplimiento, elija Administrar alertas avanzadas para ir a Office 365 Cloud App Security.](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>
  
4. En la barra de navegación en la parte superior de la pantalla, elija **alertas**.
    
5. En la columna **alerta** , haga doble clic en una alerta que pertenezca a una cuenta de usuario específica. 
    
6. En **cuentas**, en la columna **Estado** , ![elija configuración configuración icono](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **suspender usuario**.
    
## <a name="to-restore-a-user-account"></a>Para restaurar una cuenta de usuario

Vea [restaurar un usuario en Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)
  
## <a name="next-steps"></a>Pasos siguientes

- [Revisar y realizar acciones sobre alertas en Office 365 Cloud App Security](review-office-365-cas-alerts.md)
    
- [Administrar aplicaciones de OAuth con Office 365 Cloud App Security](manage-app-permissions-in-ocas.md)
    
- Revisar las [actividades de uso de Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    

