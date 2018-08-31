---
title: Configurar directivas de supervisión para su organización
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: Configurar las directivas de una revisión de supervisión para capturar las comunicaciones de los empleados para su revisión.
ms.openlocfilehash: a919d65f5c0967a44ac12b7e02d477dac2113704
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536873"
---
# <a name="configure-supervision-policies-for-your-organization"></a>Configurar directivas de supervisión para su organización

Usar directivas de supervisión para capturar a las comunicaciones de los empleados para examen por revisores internos o externos.
  
> [!NOTE]
> Uso de directivas de supervisión requiere una suscripción a Office 365 E5 para su organización. Si no tiene ese plan y desea probar supervisión, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Siga estos pasos para configurar y usar la supervisión de la organización de Office 365: 
  
- [Configurar grupos de supervisión](configure-supervision-policies.md#exampledist)
    
    Antes de empezar a usar la supervisión, determine quién habrá sus comunicaciones ha revisado y quién llevará a cabo las revisiones. Si desea empezar a trabajar con unos pocos usuarios para ver cómo funciona la supervisión, puede omitir la configuración de grupos de por ahora.
    
- [Asegúrese de supervisión disponibles en la organización](configure-supervision-policies.md#SRavailable)
    
    Agregarse al grupo de funciones de revisión de supervisión por lo que puede configurar las directivas. Cualquier persona que tiene este rol asignado puede tener acceso a la página de **supervisión** en el **Gobierno de datos** en la seguridad &amp; centro de cumplimiento. 
    
- [Configurar una directiva de supervisión](configure-supervision-policies.md#setupsuper)
    
    Primero debe crear las directivas de supervisión en la seguridad &amp; centro de cumplimiento. Estas directivas se definen las comunicaciones que están sujetas a la revisión de la organización y especifica que debe llevar a cabo las revisiones. Las comunicaciones incluyen correo electrónico, así como comunicaciones de plataforma 3rd terceros (por ejemplo, Facebook, Twitter, etcetera.)
    
- [Usar Outlook web app para revisar las comunicaciones identificadas por una directiva de supervisión](configure-supervision-policies.md#UseOutlook)
    
    El complemento de supervisión proporciona a los revisores acceso a la funcionalidad de supervisión adecuada dentro de Outlook web app para que puedan evaluar y clasificar cada elemento. Soporte técnico para la versión de escritorio de Outlook estará disponible próximamente.
    
- **Ejecute el informe de supervisión**
    
    Use los informes de supervisión para ver la actividad de revisión en el nivel de directiva y revisor. Para cada directiva, también puede ver las estadísticas de live en el estado actual de la actividad de revisión. Para obtener información detallada, vea [informes de supervisión](supervision-reports.md).
    
## <a name="set-up-groups-for-supervision"></a>Configurar grupos de supervisión
<a name="exampledist"> </a>

 Cuando se crea una directiva de supervisión, determinará que van a tener sus comunicaciones revisado y quién llevará a cabo las revisiones. En la directiva, debe usar direcciones de correo electrónico para identificar los individuos o grupos de personas. Para simplificar el programa de instalación, crear grupos para las personas que tendrán su comunicación revisado y grupos para las personas que va a revisar las comunicaciones. Si usa grupos, puede que necesite varios — por ejemplo, si desea supervisar las comunicaciones entre dos grupos distintos de personas, o si desea especificar un grupo que no se va a ser supervisados. Para obtener información detallada acerca de cómo funciona esto, vea [grupos de distribución de ejemplo](configure-supervision-policies.md#GroupExample) . 
  
Para supervisar las comunicaciones entre o dentro de los grupos de la organización, configurar los grupos de distribución en el centro de administración de Exchange (vaya a **destinatarios** \> **grupos**). Para obtener más información acerca de cómo configurar grupos de distribución, vea [Administrar grupos de distribución](http://go.microsoft.com/fwlink/?LinkId=613635)
  
> [!NOTE]
> También puede usar los grupos de distribución dinámicos o grupos de seguridad para la supervisión si lo prefiere. Para ayudarle a decidir si estas mejor más adecuado para su organización necesita, vea [Administrar grupos de seguridad habilitados para correo](http://go.microsoft.com/fwlink/?LinkId=627033)y [Administrar grupos de distribución dinámica](http://go.microsoft.com/fwlink/?LinkId=627058). 
  
### <a name="example-distribution-groups"></a>Grupos de distribución de ejemplo
<a name="GroupExample"> </a>

En este ejemplo se incluye un grupo de distribución que se ha configurado para una organización financiera denominada Contoso financiera internacional. 
  
En Contoso Financial International, se debe supervisar un muestreo de las comunicaciones entre los agentes de los Estados Unidos. Sin embargo, los responsables de cumplimiento normativo dentro de ese grupo no requieren supervisión. En este ejemplo, podemos crear los siguientes grupos:
  
|**Configurar este grupo de distribución**|**Dirección del grupo (alias)**|**Descripción**|
|:-----|:-----|:-----|
|Todos los agentes de Estados Unidos  <br/> |US_Brokers@contoso.com  <br/> |Este grupo incluye las direcciones de correo electrónico de todos los agentes en Estados Unidos que trabajan para Contoso.  <br/> |
|Todos los responsables de cumplimiento de Estados Unidos  <br/> |US_Compliance@contoso.com  <br/> |Este grupo incluyen direcciones de correo electrónico para todos los agentes de cumplimiento en Estados Unidos que trabajan para Contoso. Dado que este grupo es un subconjunto de todos los agentes en Estados Unidos, puede usar este alias para agentes de cumplimiento exentos de una directiva de supervisión.  <br/> |
   
La sección [Configurar una directiva de supervisión](configure-supervision-policies.md#setupsuper) describe cómo puede usar estos grupos al configurar la directiva. 
  
## <a name="make-supervision-available-in-your-organization"></a>Asegúrese de supervisión disponibles en la organización
<a name="SRavailable"> </a>

Para poner a disposición como una opción de menú **control** en la seguridad &amp; centro de cumplimiento, debe estar asignado el rol de administrador de revisión de supervisión. 
  
Para ello, puede agregarse como un miembro del grupo de roles de revisión de supervisión o puede crear un nuevo grupo de funciones.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Agregar a miembros a un grupo de roles de la revisión de supervisión

1. Iniciar sesión en [https://protection.office.com](https://protection.office.com) uso de credenciales para una cuenta de administrador de la organización de Office 365. 
    
2. En la seguridad &amp; centro de cumplimiento, vaya a **permisos**.
    
3. Seleccione el grupo de roles de **Revisión de supervisión** y, a continuación, haga clic en el icono de edición. 
    
4. En la sección **miembros** , agregue las personas que desea administrar la supervisión para su organización. 
    
### <a name="create-a-new-role-group"></a>Crear un nuevo grupo de roles

1. Iniciar sesión en [https://protection.office.com](https://protection.office.com) uso de credenciales para una cuenta de administrador de la organización de Office 365. 
    
2. En la seguridad &amp; centro de cumplimiento, vaya a **permisos** y, a continuación, haga clic en Agregar ( **+**).
    
3. En la sección **Roles** , haga clic en Agregar ( **+**) y desplácese hacia abajo de la **Supervisión de revisión de administrador**. Agregue esta función al grupo de funciones.
    
4. En la sección **miembros** , agregue las personas que desea administrar la supervisión para su organización. 
    
Para obtener más información sobre grupos de roles y los permisos, vea [permisos en la seguridad de Office 365 &amp; centro de cumplimiento ](permissions-in-the-security-and-compliance-center.md).
  
## <a name="set-up-a-supervision-policy"></a>Configurar una directiva de supervisión
<a name="setupsuper"> </a>

> [!IMPORTANT]
> Antes de crear una directiva de supervisión, primero debe quitar las directivas de revisión de supervisión existente. 
  
1. Iniciar sesión en [https://protection.office.com](https://protection.office.com) uso de credenciales para una cuenta de administrador de la organización de Office 365. 
    
2. En la seguridad &amp; centro de cumplimiento, vaya a haga clic en **el gobierno de datos** \> **supervisión**.
    
    > [!NOTE]
    > La versión anterior de la característica puede mostrar en el panel de navegación izquierdo como la **revisión de supervisión (retirada pronto)**. Pronto se en desuso en esta versión y se ha quitado. La nueva versión denominada **supervisión** tendrá en su lugar. 
  
3. Haga clic en **crear** y, a continuación, siga el Asistente para configurar las siguientes páginas de la directiva. 
    
### <a name="policy-name-and-description"></a>Nombre y descripción de la directiva

Escriba un nombre y una descripción para la directiva. Para fines de ejemplo, se podrá nombre a la directiva corredores de Contoso con nosotros.
  
### <a name="choose-users-to-supervise"></a>Elija los usuarios para supervisar

- En el cuadro **Supervise estos usuarios o grupos** , elija los usuarios o grupos cuyos communications en la que desea supervisar. Siguiendo con nuestro ejemplo para agentes de Contoso con nosotros, podrá elegir el grupo de US_Brokers@Contoso.com aquí. 
    
- Si ha elegido un grupo para supervisar, puede usar el cuadro **excluir a estos usuarios** a elegir a los integrantes del grupo que están exentos de supervisión. En el ejemplo, podrá excluir el grupo US_Compliance@Contoso.com aquí. 
    
### <a name="choose-communications-to-review"></a>Elija communications para revisar
<a name="CommsToReview"> </a>

De forma predeterminada, la condición **es la dirección** se muestra y no se puede quitar. Si desea delimitar aún más la revisión (por ejemplo, para revisar sólo contenido que contiene ciertas palabras o frases), haga clic en **Agregar una condición**. Puede especificar varias condiciones Si es necesario.
  
Las condiciones que elija se aplicarán a las comunicaciones de correo electrónico y 3rd terceros orígenes en su organización (como desde la lista desplegable o de Facebook). Para obtener información detallada acerca de la importación 3rd fabricante communications en su organización de Office 365, vea [datos de terceros de archivado en Office 365](https://technet.microsoft.com/EN-US/library/mt621583.aspx).
  
En la siguiente tabla se explica más acerca de cada condición.
  
|**Condición**|**Cómo usar esta condición**|
|:-----|:-----|
|La dirección es  <br/> |Elija la **entrada** para revisar las comunicaciones que se envían **a** las personas que eligió para supervisar **de** personas no se incluyen en la directiva.  <br/> Elija **saliente** si desea revisar comunicaciones que son enviados **desde** las personas que eligió para supervisar ** a ** personas no incluidas en la directiva.  <br/> Elija **interno** para revisar comunicaciones enviadas **entre** las personas que ha identificado en la directiva.  <br/> |
|El mensaje contiene cualquiera de estas palabras  <br/> El mensaje contiene ninguna de estas palabras  <br/> |Para aplicar la directiva cuando ciertas palabras o frases se incluyen o excluyen en un mensaje, escriba cada palabra o frase en una línea independiente. Cada línea de las palabras que especifique se aplicará por separado (sólo una de estas líneas debe aplicar para que la directiva que se debe aplicar al mensaje). Para obtener más información sobre cómo especificar palabras o frases, vea la sección siguiente [coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos](configure-supervision-policies.md#Matchwords).<br/> |
|Datos adjuntos contienen cualquiera de estas palabras  <br/> Datos adjuntos no contienen ninguna de estas palabras  <br/> |Para aplicar la directiva cuando ciertas palabras o frases se incluyen o excluyen en un datos adjuntos del mensaje (por ejemplo, un documento de Word), escriba cada palabra o frase en una línea independiente. Cada línea de las palabras que especifique se aplicará por separado (se debe aplicar sólo una línea para que la directiva que se debe aplicar a los datos adjuntos). Para obtener más información sobre cómo especificar palabras o frases, vea la sección siguiente [coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos](configure-supervision-policies.md#Matchwords).<br/> |
|Datos adjuntos están cualquiera de estos tipos de archivo  <br/> Datos adjuntos no son ninguno de estos tipos de archivo  <br/> |Para supervisar las comunicaciones que incluyen o excluyan tipos específicos de datos adjuntos, escriba las extensiones de archivo (como .exe o .pdf). Si desea incluir o excluir varias extensiones de archivo, escriba estos en líneas separadas. Extensión de un único archivo adjunto debe coincidir para que aplicar la directiva.  <br/> |
|El tamaño del mensaje es mayor que  <br/> No es mayor que el tamaño de mensaje  <br/> |Para revisar los mensajes según un determinado tamaño, use estas condiciones para especificar el tamaño máximo o mínimo que puede ser un mensaje antes de que esté sujeto a revisión. Por ejemplo, si especifica el **tamaño del mensaje es mayor que** \> **MB 1.0**, todos los mensajes que son 1.01 MB y será mayor estar sujeto a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.<br/> |
|Datos adjuntos son mayor que  <br/> Datos adjuntos no son mayor que  <br/> |Para revisar los mensajes según el tamaño de sus datos adjuntos, especifique el tamaño máximo o mínimo adjuntos puede ser antes de que el mensaje y sus datos adjuntos están sujetos a revisión. Por ejemplo, si especifica **los datos adjuntos son mayor que** \> **2,0 MB**, todos los mensajes con datos adjuntos MB 2.01 y realizarán más estar sujeto a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.<br/> |
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos
<a name="Matchwords"> </a>

Cada línea de las palabras que especifique se aplicará por separado (se debe aplicar sólo una línea para que la condición de directiva que se debe aplicar al correo electrónico o datos adjuntos). Por ejemplo, vamos a usar la condición, **que mensaje contiene cualquiera de estas palabras**, con el bancario"palabras clave" y "privilegiada" en líneas separadas. La directiva se aplicará a todos los mensajes que incluye el bancario"word" o la frase "interno comerciales". Se debe producir solo una de estas palabras o frases para que esta condición de directiva que se debe aplicar. Las palabras en el mensaje o adjunto deben coincidir exactamente con lo que escribe.
  
#### <a name="entering-multiple-conditions"></a>Especificar varias condiciones
<a name="Matchwords"> </a>

Si escribe varias condiciones, Office 365 usa todas las condiciones conjuntamente para determinar cuándo se debe aplicar la directiva a los elementos de comunicación. Cuando configura varias condiciones, todos se deben cumplir para que la directiva que se debe aplicar, a menos que especifique una excepción. Por ejemplo, supongamos que necesita para crear una directiva que se debe aplicar si un mensaje contiene la palabra "comercio" y es mayor que 2MB. Sin embargo, si el mensaje también contiene las palabras "Aprobado por Contoso financiero", no debe aplicar la directiva. Por lo tanto, en este caso, las tres condiciones sería como sigue: 
  
- **El mensaje contiene cualquiera de estas palabras**, con las palabras clave "comercial"
    
- **Tamaño del mensaje es mayor que**, con el valor 2 MB
    
- **El mensaje contiene ninguna de estas palabras**, con las palabras clave "Aprobado por el equipo financiero de Contoso".
    
### <a name="specify-percentage-to-review"></a>Especificar el porcentaje que desee revisar
<a name="CommsToReview"> </a>

Si desea reducir la cantidad de contenido para revisar, especifique un porcentaje. Seleccione al azar esa cantidad de contenido desde el total que cumple las condiciones que ha elegido. Si desea que los revisores para revisar todos los elementos, escriba **100%**.
  
### <a name="choose-reviewers"></a>Elija revisores
<a name="CommsToReview"> </a>

Los usuarios y grupos que elija usará la aplicación de supervisión en Outlook web app para examinar las comunicaciones que son devueltas por esta directiva. Puede incluir direcciones de correo electrónico para revisores internos o externos. 
  
### <a name="review-your-settings"></a>Revise las opciones de
<a name="CommsToReview"> </a>

Una vez que haya completado todas las secciones de la directiva de supervisión, revise la configuración y, a continuación, haga clic en **Finalizar** para guardar la directiva. Puede tardar unas horas antes de la directiva iniciar comunicaciones. Supervisión ofrece a todas las comunicaciones para su revisión en una carpeta compartida que pueden tener acceso los revisores en Outlook web app. 
  
## <a name="use-outlook-web-app-to-review-communications-identified-by-a-supervision-policy"></a>Usar Outlook web app para revisar las comunicaciones identificadas por una directiva de supervisión
<a name="UseOutlook"> </a>

Los revisores va a utilizar el complemento de supervisión para Outlook web app para revisar las comunicaciones. El complemento se instala automáticamente en Outlook web app para todos los revisores especificados en la directiva. Soporte técnico para la versión de escritorio de Outlook estará disponible próximamente.
  
 **Revisión de las comunicaciones en Outlook web app**
  
1. En Outlook web app, expanda la **supervisión - \<nombre de la directiva\> ** carpeta. 
    
2. En la ** \<nombre de la directiva\> ** subcarpeta, revisores verán todas las comunicaciones identificadas por esa directiva de supervisión. 
    
    ![Complemento de supervisión en Outlook web app que muestra la subcarpeta de la directiva de supervisión seleccionada](media/eef329bf-2bd0-477e-a715-76ca19b3347f.jpg)
  
3. Abra un elemento para revisar y haga clic en el complemento de **supervisión** . 
    
4. Use el complemento para clasificar el elemento como **compatible**, **No compatible**, **Questionable** o **resuelto**. Después de haber clasificado un elemento, se moverán a la subcarpeta correspondiente en el ** \<nombre de la directiva\> ** carpeta. 
    

