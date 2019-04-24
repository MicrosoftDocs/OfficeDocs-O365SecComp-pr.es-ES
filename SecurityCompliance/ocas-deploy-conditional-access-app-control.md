---
title: Implementar el Control de aplicaciones de acceso condicional para las aplicaciones de Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Siga estos pasos para configurar las aplicaciones de Azure AD Office 365 para que se controlen con el control de aplicación de acceso condicional de seguridad de aplicación de nube de Office 365.
ms.openlocfilehash: 72be95b3213b90cfe60d851d0852d465cdbe6ef9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263122"
---
# <a name="deploy-conditional-access-app-control-for-office-365-apps"></a>Implementar el Control de aplicaciones de acceso condicional para las aplicaciones de Office 365

|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Siguiente paso](ocas-session-policies.md) <br/> |[Empezar a usar](utilization-activities-for-ocas.md) <br/> |

Siga estos pasos para configurar las aplicaciones de Azure AD Office 365 para que se controlen con el control de aplicación de acceso condicional de seguridad de aplicación de nube de Office 365.

**Paso 1: [crear una directiva de prueba de acceso condicional de Azure ad](#step-1-create-an-azure-ad-conditional-access-test-policy)**

**Paso 2: [iniciar sesión con un usuario en el ámbito de la Directiva en las aplicaciones](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**

**Paso 3: Si no seleccionó una directiva de seguridad de aplicaciones en la nube integrada en Azure AD o si quiere aplicar la Directiva a una aplicación no destacada, configure los [controles avanzados en Cloud App Security portal](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal) .**

**Paso 4: [probar la implementación](#step-4-test-the-deployment)**

> [!IMPORTANT]
> para implementar el Control de aplicaciones de acceso condicional para las aplicaciones de Office 365, necesitará una [licencia válida para Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) , así como una licencia de seguridad de la aplicación de nube de office 365.

## <a name="step-1-create-an-azure-ad-conditional-access-test-policy"></a>Paso 1: crear una directiva de prueba de acceso condicional de Azure AD 

1. En Azure Active Directory, en **seguridad**, haga clic en **acceso condicional**.

2. Haga clic en **nueva Directiva** y cree una nueva Directiva.

3. En la Directiva de pruebas, en **usuarios**, asigne un usuario o usuario de prueba que se pueda usar para el inicio de sesión inicial y la comprobación.

4. En la Directiva de pruebas, en aplicación de la **nube**, asigne las aplicaciones que quiera controlar con el control de aplicación de acceso condicional.

5. En **sesión**, establezca la Directiva para que use cualquiera de las directivas integradas, **supervise solo** o **bloquee las descargas**. O seleccione **usar Directiva** personalizada para establecer una directiva avanzada en Cloud App Security portal.

6. Agregue las **asignaciones** de condición aplicables o conceda **los controles** (opcional).

> ![Acceso condicional de Azure AD](media/image1.png)

## <a name="step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps"></a>Paso 2: iniciar sesión con un usuario en el ámbito de la Directiva en las aplicaciones 

Una vez que haya creado la Directiva, inicie sesión en cada una de las aplicaciones configuradas en dicha Directiva. Asegúrese de iniciar sesión con un usuario configurado en la Directiva. Asegúrese de cerrar primero la sesión de las sesiones existentes.

Cloud App Security sincronizará los detalles de la Directiva con sus servidores para cada nueva aplicación en la que inicie sesión. Esto puede tardar hasta un minuto.

## <a name="step-3-configure-advanced-controls-in-the-cloud-app-security-portal"></a>Paso 3: configurar controles avanzados en Cloud App Security portal 

Las instrucciones anteriores le ayudaron a crear una directiva de seguridad de aplicación en la nube integrada para las aplicaciones destacadas directamente en Azure AD.

para configurar una directiva avanzada, cree una directiva de [acceso](ocas-access-policies.md) o una [directiva](ocas-session-policies.md) de sesión en el portal de seguridad de aplicaciones de nube de Office 365.

### <a name="to-identify-devices-using-client-certificates-this-is-optional"></a>Para identificar los dispositivos que usan certificados de cliente (esto es opcional):

1. Vaya a la configuración COG y elija **identificación del dispositivo**.

2. Cargar uno o más certificados raíz o intermedios.

3. Una vez cargado el certificado, puede crear directivas de acceso y directivas de sesión basadas en la **etiqueta de dispositivo** y el **certificado de cliente válido**.

![IDENTIFICADOR de dispositivo de control de aplicación de acceso condicional](media/image2.png)

> [!NOTE]
> Solo se solicita un certificado a un usuario si la sesión coincide con una directiva que usa el filtro de certificado de cliente válido.
> 
## <a name="step-4-test-the-deployment"></a>Paso 4: probar la implementación 

1. Primero cierre la sesión de las sesiones existentes. A continuación, intente iniciar sesión en cada aplicación que se implementó correctamente. Inicie sesión con un usuario que coincida con la Directiva configurada en Azure AD.

2. En Cloud App Security portal, en **investigar**, seleccione **registro de actividades**y asegúrese de que se capturan las actividades de inicio de sesión de cada aplicación.

3. Puede filtrar haciendo clic en **avanzadas**y, a continuación, filtrando mediante el **control de acceso de origen es igual**a.

4. Se recomienda iniciar sesión en aplicaciones móviles y de escritorio desde dispositivos administrados y no administrados. Esto es para asegurarse de que las actividades se capturan correctamente en el registro de actividades. Para comprobar que la actividad se ha capturado correctamente, haga clic en un inicio de sesión de inicio de sesión único en el que se abre el cajón de actividades. Asegúrese de que la **etiqueta** de agente de usuario refleja correctamente si el dispositivo es un cliente nativo (es decir, una aplicación móvil o de escritorio) o si es un dispositivo administrado (compatible, unido a un dominio o un certificado de cliente válido).

> [!NOTE]
> Una vez implementada, no se puede quitar una aplicación de la página de control de la aplicación de acceso condicional. Siempre que no se establezca una directiva de acceso o sesión en la aplicación, el control de aplicación de acceso condicional no cambiará ningún comportamiento de la aplicación.

## <a name="next-steps"></a>Pasos siguientes

- [Obtener información sobre las directivas de sesión en Office 365 Cloud App Security](ocas-session-policies.md)

- [Obtenga información sobre las directivas de acceso en Office 365 Cloud App Security](ocas-access-policies.md) 

- [Agrupar las direcciones IP para simplificar la administración en Office 365 Cloud App Security](group-your-ip-addresses-in-ocas.md)