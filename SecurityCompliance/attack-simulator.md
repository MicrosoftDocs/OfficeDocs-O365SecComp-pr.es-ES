---
title: Simulator ataques en Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/09/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: Como administrador global de Office 365, puede usar simulador de ataque para ejecutar los escenarios de ataque realista en su organización. Esto puede ayudar a identificar y buscar usuarios vulnerables antes de que un ataque real afecta a su negocio.
ms.openlocfilehash: ccef127c4ce4d806ef9af04673b8c68d82ce9ec6
ms.sourcegitcommit: 7c55721b51b2f321537a0cdad6644abf91996710
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2018
ms.locfileid: "26256445"
---
# <a name="attack-simulator-in-office-365"></a>Simulator ataques en Office 365

**Resumen** Si usted es un administrador global de Office 365 y su organización tiene [Información sobre amenazas de Office 365](office-365-ti.md), puede usar simulador de ataque para ejecutar los escenarios de ataque realista en su organización. Esto puede ayudar a identificar y buscar usuarios vulnerables antes de que un ataque real afecta a la línea de la parte inferior. Lea este artículo para obtener más información.
  
## <a name="the-attacks"></a>Los ataques

Actualmente, los tres tipos de simulaciones de ataque están disponibles:
  
- [Mostrar los ataques de suplantación de identidad lanza de nombre](attack-simulator.md#spearphish)
    
- [Ataque de contraseña spray](attack-simulator.md#passwordspray)
    
- [Ataque de contraseña por fuerza bruta](attack-simulator.md#bruteforce)
    
Para que un ataque que se iniciará correctamente, se usa la autenticación multifactor en la cuenta que se usa para ejecutar ataques simulados. Además, debe ser un administrador global de Office 365.
  
> [!NOTE]
> Compatibilidad con el acceso condicional estará disponible próximamente. 
  
Para obtener acceso a simulador de ataque, en la seguridad &amp; centro de cumplimiento, elija **administración de amenaza** \> **simulador de ataque**.
  
## <a name="before-you-begin"></a>Antes de comenzar...

Asegúrese de que usted y su organización cumplen los siguientes requisitos de simulador de ataque:
      
- Correo electrónico de su organización se hospeda en Exchange Online. (Simulador de ataque no está disponible para los servidores de correo electrónico locales).
    
- Es un administrador global de Office 365
    
- Su organización usa [la autenticación multifactor para usuarios de Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication&view=o365-worldwide)
 
- Su organización tiene [Información sobre amenazas de Office 365](office-365-ti.md), con simulador de ataque visible en la seguridad &amp; centro de cumplimiento (vaya a **administración de amenaza** \> **simulador de ataque**)<br/>![Administración de amenaza - simulador de ataque](media/ThreatMgmt-AttackSimulator.png)

    
## <a name="display-name-spear-phishing-attack"></a>Mostrar los ataques de suplantación de identidad lanza de nombre

Suplantación de identidad es un término genérico para una amplia serie de ataques clasificados como un ataque de estilo de ingeniería social. Este ataque se centra en lanza de suplantación de identidad, un ataque dirigido más que está dirigido a un grupo específico de personas o de una organización. Normalmente, un ataque personalizado con algunos reconocimiento lleva a cabo y uso de un nombre para mostrar que se va a generar confianza en el destinatario, como un mensaje de correo electrónico que parece que proviene de un ejecutivo dentro de la organización.
  
Este ataque se centra en lo que le permite manipular que aparece el mensaje procede del cambiando la dirección de origen y de nombre para mostrar. Cuando los ataques de suplantación de identidad lanza son correctas, ciberdelincuentes obtienen acceso a las credenciales de los usuarios.
  
### <a name="to-simulate-a-spear-phishing-attack"></a>Para simular un ataque de suplantación de identidad lanza

![Redactar el cuerpo del correo electrónico](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
Puede crear el editor de HTML enriquecido directamente en el propio campo del **cuerpo del correo electrónico** o trabajar con código fuente HTML. Hay dos campos importantes para su inclusión en el código HTML: 
  
1. En la seguridad &amp; centro de cumplimiento, elija **administración de amenaza** \> **simulador de ataque**.
    
2. Especifique un nombre de campaña significativa para el ataque o seleccione una plantilla. <br/>![Página de inicio de suplantación de identidad](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. Especifique a los destinatarios de destino. Esto puede ser individuos o grupos de la organización. Cada destinatario dirigido debe tener un buzón de Exchange Online en orden para que el ataque tenga éxito. <br/>![Selección de destinatario](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. Configurar los detalles de correo electrónico de suplantación de identidad. <br/>![Configurar detalles de correo electrónico](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/>El formato HTML puede ser tan complejos o básica como necesita la campaña de. Como el formato de correo electrónico es HTML, puede insertar imágenes y texto para mejorar believability. Tiene control sobre qué aspecto tendrá el mensaje recibido en el cliente de correo electrónico receptor.
    
5. Especifique texto para el campo **de (nombre)** . Este es el campo que se muestra en el **Nombre para mostrar** en el cliente de correo electrónico receptor. 
    
6. Especifique el texto o el campo **desde** . Este es el campo que se muestra como la dirección de correo electrónico del remitente en el cliente de correo electrónico receptor.<br/>Puede escribir un espacio de nombres de correo electrónico existente dentro de la organización (hacer esto convertirá la dirección de correo electrónico realmente resolver en el cliente receptor, facilitar un modelo de confianza muy alta), o puede escribir una dirección de correo electrónico externa. La dirección de correo electrónico que especifique no tiene que realmente existe, pero es necesario que sigue el formato de una dirección SMTP válida, como user@domainname.extension. 
  
7. Mediante el selector de la lista desplegable, seleccione una dirección URL de servidor de inicio de sesión de suplantación de identidad que refleja el tipo de contenido que tendrá dentro de su ataque. Se proporcionan varias direcciones URL con temas para que pueda elegir, como nóminas técnica, de documento entrega, etcetera. Esto es en efecto la dirección URL que los usuarios de destino se le pida que haga clic en.
    
8. Especifique una dirección URL de página de inicio personalizado. Uso esto va a redirigir a los usuarios a una dirección URL especificada al final de un ataque con éxito. Si dispone de recursos de aprendizaje de conocimiento interna, por ejemplo, se puede especificar aquí.
    
9. Especifique texto para el campo **asunto** . Este es el campo que se muestra como el **Nombre de sujeto** en el cliente de correo electrónico receptor. 
    
10. Redactar el **cuerpo del correo electrónico** que va a recibir el destino. <br/>`${username}`Inserta el nombre de los objetivos en el cuerpo del correo electrónico. <br/>`${loginserverurl}`Inserta la dirección URL que se desea que los usuarios de destino haga clic en 
    
11. **Siguiente,** a continuación, elija **Finalizar** para iniciar el ataque. El mensaje de correo electrónico de suplantación de identidad lanza se entrega a los buzones de los destinatarios del destino. 
    
## <a name="password-spray-attack"></a>Ataque de contraseña spray

Un ataque de spray contraseña contra una organización se utiliza normalmente después de un actor bad ha adquirido correctamente una lista de los usuarios válidos desde el inquilino. El actor bad sabe acerca de las contraseñas comunes que usa la gente. Se trata de un ataque ampliamente utilizado, ya que es un ataque barato para ejecución y más difíciles de detectar que fuerza bruta enfoques.
  
Este ataque se centra en lo que le permite especificar una contraseña común con una base de gran tamaño de destino de los usuarios.
  
### <a name="to-simulate-a-password-spray-attack"></a>Para simular un ataque de contraseña spray

1. En la seguridad &amp; centro de cumplimiento, elija **administración de amenaza** \> **simulador de ataque**.
    
2. Especifique un nombre de campaña significativa para el ataque.
    
3. Especifique a los destinatarios de destino. Esto puede ser individuos o grupos de la organización. Un destinatario de destino debe tener un buzón de Exchange Online en orden para que el ataque tenga éxito.
    
4. Especifique una contraseña que se usará para el ataque. Por ejemplo, una contraseña común y relevante podría intentar es `Fall2017`. Es posible que otro `Spring2018`, o `Password1`.
    
5. Elija **Finalizar** para iniciar el ataque. 
    
## <a name="brute-force-password-attack"></a>Ataque de contraseña por fuerza bruta

Un ataque de contraseña por fuerza bruta contra una organización se utiliza normalmente después de un actor bad ha adquirido correctamente una lista de usuarios claves desde el inquilino. Este ataque se centra en intentar un conjunto de contraseñas en una única cuenta de usuario.
  
### <a name="to-simulate-a-brute-force-password-attack"></a>Para simular un ataque de contraseña por fuerza bruta

1. En la seguridad &amp; centro de cumplimiento, elija **administración de amenaza** \> **simulador de ataque**.
    
2. Especifique un nombre de campaña significativa para el ataque.
    
3. Especificar al destinatario de destino. Un destinatario de destino debe tener un buzón de Exchange Online en orden para que el ataque tenga éxito.
    
4. Especificar un conjunto de contraseñas que se usará para el ataque. Puede usar un archivo de texto (.txt) para su lista de contraseñas. El archivo de texto no puede superar los 10 MB en tamaño del archivo. Usar una contraseña por línea y asegúrese de que incluir un retorno de carro después de la última contraseña en la lista.
    
5. Elija **Finalizar** para iniciar el ataque. 
    
## <a name="new-features-in-attack-simulator"></a>Nuevas características de simulador de ataque

Se agregan nuevas características a simulador de ataque. Entre estos se incluyen:
- **Avanzadas capacidades de reporting**. Podrá ver los datos como la hora más rápida (o más lenta) para abrir un mensaje de correo electrónico de simulación de ataque, el tiempo más rápido (o más lento) que haga clic en un vínculo en el mensaje y mucho más.
- **Editor de plantillas de correo electrónico**. Puede crear una plantilla de correo electrónico personalizados y reutilizables que se puede usar para simulaciones de ataque futuro.

Visite la [Guía básica de 365 de Microsoft](https://www.microsoft.com/microsoft-365/roadmap) para ver las novedades en el desarrollo, ¿qué es implantar y lo que ya se inicia.



