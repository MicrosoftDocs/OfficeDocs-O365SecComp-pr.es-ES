---
title: Introducción a las directivas de conservación
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 4/3/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid: MET150
ms.assetid: 9c3b1d52-40ce-4ba3-a520-9ae0be15538a
description: Para cumplir con las normativas del sector o las políticas internas, las organizaciones desean conservar el contenido para un determinado período de tiempo. Con una directiva de conservación en Office 365, puede conservar el contenido en sitios, los buzones de correo y las carpetas públicas indefinidamente o durante un tiempo concreto. También puede filtrar el contenido que se conservarán mediante el suministro de palabras clave o un intervalo de fechas para restringir los resultados.
ms.openlocfilehash: a26b85a563dd0e6f9ed8a70bfe9a310fc89a50f2
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272465"
---
# <a name="overview-of-preservation-policies"></a>Introducción a las directivas de conservación

> [!IMPORTANT]
> Si estuviera usando una directiva de conservación, esa directiva se ha convertido automáticamente a una directiva de retención, que es una característica nueva que hace todo lo que hace una directiva de conservación y mucho más. La directiva de conservación seguirán trabajar y conservar el contenido sin necesidad de realizar los cambios del usuario. Puede encontrar estas directivas en la página de **retención** en la seguridad &amp; centro de cumplimiento. Para obtener más información, vea [¿Qué sucedió con las directivas de conservación?](retention-policies.md#what-happened-to-preservation-policies)
  
Para cumplir con las normativas del sector o las políticas internas, las organizaciones desean conservar el contenido para un determinado período de tiempo. Con una directiva de conservación en Office 365, puede conservar el contenido en sitios, los buzones de correo y las carpetas públicas indefinidamente o durante un tiempo concreto. También puede filtrar el contenido que se conservarán mediante el suministro de palabras clave o un intervalo de fechas para restringir los resultados.
  
Por ejemplo, puede conservar el contenido en los sitios que pertenecen al departamento de ventas durante siete años y buzones específicos y restringir aún más el ámbito de la directiva de diciendo que desea conservar sólo contenido de los dos últimos años que contiene una determinada nombre del cliente.
  
Cuando el contenido está sujeto a una directiva de conservación, las personas pueden continuar editar y trabajar con el contenido como si no se cambia nada debido a que el contenido se conserva en su lugar, en su ubicación original. Pero si alguien modifica o elimina contenido que está sujeto a la directiva, se guarda una copia en una ubicación segura donde se conserve mientras la directiva está en vigor.
  
Por último, algunas organizaciones pueden necesitar cumplir con las reglas definidas por los organismos regulatorios como valores and Exchange Commission (s) norma 17a-4, lo cual requiere que después de una directiva de conservación está activada, no puede desactivar o realizado menos restrictiva. Para satisfacer este requisito, puede usar el bloqueo de conservación. Después de una directiva de se ha bloqueado, nadie, incluido el administrador: puede desactivar la directiva o que sea menos restrictiva.
  
Puede crear y administrar las directivas de conservación en la página de retención en la seguridad de Office 365 &amp; centro de cumplimiento.
  
![Página de retención en Office 365 seguridad &amp; centro de cumplimiento](media/edb2e228-efff-4619-89d1-8665b5f38639.png)
  
> [!NOTE]
> Para incluir un buzón de Exchange Online en una directiva de conservación, el buzón de correo debe tener asignada una licencia de Exchange Online Plan 2. Si un buzón se asigna una licencia de Exchange Online Plan 1, tendría que asignar una licencia independiente de archivado de Exchange Online para incluir en una directiva de conservación. 
  
## <a name="how-a-preservation-policy-works-with-content-in-place"></a>Funcionamiento de una directiva de conservación local

Cuando se incluye un sitio, un buzón o una carpeta pública en una directiva de conservación, el contenido permanece en su ubicación original. Pueden seguir trabajando con sus documentos o correo de personas, pero una copia del contenido tal como se encontraba cuando inicia la directiva se conserva. Para los sitios, contenido se conserva en la biblioteca de conservación suspensión; para carpetas públicas y los buzones de correo, contenido se conserva en la carpeta elementos recuperables. Estas ubicaciones seguras y el contenido preservado no están visibles para la mayoría de las personas. Con una directiva de conservación, las personas no es necesario incluso saber que su contenido está sujeto a la directiva.
  
![Diagrama que muestra cómo funcionan las directivas de conservación](media/2c1dd82b-84e0-49e0-ab46-d017df297040.png)
  
### <a name="site-content"></a>Contenido de sitio

Se aplica una directiva de conservación en el nivel de un sitio. Cuando se incluye un sitio en una directiva de conservación, se crea una biblioteca de conservación suspensión, si no existe uno ya. La mayoría de los usuarios no pueden ver la biblioteca de conservación suspensión porque es visible únicamente para los propietarios de colecciones de sitios.
  
Si una persona intenta cambiar o eliminar contenido en un sitio que está sujeto a una directiva de conservación, la directiva comprueba primero si el contenido del se ha cambiado desde que se aplicó la directiva. Si éste es el primer cambio desde que se aplicó la directiva de conservación, la directiva de copia el contenido en la biblioteca de conservación suspensión y, a continuación, permite a la persona cambiar o eliminar el contenido original. Tenga en cuenta que ningún contenido en el sitio se puede copiar a la biblioteca de conservación suspensión, incluso si el contenido no coincide con el filtro de la consulta utilizada por la directiva de conservación.
  
Después, un trabajo del temporizador limpia la biblioteca de conservación de documentos. El trabajo del temporizador se ejecuta periódicamente y compara todo el contenido de la biblioteca de conservación de documentos con los filtros utilizados por las directivas de conservación del sitio. A menos que el contenido coincida con, como mínimo, uno de los filtros, el trabajo del temporizador eliminará permanentemente el contenido de la biblioteca de conservación de documentos.
  
El anterior se aplica al contenido que se produce cuando se aplica la directiva de conservación. Además, cualquier contenido nuevo que ha creado o se agregan al sitio después de se ha incluido en la directiva se conservarán después de la eliminación. Sin embargo, no se copia el contenido nuevo a la hora de la primera biblioteca mantenga presionada la conservación se edita, sólo cuando se ha eliminado. Para conservar las versiones de todos los archivos, debe activar el control de versiones, vea la sección posterior en el control de versiones.
  
### <a name="mailbox-and-public-folder-content"></a>Contenido de buzones y de carpetas públicas

En el caso del correo del usuario y otros elementos, las directivas de conservación se aplican en el nivel de un buzón. En el caso de una carpeta pública, las directivas de conservación se aplican en el nivel de carpeta, no en el nivel de buzón. Tanto un buzón como una carpeta pública usan la carpeta Elementos recuperables para conservar los elementos. Solo las personas a las que se les han asignado permisos de exhibición de documentos electrónicos pueden ver la carpeta Elementos recuperables de otro usuario.  
  
De forma predeterminada, cuando una persona elimina un mensaje de una carpeta distinta de la carpeta Elementos eliminados, el mensaje se mueve a la carpeta Elementos eliminados. Cuando una persona elimina un elemento de la carpeta Elementos eliminados, el mensaje se mueve a la carpeta elementos recuperables y desaparece de la vista del usuario. Además, una persona suave puede eliminar un elemento (MAYÚS + SUPR) en cualquier carpeta, que se omite la carpeta Elementos eliminados y coloca el elemento directamente en la carpeta elementos recuperables.
  
Cuando se incluye un buzón en una directiva de conservación, los elementos eliminados se mueven a la carpeta DiscoveryHold, dentro de la carpeta Elementos recuperables. Cuando el asistente del buzón procesa el buzón periódicamente, analiza los mensajes de esta carpeta. A menos que el contenido coincida con, como mínimo, uno de los filtros que usa una directiva de conservación, el asistente del buzón eliminará permanentemente el contenido de la carpeta Elementos recuperables.
  
La carpeta elementos recuperables también contiene una carpeta de versiones. Cuando una persona intenta cambiar determinadas propiedades de un elemento de buzón de correo, como el asunto, body, datos adjuntos, los remitentes y destinatarios, o envía o recibe un mensaje de fecha: se guarda una copia del elemento original en la carpeta de versiones antes de confirmar el cambio. Esto sucede para cada cambio subsiguiente. Después de que se ha quitado la directiva de conservación, copias en la carpeta de versiones se quitan mediante el Asistente de buzón de correo.
  
### <a name="where-a-preservation-policy-is-stored"></a>Dónde se almacena una directiva de conservación

Cuando se crea una directiva de conservación, se almacena centralmente en la seguridad &amp; centro de cumplimiento y, a continuación, se implementa en los diferentes orígenes de contenido que incluye la directiva, como sitios, los buzones de correo y las carpetas públicas.
  
Después de implementar una directiva de conservación en dichos orígenes de contenido, la directiva funciona exactamente igual que una conservación local de exhibición de documentos electrónicos. Para obtener más información sobre las retenciones locales, vea:
  
- [Contiene información general de exhibición de documentos electrónicos y en contexto](https://go.microsoft.com/fwlink/p/?LinkID=404352) (SharePoint Online) 
    
- [En conservación local y retención por juicio](https://go.microsoft.com/fwlink/p/?LinkID=404353) (Exchange Online) 
    
- [Carpeta elementos recuperables](https://go.microsoft.com/fwlink/p/?LinkID=404354) (Exchange Online) 
    
### <a name="preservation-policy-vs-ediscovery-hold"></a>Directiva de conservación frente a la exhibición de documentos electrónicos

Si bien es cierto que ambas características retención contenido, estas características no deben confundirse porque sirven distintos propósitos:
  
- **Si desea conservar el contenido como parte de un requisito de retención, use una directiva de conservación.** Por ejemplo, si desea conservar el contenido durante siete años como parte del plan de retención, use una directiva de conservación. Una directiva de conservación puede conservar el contenido para un período de tiempo específico y, al final de dicho período de tiempo, el contenido se libera automáticamente desde la directiva. La directiva también se puede bloquear para que nadie pueda desactivar la directiva o que sea menos restrictiva. Una exhibición de documentos electrónicos no se puede bloquear o especificar un período de tiempo. Además, una directiva de conservación con frecuencia tiene una duración de los años, mientras una exhibición de documentos electrónicos son temporal y normalmente duración sólo la duración de un caso legal. 
    
    Además, puede crear una directiva de conservación sin los pasos adicionales que puede requerir la exhibición de documentos electrónicos, como la creación de los casos, agregar a miembros, o busca en este contenido.
    
- **Si necesita retener contenido como parte de un requisito legal o de exhibición de documentos electrónicos, use una exhibición de documentos electrónicos.** Por ejemplo, si necesita retener contenido en ubicaciones específicas como parte de una solicitud legal, use una exhibición de documentos electrónicos. En la exhibición de documentos electrónicos, el contenido relevante para un caso es normalmente confidencial o con privilegios, por lo que distintos casos pueden ser restringidos a los miembros diferentes. Además, exhibición de documentos electrónicos es compatible con las búsquedas de contenido que pueden guardar, obtener una vista previa, analiza con avanzadas exhibición de documentos electrónicos, o exportan los resultados. 
    
    A diferencia de una directiva de conservación, una exhibición de documentos electrónicos no pueden especificar un período de tiempo: una exhibición de documentos electrónicos en vigor hasta que lo desactiva o eliminarla. Además, no se puede bloquear una exhibición de documentos electrónicos.
    
## <a name="how-a-preservation-policy-works-with-document-versions-in-a-site"></a>Funcionamiento de una directiva de conservación con versiones de documentos de un sitio

Una directiva de conservación automáticamente no conserva todas las versiones de un documento en un sitio. Para ello, debe activar el control de versiones para las bibliotecas de documentos en el sitio. Para obtener más información, vea [Habilitar y configurar el control de versiones para una lista o biblioteca](https://go.microsoft.com/fwlink/p/?LinkID=404350).
  
Si se elimina un documento desde un sitio que se va a conservar y está activado el control de versiones del documento para la biblioteca, se conservarán todas las versiones del documento eliminado. 
  
Si no está activado el control de versiones de documento y un elemento está sujeto a varias directivas de conservación, la versión que se conserva es la que está activo cuando cada directiva de conservación en vigor. Por ejemplo, si 27 de versión de un elemento es la más reciente cuando el sitio se conserva la primera vez y versión 51 es la más reciente se conservarán cuando el sitio se mantiene la segunda vez, versiones 27 y 51.
  
## <a name="filtering-a-preservation-policy"></a>Filtrado de una directiva de conservación

Puede restringir el contenido sujeto a una directiva de conservación agregando a la directiva palabras clave o un intervalo de fechas. 
  
![Uso de palabras clave e intervalos de fechas como filtros al crear una política de conservación](media/603cef40-8f7c-4140-956f-28c092273582.png)
  
### <a name="filter-by-using-keywords"></a>Filtrado por palabras clave

Una directiva de conservación es compatible con el lenguaje de consulta de palabras clave (KQL). Por ejemplo, puede usar los operadores básicos y like y o, y se puede hacer una búsqueda de proximidad donde "marketing de NEAR(30) wingtip" identifica los resultados donde es "wingtip" dentro de 30 caracteres de "marketing". Una consulta de palabras clave le ayuda a identificar y conservar sólo el contenido relevante.
  
### <a name="filter-by-using-a-date-range"></a>Filtrado por intervalo de fechas

También puede filtrar la directiva para solo conserve el contenido que se encuentre dentro de un intervalo de fechas específico. En el caso de los mensajes, la fecha debe referirse a la fecha de recepción y, en el caso de los documentos y sitios, la fecha deberá indicar la fecha de modificación. Esto significa que podrá conservar el contenido que incluya los mensajes recibidos y los documentos modificados dentro de un intervalo de fechas concreto, o bien antes o después de una fecha de inicio o finalización.
  
## <a name="preserving-content-for-a-specific-period-of-time"></a>Conservación de contenido durante un período de tiempo específico

Con una directiva de conservación, se puede conservar el contenido indefinidamente o durante un número específico de días, meses o años. Tenga en cuenta que la duración del tiempo de conservación del contenido se calcula a partir de la antigüedad del contenido, no de la fecha de creación de la directiva de conservación. 
  
Por ejemplo, si desea conservar el contenido en un sitio durante siete años y un documento en ese sitio no se ha modificado en seis años, el documento se conservarán para sólo otro año si no se modifica. Si se edita el documento nuevo, se calcula la antigüedad de los documentos de la nueva fecha última modificación y se conservarán por otros siete años.
  
De la misma forma, si quiere conservar el contenido de un buzón durante siete años, y uno de los mensajes se envió hace seis años, el mensaje se conservará solo durante un año más a menos que se modifique la fecha de recepción. En este caso, se guardará una nueva versión del mensaje tal y como existía antes de que se editara en la carpeta Elementos recuperables, y la antigüedad del mensaje se calculará a partir de la nueva fecha de recepción, por lo que se conservará durante otros siete años.
  
![Configuración de la duración de una directiva de conservación nueva](media/455aac78-4c29-4dbb-93a2-b431b99002d9.png)
  
## <a name="locking-a-preservation-policy"></a>Bloquear una directiva de conservación

Algunas organizaciones pueden necesitar cumplir con las reglas definidas por los organismos regulatorios como valores and Exchange Commission (s) norma 17a-4, lo cual requiere que después de una directiva de conservación está activada, no puede desactivar o realizado menos restrictiva. Con conservación de bloqueo, puede bloquear la directiva por lo que ningún otro — incluido el administrador: puede desactivar la directiva o que sea menos restrictiva.
  
Después de una directiva de se ha bloqueado, nadie puede desactivarla o quitar el contenido de la directiva. Y no es posible modificar o eliminar contenido que está sujeto a la directiva durante el período de conservación. Después de la directiva del se ha bloqueado, son las formas sólo puede modificar la directiva de conservación mediante la adición de contenido a ella o la ampliación de su duración. Una directiva de bloqueada se puede incrementar o extendida, pero no puede ser reducido o desactivado.
  
Por lo tanto, antes de bloquear una directiva de conservación, es muy importante que comprenda los requisitos de cumplimiento de normas de la organización y no bloquean una directiva hasta que esté seguro de que es lo que necesita.
  
![Opción para activar el Bloqueo de conservación](media/cf9cc070-ddfb-469c-a47e-f88005a82fe4.png)
  
## <a name="turning-off-a-preservation-policy"></a>Desactivación de una directiva de conservación

Si decide no bloquear la directiva de conservación, puede liberarlo en cualquier momento, incluso antes de finalizar el período de tiempo especificado por la directiva. Para ello, simplemente desactive la directiva.
  
![Opción para desactivar una directiva de conservación de la página de retención de la seguridad &amp; centro de cumplimiento](media/fdb44455-da01-4480-8fa6-0e3b29b1f535.png)
  
Sin embargo, no se puede eliminar una directiva de conservación mientras aún activa de la directiva. Para eliminar una directiva de conservación, primero tendrá que desactivar y, a continuación, eliminar la directiva.
  
Después de desactivar una directiva de conservación, todos los elementos sujetos a esa directiva en la biblioteca de conservación mantenga o la carpeta de elementos recuperables son aptos para el proceso de limpieza estándar que se ha descrito anteriormente. Tenga en cuenta que esto significa que los elementos publicada el de una directiva no se eliminan inmediatamente; en su lugar, permanecen en la biblioteca de conservación mantenga o la carpeta de elementos recuperables hasta que el proceso periódicamente limpia la biblioteca o carpeta.
  
## <a name="using-preservation-policies-with-retention-policies-and-document-deletion-policies"></a>Usar directivas de conservación con directivas de retención y con directivas de eliminación de documentos

Una directiva de conservación garantiza la conservación del contenido de forma indefinida o durante un período de tiempo concreto, mientras que una directiva de retención para un buzón y una directiva de eliminación de documentos para un sitio garantizan que el contenido se eliminará después de un período de tiempo específico. Si necesita retener el contenido durante un período concreto de tiempo, puede usar una directiva de conservación junto con una directiva de retención o una directiva de eliminación. 
  
### <a name="site-content"></a>Contenido de sitio

En el caso de un sitio, puede usar una directiva de conservación junto con una directiva de eliminación de documentos. Por ejemplo, puede conservar documentos durante cinco años después de que se modifiquen y, después, configurar una directiva de eliminación que los elimine cinco años después de la última modificación.
  
Si una directiva de eliminación de documentos, elimina el contenido que está sujeto a una directiva de conservación, aún se conservará el contenido en la biblioteca de conservación suspensión. Por ejemplo, si una directiva de conservación conserva el contenido de dos años, pero una directiva de eliminación de documentos, elimina el contenido después de un año, aún se conservará cualquier contenido que se elimina. Para obtener más información, vea [información general de las directivas de eliminación de documentos](https://support.office.com/article/55e8d858-f278-482b-a198-2e62d6a2e6e5).
  
### <a name="mailbox-content"></a>Contenido del buzón

Para un buzón de correo, puede combinar una directiva de conservación con una directiva de retención que tiene una etiqueta de directiva única predeterminada. Por ejemplo, podría conservar los elementos del buzón durante siete años y, a continuación, configurar una directiva de retención para eliminarlos siete años después de que se han recibido (para los mensajes) o crear (para los elementos que no se enviarán, al igual que las notas). La directiva de conservación garantiza que los elementos que se eliminan se conservan para al menos la duración especificada, mientras que la directiva de retención se asegura de que los elementos del buzón se eliminan al final de dicho período. Para obtener más información, vea [etiquetas de retención y las directivas de retención](https://go.microsoft.com/fwlink/p/?LinkID=404351).
  
## <a name="permissions"></a>Permisos

Los miembros de su equipo de cumplimiento de normas que va a usar la seguridad &amp; centro de cumplimiento para crear directivas de conservación necesita permisos para el:
  
-  Seguridad de Office 365 &amp; centro de cumplimiento 
    
- Sitios con contenido que deben conservarse.
    
- Buzones con contenido que deben conservarse.
    
### <a name="office-365-security-amp-compliance-center"></a>Seguridad de Office 365 &amp; centro de cumplimiento

Como un administrador de inquilinos, que desea proporcionar a los responsables del cumplimiento normativo y otras personas el acceso a la seguridad &amp; centro de cumplimiento, sin conceder todos los permisos de un administrador de inquilinos. Para obtener más información, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md).
  
### <a name="sites"></a>Sitios

Los miembros de su equipo de cumplimiento que crean directivas de conservación necesitan permisos para acceder a las colecciones de sitios en las que se aplicarán las directivas. Además, si los responsables de cumplimento también crean directivas de eliminación de documentos, necesitan permisos para acceder a la colección de sitios del Centro de directivas de cumplimiento donde se crean y se almacenan las directivas de eliminación de documentos. Le recomendamos que haga lo siguiente:
  
1. Crear un grupo de seguridad que contiene todos los usuarios del centro de la directiva de cumplimiento, es muy probable que el equipo de administración de directivas de cumplimiento. Para obtener más información, vea [Grupos de seguridad de Manage Mail-Enabled](https://go.microsoft.com/fwlink/p/?LinkID=404345) . 
    
2. En el centro de la directiva de cumplimiento, agregue el grupo de seguridad al grupo de propietarios de la colección de sitios. Para obtener más información, vea [permisos para los administradores de colección de sitios](https://go.microsoft.com/fwlink/p/?LinkID=404346) . 
    
3. En cada colección de sitios a la que necesite asignar directivas de conservación, agregue el grupo de seguridad al grupo de visitantes de la colección de sitios (permisos de lectura).
    
### <a name="mailboxes-and-public-folders"></a>Buzones de correo y carpetas públicas

Para aplicar una directiva de conservación a un buzón de correo, los responsables de cumplimiento necesitan al menos permisos de lectura en ese buzón. 
  
Para aplicar una directiva de conservación a una carpeta pública, los responsables de cumplimiento necesitan al menos permisos de lectura en todas las carpetas públicas.
  

