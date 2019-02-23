---
title: Crear y aplicar directivas de administración de la información
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/16/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
description: Las directivas de administración de la información permiten a su organización controlar el tiempo que se conservará el contenido, auditar lo que hacen los usuarios con el contenido y agregar códigos de barras o etiquetas a los documentos. Una Directiva puede ayudar a garantizar el cumplimiento de las regulaciones legales y gubernamentales o los procesos de negocio internos. Como administrador, puede configurar una directiva para controlar cómo realizar un seguimiento de los documentos y durante cuánto tiempo se conservan los documentos.
ms.openlocfilehash: d4161ad3684a006f0e4b2b9e0e856ea0a8aa67fc
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214700"
---
# <a name="create-and-apply-information-management-policies"></a>Crear y aplicar directivas de administración de la información

Las directivas de administración de la información permiten a su organización controlar el tiempo que se conservará el contenido, auditar lo que hacen los usuarios con el contenido y agregar códigos de barras o etiquetas a los documentos. Una Directiva puede ayudar a garantizar el cumplimiento de las regulaciones legales y gubernamentales o los procesos de negocio internos. Como administrador, puede configurar una directiva para controlar cómo realizar un seguimiento de los documentos y durante cuánto tiempo se conservan los documentos.
  
Puede crear una directiva de administración de la información en tres ubicaciones distintas en la jerarquía del sitio, de la más amplia hasta el menor:
  
- Cree una directiva para usarla en varios tipos de contenido dentro de una colección de sitios.
    
- Cree una directiva para un tipo de contenido de sitio.
    
- Cree una directiva para una lista o biblioteca.
    
Para obtener más información, vea [Introducción a las directivas de administración de la información](intro-to-info-mgmt-policies.md).
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a>Crear una directiva para varios tipos de contenido dentro de una colección de sitios
<a name="__toc261001590"> </a>

Para asegurarse de que se aplica una directiva de información a todos los documentos de un tipo determinado dentro de una colección de sitios, considere la posibilidad de crear la Directiva en el nivel de colección de sitios y, posteriormente, aplicar la Directiva a los tipos de contenido. Se denominan directivas de colección de sitios. 
  
1. en la página \> ****![principal de la colección de sitios, en el botón configuración de SharePoint 2016 de la barra de título. ](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) **sitio.** \>
    
    En un sitio conectado a un grupo de SharePoint, haga clic en **configuración**, en **contenidos del sitio**y, a continuación, en **configuración del sitio**. 
    
2. En la página Configuración del sitio, en **plantillas de directiva de tipo de contenido**de administración \> de la colección de **sitios** . 
  
![Vínculo de plantilla de directiva de tipo de contenido en la página Configuración del sitio](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. En la página \> directivas, **cree**. 
    
4. Escriba un nombre y una descripción para la Directiva y, a continuación, escriba una breve declaración de directiva que explique a los usuarios para qué sirve la Directiva.
    
5. Consulte la siguiente sección sobre la creación de directivas para un tipo de contenido de sitio para obtener información sobre cómo configurar las características que desea asociar a la Directiva. 
    
6. Elija **Aceptar**.
    
## <a name="create-a-policy-for-a-site-content-type"></a>Crear una directiva para un tipo de contenido de sitio
<a name="__create_a_policy"> </a>

Agregar una directiva de administración de información a un tipo de contenido facilita la Asociación de características de directiva con varias listas o bibliotecas. Puede elegir agregar una directiva de administración de la información existente a un tipo de contenido o crear una Directiva única específica para un tipo de contenido individual.
  
 También puede Agregar una directiva de administración de información a un tipo de contenido específico de las listas. Esto tiene el efecto de aplicar la Directiva solo a los elementos de la lista que usan el tipo de contenido. 
  
1. en la página \> ****![principal de la colección de sitios, en el botón configuración de SharePoint 2016 de la barra de título. ](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) **sitio.** \>
    
    En un sitio conectado a un grupo de SharePoint, haga clic en **configuración**, en **contenidos del sitio**y, a continuación, en **configuración del sitio**. 
    
2. En la página Configuración del sitio, en **tipos de contenido de sitio**de galerías \> del **Diseñador Web** .
  
![Vínculo tipos de contenido de sitio de la página Configuración del sitio](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. En la página Configuración del tipo de contenido de sitio, seleccione el tipo de contenido al que desea agregar una directiva.
    
4. En la página tipo de contenido de sitio **** \> , en configuración de la **Directiva de administración de información**.
    
5. En la página Editar Directiva, escriba un nombre y una descripción para la Directiva y, a continuación, escriba una descripción breve que explique a los usuarios para qué sirve la Directiva.
    
6. En las siguientes secciones, seleccione las características de directiva individuales que desea agregar a la Directiva de administración de la información. 
  
![Tipos de directivas de contenido](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. Para especificar un período de retención para documentos y elementos que están sujetos a esta Directiva, elija **Habilitar retención**y, a continuación, especifique el período de retención y las acciones que desea que se produzcan cuando expiren los elementos.
    
    Para especificar un período de retención
    
||||||**1.**|* * Elija * * Agregar una etapa de retención para registros... * * * *|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> | Seleccione una opción de período de retención para especificar Cuándo expirarán los documentos o elementos. Realice una de las siguientes acciones:<br/>  Para establecer la fecha de expiración en función de una propiedad de fecha, en **evento** \> **esta fase se basa en una propiedad de fecha del elemento**y, a continuación, selecciona la acción del documento o elemento (por ejemplo, creado o modificado) y el incremento de tiempo después de esta acción ( por ejemplo, el número de días, meses o años cuando desea que el elemento expire.  <br/>  Para usar una fórmula de retención personalizada para determinar la expiración, elija **establecer mediante una fórmula de retención personalizada instalada en este servidor**.  <br/> > [!NOTE]> esta opción solo está disponible si el administrador ha configurado una fórmula personalizada.           |
||||||3.  <br/> |La opción **iniciar un flujo de trabajo** solo está disponible si está definiendo una directiva para una lista, biblioteca o tipo de contenido que ya tiene asociado un flujo de trabajo. A continuación, se le ofrecerá una selección de flujos de trabajo para elegir.<br/> |
||||||4.  <br/> |En la **** sección periodicidad, seleccione **repetir la acción de esta fase...** y especifique la frecuencia con la que desea que se repita la acción.  <br/> > [!NOTE]> esta opción solo está disponible si la acción seleccionada puede repetirse. Por ejemplo, no puede establecer la periodicidad para que la acción elimine de **forma permanente**.           |
||||||5.  <br/> |Elija **Aceptar**.  <br/> |
   
1. Para habilitar la auditoría de los documentos y elementos que están sujetos a esta Directiva, elija **Habilitar auditoría**y, a continuación, especifique los eventos que desea auditar.
    
    Para habilitar la auditoría
    
||||||1. * * * *|En la página Editar Directiva, * * **en** **auditar** **\>** **Habilitar auditoría** * * y, a continuación, active las casillas de verificación situadas junto a los eventos para los que desea mantener una pista de auditoría. * * * *|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |**Para solicitar a los usuarios que inserten estos códigos de barras en los documentos,** **elige** **Pedir a los usuarios que inserten un código de barras antes de guardar o imprimir** **.** <br/> |
||||||**3.** <br/> |**Elige** **OK** * * para aplicar la característica de auditoría a la Directiva. ** <br/> |
|||||||La característica de directiva de auditoría permite a las organizaciones crear y analizar registros de auditoría para documentos y enumerar elementos como listas de tareas, listas de problemas, grupos de discusión y calendarios. Esta característica de directiva proporciona un registro de auditoría que registra los eventos, como cuando se ve, se modifica o se elimina el contenido.  <br/> |
|||||||Cuando la auditoría está habilitada como parte de una directiva de administración de la información, los administradores pueden ver los datos de auditoría en los informes de uso de directivas que se basan en Microsoft Excel y que resumen el uso actual. Los administradores pueden usar estos informes para determinar cómo se usa la información dentro de la organización. Estos informes también pueden ayudar a las organizaciones a comprobar y documentar el cumplimiento de su normativa o a investigar posibles problemas.  <br/> |
|||||||El registro de auditoría graba la siguiente información: nombre del evento, fecha y hora del evento y nombre de sistema del usuario que realizó la acción.  <br/> |
   
1. Cuando los códigos de barras se habilitan como parte de una directiva, se agregan a las propiedades del documento y se muestran en la zona del encabezado del documento al que se aplica el código de barras. Al igual que las etiquetas, los códigos de barras también se pueden quitar de un documento de forma manual. Puede especificar si se debe pedir a los usuarios que incluyan el código de barras al imprimir o guardar un elemento, o si el código de barras debe insertarse manualmente mediante la pestaña **Insertar** de 2010 programas de la versión de Office. 
    
    Para habilitar los códigos de barras
    
||||||1. * * * *|**En la página Editar Directiva, en **códigos de barras** \> , **habilite códigos de barras**.**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |Para solicitar a los usuarios que inserten estos códigos de barras en documentos, elija **solicitar a los usuarios que inserten un código de barras antes de guardar o imprimir**.  <br/> |
||||||**3.** <br/> |Elija **Aceptar** para aplicar la característica de código de barras a la Directiva.  <br/> |
|||||||
 La Directiva de códigos de barras genera códigos de barras estándar de código 39. Cada imagen de código de barras incluye texto debajo del símbolo de código de barras que representa el valor del código de barras. Esto permite usar los datos del código de barras incluso cuando el hardware de análisis no está disponible. Los usuarios pueden escribir manualmente el número del código de barras en el cuadro de búsqueda para buscar el elemento en un sitio.  <br/> |
   
1. Para requerir que los documentos que están sujetos a esta Directiva tengan etiquetas, elija **Habilitar etiquetas**y, a continuación, especifique la configuración que desee para las etiquetas.
    
    Para habilitar las etiquetas
    
||||||**1.**|* * Para requerir que los usuarios agreguen una etiqueta a un documento, elija **solicitar a los usuarios que inserten una etiqueta antes de guardar o imprimir**.  <br/> > [!NOTE]> si desea que las etiquetas sean opcionales, no active esta casilla de verificación.        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> |Para bloquear una etiqueta para que no se pueda cambiar una vez insertada, elija **impedir cambios en las etiquetas después**de que se hayan agregado.  <br/>  Esta opción impide que el texto de la etiqueta se actualice una vez que la etiqueta se haya insertado en un elemento dentro de una aplicación cliente como Word, Excel o PowerPoint. Si desea que la etiqueta se actualice cuando se actualicen las propiedades de este documento o elemento, no active esta casilla de verificación.<br/> |
||||||3.  <br/> |En el cuadro formato de etiqueta, escriba el texto de la etiqueta tal como desea que se muestre. Las etiquetas pueden contener hasta 10 referencias de columna, cada una de las cuales puede tener una longitud de hasta 255 caracteres. Para crear el formato de la etiqueta, haga lo siguiente:  <br/> Escriba los nombres de las columnas que desea incluir en la etiqueta en el orden en que desea que aparezcan. Escriba los nombres de columna entre llaves ({}), como se muestra en el ejemplo de la página Editar Directiva.  <br/> Escriba palabras para identificar las columnas fuera de los corchetes, como se muestra en el ejemplo de la página Editar Directiva.  <br/> |
||||||4.  <br/> |Para agregar un salto de línea, escriba **\n** donde desea que aparezca el salto de línea.  <br/> |
||||||5.  <br/> |Seleccione el tamaño de fuente y el estilo que desee y especifique si desea que la etiqueta esté situada a la izquierda, a la derecha o en el centro del documento.  <br/>  Seleccione una fuente y un estilo que estén disponibles en los equipos de los usuarios. El tamaño de la fuente afecta a la cantidad de texto que se puede mostrar en la etiqueta.  <br/> |
||||||6.  <br/> |Escriba el alto y el ancho de la etiqueta. El alto de la etiqueta puede oscilar entre 0,25 pulgadas y 20 pulgadas y el ancho de la etiqueta puede oscilar entre 0,25 pulgadas y 20 pulgadas. El texto de la etiqueta siempre se centra verticalmente dentro de la imagen de la etiqueta.  <br/> |
||||||7.  <br/> |Elija **Actualizar** para obtener una vista previa del contenido de la etiqueta.  <br/> |
   
1. Elija **Aceptar**.
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a>Crear una directiva para una lista, una biblioteca o una carpeta (directiva de retención basada en ubicación)
<a name="__create_a_policy"> </a>

Puede definir una directiva de retención que se aplique solo a una lista, biblioteca o carpeta específica. Sin embargo, si crea una directiva de retención de este modo, no podrá volver a usar esta directiva en otras listas, bibliotecas, carpetas o sitios, ni aplicar una directiva de colección de sitios a una directiva basada en una ubicación.
  
Si desea aplicar una sola directiva de retención a todos los tipos de contenido en una sola ubicación, probablemente querrá usar retención basada en la ubicación. En la mayoría de los casos, querrá comprobar que se especifica una directiva de retención para todos los tipos de contenido.
  
 Cada subcarpeta hereda la Directiva de retención de su elemento principal, a menos que elija interrumpir la herencia y definir una nueva Directiva de retención en el nivel secundario. 
  
Si desea definir una directiva de administración de información distinta de la retención en una lista o biblioteca, debe definir una directiva de administración de la información para cada tipo de contenido de lista individual asociado a esa lista o biblioteca.
  
 Si en algún momento decide cambiar de tipo de contenido a directivas basadas en la ubicación para una lista o biblioteca, solo se usará la Directiva de retención como directiva basada en la ubicación. Todas las demás directivas de administración (auditorías, códigos de barras y códigos de barras) se heredarán de los tipos de contenido asociados. 
  
 Las directivas basadas en ubicaciones se pueden deshabilitar para una colección de sitios mediante la desactivación de la característica de retención basada en bibliotecas y carpetas. Esto permite a los administradores de colecciones de sitios asegurarse de que las directivas de tipo de contenido no se reemplazan por las directivas basadas en la ubicación del administrador de la lista. 
  
Necesita al menos el permiso administrar listas para cambiar la configuración de la Directiva de administración de la información de una lista o biblioteca.
  
1. Desplácese a la lista o biblioteca para la que desea especificar una directiva de administración de información. 
    
2. En la cinta de opciones, **** elija la biblioteca o la configuración de **** la \> **biblioteca** de fichas de **lista** o de lista.
    
    En SharePoint Online, haga clic en **configuración** y, a continuación, haga clic en **configuración de lista** o **configuración de biblioteca**. 
    
3. En **permisos y** \> **Opciones de directiva de administración de información**de administración.
  
![Vínculo directivas de administración de la información en la página de configuración de la biblioteca de documentos](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. En la página Configuración de la Directiva de administración de la información, asegúrese de que el origen de la retención de la lista o biblioteca esté establecido en bibliotecas y carpetas. 
  
Si **tipo de contenido** aparece como origen, haga clic en **cambiar origen**y, a continuación, haga clic en **biblioteca y carpetas**. Se le advierte de que se omitirán las directivas de retención de tipo de contenido. Haga clic en **Aceptar**. 
    
5. En la página Editar Directiva, en **programación de retención basada en bibliotecas**, escriba una breve descripción de la Directiva que va a crear. 
    
6. Elija **Agregar una fase de retención...**
    
     Tenga en cuenta que, en registros, puede elegir definir distintas directivas de retención para los registros seleccionando la opción definir distintas fases de retención para los registros. 
    
7. En el cuadro de diálogo Propiedades de fase, seleccione una opción de período de retención para especificar Cuándo expirarán los documentos o elementos. Realice una de las siguientes acciones:
    
  - Para establecer la fecha de expiración en función de una propiedad de fecha, en **evento** \> **esta fase se basa en una propiedad de fecha del elemento**y, a continuación, selecciona la acción del documento o elemento (por ejemplo, creado o modificado) y el incremento de tiempo después de esta acción ( por ejemplo, el número de días, meses o años cuando desea que el elemento expire. 
    
  - Para usar una fórmula de retención personalizada para determinar la expiración, elija **establecer mediante una fórmula de retención personalizada instalada en este servidor**. 
    
    > [!NOTE]
    >  Esta opción solo está disponible si el administrador ha configurado una fórmula personalizada. 
  
  - En **acción**, especifique lo que desea que suceda cuando expire el documento o elemento. Para permitir que una acción específica se produzca en el documento o elemento (por ejemplo, la eliminación), seleccione una acción de la lista. 
    
8. La opción **iniciar un flujo de trabajo** solo está disponible si está definiendo una directiva para una lista, biblioteca o tipo de contenido que ya tiene asociado un flujo de trabajo. A continuación, se le ofrecerá una selección de flujos de trabajo para elegir. 
    
9. En **periodicidad**, elija **repetir la acción de esta fase...** y especifique la frecuencia con la que desea que se repita la acción. 
    
    > [!NOTE]
    >  Esta opción solo está disponible si la acción seleccionada puede repetirse. Por ejemplo, no puede establecer la periodicidad para que la acción elimine de **forma permanente**. 
  
10. Elija **Aceptar**.
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a>Aplicar una directiva de colección de sitios a un tipo de contenido
<a name="__apply_a_site"> </a>

Si ya se han creado directivas de administración de la información para su sitio como directivas de colección de sitios, puede aplicar una de las directivas a un tipo de contenido. De esta forma, puede aplicar la misma directiva a varios tipos de contenido en una colección de sitios que no comparten el mismo tipo de contenido primario.
  
 Si desea aplicar directivas a varios tipos de contenido en una colección de sitios y tiene configurado un servicio de metaDatos administrados, puede usar la publicación de tipo de contenido para publicar directivas de administración de la información en varias colecciones de sitios. Vea la sección [aplicar una directiva a los tipos de contenido en las colecciones de sitios](create-info-mgmt-policies.md#__apply_a_policy) para obtener más información. 
  
1. Navegue hasta la lista o biblioteca que contiene el tipo de contenido al que desea aplicar una directiva.
    
2. En la cinta de opciones, **** elija la biblioteca o la configuración de **** la \> **biblioteca** de fichas de **lista** o de lista.
    
    En SharePoint Online, haga clic en **configuración** y, a continuación, haga clic en **configuración de lista** o **configuración de biblioteca**. 
    
3. En **permisos y** \> **Opciones de directiva de administración de información**de administración.
  
![Vínculo directivas de administración de la información en la página de configuración de la biblioteca de documentos](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Compruebe que el origen de la Directiva está establecido en **tipos de contenido**y en directivas de **tipo de contenido** Seleccione el tipo de contenido al que desea aplicar la Directiva. 
    
5. En **especificar la Directiva** \> **use una directiva de colección de sitios**y, a continuación, seleccione la Directiva que desea aplicar en la lista. 
    
    > [!NOTE]
    >  Si la opción **usar una directiva de colección de sitios** no está disponible, no se definió ninguna directiva de colección de sitios para la colección de sitios. 
  
6. Elija **Aceptar**.
    
     Si la lista o biblioteca con la que trabaja admite la administración de varios tipos de contenido, en **tipos de contenido** puede elegir el tipo de contenido para el que desea especificar una directiva de administración de la información. Esto le llevará directamente al paso 5 anterior. 
    
## <a name="apply-a-policy-across-site-collections"></a>Aplicar una directiva en las colecciones de sitios
<a name="__toc260646789"> </a>

Compartir tipos de contenido entre colecciones de sitios mediante una aplicación de servicio de metaDatos administrados para configurar la publicación de tipo de contenido. La publicación de tipo de contenido ayuda a administrar el contenido y los metadatos de manera coherente en los sitios, ya que los tipos de contenido se pueden crear y actualizar de forma centralizada, y las actualizaciones se pueden publicar en varias colecciones de sitios o aplicaciones Web de suscripción.
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a>Crear una plantilla a partir de una directiva existente para usarla en las colecciones de sitios
<a name="__toc262125409"> </a>

Puede definir una directiva de administración de la información y, a continuación, crear una plantilla a partir de ella para usarla en varias colecciones de sitios. Este método se puede usar si desea tener una copia de seguridad de las directivas de información o también puede usarse como método alternativo a usar la publicación de tipo de contenido para aplicar una directiva en las colecciones de sitios. Puede crear una plantilla o una copia de seguridad de la Directiva exportando la Directiva de una colección de sitios y, a continuación, importándola a una ubicación guardada o a otra colección de sitios.
  
> [!IMPORTANT]
>  Si usa la característica de exportación e importación como forma de realizar un conjunto de plantillas de directivas, tenga en cuenta que existe un identificador único en el archivo Policy. Xml. Por este motivo, no se puede importar la Directiva a un sitio más de una vez sin cambiar este identificador único. 
  
### <a name="export-a-policy"></a>Exportar una directiva
<a name="__toc260646790"> </a>

1. En la Página principal de la colección de sitios, elija **configuración**![pequeña de engranaje que ha tomado la configuración del sitio. ](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) **sitio.** \>
    
    En un sitio conectado a un grupo de SharePoint, haga clic en **configuración**, en **contenidos del sitio**y, a continuación, en **configuración del sitio**. 
    
2. En la página Configuración del sitio, en **plantillas de directiva de tipo de contenido**de administración \> de la colección de **sitios** . 
  
![Vínculo de plantilla de directiva de tipo de contenido en la página Configuración del sitio](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Elija la Directiva que desea exportar \> desplazar a la \> **exportación**inferior.
    
4. Cuando se le pida que guarde o abra el archivo, elija **Guardar**y, a continuación, seleccione una ubicación en la que guardar el archivo. Asegúrese de seleccionar una ubicación que esté disponible para las colecciones de sitios que están importando la Directiva.
    
5. Cuando se muestre el cuadro de diálogo Descarga completada, elija **cerrar**.
    
### <a name="import-a-policy-to-a-different-site-collection"></a>Importar una directiva a una colección de sitios diferente
<a name="__toc260646791"> </a>

La importación de una directiva de administración de la información permite aplicarla a varios tipos de contenido en el nivel de sitio o de lista dentro de una colección de sitios determinada. Las ventajas de hacerlo son dobles: no es necesario volver a definir y aplicar la Directiva en cada tipo de contenido, y se pueden administrar con mayor facilidad las modificaciones de la Directiva realizando cambios en la Directiva en un solo punto.
  
1. En la Página principal de la colección de sitios a la que desea aplicar la Directiva, elija **configuración**![de pequeña configuración de engranaje que requería el lugar de configuración del sitio. ](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) **sitio.** \>
    
    En un sitio conectado a un grupo de SharePoint, haga clic en **configuración**, en **contenidos del sitio**y, a continuación, en **configuración del sitio**. 
    
2. En la página Configuración del sitio, en **plantillas de directiva de tipo de contenido**de administración \> de la colección de **sitios** .
    
3. En la página \> directivas, vaya a **importar** \> **examinar** para buscar el archivo XML de la Directiva. 
    
4. Seleccione el archivo XML en el que se ha guardado \> la directiva **abierta**. 
    
5. En la página \> importar una directiva de colección de sitios, **importación** para agregar la Directiva a la colección de sitios. 
    
La Directiva importada ahora puede aplicarse a uno o varios tipos de contenido en el nivel de sitio o de lista. 
  
[Las directivas de administración de la información permiten a su organización controlar el tiempo que se conservará el contenido, auditar lo que hacen los usuarios con el contenido y agregar códigos de barras o etiquetas a los documentos. Una Directiva puede ayudar a garantizar el cumplimiento de las regulaciones legales y gubernamentales o los procesos de negocio internos. Como administrador, puede configurar una directiva para controlar cómo realizar un seguimiento de los documentos y durante cuánto tiempo se conservan los documentos. Puede crear una directiva de administración de la información en tres ubicaciones distintas en la jerarquía del sitio, de la más amplia hasta la más restringida: cree una directiva para usarla en varios tipos de contenido dentro de una colección de sitios. Cree una directiva para un tipo de contenido de sitio. Cree una directiva para una lista o biblioteca. Para obtener más información, vea Introducción a las directivas de administración de la información.](create-info-mgmt-policies.md#__top)
  

