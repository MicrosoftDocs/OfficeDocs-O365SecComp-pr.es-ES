---
title: Configurar usuarios y casos en la exhibición de documentos electrónicos avanzada de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Obtenga información sobre cómo configurar roles de usuario, crear casos y asignar usuarios a los casos en Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 5a22e0683e49ebdaf8391e092aeb101386e0636b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260708"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a>Configurar usuarios y casos en la exhibición de documentos electrónicos avanzada de Office 365

En este tema se describe cómo configurar usuarios y casos para la exhibición avanzada de documentos electrónicos de Office 365.
  
> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="prerequisites"></a>Requisitos previos

Antes de configurar casos y usuarios en la exhibición avanzada de documentos electrónicos, se requiere lo siguiente:
  
- Para analizar los datos de un usuario con la exhibición avanzada de documentos electrónicos, el usuario (el custodio de los datos) debe tener asignada una licencia de Office 365 E5. Como alternativa, se puede asignar una licencia independiente de eDiscovery avanzado a los usuarios con una licencia de Office 365 E1 o E3. Los administradores y los responsables de cumplimiento que se asignan a los casos y usan la exhibición avanzada de documentos electrónicos para analizar los datos no necesitan una licencia E5. 
    
- Debe ser miembro del grupo de roles eDiscovery Manager en el centro de seguridad &amp; y cumplimiento de Office 365 para crear un caso de exhibición de documentos electrónicos y agregarle miembros. Para agregarse al grupo de roles de eDiscovery Manager en &amp; el centro de seguridad y cumplimiento, debe ser administrador global de la organización de Office 365. Si no es un administrador global, deberá solicitar a un administrador global que le agregue al grupo de roles eDiscovery Manager. Para más información, visite:
    
  - [Permisos en el centro de seguridad &amp; y cumplimiento de 365 de Microsoft](permissions-in-the-security-and-compliance-center.md)
    
  - [Asignar permisos de eDiscovery en el centro de &amp; seguridad y cumplimiento de 365 de Microsoft](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>Paso 1: asignar permisos de eDiscovery para los usuarios

El primer paso consiste en asignar a los usuarios los permisos de requisitos &amp; en el centro de seguridad y cumplimiento para que puedan agregarse como miembro de un caso de exhibición de documentos electrónicos. Una vez que un usuario se ha agregado como miembro de un caso en &amp; el centro de seguridad y cumplimiento, podrá obtener acceso al caso en la exhibición avanzada de documentos electrónicos.
  
Para asignar a un usuario los permisos necesarios para que se puedan agregar como miembro de un caso de exhibición de documentos electrónicos, vea el paso 1 en [casos de &amp; eDiscovery en el centro de seguridad y cumplimiento de Microsoft 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>Paso 2: crear un caso de exhibición de documentos electrónicos y agregar miembros

El siguiente paso es crear un nuevo caso de exhibición de documentos electrónicos &amp; en el centro de seguridad y cumplimiento y agregar miembros. Los miembros del caso podrán acceder al caso en la exhibición avanzada de documentos electrónicos.
  
1. Para crear un nuevo caso de eDiscovery, vea el paso 2 en [casos de eDiscovery en el &amp; centro de seguridad y cumplimiento de Microsoft 365](ediscovery-cases.md#step-2-create-a-new-case).
    
2. Para agregar miembros a un caso de eDiscovery, vea el paso 3 de [los casos de eDiscovery en &amp; el centro de seguridad y cumplimiento de 365 de Microsoft](ediscovery-cases.md#step-3-add-members-to-a-case) .
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>Paso 3: ir a un caso en eDiscovery avanzado

Después de crear un caso de exhibición de documentos electrónicos y agregar miembros, usted (o cualquier miembro del caso) puede tener acceso al caso correspondiente en eDiscovery avanzado. Para obtener acceso a un caso en la exhibición avanzada de documentos electrónicos, vea el paso 8 en [los casos de eDiscovery en el centro de seguridad &amp; y cumplimiento de Microsoft 365](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).
  
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Preparar datos](prepare-data-for-advanced-ediscovery.md)
 