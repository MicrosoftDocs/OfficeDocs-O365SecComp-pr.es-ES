---
title: Buscar e investigar correo electrónico malintencionado que se entregó en Office 365
keywords: TIMailData-en línea, incidente de seguridad, incidente, ATP PowerShell, malware de correo electrónico, usuarios comprometidos, phishing de correo electrónico, malware de correo electrónico, leer encabezados de correo electrónico, leer encabezados, abrir encabezados de correo electrónico
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo usar la investigación de amenazas y las capacidades de respuesta para buscar y investigar correo electrónico malintencionado.
ms.openlocfilehash: a57e72c74a7b2f819ecee7fbf604795e4a094693
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761686"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-in-office-365"></a>Buscar e investigar correo electrónico malintencionado que se entregó en Office 365

La [protección contra amenazas avanzada de Office 365](office-365-atp.md) le permite investigar las actividades que ponen en riesgo a las personas de su organización y emprender acciones para proteger a su organización. Por ejemplo, si forma parte del equipo de seguridad de su organización, puede encontrar e investigar los mensajes de correo electrónico sospechosos que se entregaron. Para ello, puede usar el [Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md).
  
## <a name="before-you-begin"></a>Antes de comenzar...

Asegúrese de que se cumplen los siguientes requisitos:
  
- Su organización tiene [Office 365 de protección contra amenazas avanzada](office-365-atp.md) y [se asignan licencias a los usuarios](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).
    
- El [registro de auditoría de Office 365](turn-audit-log-search-on-or-off.md) está activado para su organización. 
    
- Su organización tiene directivas definidas para protección contra correo electrónico no deseado, antimalware, antiphishing, etc. Consulte [proteger contra amenazas en Office 365](protect-against-threats.md).
    
- Es un administrador global de Office 365 o bien tiene el rol de administrador de seguridad o de búsqueda y depuración asignado en &amp; el centro de seguridad y cumplimiento. Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md). Para algunas acciones, también debe tener asignado un nuevo rol de vista previa. 

#### <a name="preview-role-permissions"></a>Vista previa de permisos de roles

Para realizar determinadas acciones, como ver los encabezados de mensajes o descargar el contenido de los mensajes de correo electrónico, debe tener un nuevo rol denominado *vista previa* agregada a otro grupo de roles de Office 365 adecuado. La siguiente tabla clarifica los permisos y las funciones necesarias.

|Actividad  |Grupo de funciones |¿Se requiere un rol de vista previa?  |
|---------|---------|---------|
|Usar el explorador de amenazas (y detecciones en tiempo real) para analizar las amenazas     |Administrador global de Office 365 <br> Administrador de seguridad <br> Lector de seguridad     | No   |
|Usar el explorador de amenazas (y detecciones en tiempo real) para ver los encabezados de los mensajes de correo electrónico, así como para obtener una vista previa y descargar los mensajes de correo electrónico en cuarentena    |Administrador global de Office 365 <br> Administrador de seguridad <br>Lector de seguridad   |       No  |
|Usar el explorador de amenazas para ver los encabezados y descargar los mensajes de correo electrónico que se entregan a los buzones     |Administrador global de Office 365 <br>Administrador de seguridad <br> Lector de seguridad <br> Vista previa   |   Sí      |

> [!NOTE]
> La *vista previa* es un rol y no un grupo de roles; el rol de vista previa debe agregarse a un grupo de roles existente para Office 365. El rol de administrador global de Office 365 se asigna al centro de administración[https://admin.microsoft.com](https://admin.microsoft.com)de Microsoft 365 () y los roles de administrador de seguridad y lector de seguridad se asignan en el[https://protection.office.com](https://protection.office.com)centro de seguridad & cumplimiento de Office 365 (). Para obtener más información acerca de los roles y los permisos, consulte [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Buscar y eliminar correo electrónico sospechoso que se entregó

El explorador de amenazas es un informe eficaz que puede servir para varios propósitos, como buscar y eliminar mensajes, identificar la dirección IP de un remitente de correo electrónico malintencionado o iniciar un incidente para una mayor investigación. El siguiente procedimiento se centra en usar el explorador para buscar y eliminar correo electrónico malintencionado de los buzones de los destinatarios.

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365. Esto le llevará al centro de &amp; seguridad y cumplimiento. 
    
2. En el panel de navegación izquierdo, elija **Threat Management** \> **Explorer**.

    ![Explorador con los campos acción de entrega y ubicación de entrega.](media/ThreatExFields.PNG)

    Es posible que observe la nueva columna **acciones especiales** . Esta característica está destinada a comunicar a los administradores el resultado del procesamiento de un correo electrónico. Se puede tener acceso a la columna **acciones especiales** en el mismo lugar que la **acción de entrega** y la **Ubicación de entrega**. Las acciones especiales podrían actualizarse al final de la escala de tiempo de correo electrónico del explorador de amenazas, que es una nueva característica destinada a mejorar la experiencia de búsqueda para los administradores.

3. Para ver una escala de tiempo de correo electrónico, haga clic en el asunto de un mensaje de correo electrónico y, a continuación, en **correo electrónico escala de tiempo**. (Aparece entre otros títulos en el panel, como **Resumen** o **detalles**).

    Una vez que haya abierto la escala de tiempo de correo electrónico, verá una tabla que le indicará los eventos posteriores a la entrega para ese correo. En el caso de que no haya más eventos para el correo electrónico, debería ver un evento único para la entrega original que indique un resultado como **bloqueado** con un veredicto como **phish**. La pestaña también tiene la opción de exportar toda la escala de tiempo de correo electrónico y, de este modo, se exportan todos los detalles de la ficha y los detalles del correo electrónico (cosas como asunto, remitente, destinatario, red e identificador del mensaje).

    La escala de tiempo del correo electrónico reduce la aleatoriedad porque hay menos tiempo dedicado a comprobar las distintas ubicaciones para tratar de comprender los eventos que han sucedido desde que llegó el correo electrónico. Cuando se producen varios eventos en, o cerca de, al mismo tiempo en un correo electrónico, esos eventos se muestran en una vista de escala de tiempo. 
    
    Algunos de los eventos que se producen después de la entrega a su correo se capturan en la columna **acciones especiales** . La combinación de la información de la escala de tiempo de correo electrónico junto con acciones especiales realizadas en la entrega de correo electrónico proporciona a los administradores información sobre cómo funcionan sus directivas, dónde se enrutaron finalmente el correo electrónico y, en algunos casos, qué es la evaluación final. 

4. En el menú **Ver** , elija **todo el correo electrónico**.

    ![Usar el menú Ver para elegir entre los informes de correo electrónico y de contenido](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    Observe las etiquetas que aparecen en el informe, como **entregado**, **desconocido**o **entregado a correo no deseado**.

    ![Explorador de amenazas que muestra datos de todo el correo electrónico](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    (En función de las acciones realizadas en los mensajes de correo electrónico de su organización, es posible que vea otras etiquetas, como **bloqueado** o **reemplazado**.)
    
6. En el informe, seleccione **entregado** para ver solo los mensajes de correo electrónico que finalizaron en las bandejas de los usuarios.

    ![Al hacer clic en "entregado a correo no deseado" se quitan los datos de la vista](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
7. Debajo del gráfico, revise la lista de **correo electrónico** que hay debajo del gráfico.

    ![Debajo del gráfico, se muestra una lista de los mensajes de correo electrónico que se detectaron](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
8. En la lista, elija un elemento para ver más detalles sobre el mensaje de correo electrónico. Por ejemplo, puede hacer clic en la línea de asunto para ver información sobre el remitente, los destinatarios, los datos adjuntos y otros mensajes de correo electrónico similares.

    ![Puede ver información adicional acerca de un elemento](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
9. Después de ver la información sobre los mensajes de correo electrónico, seleccione uno o más elementos de la lista para activar **+ acciones**.
    
10. Utilice la lista de **acciones +** para aplicar una acción, como **mover a elementos eliminados** . Esto elimina los mensajes seleccionados de los buzones de correo de los destinatarios.

    ![Al seleccionar uno o más mensajes de correo electrónico, puede elegir entre varias acciones disponibles.](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## <a name="dealing-with-suspicious-email-messages"></a>Tratar mensajes de correo electrónico sospechosos

Los atacantes malintencionados podrían enviar correo a personas de su organización para intentar phish sus credenciales y obtener acceso a sus secretos corporativos. Para ayudar a evitar esto, use los servicios de protección contra amenazas en Office 365, incluidos [Exchange Online Protection](eop/exchange-online-protection-overview.md) y la [protección contra amenazas avanzada](office-365-atp.md). Sin embargo, ocasionalmente se produce que un atacante envía un correo electrónico que contiene un vínculo (URL) que sólo más adelante apunta a contenido malintencionado (como malware). O bien, es posible que se vea demasiado tarde si alguien de su organización se ha puesto en peligro y, mientras se ha puesto en peligro, el atacante ha usado su cuenta para enviar correo electrónico a otros usuarios de la organización. Como parte de la gestión de cualquiera de estos escenarios, puede quitar los mensajes de correo electrónico sospechosos de las bandejas de los usuarios. Para ello, puede usar el [Explorador de amenazas](threat-explorer.md).

## <a name="finding-re-routed-email-messages-after-actions-are-taken"></a>Buscar mensajes de correo electrónico redireccionados una vez realizadas las acciones

El explorador de amenazas proporciona a su equipo de operaciones de seguridad los detalles que necesitan para investigar el correo electrónico sospechoso. El equipo de operaciones de seguridad puede:

- [Ver los encabezados de correo electrónico y descargar el cuerpo del correo electrónico](#view-the-email-headers-and-download-the-email-body) 

- [Comprobar la acción y la ubicación de la entrega](#check-the-delivery-action-and-location)

- [Ver la escala de tiempo del correo electrónico](#view-the-timeline-of-your-email)

### <a name="view-the-email-headers-and-download-the-email-body"></a>Ver los encabezados de correo electrónico y descargar el cuerpo del correo electrónico

La capacidad de obtener una vista previa de los encabezados de correo electrónico y descargar el cuerpo de un cuerpo de correo electrónico son funciones eficaces en el explorador de amenazas. Se deben asignar [los permisos](permissions-in-the-security-and-compliance-center.md) adecuados. Consulte [Preview role Permissions](#preview-role-permissions).

Para obtener acceso al encabezado del mensaje y a las opciones de descarga del correo electrónico, siga estos pasos: 

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365. Esto le llevará al centro de &amp; seguridad y cumplimiento. 
    
2. En el panel de navegación izquierdo, elija **Threat Management** \> **Explorer**.

3. Haga clic en un asunto en la tabla del explorador de amenazas. 

    Se abrirá el control flotante, donde se colocan tanto la vista previa del encabezado como los vínculos de descarga de correo electrónico.

    ![Control flotante del explorador de amenazas con vínculos de descarga y vista previa en la página.](media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> Esta funcionalidad no se muestra para los mensajes de correo electrónico que nunca se encontraron en el buzón de un usuario, lo que puede ocurrir si se perdió un correo electrónico o se produjo un error en su entrega. En los casos en los que se eliminaron los mensajes de correo electrónico de los buzones de los usuarios, los administradores ven el mensaje de error "no se encuentra el correo".

### <a name="check-the-delivery-action-and-location"></a>Comprobar la acción y la ubicación de la entrega

En el [Explorador de amenazas (y en detección en tiempo real)](threat-explorer.md), ahora tiene columnas de **acción de entrega** y ubicación de **entrega** en lugar de la columna de **Estado de entrega** anterior. Esto da como resultado una imagen más completa de la ubicación de los mensajes de correo electrónico. Parte del objetivo de este cambio es facilitar la búsqueda de operaciones de seguridad, pero el resultado neto es conocer la ubicación de los mensajes de correo electrónico con problemas de un vistazo.

El estado de entrega ahora se divide en dos columnas:

- **Acción de entrega** : ¿Cuál es el estado de este correo electrónico?

- **Ubicación de entrega** : ¿Dónde se distribuyó este correo electrónico como resultado?

La acción de entrega es la acción que se realiza en un correo electrónico debido a las directivas o detecciones existentes. Estas son las posibles acciones que puede realizar un correo electrónico:

- **Delivered** : el correo electrónico se entregó a la bandeja de entrada o a la carpeta de un usuario y el usuario puede acceder a él directamente.

- Correo electrónico **no deseado** : el correo electrónico se envió a la carpeta de correo no deseado o a la carpeta eliminada del usuario y el usuario tiene acceso a los mensajes de correo electrónico en su carpeta de correo no deseado o eliminado.

- **Bloqueado** : todos los mensajes de correo electrónico que se hayan puesto en cuarentena, que hayan fallado o que se hayan quitado. (El usuario no tiene acceso completamente a esto).

- **Reemplazado** : cualquier correo electrónico en el que los datos adjuntos malintencionados se reemplazan por archivos. txt que indican que los datos adjuntos eran malintencionados.
 
Ubicación de entrega muestra los resultados de las directivas y detecciones que se ejecutan después de la entrega. Está vinculado a una acción de entrega. Este campo se agregó para proporcionar información sobre la acción tomada cuando se encuentra un mensaje problemático. Estos son los valores posibles de la ubicación de entrega:

- **Bandeja de entrada o carpeta** : el correo electrónico está en la bandeja de entrada o en una carpeta (según las reglas de correo electrónico).

- Local **o externa** : el buzón de correo no existe en la nube pero es local.

- **Carpeta de correo no deseado** : el correo electrónico se encuentra en la carpeta de correo no deseado del usuario.

- **Carpeta elementos eliminados** : el correo electrónico se encuentra en la carpeta elementos eliminados del usuario.

- **Cuarentena** : el correo electrónico que se encuentra en cuarentena y no en el buzón de un usuario.

- **Failed** – el correo electrónico no pudo llegar al buzón.

- **Descartado** : el correo electrónico se pierde en algún lugar del flujo de correo.

### <a name="view-the-timeline-of-your-email"></a>Ver la escala de tiempo del correo electrónico
  
La **escala de tiempo de correo electrónico** es un campo en el explorador de amenazas que facilita la búsqueda del equipo de operaciones de seguridad. Cuando se producen varios eventos en o cerca de la misma hora en un correo electrónico, esos eventos se muestran en una vista de escala de tiempo. Algunos de los eventos que se producen después de la entrega en el correo electrónico se capturan en la columna **acciones especiales** . La combinación de información de la escala de tiempo de un mensaje de correo electrónico con cualquier acción especial realizada tras la entrega proporciona a los administradores información sobre las directivas y el tratamiento de las amenazas (por ejemplo, dónde se enrutó el correo y, en algunos casos, qué es la evaluación final).
  
## <a name="related-topics"></a>Temas relacionados

[Protección contra amenazas avanzada de Office 365](office-365-ti.md)
  
[Protección contra amenazas en Office 365](protect-against-threats.md)
  
[Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)
  

