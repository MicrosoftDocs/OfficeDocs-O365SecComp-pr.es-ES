---
title: Simulador de ataques en Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/05/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Como administrador global de Office 365, puede usar simulador de ataque para ejecutar escenarios de ataque realistas en su organización. Esto puede ayudarle a identificar y encontrar a los usuarios vulnerables antes de que un ataque real reconozca a su empresa.
ms.openlocfilehash: 8cbe3c5c34bbc68fc89c8550d9711d953dced9b5
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2019
ms.locfileid: "30524064"
---
# <a name="attack-simulator-in-office-365"></a>Simulador de ataques en Office 365

**Resumen** Si es un administrador global de Office 365 y su organización tiene [office 365 de investigación de amenazas y respuesta capabilties](office-365-ti.md), puede usar simulaDor de ataque para ejecutar escenarios de ataque realistas en su organización. Esto puede ayudarle a identificar y encontrar usuarios vulnerables antes de que un ataque real afecte a su conclusión. Lea este artículo para obtener más información.

> [!IMPORTANT]
> Office 365 Threat Intelligence ahora forma parte de Office 365 plan de protección contra amenazas avanzada 2, con capacidades de protección contra amenazas adicionales. Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).
  
## <a name="the-attacks"></a>Los ataques

Actualmente hay disponibles tres tipos de simulaciones de ataque:
  
- [Nombre para mostrar: ataque de suplantación de identidad](attack-simulator.md#spearphish)
    
- [Ataque rociado de contraseñas](attack-simulator.md#passwordspray)
    
- [Ataque de fuerza bruta con contraseña](attack-simulator.md#bruteforce)
    
Para que un ataque se inicie correctamente, use la autenticación multifactor en la cuenta que está usando para ejecutar ataques simulados. Además, debe ser un administrador global de Office 365.
  
> [!NOTE]
> La compatibilidad con el acceso condicional estará disponible próximamente. 
  
Para tener acceso al simulador de ataques &amp; , en el centro de seguridad y cumplimiento, elija simulador de **ataques**de **Administración** \> de amenazas.
  
## <a name="before-you-begin"></a>Antes de comenzar...

Asegúrese de que usted y su organización cumplen con los siguientes requisitos para simuladores de ataques:
      
- **El correo electrónico de la organización se hospeda en Exchange Online**. (El simulador de ataque no está disponible para los servidores de correo electrónico locales).
    
- **Es un administrador global de Office 365**
    
- **La [autenticación multifactor](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide) (MFA) está activada, como mínimo, para la cuenta de administrador global de Office 365**. (Idealmente, la MFA está activada para todos los usuarios de la organización).
 
- **su organización tiene [Office 365 Threat Intelligence](office-365-ti.md)**, con simulador de ataque visible en &amp; el centro de seguridad y cumplimiento (vaya a simulador de **ataque**de **administración** \> de amenazas)<br/>![Administración de amenazas: simulador de ataque](media/ThreatMgmt-AttackSimulator.png)

    
## <a name="display-name-spear-phishing-attack"></a>Nombre para mostrar: ataque de suplantación de identidad

La suPlantación de identidad (phishing) es un término genérico para un conjunto amplio de ataques que se clasifican como un ataque de tipo de ingeniería social. Este ataque se centra en la suplantación de identidad (phishing), un ataque más objetivo destinado a un grupo específico de personas o una organización. Normalmente, se trata de un ataque personalizado con algún reconocimiento realizado y con un nombre para mostrar que generará confianza en el destinatario, como un mensaje de correo electrónico que parece que proviene de un ejecutivo de la organización.
  
Este ataque se centra en permitirle manipular a la que parece que el mensaje se ha originado cambiando el nombre para mostrar y la dirección de origen. Cuando los ataques de "Spear-phishing" son correctos, los delincuentes pueden obtener acceso a las credenciales de los usuarios.
  
### <a name="to-simulate-a-spear-phishing-attack"></a>Para simular un ataque de "Spear phishing"

![Crear cuerpo de correo electrónico](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
Puede crear el editor HTML enriquecido directamente en el propio campo **del cuerpo del correo electrónico** o trabajar con el código fuente HTML.
  
1. En el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), elija simulador de **ataque**de **Administración** \> de amenazas.
    
2. Especifique un nombre de campaña significativo para el ataque o seleccione una plantilla. <br/>![Página de inicio de phishing](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. Especifique los destinatarios de destino. Puede tratarse de personas o grupos de la organización. Cada destinatario de destino debe tener un buzón de Exchange Online para que el ataque tenga éxito. <br/>![Selección de destinatarios](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. Configure los detalles del correo de suPlantación de identidad. <br/>![Configuración de detalles de correo electrónico](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/>El formato HTML puede ser tan complejo o básico como las necesidades de la campaña. Como el formato de correo electrónico es HTML, puede insertar imágenes y texto para mejorar la increíble. Tiene control sobre la apariencia que tendrá el mensaje recibido en el cliente de correo electrónico de recepción.
    
5. Especifique el texto para el campo **de (nombre)** . Este es el campo que se muestra en el **nombre para mostrar** en el cliente de correo electrónico de recepción. 
    
6. Especifique el texto o el campo **de** . Se trata del campo que muestra la dirección de correo electrónico del remitente en el cliente de correo electrónico de recepción. <br/>Puede escribir un espacio de nombres de correo electrónico existente dentro de la organización (al hacerlo, la dirección de correo electrónico se resolverá realmente en el cliente receptor, lo que facilitará un modelo de confianza muy alto) o puede escribir una dirección de correo electrónico externa. La dirección de correo electrónico que especifique no tiene que existir realmente, pero necesita seguir el formato de una dirección SMTP válida, como usuario @ nombreDeDominio. extensión. 
  
7. Mediante el selector de lista desplegable, seleccione una dirección URL del servidor de inicio de sesión de suPlantación de identidad (phishing) que refleje el tipo de contenido que tendrá en el ataque. Se proporcionan varias URL con temas que puede elegir, como la entrega de documentos, técnicas, nóminas, etc. De hecho, se trata de la URL a la que se pide a los usuarios de destino que haga clic.
    
8. Especificar una dirección URL de la página de aterrizaje personalizada. Al usar esto, se redirigirá a los usuarios a una dirección URL que especifique al final de un ataque realizado correctamente. Si tiene un entrenamiento de conciencia interno, por ejemplo, puede especificarlo aquí.
    
9. Especifique el texto para **** el campo Subject. Este es el campo que muestra el **nombre del sujeto** en el cliente de correo electrónico de recepción. 
    
10. Redacte el **cuerpo del correo electrónico** que recibirá el destino. <br/>`${username}`inserta el nombre de los destinos en el cuerpo del correo electrónico. <br/>`${loginserverurl}`inserta la dirección URL en la que desea que los usuarios de destino haga clic 
    
11. Elija **siguiente y** luego **Finalizar** para iniciar el ataque. El mensaje de correo electrónico de "Spear phishing" se entrega a los buzones de los destinatarios de destino. 
    
## <a name="password-spray-attack"></a>Ataque rociado de contraseñas

Un ataque por pulverización de contraseña contra una organización suele usarse después de que un actor incorrecto haya adquirido correctamente una lista de usuarios válidos del espacio empresarial. El actor incorrecto conoce las contraseñas comunes que usan las personas. Se trata de un ataque de uso generalizado, ya que es un ataque barato de ejecutar y más difícil de detectar que los enfoques de fuerza bruta.
  
Este ataque se centra en permitir que especifique una contraseña común en una base de usuarios de gran tamaño.
  
### <a name="to-simulate-a-password-spray-attack"></a>Para simular un ataque rociado de contraseñas

1. En el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), elija simulador de **ataque**de **Administración** \> de amenazas.
    
2. Especifique un nombre de campaña significativo para el ataque.
    
3. Especifique los destinatarios de destino. Puede tratarse de personas o grupos de la organización. Un destinatario de destino debe tener un buzón de Exchange Online para que el ataque tenga éxito.
    
4. Especifique la contraseña que se va a usar para el ataque. Por ejemplo, una contraseña común y relevante que podría probar es `Fall2017`. Otro podría ser `Spring2018`o `Password1`.
    
5. Elija **Finalizar** para iniciar el ataque. 
    
## <a name="brute-force-password-attack"></a>Ataque de fuerza bruta con contraseña

Un ataque de fuerza bruta contra una organización se suele usar después de que un actor incorrecto haya adquirido correctamente una lista de usuarios clave del espacio empresarial. Este ataque se centra en probar un conjunto de contraseñas en una sola cuenta de usuario.
  
### <a name="to-simulate-a-brute-force-password-attack"></a>Para simular un ataque de fuerza bruta de contraseña

1. En el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), elija simulador de **ataque**de **Administración** \> de amenazas.
    
2. Especifique un nombre de campaña significativo para el ataque.
    
3. Especifique el destinatario de destino. Un destinatario de destino debe tener un buzón de Exchange Online para que el ataque tenga éxito.
    
4. Especifique un conjunto de contraseñas que se usarán para el ataque. Para ello, puede usar un archivo de texto (. txt) para la lista de contraseñas. El archivo de texto no puede superar los 10 MB en el tamaño del archivo. Use una contraseña por línea y asegúrese de incluir un retorno de la última contraseña en la lista.
    
5. Elija **Finalizar** para iniciar el ataque. 
    
## <a name="new-features-in-attack-simulator"></a>Nuevas características en el simulador de ataques

Se han agregado nuevas características a simulador de ataque. Entre estos, incluyen los siguientes:

- **Capacidades avanzadas de generación de informes**. Podrá ver datos como el tiempo más rápido (o más lento) para abrir un mensaje de correo electrónico de simulación de ataque, el tiempo más rápido o más lento para hacer clic en un vínculo del mensaje, y más.

- **Editor de plantillas de correo electrónico**. Puede crear una plantilla de correo electrónico personalizada y reutilizable que puede usar para simulaciones de ataque futuras.

Visite el [mapa de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para ver lo que se está desarrollando, lo que está implementando y lo que ya se ha iniciado.

## <a name="see-also"></a>Vea también

[Desription del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)



