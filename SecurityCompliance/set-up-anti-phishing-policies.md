---
title: Configurar las directivas de protección contra suplantación de identidad ATP de Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 07/10/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
description: Protección contra suplantación de identidad (phishing), con protección completa como parte de la protección básica y protección contra amenazas avanzada de Office 365 en Office 365 Exchange Online Protection, puede ayudar a proteger su organización de ataques malintencionados basados en suplantación de identidad. y otros ataques de suplantación de identidad.
ms.openlocfilehash: 8ad7224b63ec599cdb8120dd4ee17493b75f1738
ms.sourcegitcommit: d4acce11a26536b9d6ca71ba4933fc95136198a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "36407939"
---
# <a name="set-up-office-365-atp-anti-phishing-and-anti-phishing-policies"></a>Configurar directivas contra suplantación de identidad y directivas contra suplantación de identidad de ATP de Office 365

La protección contra suplantación de [identidad ATP](atp-anti-phishing.md), parte de la [protección contra amenazas avanzada de Office 365](office-365-atp.md), puede ayudar a proteger a su organización de ataques de suplantación de identidad (phishing) malintencionados y otros ataques de suplantación de identidad. Si es un administrador global o de seguridad de Office 365 Enterprise, puede configurar las directivas antiphishing de ATP. 

Los ataques de suplantación de identidad (phishing) se presentan en una variedad de formularios de ataques basados en productos destinados a la suplantación de identidad o Whaling. Con una complejidad cada vez mayor, es difícil incluso para la vista entrenada identificar algunos de estos ataques sofisticados. Afortunadamente, la protección contra amenazas avanzada de Office 365 puede resultar útil. Puede configurar una directiva contra la suplantación de identidad ATP para asegurarse de que su organización está protegida contra dichos ataques.
  
> [!NOTE]
> La protección contra phishing de ATP solo está disponible en la protección contra amenazas avanzada (ATP). ATP se incluye en las suscripciones, como [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 enterprise E5, Office 365 Education A5, etc. Si su organización tiene una suscripción de Office 365 que no incluye ATP de Office 365, puede comprar ATP como complemento. Para obtener más información, consulte [planes y precios](https://products.office.com/exchange/advance-threat-protection) de la protección contra amenazas avanzada de Office 365 y la [Descripción del servicio de protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Asegúrese de que su organización usa la versión más reciente de Office 365 ProPlus en Windows para aprovechar al máximo la protección contra la suplantación de identidad ATP. 

También hay disponible una directiva antiphishing para Office 365 Exchange Online Protection, con un conjunto limitado de protección contra la suplantación de identidad que se ha diseñado para protegerse contra ataques basados en autenticación y en los que se puede interceptar.
  
Qué hacer:
  
1. Revise los requisitos previos.

2. Obtenga información acerca de las opciones de la Directiva antiphishing de ATP y contra phishing.

3. Configurar una directiva antiphishing o una directiva contra la suplantación de identidad ATP.

>[!IMPORTANT]
> Para obtener información sobre cómo se aplican varias tecnologías, vea [cómo se combinan las directivas y las protecciones](https://docs.microsoft.com/office365/securitycompliance/how-policies-and-protections-are-combined).

## <a name="review-the-prerequisites"></a>Revisión de los requisitos previos

- Para definir (o editar) las directivas de ATP, debe tener asignado un rol apropiado. En la tabla siguiente se describen algunos ejemplos:

    |Role  |Dónde y cómo se asigna  |
    |---------|---------|
    |Administrador global de Office 365 |La persona que se registra para comprar Office 365 es un administrador global de forma predeterminada. (Consulte [acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obtener más información).         |
    |Administrador de seguridad |Centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
    |Administración de la organización de Exchange Online |Centro de administración de[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

    Para obtener más información acerca de los roles y los permisos, consulte Permissions [in the Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Probablemente, configurará varias directivas antiphishing para su organización. Office 365 exige estas directivas en el orden en que aparecen en la **Página antiphishing** y en las páginas **contra** la suplantación de identidad ATP &amp; en el centro de seguridad y cumplimiento. Una vez que haya revisado las opciones de la [Directiva](#learn-about-atp-anti-phishing-policy-options), Tómese tiempo para determinar cuántas directivas necesitará y la prioridad de cada una. 

- Planee dedicar unos 5-15 minutos a configurar su primera Directiva antiphishing.

- Espere hasta 30 minutos para que la directiva nueva o actualizada se extienda a todos los centros de seguridad de Office 365.

## <a name="set-up-an-anti-phishing-or-atp-anti-phishing-policy"></a>Configurar una directiva antiphishing contra la suplantación de identidad (phishing) o ATP

Cada organización de Office 365 tiene una directiva anti-phishing predeterminada que se aplica a todos los usuarios. Puede crear varias directivas de suplantación de identidad (phishing) personalizadas que se pueden asignar a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas que cree tienen prioridad sobre la directiva predeterminada. Puede Agregar, editar y eliminar directivas antiphishing en el centro de seguridad &amp; y cumplimiento de Office 365.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa. 

2. En el centro de navegación &amp; izquierdo de Office 365 Security Compliance Center, en **Administración de amenazas**, elija **Directiva**.

3. En la página **Directiva** , elija **anti-phishing** o **ATP antiphishing**.

4. En la página contra la suplantación de identidad **(phishing** ) de **ATP** , realice una de las siguientes acciones:

    - Para agregar una nueva Directiva, seleccione **+ crear**.
    - Para editar una directiva existente, seleccione el nombre de la Directiva en la lista que aparece en la página contra la suplantación de **identidad** . (También puede elegir la **directiva predeterminada** que se encuentra encima de la lista). En la página que aparece, elija **Editar Directiva**.  

5. Especifique el nombre, la descripción y la configuración de la directiva. Para obtener más información, consulte [información sobre las opciones de directiva](#learn-about-atp-anti-phishing-policy-options) de antiphishing de ATP. 

6. Una vez que haya revisado la configuración, elija **crear esta directiva** (o **Guardar**).

## <a name="learn-about-atp-anti-phishing-policy-options"></a>Obtener información sobre las opciones de directiva antiphishing de ATP

Al configurar o editar las directivas antiphishing de ATP, puede elegir entre varias opciones que proporcionan la protección más sofisticada y completa, tal como se describe en la tabla siguiente:
  
|**Esta configuración**|**Se obtiene este resultado**|**Se usa cuando se desea:**|
|:-----|:-----|:-----|
|**Agregar usuarios para protegerlos** <br/> |Define qué direcciones de correo electrónico estarán protegidas por la Directiva. Puede Agregar hasta 60 direcciones internas y externas que desea proteger de la suplantación.  <br/> |Cuando desee asegurarse de que el correo de fuera de la organización no es una suplantación de uno de los usuarios de la lista de usuarios que va a proteger. Algunos ejemplos de usuarios que puede desear proteger son ejecutivos de alto nivel, propietarios de empresas, miembros externos de la Junta, etc.  <br/> Esta lista de usuarios protegidos es diferente de la lista de personas a las que se aplica la Directiva o, en su lugar, de la que se aplica la Directiva. Defina la lista se aplica a en la sección **aplicado a** de las opciones de directiva.  <br/> Por ejemplo, si agrega `Mary Smith <marys@contoso.com>` como un usuario para proteger, aplique la Directiva al grupo "todos los usuarios". Esto garantizará que un correo que apareció como suplantar "Silvia Smith" se envíe a un usuario del grupo "todos los usuarios" sería actuado en la Directiva.  <br/> |
|**Agregar dominios para proteger** <br/> |Permite elegir qué dominios desea proteger de la suplantación. Puede especificar que la directiva incluya todos los dominios personalizados, una lista de dominios separados por comas o una combinación de ambos. Si elige **incluir automáticamente los dominios**de su propiedad y después agrega un dominio a su organización de Office 365, esta directiva antiphishing estará en vigor para el nuevo dominio.  <br/> |Siempre que desee asegurarse de que el correo de fuera de la organización no es una suplantación de uno de los dominios definidos en la lista de dominios comprobados o de un dominio asociado.  <br/> |
|**Elegir acciones** <br/> |Elija la acción que se realizará cuando Office 365 detecte un intento de suplantación con los usuarios y los dominios que agregó a la Directiva. Puede elegir distintas acciones para los usuarios y los dominios en la misma directiva contra la suplantación de identidad (phishing). Estas acciones se aplican a cualquier correo electrónico entrante que haya sido identificado por Office 365 como suplantación de una cuenta de usuario o dominio que se encuentra bajo la protección de esta Directiva contra la suplantación de identidad.  <br/> **Mensaje en cuarentena** El correo electrónico se enviará a la cuarentena de Office 365. Si elige esta opción, no se enviará el correo electrónico al destinatario original.  <br/> **Redirigir un mensaje a otra dirección de correo electrónico** El correo electrónico se enviará a la dirección de correo electrónico que especifique. Puede especificar varias direcciones de correo electrónico. Si elige esta opción, no se enviará el correo electrónico al destinatario original.  <br/> **Mover el mensaje a la carpeta de correo no deseado de los destinatarios** El correo electrónico se enviará a la carpeta de correo no deseado de los destinatarios. Cuando elige esta opción, el correo electrónico se sigue enviando al destinatario original, pero no se coloca en la bandeja de entrada del destinatario.  <br/> **Entregar el mensaje y agregar otras direcciones a la línea CCO** El correo electrónico se entregará al destinatario original. Además, los usuarios que identifique se agregarán a la línea CCO del mensaje antes de su entrega. Cuando elige esta opción, el correo electrónico se sigue enviando a la bandeja de entrada del destinatario original.  <br/> **No aplicar ninguna acción** El correo electrónico se entregará en la bandeja de entrada del destinatario original. No se realizará ninguna otra acción en el mensaje de correo electrónico.  <br/> **Activar sugerencias de protección contra suplantación de identidad** Habilita las sugerencias de seguridad contra el phishing en el correo electrónico.  <br/> |Cuando desee realizar una acción en los mensajes que Office 365 haya determinado como una suplantación de un usuario o dominio, tal como se define en la Directiva.  <br/> |
|**Habilitar la inteligencia de buzones** <br/> |Habilita o deshabilita la inteligencia de buzones para esta Directiva. Solo se puede habilitar la inteligencia de buzones de correo para cuentas basadas en la nube, es decir, cuentas cuyo buzón de correo se hospeda completamente en Office 365. La inteligencia de buzones también se puede habilitar para la suplantación de usuario. <br/> |Cuando desee mejorar los resultados de la suplantación para los usuarios en función del mapa de remitentes individuales de cada usuario. La inteligencia de buzones de correo se crea en torno a las personas que envían y reciben correo desde dentro de la organización y fuera de la organización. Esta inteligencia permite a Office 365 personalizar la detección de suplantación de usuario y administrar mejor los falsos positivos. Cuando se detecta la suplantación del usuario, en función de la inteligencia de buzones de correo, puede definir la acción que se llevará a cabo en el mensaje. <br/> |
|**Agregar dominios y remitentes de confianza** <br/> |Define las direcciones de correo electrónico y los dominios que no se considerarán suplantación por esta Directiva. Los mensajes de las direcciones de correo electrónico y los dominios de remitentes que agregue como remitentes y dominios de confianza nunca se clasificarán como un ataque basado en suplantación. Como resultado, las acciones y la configuración relacionadas con la suplantación definida en esta Directiva no se aplicarán a los mensajes de estos remitentes y dominios.  <br/><br/>El límite máximo de estas listas es de aproximadamente 1000 entradas. |Cuando los usuarios interactúan con dominios o usuarios que desencadenan la suplantación, pero se consideran seguros. Por ejemplo, si un asociado tiene el mismo nombre para mostrar o nombre de dominio similar que un usuario definido en la lista.  <br/> |
|**Aplicado a** <br/> |Define los destinatarios cuyos mensajes de correo electrónico entrantes estarán sujetos a las reglas de la Directiva. Puede crear condiciones y excepciones para los destinatarios asociados con la Directiva.  <br/> Por ejemplo, puede crear una directiva global para su organización aplicando la regla a todos los destinatarios de su dominio.  <br/> También puede crear reglas de excepción, como una regla que no analiza los mensajes de correo electrónico de un grupo específico de destinatarios.  <br/> |Cada Directiva debe estar asociada a un conjunto de usuarios, por ejemplo, a los usuarios de un grupo o dominio en particular.  <br/> |
|**Umbrales de suplantación de identidad avanzada** <br/> |Define el nivel de configuración de la forma en que se administran los mensajes de suplantación de identidad.  <br/> **Estándar** El correo electrónico sospechoso de ser phish se trata de la forma estándar.  <br/> **Agresivo** El sistema controla el correo electrónico sospechoso de ser phish con un grado alto o muy alto de confianza.  <br/> **Más agresivo** El sistema controla el correo electrónico sospechoso de ser phish con un grado de confianza medio, alto o muy alto de la misma manera.  <br/> **Más agresivo** El sistema controla el correo electrónico sospechoso de ser phish con un grado de confianza bajo, medio, alto o muy alto, de la misma forma.  <br/> |Cuándo desea ser más agresivo en el tratamiento de los mensajes de suplantación de identidad en Office 365. Por ejemplo, los mensajes con una probabilidad muy alta de ser phish tendrán las acciones más agresivas que se tomen en ellos, mientras que los mensajes con una probabilidad baja tienen menos acciones agresivas que se realizan en ellos. Esta configuración también influye en otras partes del sistema de filtrado que combinan señales. Esto no significa necesariamente que se implementen distintas acciones.  Básicamente, se establece la probabilidad de que el correo sea phish, para determinar la (misma) acción designada. La posibilidad de mover los mensajes correctos aumenta a medida que aumenta el nivel de configuración.  <br/>|

## <a name="learn-about-anti-phishing-policy-options"></a>Obtener información sobre las opciones de la Directiva antiphishing

Al configurar o editar su antiphishing, puede elegir entre varias opciones, como se describe en la tabla siguiente: 

|**Esta configuración**|**Se obtiene este resultado**|**Se usa cuando se desea:**|
|:-----|:-----|:-----|
|**Aplicado a** <br/> |Define los destinatarios cuyos mensajes de correo electrónico entrantes estarán sujetos a las reglas de la Directiva. Puede crear condiciones y excepciones para los destinatarios asociados con la Directiva.  <br/> Por ejemplo, puede crear una directiva global para su organización aplicando la regla a todos los destinatarios de su dominio.  <br/> También puede crear reglas de excepción, como una regla que no analiza los mensajes de correo electrónico de un grupo específico de destinatarios.  <br/> |Cada Directiva debe estar asociada a un conjunto de usuarios, por ejemplo, a los usuarios de un grupo o dominio en particular.  <br/> | 
|**Elegir acciones** <br/> |Elija la acción que se realizará cuando Office 365 detecte un intento de imitación dentro de una organización o de una organización externa contra los usuarios. Estas acciones se aplican a cualquier correo electrónico entrante que haya sido identificado por Office 365 como un intento de suplantación para los usuarios que se encuentran bajo la protección de esta Directiva contra la suplantación de identidad.  <br/> **Mensaje en cuarentena** El correo electrónico se enviará a la cuarentena de Office 365. Si elige esta opción, no se enviará el correo electrónico al destinatario original.  <br/> **Mover el mensaje a la carpeta de correo no deseado de los destinatarios** El correo electrónico se enviará a la carpeta de correo no deseado de los destinatarios. Cuando elige esta opción, el correo electrónico se sigue enviando al destinatario original, pero no se coloca en la bandeja de entrada del destinatario.  <br/> **No aplicar ninguna acción** El correo electrónico se entregará en la bandeja de entrada del destinatario original. No se realizará ninguna otra acción en el mensaje de correo electrónico.  <br/> |Cuando desee realizar una acción en los mensajes que Office 365 haya determinado como un intento de suplantación de dominios internos o externos según se haya definido en la Directiva.  <br/>|

Una vez que la organización haya configurado las directivas antiphishing o las directivas antiphishing de ATP, puede ver cómo funciona el servicio mediante la [visualización de informes para la protección contra amenazas avanzada](view-reports-for-atp.md).
  
## <a name="example-anti-phishing-policy-to-protect-a-user-and-a-domain"></a>Ejemplo: Directiva contra la suplantación de identidad (phishing) para proteger un usuario y un dominio

En este ejemplo se configura una directiva denominada "domain and CEO" que proporciona protección de usuarios y dominios de suplantación y, a continuación, aplica la Directiva a todos los correos electrónicos `contoso.com`recibidos por los usuarios del dominio. El administrador de seguridad ha determinado que la Directiva debe cumplir con estos requisitos empresariales:
  
- La Directiva debe proporcionar protección para la cuenta de correo electrónico del CEO y para todo el dominio.

- Los mensajes que se determinan como intentos de suplantación con la cuenta de usuario del CEO deben redirigirse a la dirección de correo electrónico del administrador de seguridad.

- Los mensajes que se determinan como intentos de suplantación con el dominio son menos urgentes y deben estar en cuarentena para revisarlos posteriormente.

El administrador de seguridad de Contoso podría usar valores como los siguientes para crear una directiva antiphishing que satisfaga estas necesidades.
  
|||
|:-----|:-----|
|**Configuración u opción** <br/> |**Ejemplo** <br/> |
|Nombre  <br/> |Dominio y CEO  <br/> |
|Descripción  <br/> |Asegúrese de que el CEO y nuestro dominio no se suplantan.  <br/> |
|Agregar usuarios para protegerlos  <br/> |La dirección de correo electrónico del CEO como mínimo.  <br/> |
|Agregar dominios para proteger  <br/> |El dominio de la organización que incluye la oficina del CEO.  <br/> |
|Elegir acciones  <br/> |Si un usuario suplantado envía un correo electrónico: elija redirigir **un mensaje a otra dirección de correo electrónico** y, a continuación, escriba la dirección de correo `securityadmin@contoso.com`electrónico del administrador de seguridad, por ejemplo,.  <br/> Si un dominio suplantado envía un correo electrónico: elija **mensaje en cuarentena**.  <br/> |
|Inteligencia de buzones  <br/> |De forma predeterminada, la inteligencia de buzones se selecciona cuando se crea una nueva Directiva antiphishing. Deje esta configuración **activada** para obtener los mejores resultados.  <br/> |
|Agregar dominios y remitentes de confianza  <br/> |Para este ejemplo, no defina ningún reemplazo.  <br/> |
|Aplicado a  <br/> |Seleccione **el dominio del destinatario es**. En **cualquiera de estos**, seleccione **elegir**. Seleccione **+ Agregar**. Active la casilla de verificación situada junto al nombre del dominio, por ejemplo `contoso.com`, en la lista y, a continuación, seleccione **Agregar**. Seleccione **listo**.  <br/> |

## <a name="delete-an-anti-phishing-or-atp-anti-phishing-policy"></a>Eliminación de una directiva antiphishing de ATP o contra la suplantación de identidad

Puede eliminar las directivas personalizadas que haya creado mediante el centro de &amp; seguridad y cumplimiento. No puede eliminar la directiva predeterminada para su organización. Se recomienda usar el centro &amp; de seguridad y cumplimiento para revisar o editar cualquiera de las directivas de ATP.
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa.

2. En el panel de navegación izquierdo, en **Administración de amenazas**, elija **Directiva**.

3. En la página **Directiva** , elija **anti-phishing** o **ATP antiphishing**.

4. En la página contra la suplantación de identidad **(phishing** ) de **ATP** , seleccione el nombre de la Directiva de la lista.

5. En la página que aparece, elija **eliminar Directiva**. Espere hasta 30 minutos para que los cambios se extiendan a todos los centros de seguridad de Office 365.

## <a name="next-steps"></a>Pasos siguientes

Una vez que se hayan implementado las directivas antiphishing, podrá ver cómo funcionan las características de protección contra amenazas en su organización al ver los informes. Vea los siguientes recursos para obtener más información:

- [Ver informes para Office 365 ATP](view-reports-for-atp.md) o [ver informes de seguridad de correo electrónico](view-email-security-reports.md)

- [Usar el explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md)

Manténgase al tanto de las nuevas características que llegarán a ATP. visite el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) y obtenga información sobre [las nuevas características que se agregan a ATP](office-365-atp.md#new-features-in-office-365-atp).
