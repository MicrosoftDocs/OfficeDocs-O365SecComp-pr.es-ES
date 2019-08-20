---
title: Busque y investigue el correo electrónico malintencionado que se entregó en Office 365, TIMailData-en línea, incidente de seguridad, incidente, PowerShell de ATP, malware de correo electrónico, usuarios comprometidos, phish a correo electrónico, malware de correo electrónico, leer encabezados de correo, leer encabezados, abrir encabezados de correo electrónico
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 08/07/2019
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
ms.openlocfilehash: 2049b3b8e0d7b9173639af3c48f75a072744fb7f
ms.sourcegitcommit: dbcb3df3b313f7a9ea6669425e0a0498be844ae9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "36444879"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-in-office-365"></a>Buscar e investigar correo electrónico malintencionado que se entregó en Office 365

La [protección contra amenazas avanzada de Office 365](office-365-atp.md) le permite investigar actividades que pongan en riesgo a los usuarios y emprender acciones para proteger su organización. Por ejemplo, si forma parte del equipo de seguridad de su organización, puede encontrar e investigar los mensajes de correo electrónico sospechosos que se entregaron a los usuarios. Para ello, puede usar el [Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md).
  
## <a name="before-you-begin"></a>Antes de comenzar...

Asegúrese de que se cumplen los siguientes requisitos:
  
- Su organización tiene [Office 365 de protección contra amenazas avanzada](office-365-atp.md) y [se asignan licencias a los usuarios](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).
    
- El [registro de auditoría de Office 365](turn-audit-log-search-on-or-off.md) está activado para su organización. 
    
- Su organización tiene directivas definidas para protección contra correo electrónico no deseado, antimalware, antiphishing, etc. Consulte [proteger contra amenazas en Office 365](protect-against-threats.md).
    
- Es un administrador global de Office 365 o bien tiene el rol de administrador de seguridad o de búsqueda y depuración asignado en &amp; el centro de seguridad y cumplimiento. Consulte [permisos en el centro de seguridad &amp; y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).
    
## <a name="dealing-with-suspicious-emails"></a>Tratar los correos sospechosos

Los atacantes malintencionados pueden enviar correo a sus usuarios para probar y phish sus credenciales y obtener acceso a sus secretos corporativos. Para evitarlo, debe usar los servicios de protección contra amenazas en Office 365, incluidos [Exchange Online Protection](eop/exchange-online-protection-overview.md) y la [protección contra amenazas avanzada](office-365-atp.md). Sin embargo, hay veces en las que un atacante puede enviar correo a los usuarios que contengan una dirección URL y que, más adelante, esta dirección URL apunte a contenido malintencionado (malware, etc.). 

Como alternativa, es posible que se vea demasiado tarde que un usuario de la organización se ha puesto en peligro y, mientras que el usuario ha estado en peligro, el atacante ha usado esa cuenta para enviar correo electrónico a otros usuarios de la compañía. Como parte de la limpieza de ambos escenarios, es posible que desee quitar los mensajes de correo electrónico de las bandejas de los usuarios. En situaciones como estas, puede aprovechar [el explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md) para buscar y quitar los mensajes de correo electrónico.

## <a name="where-re-routed-emails-are-located-after-actions-are-taken"></a>Dónde se encuentran los mensajes de correo electrónico redistribuidos una vez que se llevan a cabo acciones

Entonces, ¿dónde se envían los mensajes de correo electrónico y qué herramientas ayudan a los investigadores a comprender qué les ha ocurrido? Los campos del explorador de amenazas reportan información que ayudará a los administradores a descodificar eventos de correo electrónico con problemas.

### <a name="view-the-email-headers-and-download-the-email-body"></a>Ver los encabezados de correo electrónico y descargar el cuerpo del correo electrónico

**La vista previa del encabezado de correo electrónico y la descarga del cuerpo del correo** electrónico son características útiles de administración de amenazas de correo electrónico disponibles en el explorador de amenazas. Los administradores podrán analizar y descargar encabezados y correos electrónicos en busca de amenazas. El acceso para usar esta característica está controlado por el control de acceso basado en roles (RBAC), para reducir el riesgo de exposición del contenido de correo electrónico del usuario.

Un nuevo *rol*, denominado "vista previa", debe agregarse a otro grupo de roles de Office 365 (por ejemplo, a operaciones de la SEC o administrador de la SEC) para conceder la capacidad de descargar correos y obtener una vista previa de los encabezados en la vista de todos los correos electrónicos.

Para ver el control flotante con la descarga de correo electrónico y las opciones de vista previa de encabezado de correo electrónico: 

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365. Esto le llevará al centro de &amp; seguridad y cumplimiento. 
    
2. En el panel de navegación izquierdo, elija **Threat Management** \> **Explorer**.

3. Haga clic en un asunto en la tabla del explorador de amenazas.

Se abrirá el control flotante, donde se colocan tanto la vista previa del encabezado como los vínculos de descarga de correo electrónico.

> [!IMPORTANT]
> Use las siguientes tablas juntas. Uno le indica el RBAC obligatorio, el otro, la ubicación donde se deben conceder los derechos.
<p>

|Actividad  |RoleGroup de RBAC con acceso |¿El rol "vista previa" es necesario?  |
|---------|---------|---------|
|Usar el explorador de amenazas (y detecciones en tiempo real) para analizar las amenazas     |  Administrador global de Office 365,<br> Administrador de seguridad, <br> Lector de seguridad      | No   |
|Usar el explorador de amenazas (y detecciones en tiempo real) para ver los encabezados de los mensajes de correo electrónico, y para descargar los mensajes de correo electrónico en cuarentena    |     Administrador global de Office 365, <br> Administrador de seguridad, <br>Lector de seguridad    |       No  |
|Usar el explorador de amenazas para ver los encabezados y descargar los correos electrónicos que se entregan a los buzones     |      Administrador global de Office 365, <br>Administrador de seguridad,<br> Lector de seguridad, <br> Vista previa    |   Sí      |

<br>

|RoleGroup de RBAC  |Dónde se les asignan los usuarios  |
|---------|---------|
| Administrador global   | Centro de administración de Office 365        |
| Administrador de seguridad      |    Centro de seguridad y cumplimiento     |
| Lector de seguridad   |    Centro de seguridad y cumplimiento     |
|      |    Centro de seguridad y cumplimiento     |


> [!CAUTION]
> Recuerde que ' vista previa ' es un rol y no un RoleGroup y que el rol debe agregarse a un RoleGroup posteriormente.

![Control flotante del explorador de amenazas con vínculos de descarga y vista previa en la página.](media/ThreatExplorerDownloadandPreview.PNG)

### <a name="check-the-delivery-action-and-location"></a>Comprobar la acción y la ubicación de la entrega

Detecciones en tiempo real del explorador de amenazas ha agregado los campos acción de entrega y ubicación de entrega en el estado del lugar de entrega. Esto da como resultado una imagen más completa de dónde se encuentran los correos electrónicos. Parte del objetivo de este cambio es facilitar la búsqueda para los operadores de seguridad, pero el resultado neto es conocer la ubicación de los correos electrónicos con problemas de un vistazo.

El estado de entrega ahora se divide en dos columnas:

- **Acción de entrega** : ¿Cuál es el estado de este correo electrónico?
- **Ubicación de entrega** : ¿Dónde se distribuyó este correo electrónico como resultado?

La acción de entrega es la acción que se realiza en un correo electrónico debido a las directivas o detecciones existentes. Estas son las posibles acciones que puede realizar un correo electrónico:

- **Delivered** : el correo electrónico se entregó a la bandeja de entrada o a la carpeta de un usuario y el usuario puede acceder a él directamente.
- Correo electrónico **no deseado** : el correo electrónico se envió a la carpeta de correo no deseado o a la carpeta eliminada del usuario y el usuario tiene acceso a los correos electrónicos en su carpeta de correo no deseado o eliminado.
- **Bloqueado** : cualquier correo electrónico que esté en cuarentena, que falle o que se haya cancelado. El usuario no tiene acceso completamente a esto.
- **Reemplazado** : cualquier correo electrónico en el que los datos adjuntos malintencionados se reemplazan por archivos. txt que indican que los datos adjuntos eran malintencionados.
 
Ubicación de entrega muestra los resultados de las directivas y detecciones que se ejecutan después de la entrega. Está vinculado a una acción de entrega. Este campo se agregó para proporcionar información sobre la acción tomada cuando se encuentra un mensaje problemático. Estos son los valores posibles de la ubicación de entrega:

- **Bandeja de entrada o carpeta** : el correo electrónico se encuentra en la bandeja de entrada o en una carpeta (según las reglas de correo electrónico).
- Local **o externa** : el buzón de correo no existe en la nube pero es local.
- **Carpeta de correo no deseado** : el correo electrónico en la carpeta de correo no deseado de un usuario.
- **Carpeta elementos eliminados** : el correo electrónico de la carpeta elementos eliminados de un usuario.
- **Cuarentena** : el correo electrónico en cuarentena y no se encuentra en el buzón de un usuario.
- **Failed** – el correo electrónico no pudo llegar al buzón.
- **** Perdido: el correo electrónico se pierde en algún lugar del flujo de correo.

### <a name="view-the-timeline-of-your-email"></a>Ver la escala de tiempo del correo electrónico
  
 **Escala de tiempo de correo electrónico** otro campo del explorador de amenazas también será AKE la búsqueda más sencilla para los administradores. En lugar de dedicar una valiosa comprobación de tiempo en la que el correo electrónico podría haber desaparecido, cuando, mientras investiga un evento, cuando se producen varios eventos en, o cerca de, la misma hora en un correo electrónico, esos eventos se muestran en una vista de escala de tiempo. Algunos de los eventos que se producen después de la entrega a su correo se capturarán en la columna "*acción especial*". La combinación de información de la escala de tiempo del correo con la acción especial tomada en la entrega posterior de correo proporciona a los administradores información sobre las directivas y el tratamiento de amenazas (por ejemplo, dónde se enrutó el correo y, en algunos casos, qué es la evaluación final).

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Buscar y eliminar correo electrónico sospechoso que se entregó

> [!TIP]
> El explorador de amenazas (a veces denominado explorador) es un informe eficaz que puede servir para varios propósitos, como buscar y eliminar mensajes, identificar la dirección IP de un remitente de correo electrónico malintencionado o iniciar un incidente para una mayor investigación. El siguiente procedimiento se centra en usar el explorador para buscar y eliminar correo electrónico malintencionado de los buzones de los destinatarios.

Para ver los cambios en el campo Estado de entrega anterior (ahora acción de entrega y ubicación de entrega): 

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa para Office 365. Esto le llevará al centro de &amp; seguridad y cumplimiento. 
    
2. En el panel de navegación izquierdo, elija **Threat Management** \> **Explorer**.


![Explorador de amenazas con los campos acción de entrega y ubicación de entrega.](media/ThreatExFields.PNG)

Puede que vea la nueva columna "acciones especiales" en este gráfico. Esta característica está destinada a comunicar a los administradores el resultado del procesamiento de un correo electrónico. Las acciones especiales pueden actualizarse al final de la escala de *tiempo de correo electrónico*del explorador de amenazas, que es una nueva característica destinada a mejorar la experiencia de búsqueda para los administradores.

La escala de tiempo del correo electrónico reduce la aleatoriedad porque hay menos tiempo dedicado a comprobar diferentes ubicaciones para tratar de comprender los eventos que han sucedido desde que llegó el correo electrónico. Cuando se producen varios eventos en, o cerca de, al mismo tiempo en un correo electrónico, esos eventos se mostrarán en una vista escala de tiempo. Algunos de los eventos que se producen después de la entrega a su correo se capturarán en la columna "acciones especiales". La combinación de la información de la *escala de tiempo de correo electrónico* de ese correo con las *acciones especiales* realizadas en la entrega posterior de correo proporcionará a los administradores información sobre cómo funcionan sus directivas, dónde se enrutó el correo finalmente y, en algunos casos, cuál es el final la evaluación fue. Se puede tener acceso a la columna acciones especiales en el mismo lugar que la acción de entrega y la ubicación de entrega, pero para ver una escala de tiempo de correo electrónico:

1. Haga clic en el asunto del correo electrónico.
2. En el panel que aparece, haga clic en *correo electrónico escala de tiempo*. (Aparecerá entre otros títulos en el panel, como "Resumen" o "detalles", et cetera.)

Una vez que haya abierto la escala de tiempo de correo electrónico, verá una tabla que le indicará los eventos posteriores a la entrega para ese correo o, en el caso de que no haya más eventos para el correo electrónico, verá un solo evento para la entrega original que indicará un resultado como *bloqueado* con un veredicto como *phish*. La pestaña también tiene la opción de exportar toda la escala de tiempo de correo electrónico y, a continuación, se exportarán todos los detalles de la ficha y los detalles del correo electrónico (aspectos como el asunto, el remitente, el destinatario, la red y el identificador del mensaje).

3. En el menú Ver, elija **todo el correo electrónico**.<br/>![Usar el menú Ver para elegir entre los informes de correo electrónico y de contenido](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Observe las etiquetas que aparecen en el informe, como **entregado**, **desconocido**o **entregado a correo no deseado**.<br/>![Explorador de amenazas que muestra datos de todo el correo electrónico](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(En función de las acciones realizadas en los mensajes de correo electrónico de su organización, es posible que vea etiquetas adicionales, como **bloqueado** o **reemplazado**.)
    
5. En el informe, seleccione **entregado** para ver solo los correos electrónicos que finalizaron en las bandejas de correo de los usuarios.<br/>![Al hacer clic en "entregado a correo no deseado" se quitan los datos de la vista](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Debajo del gráfico, revise la lista de **correo electrónico** que hay debajo del gráfico.<br/>![Debajo del gráfico, se muestra una lista de los mensajes de correo electrónico que se detectaron](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. En la lista, elija un elemento para ver más detalles sobre el mensaje de correo electrónico. Por ejemplo, puede hacer clic en la línea de asunto para ver información sobre el remitente, los destinatarios, los datos adjuntos y otros mensajes de correo electrónico similares.<br/>![Puede ver información adicional acerca de un elemento, incluidos los detalles y los datos adjuntos](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. Después de ver la información sobre los mensajes de correo electrónico, seleccione uno o más elementos de la lista para activar **+ acciones**.
    
9. Utilice la lista de **acciones +** para aplicar una acción, como **mover a** elementos eliminados. Se eliminarán los mensajes seleccionados de los buzones de correo de los destinatarios.<br/>![Al seleccionar uno o más mensajes de correo electrónico, puede elegir entre varias acciones disponibles.](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a>Temas relacionados

[Plan 2 de protección contra amenazas avanzada de Office 365](office-365-ti.md)
  
[Protección contra amenazas en Office 365](protect-against-threats.md)
  
[Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)
  

