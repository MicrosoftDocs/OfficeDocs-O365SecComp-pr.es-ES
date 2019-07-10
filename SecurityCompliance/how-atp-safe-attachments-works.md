---
title: Funcionamiento de los datos adjuntos seguros de ATP de Office 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: La característica datos adjuntos seguros proporciona comprobación del tiempo de los datos adjuntos de correo electrónico. Usar datos adjuntos seguros para proteger a su organización de archivos malintencionados envíe o reciba mensajes de correo electrónico.
ms.openlocfilehash: f0f117388957a14e3765b963a0e390ffb8fd7943
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599176"
---
# <a name="how-ffice-365-atp-safe-attachments-works"></a>Cómo funciona ffice datos adjuntos seguros de ATP 365

## <a name="how-it-works"></a>Cómo funciona

La característica de datos adjuntos seguros de ATP comprueba los datos adjuntos del correo electrónico de las personas de su organización. Cuando se implementa una directiva de datos adjuntos seguros de ATP y alguien que cubre esa Directiva ve su correo electrónico en Office 365, se comprueban los datos adjuntos del correo electrónico y se realizan las acciones adecuadas, según las directivas de datos adjuntos seguros de ATP. Según cómo se hayan definido las directivas, los usuarios pueden seguir trabajando sin saber nunca que se les enviaron archivos malintencionados.
  
A continuación se muestran dos ejemplos de datos adjuntos seguros de ATP en el trabajo.
  
- **Ejemplo 1: datos adjuntos de correo electrónico** Supongamos que lee recibe un mensaje de correo electrónico que tiene datos adjuntos. No es obvio si esos datos adjuntos son seguros o contiene malware diseñado para robar las credenciales de usuario de Lee. En la organización de Lee, un administrador de seguridad definió una directiva de datos adjuntos seguros de ATP hace unos días. Con la característica de datos adjuntos seguros de ATP, los datos adjuntos de correo electrónico se abren y se prueban en un entorno virtual antes de que Lucas los reciba. Si los datos adjuntos se determinan como malintencionados, se eliminarán automáticamente. Si los datos adjuntos son seguros, se abrirán como se esperaba cuando lee hace clic en él.

- **Ejemplo 2: archivo en SharePoint Online** Supongamos que Jean ha recibido un archivo y lo ha cargado en una biblioteca en SharePoint Online. Jean comparte el vínculo al archivo con el resto del equipo, sin saber que el archivo es realmente malintencionado. Afortunadamente, [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) detecta el archivo malintencionado y lo bloquea. Unos días más tarde, Carlos abrirá el documento. Aunque Carlos puede ver el archivo está allí, Carlos no puede abrirlo ni compartirlo, lo que protege al equipo de Cristina y a otros usuarios del archivo malintencionado.

Las directivas de datos adjuntos seguros de ATP se pueden aplicar a personas o grupos específicos de la organización o a todo el dominio. Además, las directivas de datos adjuntos seguros de ATP se pueden configurar para usar datos adjuntos de marcador de posición mientras se analizan los datos adjuntos reales. Para obtener más información, consulte **[configurar las directivas de datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)**.

> [!NOTE]
> El análisis de datos adjuntos seguros de ATP tiene lugar en la misma región en la que residen los datos de Office 365. Para obtener más información acerca de la geografía del centro de datos, consulte [¿dónde están los datos ubicados?](https://products.office.com/where-is-your-data-located?geo=All) 

