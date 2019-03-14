---
title: Directivas de acceso en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Las directivas de acceso de Office 365 Cloud App Security permiten la supervisión y el control en tiempo real del acceso a las aplicaciones en la nube en función del usuario, la ubicación, el dispositivo y la aplicación. Puede crear directivas de acceso para cualquier dispositivo, incluidos los dispositivos que no están Unidos a un dominio y que Windows Intune no administra mediante la implementación de certificados de cliente en dispositivos administrados o mediante el uso de certificados existentes, como certificados MDM de terceros. Por ejemplo, puede implementar certificados de cliente en dispositivos administrados y, a continuación, bloquear el acceso desde dispositivos sin un certificado.
ms.openlocfilehash: 5e8b8fa293420bc9ff3616daf288b8e02a2eb768
ms.sourcegitcommit: 866d8cab6bcfdd124516a8369e47ec797bc7cf8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2019
ms.locfileid: "30312087"
---
# <a name="access-policies-in-office-365-cloud-app-security"></a>Directivas de acceso en Office 365 Cloud App Security

|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Paso siguiente](group-your-ip-addresses-in-ocas.md) <br/> |[Empezar a usar](utilization-activities-for-ocas.md) <br/> |

Las directivas de acceso de Office 365 Cloud App Security permiten la supervisión y el control en tiempo real del acceso a las aplicaciones en la nube en función del usuario, la ubicación, el dispositivo y la aplicación. Puede crear directivas de acceso para cualquier dispositivo, incluidos los dispositivos que no están Unidos a un dominio y que Windows Intune no administra mediante la implementación de certificados de cliente en dispositivos administrados o mediante el uso de certificados existentes, como certificados MDM de terceros. Por ejemplo, puede implementar certificados de cliente en dispositivos administrados y, a continuación, bloquear el acceso desde dispositivos sin un certificado.

En lugar de permitir o bloquear completamente el acceso, con [directivas](ocas-session-policies.md) de sesión puede permitir el acceso a la vez que supervisa la sesión o limita actividades de sesión específicas.

## <a name="prerequisites-to-using-access-policies"></a>Requisitos previos para usar directivas de acceso

- Licencia de Azure AD Premium P1

- Las aplicaciones relevantes deben [implementarse con el control de aplicación de acceso condicional](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)

- debe haber una  [directiva de acceso condicional de Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)que redirija a los usuarios a Office 365 Cloud App Security, como se describe a continuación.

## <a name="create-an-azure-ad-conditional-access-policy"></a>Crear una directiva de acceso condicional de Azure AD

Directivas de acceso condicional de Azure Active Directory y directivas de sesión de Cloud App Security trabajan conjuntamente para examinar cada sesión de usuario y tomar decisiones de directiva para cada aplicación. Para configurar una directiva de acceso condicional en Azure AD, siga este procedimiento:

1. Configure una  [Directiva de acceso condicional de Azure ad](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)con asignaciones para el usuario o grupo de usuarios y la aplicación que quiera controlar con el control de aplicación de acceso condicional.<br>Nota: esta directiva solo afectará a las aplicaciones que se implementaron con el  [control de aplicación de acceso condicional](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad).

2. enrutar a los usuarios a Office 365 Cloud App Security seleccionando la opción **usar Control de aplicación de acceso condicional en restricciones** forzadas en la **sesión**.

## <a name="create-a-cloud-app-security-access-policy"></a>Crear una directiva de acceso de Cloud App Security

Para crear una nueva Directiva de acceso, siga este procedimiento:

1. En el portal, seleccione **control** seguido de **directivas**.

2. En la página **directivas** , haga clic en **crear Directiva** y seleccione **Directiva de acceso**.

3. En la ventana **Directiva** de acceso, asigne un nombre a la Directiva, como *bloquear el acceso desde dispositivos no administrados*.

4. En la sección **actividades que coinciden con todas las de la siguiente** sección, en origen de la **actividad**, seleccione filtros de actividad adicionales para aplicarlos a la Directiva. Los filtros incluyen las siguientes opciones:
    
    - **Etiquetas de dispositivo**: Use este filtro para identificar los dispositivos no administrados.
    
    - **Ubicación**: Use este filtro para identificar ubicaciones desconocidas (y, por lo tanto, arriesgadas).
    
    - **Dirección IP**: Use este filtro para filtrar por direcciones IP o use etiquetas de direcciones IP asignadas previamente.
    
    - **Etiqueta de agente de usuario**: Use este filtro para habilitar la heurística de identificación de aplicaciones móviles y de escritorio. Este filtro se puede establecer en igual a o no es igual a. Los valores deben probarse con sus aplicaciones móviles y de escritorio para cada aplicación en la nube.

5. En **acciones**, seleccione una de las siguientes opciones:
    
    - **Permitir**: establezca esta acción para permitir explícitamente el acceso según los filtros de directiva que establezca.
    
    - **Bloquear**: establezca esta acción para bloquear explícitamente el acceso de acuerdo con los filtros de directiva que establezca.

6. Puede  **crear una alerta para cada evento que coincida con la gravedad de la Directiva**y establecer un límite de alerta y seleccionar si desea la alerta como un correo electrónico, un mensaje de texto o ambos.

## <a name="next-steps"></a>Pasos siguientes

- [Agrupar las direcciones IP para simplificar la administración en Office 365 Cloud App Security](group-your-ip-addresses-in-ocas.md)