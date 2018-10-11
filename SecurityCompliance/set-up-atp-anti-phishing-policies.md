---
title: Configurar las directivas de ATP contra suplantación de identidad de Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/11/2018
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
description: Protección contra suplantación de identidad de ATP, parte de Office 365 avanzada protección contra amenazas, puede ayudar a proteger su organización frente a ataques de suplantación de identidad basada en suplantación malintencionado y otros ataques de suplantación de identidad. Si usted es un Office 365 información global de empresa o un administrador de seguridad, puede configurar las directivas de ATP contra suplantación de identidad. Suplantación de identidad ataques proceden de en una gran variedad de formularios ataques de mercancía a phishing lanza dirigido o whaling. Con la creciente complejidad, es difícil para incluso un ojo capacitado identificar algunos de estos ataques sofisticados. Afortunadamente, puede ayudar la protección de amenaza avanzada de Office 365. Puede configurar una directiva de anti-phishing ATP para ayudar a garantizar que la organización está protegida frente a estos ataques.
ms.openlocfilehash: 37a38863296ab87feaade93b7939029b9306ec30
ms.sourcegitcommit: 176ce86e2b440c079414fe99d4b0b9e89ccebb40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "25496571"
---
# <a name="set-up-office-365-atp-anti-phishing-policies"></a>Configurar las directivas de ATP contra suplantación de identidad de Office 365

[Protección contra suplantación de identidad de ATP](atp-anti-phishing.md), parte de [La protección de amenaza avanzada de Office 365](office-365-atp.md), puede ayudar a proteger su organización frente a ataques de suplantación de identidad basada en suplantación malintencionado y otros ataques de suplantación de identidad. Si usted es un Office 365 información global de empresa o un administrador de seguridad, puede configurar las directivas de ATP contra suplantación de identidad. 

Suplantación de identidad ataques proceden de en una gran variedad de formularios ataques de mercancía a phishing lanza dirigido o whaling. Con la creciente complejidad, es difícil para incluso un ojo capacitado identificar algunos de estos ataques sofisticados. Afortunadamente, puede ayudar la protección de amenaza avanzada de Office 365. Puede configurar una directiva de anti-phishing ATP para ayudar a garantizar que la organización está protegida frente a estos ataques.
  
> [!NOTE]
> Sólo está disponible en avanzada protección contra amenazas, disponibles con Office 365 Enterprise E5 ATP contra suplantación de identidad. Si su organización usa otra suscripción de Office 365 Enterprise, protección avanzada de amenaza puede adquirirse como un complemento. (Como un administrador global, en el centro de administración de Office 365, elija **facturación** \> **Agregar suscripciones**.) Para obtener más información acerca de las opciones del plan, consulte [comparar todos los Office 365 para planes de negocios](https://go.microsoft.com/fwlink/?linkid=844053). Asegúrese de que su organización usa la versión más reciente de Office 365 ProPlus en Windows para aprovechar al máximo de protección contra suplantación de identidad de ATP. 
  
Lo que debe hacer:
  
1. Revise los requisitos previos.
    
2. Obtenga información acerca de las opciones de directiva contra suplantación de identidad de ATP.
    
3. Establecer una directiva de ATP contra suplantación de identidad.
    
## <a name="review-the-prerequisites"></a>Revise los requisitos previos

- Asegúrese de que es un miembro del grupo de roles de **administradores de empresa** o de **administradores de seguridad** . 
    
- [Obtenga información acerca de las opciones de directiva contra suplantación de identidad de ATP](set-up-atp-anti-phishing-policies.md#learn-about-atp-anti-phishing-policy-options) (en este artículo). 
    
- Probablemente se instalará varias directivas contra suplantación de identidad de ATP para su organización. Office 365 aplica estas directivas en el orden en que aparecen en la página de **ATP contra suplantación de identidad** en la seguridad &amp; centro de cumplimiento. Una vez que haya revisado las opciones de directiva, se necesite algún tiempo para determinar cuántas directivas que necesitará y la prioridad para cada uno. 
    
- Planifique dedicar aproximadamente 5-15 minutos para configurar su primera Directiva contra suplantación de identidad de ATP.
    
- Permitir hasta 30 minutos para la directiva de nueva o actualizada para propagarse a todos los centros de datos de Office 365.
    
## <a name="set-up-an-atp-anti-phishing-policy"></a>Establecer una directiva de ATP contra suplantación de identidad

Cada organización en Office 365 tiene una directiva contra suplantación de identidad predeterminada que se aplica a todos los usuarios. También puede crear varias directivas contra suplantación de identidad personalizadas que puede delimitar a determinados usuarios, grupos o dominios dentro de la organización. Las directivas personalizadas que cree tendrán prioridad sobre la directiva predeterminada. Agregar, editar y eliminar directivas de ATP contra suplantación de identidad en la seguridad de Office 365 &amp; centro de cumplimiento.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela. 
    
2. En la seguridad de Office 365 &amp; centro de cumplimiento, en el panel de navegación izquierdo, en **administración de amenaza**, elija la **Directiva**.
    
3. En la página **Directiva** , elija **ATP contra suplantación de identidad**.
    
4. En la página **contra suplantación de identidad** , realice una de las siguientes: 
    
  - Para agregar una nueva directiva seleccione **+ crear**.
    
  - Para editar una directiva existente, seleccione el nombre de la directiva de la lista que aparece en la página de **Anti-phishing** o elija **Directiva predeterminada** encima de la lista para editar el poicy predeterminado para su organización. En la página que aparece, elija **Editar directiva**.  
    
    Se inicia un asistente que le guiará en el proceso de definición de la directiva contra suplantación de identidad.
    
5. Especifique el nombre, la descripción y la configuración para la directiva. Para obtener más información, vea [Aprenda acerca de las opciones de directiva contra suplantación de identidad de ATP](#learn-about-atp-anti-phishing-policy-options) . 
    
6. Una vez haya revisado la configuración, elija **crear esta directiva** o **Guardar** según corresponda. 
    
## <a name="learn-about-atp-anti-phishing-policy-options"></a>Obtenga información acerca de las opciones de directiva contra suplantación de identidad de ATP

Como se puede configurar o edición las directivas de anti-phishing ATP, puede elegir entre varias opciones, tal como se describe en la siguiente tabla:
  
|**Esta opción de configuración**|**Se obtiene este resultado**|**Usar cuando desea:**|
|:-----|:-----|:-----|
|**Agregar usuarios a proteger** <br/> |Define qué direcciones de correo electrónico estará protegidos por la directiva. Puede agregar hasta 60 direcciones internas y externas que se desean proteger de suplantación.  <br/> |Cuando desea asegurarse de que el correo desde fuera de su organización, no es una representación de uno de los usuarios en la lista de usuarios que va a proteger. Ejemplos de usuarios, es posible que desee proteger son los ejecutivos de alto nivel, los propietarios de negocios, consejeros externos y así sucesivamente.<br/> Esta lista de usuarios protegidas es diferente de la lista de personas a la que se aplica la directiva, o en su lugar, para la que se aplica la directiva. Defina el se aplica a la lista en la sección **se aplica a** de las opciones de directiva.<br/> Por ejemplo, si agrega Mary Smith \<marys@contoso.com\> como un usuario para proteger, a continuación, aplicar la directiva para el grupo "todos los usuarios". Esto garantizará que un correo que aparecía suplantar a "Mary Smith" enviado a un usuario en el grupo "Todos los usuarios" ¿actúa en por la directiva.<br/> |
|**Agregar dominios para proteger** <br/> |Le permite elegir qué dominios que desea proteger de suplantación. Puede especificar que la directiva incluya todos los dominios personalizados, una lista separada por comas de dominios o una combinación de ambas. Si decide **incluir automáticamente los dominios que poseen**y luego se agrega un dominio a su organización de Office 365, esta directiva contra suplantación de identidad estará en contexto para el nuevo dominio.<br/> |Cada vez que desea asegurarse de que el correo desde fuera de su organización no es una representación de uno de los dominios definidos en la lista de dominios comprobadas o de un dominio de socio.  <br/> |
|**Elija Acciones** <br/> |Elija la acción que se realizará cuando Office 365 detecta un intento de suplantación frente a los usuarios y los dominios que agregó a la directiva. Puede elegir diferentes acciones para los usuarios y los dominios en la misma directiva contra suplantación de identidad. Estas acciones se aplican a cualquier dominio que está bajo la protección de esta directiva contra suplantación de identidad o el correo electrónico entrante que se ha identificado por Office 365 como suplantación de una cuenta de usuario.<br/> **Mensaje en cuarentena** Correo electrónico se enviarán a cuarentena de Office 365. Al elegir esta opción, el correo electrónico no se envía al destinatario original.<br/> **Redirigir el mensaje a otra dirección de correo electrónico** Correo electrónico se enviarán a la dirección de correo electrónico que especifique. Puede especificar varias direcciones de correo electrónico. Al elegir esta opción, el correo electrónico no se envía al destinatario original.<br/> **Mover el mensaje a la carpeta de correo electrónico no deseado de los destinatarios** Correo electrónico se enviarán a la carpeta de correo electrónico no deseado de los destinatarios. Al elegir esta opción, el correo electrónico aún se envía al destinatario original, pero no se coloca en la Bandeja de entrada del destinatario.<br/> **Entregar el mensaje y agregar otras direcciones en la línea CCO** Correo electrónico se entregarán al destinatario original. Además, los usuarios que se identifica se agregará a la línea CCO del mensaje antes de se entregue. Al elegir esta opción, el correo electrónico aún se envía a la Bandeja de entrada del destinatario original.<br/> **No aplicar ninguna acción** Correo electrónico se entregarán en la Bandeja de entrada del destinatario original. En el mensaje de correo electrónico no se llevará a cabo ninguna otra acción.<br/> **Activar sugerencias de protección de suplantación de identidad** Permite sugerencias de seguridad contra suplantación de identidad en el correo electrónico.  <br/> |Cuando desee realizar una acción en los mensajes que Office 365 ha determinado como una suplantación de un usuario o dominio tal como se define en la directiva.  <br/> |
|**Habilitar la inteligencia de buzón de correo** <br/> |Habilita o deshabilita la inteligencia de buzón de correo para esta directiva. Sólo se puede habilitar inteligencia de buzón de correo para basados en la nube las cuentas, es decir, las cuentas cuyo buzón de correo está hospedado por completo en Office 365.  <br/> |Cuando desea mejorar los resultados de la suplantación de usuarios en función de mapa de remitente individual de cada usuario. Inteligencia de buzón de correo se basa alrededor de las personas que enviar y recibe correo desde. Esta inteligencia permite a Office 365 personalizar la directiva de suplantación en un nivel de usuario con el fin de controlar mejor resultados con falsos positivos.  <br/> |
|**Agregar dominios y remitentes de confianza** <br/> |Define las direcciones de correo electrónico y dominios que no se considerarán suplantaciones por esta directiva. Los mensajes de las direcciones de correo electrónico del remitente y dominios agregar como remitentes de confianza y dominios nunca no clasificarse como un ataque de suplantación. Como resultado, las acciones y configuración de esta directiva no se aplicarán a los mensajes de estos remitentes y dominios.  <br/> |Cuando los usuarios interactúan con dominios o usuarios que desencadenan suplantación pero se consideran seguros. Por ejemplo, si un socio tiene el mismo/similar Mostrar nombre o nombre de dominio como un usuario definido en la lista.  <br/> |
|**Aplica a** <br/> |Define a los destinatarios cuyos mensajes de correo electrónico entrante estarán sujetas a las reglas de la directiva. Puede crear condiciones y excepciones para los destinatarios asociados a la directiva.  <br/> Por ejemplo, puede crear una directiva global para su organización mediante la aplicación de la regla a todos los destinatarios del dominio.  <br/> También puede crear reglas de excepción, como una regla que no examina los mensajes de correo electrónico para un grupo específico de destinatarios.  <br/> |Cada directiva debe estar asociado a un conjunto de usuarios, por ejemplo, los usuarios de un determinado grupo o dominio.  <br/> |
|**Umbrales de suplantación de identidad avanzadas** <br/> |Define el nivel de configuración de cómo se controlan los mensajes de suplantación de identidad.  <br/> **Estándar** Correo electrónico que parece para ser phishing se administra en la forma habitual.  <br/> **Agresivo** Correo electrónico parece para ser phishing con un alto o muy alto grado de confianza se controlan mediante el sistema de la misma manera.  <br/> **Sea más restrictivo** Correo electrónico parece para ser phishing con una media, alta, o muy alto grado de confianza se controlan mediante el sistema de la misma manera.  <br/> **Más agresivo** Correo electrónico que parece para ser phishing con un grado bajo, mediano, alto o muy alto de confianza se controlan mediante el sistema de la misma manera.  <br/> |Cuando desea que sea más restrictivo en el tratamiento de los mensajes de suplantación de identidad potencialmente dentro de Office 365. Por ejemplo, los mensajes con una probabilidad muy alta de que se va a phishing tendrá las acciones más agresivas efectuadas en ellos, mientras que los mensajes con una probabilidad baja tienen menos agresivas acciones llevadas a cabo en ellos. Esta configuración también afecta a otros elementos del sistema de filtrado que combinan las señales juntos. La posibilidad de mover mensajes de buena aumenta a medida que el nivel de los aumentos de configuración.  <br/> |
   
Después de que su organización ha configurado directivas de ATP contra suplantación de identidad, puede ver cómo funciona el servicio mediante la [visualización de informes de protección avanzada de amenaza](view-reports-for-atp.md).
  
## <a name="example-anti-phishing-policy-to-protect-a-user-and-a-domain"></a>Ejemplo: Contra suplantación de identidad de una directiva para proteger un usuario y un dominio

En este ejemplo se configura una directiva denominada "Dominio y CEO" que ofrece protección de usuario y dominio de suplantación y, a continuación, se aplica la directiva a todos los correos electrónicos recibidos por los usuarios dentro del dominio `contoso.com`. El Administrador de seguridad ha determinado que la directiva debe cumplir estos requisitos empresariales:
  
- La directiva que se necesita proporcionar protección para el CEO cuenta y todo el dominio de correo electrónico.
    
- Los mensajes que van a ser intentos fallidos de suplantación en la cuenta de usuario del director general necesitan que se redirija a la dirección de correo electrónico del Administrador de seguridad.
    
- Los mensajes que van a ser intentos fallidos de suplantación en el dominio son menos urgentes y deben ser en cuarentena para su revisión posterior.
    
El Administrador de seguridad de Contoso es posible que use valores como la siguiente con el fin de crear una directiva contra suplantación de identidad que cumpla estas necesidades.
  
|||
|:-----|:-----|
|**Configuración o la opción** <br/> |**Ejemplo** <br/> |
|Nombre  <br/> |Dominio y consejero Delegado  <br/> |
|Descripción  <br/> |Asegúrese de que el director general y nuestro dominio no son suplantados.  <br/> |
|Agregar usuarios a proteger  <br/> |Dirección de correo electrónico del CEO como mínimo.  <br/> |
|Agregar dominios para proteger  <br/> |El dominio organizativo que incluye la oficina del CEO.  <br/> |
|Elija Acciones  <br/> |Si el correo electrónico se envía por un usuario suplantado: elija **redirigir el mensaje a otra dirección de correo electrónico** y, a continuación, escriba la dirección de correo electrónico del Administrador de seguridad, por ejemplo, `securityadmin@contoso.com`.  <br/> Si el correo electrónico se envía por un dominio suplantado: elija **el mensaje en cuarentena**.  <br/> |
|Inteligencia de buzón de correo  <br/> |De forma predeterminada, se selecciona inteligencia de buzón de correo cuando se crea una nueva directiva contra suplantación de identidad. Deje esta opción **en** para obtener los mejores resultados.<br/> |
|Agregar dominios y remitentes de confianza  <br/> |Para este ejemplo, no defina los reemplazos.  <br/> |
|Aplica a  <br/> |Seleccione **el dominio de destinatario es**. En **cualquiera de estas**, seleccione **Elegir**. Seleccione **+ Agregar**. Seleccione la casilla de verificación situada junto al nombre del dominio, por ejemplo, `contoso.com`, en la lista y, a continuación, seleccione **Agregar**. Seleccione **Listo**.<br/> |
   
## <a name="delete-an-atp-anti-phishing-policy"></a>Eliminar una directiva de ATP contra suplantación de identidad

Puede eliminar las directivas personalizadas que ha creado mediante el uso de la seguridad &amp; centro de cumplimiento. No se puede eliminar la directiva predeterminada para la organización. Se recomienda usar la seguridad &amp; centro de cumplimiento para revisar o modificar cualquiera de las directivas de ATP.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) y el inicio de sesión con la cuenta de trabajo o escuela. 
    
2. En la izquierda, en **administración de amenaza**, elija la **Directiva**.
    
3. En la página **Directiva** , elija **ATP contra suplantación de identidad**.
    
4. En la página **contra suplantación de identidad** , seleccione el nombre de la directiva de la lista que aparece en la página **contra suplantación de identidad** . En la página que aparece, elija **Eliminar directiva**. Permitir hasta 30 minutos para que los cambios propagar a todos los centros de datos de Office 365.
    
## <a name="related-topics"></a>Temas relacionados

[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[Protección contra suplantación de identidad (phishing) en Office 365](anti-phishing-protection.md)
  
[Funciones de ATP contra suplantación de identidad en Office 365](atp-anti-phishing.md)
  
[Configurar directivas de ATP vínculos seguros en Office 365](set-up-atp-safe-links-policies.md)
  
[Configurar las directivas de los datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)
  
[Ver los informes de protección contra amenazas de avanzada](view-reports-for-atp.md)
  

