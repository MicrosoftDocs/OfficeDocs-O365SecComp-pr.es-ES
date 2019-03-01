---
title: Enviar notificaciones de correo electrónico y Mostrar sugerencias de directiva para directivas de DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 87496bc5-9601-4473-8021-cb05c71369c1
description: 'Una sugerencia de directiva es una notificación o advertencia que aparece cuando alguien trabaja con contenido que entra en conflicto con una directiva DLP. Puede usar notificaciones de correo electrónico y sugerencias de directiva para aumentar el conocimiento y ayudar a los usuarios acerca de las directivas de la organización. También puede dar a los usuarios la opción de invalidar la Directiva, de modo que no se bloqueen si tienen una necesidad empresarial válida o si la Directiva está detectando un falso positivo. '
ms.openlocfilehash: 77bf9947356a4c8986e8b8cca7544350fa300c01
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341701"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a>Enviar notificaciones de correo electrónico y Mostrar sugerencias de directiva para directivas de DLP

Puede usar una directiva de prevención de pérdida de datos (DLP) para identificar, supervisar y proteger información confidencial en Office 365. Desea que las personas de la organización que trabajan con esta información confidencial sigan siendo compatibles con las directivas de DLP, pero no desea bloquearlas sin necesidad de que se realice su trabajo. Aquí es donde las notificaciones de correo electrónico y las sugerencias de Directiva pueden ser de ayuda.
  
![La barra de mensajes muestra sugerencia de directiva en Excel 2016](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
Una sugerencia de directiva es una notificación o advertencia que aparece cuando un usuario trabaja con contenido que entra en conflicto con una directiva DLP, por ejemplo, contenido como un libro de Excel en un sitio de OneDrive para la empresa que contiene información de identificación personal (PII) y es compartido con un usuario externo.
  
Puede usar notificaciones de correo electrónico y sugerencias de directiva para aumentar el conocimiento y ayudar a los usuarios acerca de las directivas de la organización. También puede dar a los usuarios la opción de invalidar la Directiva, de modo que no se bloqueen si tienen una necesidad empresarial válida o si la Directiva está detectando un falso positivo.
  
En el centro de seguridad &amp; y cumplimiento de Office 365, al crear una directiva DLP, puede configurar las notificaciones de usuario para:
  
- Envíe una notificación por correo electrónico a las personas que elija que describan el problema.
    
- Mostrar una sugerencia de directiva para el contenido que está en conflicto con la Directiva DLP:
    
  - Para el correo electrónico en Outlook en la web y Outlook 2013 y versiones posteriores, la sugerencia de directiva aparece en la parte superior de un mensaje encima de los destinatarios mientras se redacta el mensaje.
    
  - Para los documentos de una cuenta de OneDrive para la empresa o un sitio de SharePoint Online, la sugerencia de Directiva se indica mediante un icono de advertencia que aparece en el elemento. Para ver más información, puede seleccionar un elemento y, a continuación ****![, elegir el icono](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) del panel de información de información en la esquina superior derecha de la página para abrir el panel de detalles. 
    
  - Para los documentos de Excel 2016, PowerPoint 2016 y Word 2016 que se almacenan en un sitio de OneDrive para la empresa o un sitio de SharePoint Online que se incluye en la Directiva DLP, la sugerencia de directiva aparece en la barra de mensajes y en la vista Backstage (menú **archivo** \> ** Información**).
    
## <a name="add-user-notifications-to-a-dlp-policy"></a>Agregar notificaciones de usuario a una directiva DLP

Al crear una directiva DLP, las notificaciones de correo electrónico y las sugerencias de directiva forman parte de la sección notificaciones de **usuario** . 
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa. Ahora está en el centro de seguridad &amp; y cumplimiento de Office 365.
    
3. En la directiva &amp; \> \> **** \> **** **** de prevención de pérdida de datos de navegación del centro de cumplimiento de seguridad izquierdo + crear una directiva. \>
    
    ![Botón crear una directiva](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Elija la plantilla de directiva DLP que protege los tipos de información confidencial que necesita \> a **continuación**.
    
    Para empezar con una plantilla vacía, seleccione **** \> **Directiva** \> personalizada personalizada a **continuación**.
    
5. Asigne un nombre \> a la Directiva a **continuación**.
    
6. Para elegir las ubicaciones que desea que proteja la Directiva DLP, realice una de las siguientes acciones:
    
  - elija **todas las ubicaciones en Office 365** \> **siguiente**.
    
  - Elija **permitirme elegir ubicaciones** \> específicas a **continuación**.
    
    Para incluir o excluir una ubicación completa, como todos los correos electrónicos de Exchange o todas las cuentas de OneDrive, cambie el **Estado** de dicha ubicación a activado o desactivado. 
    
    Para incluir solo sitios de SharePoint específicos o cuentas de OneDrive, cambie el **Estado** a activado y, a continuación, haga clic en los vínculos de **incluir** para elegir sitios o cuentas específicos. 
    
7. Elija **Usar configuración** \> avanzada a **continuación**.
    
8. Seleccione **+ nueva regla**.
    
9. En el editor de reglas, en notificaciones de **usuario**, cambie el estado a.
    
    ![Sección de notificaciones de usuario del editor de reglas](media/47705927-c60b-4054-a072-ab914f33d15d.png)
  
## <a name="options-for-configuring-email-notifications"></a>Opciones para configurar las notificaciones de correo electrónico

Para cada regla en una directiva DLP, puede:
  
- Enviar la notificación a las personas que elija. Estas personas pueden ser el propietario del contenido, la persona que modificó por última vez el contenido, el propietario del sitio donde se almacena el contenido o un usuario específico.
    
- Personalizar el texto que se incluye en la notificación mediante HTML o tokens. Vea la sección siguiente para obtener más información.
    
> [!NOTE]
>  Las notificaciones de correo electrónico solo pueden enviarse a destinatarios individuales, no a grupos ni a listas de distribución. > solo el nuevo contenido desencadenará una notificación de correo electrónico. La edición del contenido existente desencadenará sugerencias de Directiva, pero no una notificación de correo electrónico. 
  
![Opciones de notificación de correo electrónico](media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a>Notificación de correo electrónico predeterminada

Las notificaciones tienen una línea de asunto que comienza con la acción emprendida, como "notificación", "mensaje bloqueado" para el correo electrónico o "acceso bloqueado" para los documentos. Si la notificación se redirige a un documento, el cuerpo del mensaje de notificación incluye un vínculo que le lleva al sitio donde se almacena el documento y abre la sugerencia de directiva para el documento, donde puede resolver cualquier problema (consulte la sección siguiente sobre sugerencias de directiva). Si la notificación está relacionada con un mensaje, la notificación incluye como datos adjuntos el mensaje que coincide con una directiva de DLP.
  
![Mensaje de notificación](media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
De forma predeterminada, las notificaciones muestran texto similar al siguiente para un elemento de un sitio. El texto de notificación se configura por separado para cada regla, por lo que el texto que se muestra es diferente en función de qué regla coincida.

|**Si la regla de directiva DLP hace esto...**|**A continuación, la notificación predeterminada para documentos de SharePoint o OneDrive para la empresa indica que...**|**A continuación, la notificación predeterminada para los mensajes de Outlook dice esto...**|
|:-----|:-----|:-----|
|Envía una notificación pero no permite la invalidación  <br/> |Este elemento está en conflicto con una directiva de la organización.  <br/> |El mensaje de correo electrónico entra en conflicto con una directiva de la organización.  <br/> |
|Bloquea el acceso, envía una notificación y permite la invalidación  <br/> |Este elemento está en conflicto con una directiva de la organización. Si no resuelve este conflicto, es posible que se bloquee el acceso a este archivo.  <br/> |El mensaje de correo electrónico entra en conflicto con una directiva de la organización. El mensaje no se entregó a todos los destinatarios.  <br/> |
|Bloquea el acceso y envía una notificación  <br/> |Este elemento está en conflicto con una directiva de la organización. El acceso a este elemento está bloqueado para todos excepto para su propietario, para el último usuario que lo modificó y para el administrador de la colección de sitios primaria.  <br/> |El mensaje de correo electrónico entra en conflicto con una directiva de la organización. El mensaje no se entregó a todos los destinatarios.  <br/> |
   
### <a name="custom-email-notification"></a>Notificación de correo electrónico personalizada

Puede crear una notificación de correo electrónico personalizada en lugar de enviar la notificación de correo electrónico predeterminada a los usuarios finales o administradores. La notificación de correo electrónico personalizada admite HTML y tiene un límite de 5.000 caracteres. Puede usar HTML para incluir imágenes, formato y otras marcas en la notificación.
  
También puede usar los siguientes tokens para ayudar a personalizar la notificación de correo electrónico. Estos tokens son variables que se reemplazan por información específica en la notificación que se envía.

|**Comproba**|**Descripción**|
|:-----|:-----|
|%% AppliedActions%%  <br/> |Acciones aplicadas al contenido.  <br/> |
|%% ContentURL%%  <br/> |Dirección URL del documento en el sitio de SharePoint Online o el sitio de OneDrive para la empresa.  <br/> |
|%% MatchedConditions%%  <br/> |Las condiciones que coinciden con el contenido. Use este token para informar a los usuarios de posibles problemas con el contenido.  <br/> |
   
![Mensaje de notificación que muestra dónde aparecen los tokens](media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a>Opciones para configurar sugerencias de directiva

Para cada regla de una directiva DLP, puede configurar sugerencias de directiva para:
  
- Solo tiene que notificar a la persona que el contenido está en conflicto con una directiva DLP, de modo que puedan actuar para resolver el conflicto. Puede usar el texto predeterminado (consulte las siguientes tablas) o especificar texto personalizado sobre las directivas específicas de su organización.
    
- Permitir que la persona invalide la directiva DLP. Opcionalmente, puede:
    
  - Requerir que la persona escriba una justificación comercial para invalidar la Directiva. Esta información se registra y se puede ver en los informes DLP en la sección **informes** del centro de seguridad &amp; y cumplimiento. 
    
  - Permitir que la persona informe de un falso positivo e invalide la directiva DLP. Esta información también se registra en los informes, de modo que puede usar falsos positivos para ajustar las reglas.
    
![Opciones de sugerencia de Directiva](media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
Por ejemplo, puede tener una directiva DLP aplicada a sitios de OneDrive para la empresa que detecta información de identificación personal (PII), y esta directiva tiene tres reglas:
  
1. Primera regla: Si se detectan menos de cinco instancias de información confidencial en un documento y el documento se comparte con personas que pertenecen a la organización, la acción **Enviar una notificación** muestra una sugerencia de directiva. Para obtener sugerencias de directiva, no se necesitan opciones de invalidación porque esta regla simplemente está avisando a las personas y no está bloqueando el acceso. 
    
2. Segunda regla: si se detectan más de cinco instancias de esta información confidencial en un documento y el documento se comparte con personas dentro de la organización, la acción **bloquear el acceso a contenido** restringe los permisos para el archivo y el ** Enviar una** acción de notificación permite a los usuarios invalidar las acciones de esta regla proporcionando una justificación empresarial. A veces, la empresa de su organización requiere que los usuarios internos compartan los datos de PII y no quiere que la Directiva DLP la bloquee este trabajo. 
    
3. Tercera regla: Si se detectan más de cinco instancias de información confidencial en un documento y el documento se comparte con personas externas a la organización, la acción **Bloquear el acceso al contenido** restringe los permisos para el archivo y la acción **Enviar una notificación** no permite a los usuarios invalidar las acciones de esta regla porque la información se comparte con el exterior. Bajo ninguna circunstancia las personas de su organización pueden compartir datos de PII fuera de la organización. 
    
Estos son algunos puntos clave para comprender el uso de una sugerencia de directiva para invalidar una regla:
  
- La opción para invalidar es por regla y invalida todas las acciones de la regla (excepto el envío de una notificación, que no se puede invalidar).
    
- El contenido puede coincidir con varias reglas de una directiva de DLP, pero solo se mostrará la sugerencia de directiva de la regla de mayor prioridad más restrictiva. Por ejemplo, una sugerencia de directiva de una regla que bloquea el acceso al contenido se muestra en una sugerencia de directiva a partir de una regla que simplemente envía una notificación. Esto impide que los usuarios vean una cascada de sugerencias de directiva.
    
- Si las sugerencias de directiva en la regla más restrictiva permite que los usuarios invaliden la regla, la invalidación de esta regla invalida también otras reglas que coinciden con el contenido.
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a>Sugerencias de directiva en sitios de OneDrive para la Empresa y sitios de SharePoint Online

Cuando un documento de un sitio de OneDrive para la empresa o un sitio de SharePoint Online coincide con una regla en una directiva DLP y esa regla usa sugerencias de Directiva, las sugerencias de directiva muestran iconos especiales en el documento:
  
1. Si la regla envía una notificación sobre el archivo, aparece el icono de advertencia.
    
2. Si la regla bloquea el acceso al documento, aparece el icono de bloqueado.
    
![Iconos de sugerencia de directiva en los documentos de una cuenta de OneDrive](media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
Para realizar una acción en un documento, puede seleccionar un elemento \> elegir el icono](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) del panel de información de **información**![en la esquina superior derecha de la página para abrir \> el panel de detalles **ver la sugerencia de directiva**.
  
La sugerencia de directiva enumera los problemas con el contenido y, si las sugerencias de directiva están configuradas con estas opciones, puede elegir **Resolver** y luego **Invalidar** la sugerencia de directiva o **Informar** de un falso positivo. 
  
![Panel de información que muestra la sugerencia de Directiva](media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![Sugerencia de directiva con la opción de invalidar](media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
Las directivas DLP se sincronizan con los sitios y el contenido se evalúa con estas periódicamente y de forma asincrónica, por lo que puede haber un breve retraso entre el momento en que se crea la directiva DLP y el momento en que se empiezan a ver sugerencias de directiva. Puede haber un retraso similar desde el momento en que se invalida o resuelve una sugerencia de directiva hasta cuando desaparece el icono en el documento en el sitio.
  
### <a name="default-text-for-policy-tips-on-sites"></a>Texto predeterminado para las sugerencias de directiva en los sitios

De forma predeterminada, las sugerencias de directiva muestran texto similar al siguiente para un elemento de un sitio. El texto de notificación se configura por separado para cada regla, por lo que el texto que se muestra es diferente en función de qué regla coincida.

|**Si la regla de directiva DLP hace esto...**|**La sugerencia de directiva predeterminada indica lo siguiente...**|
|:-----|:-----|
|Envía una notificación pero no permite la invalidación  <br/> |Este elemento está en conflicto con una directiva de la organización.  <br/> |
|Bloquea el acceso, envía una notificación y permite la invalidación  <br/> |Este elemento está en conflicto con una directiva de la organización. Si no resuelve este conflicto, es posible que se bloquee el acceso a este archivo.  <br/> |
|Bloquea el acceso y envía una notificación  <br/> |Este elemento está en conflicto con una directiva de la organización. El acceso a este elemento está bloqueado para todos excepto para su propietario, para el último usuario que lo modificó y para el administrador de la colección de sitios primaria.  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a>Texto personalizado para sugerencias de directivas en los sitios

Puede personalizar el texto de las sugerencias de directiva independientemente de la notificación de correo electrónico. A diferencia del texto personalizado para las notificaciones de correo electrónico (consulte la sección anterior), el texto personalizado para las sugerencias de Directiva no acepta HTML ni tokens. En su lugar, el texto personalizado para las sugerencias de directiva es texto sin formato con un límite de 256 caracteres.
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a>Sugerencias de directiva en Outlook en la web y Outlook 2013 y versiones posteriores

Al redactar un nuevo correo electrónico en Outlook en la web y Outlook 2013 y versiones posteriores, verá una sugerencia de Directiva si agrega contenido que coincide con una regla de una directiva DLP y esa regla usa sugerencias de directiva. La sugerencia de directiva aparece en la parte superior del mensaje, encima de los destinatarios mientras se redacta el mensaje.
  
![Sugerencia de directiva en la parte superior del mensaje que se está redactando](media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
Las sugerencias de directiva funcionan independientemente de si la información confidencial aparece en el cuerpo del mensaje, en la línea de asunto o incluso en un dato adjunto del mensaje, como se muestra aquí.
  
![Sugerencia de directiva que muestra que un archivo adjunto entra en conflicto con una directiva DLP](media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
Si las sugerencias de directiva están configuradas para permitir invalidar, puede elegir **Mostrar detalles** \> **omitir** \> especificar una justificación del \> negocio o informar de una **anulación**de falso positivo.
  
![Sugerencia de directiva en mensaje ampliado para mostrar opción de anulación](media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![Cuadro de diálogo de sugerencia de directiva donde puede invalidar la sugerencia de Directiva](media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
Tenga en cuenta que, al agregar información confidencial a un correo electrónico, puede haber latencia entre el momento en que se agrega la información confidencial y el momento en que aparece la sugerencia de directiva.

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a>Outlook 2013 y versiones posteriores admiten la visualización de sugerencias de directiva solo para algunas condiciones

Actualmente, Outlook 2013 y versiones posteriores admiten la visualización de sugerencias de directiva solo para estas condiciones:

- Contenido contiene
- El contenido se comparte

Actualmente estamos trabajando en soporte para mostrar sugerencias de directiva para condiciones adicionales. Entre ellos se incluyen:

- No se pudo analizar el contenido de los datos adjuntos de correo electrónico
- No se completó el análisis del contenido de los datos adjuntos de correo
- La extensión del archivo adjunto es
- Los datos adJuntos están protegidos con contraseña
- La propiedad de documento es
- El dominio del destinatario es
- La dirección IP del remitente es

Tenga en cuenta que todas estas condiciones funcionan en Outlook, donde coincidirán con el contenido y aplicarán acciones de protección en el contenido. Pero Mostrar sugerencias de directiva a los usuarios todavía no es compatible.
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-office-365-security-amp-compliance-center"></a>Sugerencias de directiva en el centro de administración de Exchange frente al centro &amp; de seguridad y cumplimiento de Office 365

Las sugerencias de Directiva pueden funcionar con las directivas de DLP y las reglas de flujo de correo creadas en el centro de administración de Exchange o con las &amp; directivas de DLP creadas en el centro de seguridad y cumplimiento de Office 365, pero no en ambos. Esto se debe a que estas directivas se almacenan en ubicaciones distintas, pero las sugerencias de directiva solo pueden dibujar desde una única ubicación.
  
Si ha configurado sugerencias de directiva en el centro de administración de Exchange, las sugerencias de directiva que configure en el &amp; centro de seguridad y cumplimiento de Office 365 no aparecerán a los usuarios en Outlook en la web ni en Outlook 2013 y versiones posteriores hasta que desactive las sugerencias de Exchange. Centro de administración. Esto garantiza que las reglas de flujo de correo de Exchange actuales (también conocidas como reglas de transporte) seguirán funcionando hasta que elija cambiar al centro de seguridad &amp; y cumplimiento de Office 365.
  
Tenga en cuenta que, aunque las sugerencias de directiva solo pueden dibujar desde una única ubicación, siempre se envían notificaciones de correo electrónico, incluso si usa directivas de DLP &amp; tanto en el centro de administración de seguridad de Office 365 como en el centro de administración de Exchange.
  
### <a name="default-text-for-policy-tips-in-email"></a>Texto predeterminado para las sugerencias de directiva en el correo electrónico

De forma predeterminada, las sugerencias de directiva muestran texto similar al siguiente para el correo electrónico.

|**Si la regla de directiva DLP hace esto...**|**La sugerencia de directiva predeterminada indica lo siguiente...**|
|:-----|:-----|
|Envía una notificación pero no permite la invalidación  <br/> |El correo electrónico entra en conflicto con una directiva de la organización.  <br/> |
|Bloquea el acceso, envía una notificación y permite la invalidación  <br/> |El correo electrónico entra en conflicto con una directiva de la organización.  <br/> |
|Bloquea el acceso y envía una notificación  <br/> |El correo electrónico entra en conflicto con una directiva de la organización.  <br/> |
   
## <a name="policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a>Sugerencias de directiva en Excel 2016, PowerPoint 2016 y Word 2016

Cuando los usuarios trabajan con contenido confidencial en las versiones de escritorio de Excel 2016, PowerPoint 2016 y Word 2016, las sugerencias de directiva pueden notificarles en tiempo real que el contenido está en conflicto con una directiva DLP. Esto requiere lo siguiente:
  
- El documento de Office está almacenado en un sitio de OneDrive para la Empresa o sitio de SharePoint Online.
    
- El sitio se incluye en una directiva DLP configurada para usar sugerencias de directiva.
    
Estos programas de escritorio de Office 2016 sincronizan automáticamente las directivas de DLP directamente desde Office 365 y, a continuación, examinan los documentos para asegurarse de que no entran en conflicto con las directivas de DLP y muestran sugerencias de directivas en tiempo real.
  
En función de cómo se configuran las sugerencias de directiva en la directiva DLP, los usuarios pueden optar por simplemente ignorar la sugerencia de directiva, invalidar la directiva con o sin una justificación del negocio o informar de un falso positivo.
  
Las sugerencias de directiva aparecen en la barra de mensajes.
  
![La barra de mensajes muestra sugerencia de directiva en Excel 2016](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
Y las sugerencias de directiva también aparecen en la vista Backstage (en la pestaña **Archivo**). 
  
![Backstage muestra una sugerencia de directiva en Excel 2016](media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
Si las sugerencias de directiva en la directiva DLP se configuran con estas opciones, puede elegir **Resolver** para **Invalidar** una sugerencia de directiva o **Informar** de un falso positivo. 
  
![Opciones de la sugerencia de directiva en Backstage en Excel 2016](media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
En cada uno de estos programas de escritorio de Office 2016, los usuarios pueden desactivar las sugerencias de directiva. Si se desactivan, las sugerencias de directiva que son notificaciones simples no aparecerán en la barra de mensajes o la vista Backstage (en la pestaña **Archivo**). Sin embargo, seguirán apareciendo las sugerencias de directiva de bloqueo e invalidación y seguirán recibiendo la notificación por correo electrónico. Además, la desactivación de las sugerencias de directiva no exime al documento de las directivas DLP que se le han aplicado. 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a>Texto predeterminado para las sugerencias de directiva en Excel 2016, PowerPoint 2016 y Word 2016

De forma predeterminada, las sugerencias de directiva muestran texto similar para lo siguiente en la barra de mensajes y vista Backstage de un documento abierto. El texto de notificación se configura por separado para cada regla, por lo que el texto que se muestra es diferente en función de qué regla coincida.

|**Si la regla de directiva DLP hace esto...**|**La sugerencia de directiva predeterminada indica lo siguiente...**|
|:-----|:-----|
|Envía una notificación pero no permite la invalidación  <br/> |Este archivo está en conflicto con una directiva de la organización. Para obtener más información, vaya al menú **archivo** .<br/> |
|Bloquea el acceso, envía una notificación y permite la invalidación  <br/> |Este archivo está en conflicto con una directiva de la organización. Si no resuelve este conflicto, es posible que se bloquee el acceso a este archivo. Para obtener más información, vaya al menú **archivo** .<br/> |
|Bloquea el acceso y envía una notificación  <br/> |Este archivo está en conflicto con una directiva de la organización. Si no resuelve este conflicto, es posible que se bloquee el acceso a este archivo. Para obtener más información, vaya al menú **archivo** .<br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a>Texto personalizado para sugerencias de directiva en Excel 2016, PowerPoint 2016 y Word 2016

Puede personalizar el texto de las sugerencias de directiva independientemente de la notificación de correo electrónico. A diferencia del texto personalizado para las notificaciones de correo electrónico (consulte la sección anterior), el texto personalizado para las sugerencias de Directiva no acepta HTML ni tokens. En su lugar, el texto personalizado para las sugerencias de directiva es texto sin formato con un límite de 256 caracteres.
  
## <a name="more-information"></a>Más información

- [Información general sobre las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md)
    
- [Crear una directiva DLP a partir de una plantilla](create-a-dlp-policy-from-a-template.md)
    
- [Crear una directiva DLP para proteger documentos con FCI u otras propiedades](protect-documents-that-have-fci-or-other-properties.md)
    
- [Qué incluyen las plantillas de directiva DLP](what-the-dlp-policy-templates-include.md)
    
- [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)
    

