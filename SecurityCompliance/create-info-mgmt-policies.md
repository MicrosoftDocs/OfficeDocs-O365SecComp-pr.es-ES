---
title: Crear y aplicar directivas de administración de información
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
description: Directivas de administración de información permiten la organización para controlar cuánto tiempo desea conservar el contenido, en ¿qué personas con contenido de auditoría y para agregar códigos de barras o etiquetas en documentos. Una directiva puede ayudar a exigir el cumplimiento de reglamentaciones gubernamentales y legales o los procesos internos de la empresa. Como administrador, puede configurar una directiva para controlar cómo realizar un seguimiento de documentos y cuánto tiempo desea retener los documentos.
ms.openlocfilehash: cc15b7d830e6c13e00045f7e4b672ac4a755a70e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535882"
---
# <a name="create-and-apply-information-management-policies"></a>Crear y aplicar directivas de administración de información

Directivas de administración de información permiten la organización para controlar cuánto tiempo desea conservar el contenido, en ¿qué personas con contenido de auditoría y para agregar códigos de barras o etiquetas en documentos. Una directiva puede ayudar a exigir el cumplimiento de reglamentaciones gubernamentales y legales o los procesos internos de la empresa. Como administrador, puede configurar una directiva para controlar cómo realizar un seguimiento de documentos y cuánto tiempo desea retener los documentos.
  
Puede crear un puede de directiva de administración de información en tres ubicaciones diferentes en la jerarquía del sitio, desde la más amplia para el más restringido:
  
- Crear una directiva para usar en varios tipos de contenido dentro de una colección de sitios.
    
- Crear una directiva para un tipo de contenido de sitio.
    
- Crear una directiva para una lista o biblioteca.
    
Para obtener más información, vea [Introducción a las directivas de administración de información](intro-to-info-mgmt-policies.md).
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a>Crear una directiva para varios tipos de contenido dentro de una colección de sitios
<a name="__toc261001590"> </a>

Para asegurarse de que una directiva de información se aplica a todos los documentos de un tipo determinado dentro de una colección de sitios, considere la posibilidad de crear la directiva en el nivel de colección de sitios y, a continuación, más adelante, aplicar la directiva a los tipos de contenido. Estos se conocen como directivas de colección de sitios. 
  
1. En la página principal de colección de sitios \> **configuración**![botón Configuración de 2016 de SharePoint en la barra de título. ](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Configuración del sitio**.
    
    En un sitio de SharePoint conectados de grupo, haga clic en **configuración**, haga clic en **Contenido del sitio**y, a continuación, haga clic en **Configuración del sitio**. 
    
2. En la página Configuración del sitio, en **Administración de la colección de sitios** \> **Plantillas de directiva de tipo de contenido**. 
  
![Vínculo de plantilla de directiva de tipo de contenido en la página Configuración del sitio](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. En la página directivas \> **crear**. 
    
4. Escriba un nombre y una descripción para la directiva y, a continuación, escribir una breve declaración de directiva que se explica a los usuarios cuál es la directiva.
    
5. Vea la siguiente sección sobre la creación de directivas para un tipo de contenido de sitio aprender a configurar las características que desea asociar con la directiva. 
    
6. Elija **Aceptar**.
    
## <a name="create-a-policy-for-a-site-content-type"></a>Crear una directiva para un tipo de contenido de sitio
<a name="__create_a_policy"> </a>

Adición de una directiva de administración de información a un tipo de contenido facilita la asociar características de directiva a varias listas o bibliotecas. Puede elegir agregar una directiva de administración de información existente a un tipo de contenido o crear una única directiva específica de un tipo de contenido individual.
  
 También puede agregar una directiva de administración de información a un tipo de contenido que es específico de listas. Esto tiene el efecto de aplicar la directiva únicamente a los elementos de esa lista que usan el tipo de contenido. 
  
1. En la página principal de colección de sitios \> **configuración**![botón Configuración de 2016 de SharePoint en la barra de título. ](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Configuración del sitio**.
    
    En un sitio de SharePoint conectados de grupo, haga clic en **configuración**, haga clic en **Contenido del sitio**y, a continuación, haga clic en **Configuración del sitio**. 
    
2. En la página Configuración del sitio, en **Galerías del Diseñador Web** \> **los tipos de contenido de sitio**.
  
![Vínculo de tipos de contenido de sitio en la página Configuración del sitio](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. En la página Configuración del tipo de contenido de sitio, seleccione el tipo de contenido que desea agregar una directiva.
    
4. En la página tipo de contenido de sitio, en **configuración de** \> **configuración de directiva de administración de información**.
    
5. En la página Editar directiva, escriba un nombre y una descripción para la directiva y, a continuación, escriba una descripción breve que se explica a los usuarios cuál es la directiva.
    
6. En las secciones siguientes, seleccione las características de directiva individuales que desee agregar a la directiva de administración de información. 
  
![Tipos de directivas de contenido](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. Para especificar un período de retención para documentos y elementos que están sujetos a esta directiva, elija **Habilitar la retención**y, a continuación, especifique el período de retención y las acciones que desea que se producen cuando los elementos caduquen.
    
    Para especificar un período de retención
    
||||||**1.**|** Elija ** Agregar una fase de retención para los registros... ***|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> | Seleccione una opción de período de retención para especificar cuando se establecen los documentos o elementos a punto de caducar. Realice una de las siguientes opciones:<br/>  Para establecer la fecha de caducidad según una propiedad de fecha, en el **evento** \> **esta etapa se basa en una propiedad de fecha en el elemento**y a continuación, seleccione la acción de documento o elemento (por ejemplo, creado o modificado) y el incremento de tiempo después de esta acción () Por ejemplo, el número de días, meses o años) cuando desee el elemento a punto de caducar.  <br/>  Para usar una fórmula de retención personalizada para determinar la expiración, elija **establecer mediante una fórmula de retención personalizada instalada en este servidor**.  <br/> > [!NOTE]> Esta opción sólo está disponible si se ha configurado una fórmula personalizada por el administrador.           |
||||||3.  <br/> |La opción para **iniciar un flujo de trabajo** está disponible sólo si está definiendo una directiva para una lista, biblioteca o tipo de contenido que ya tiene un flujo de trabajo asociado con él. A continuación, le dará una opción de flujos de trabajo que puede elegir.<br/> |
||||||4.  <br/> |En la sección de **repetición** , seleccione **Repita la acción de esta fase...** y especifique la frecuencia con la que desea que la acción que se repite.  <br/> > [!NOTE]> Esta opción sólo está disponible si se puede repetir la acción que ha seleccionado. Por ejemplo, no se puede establecer la periodicidad de la acción de **Eliminar de forma permanente**.           |
||||||5.  <br/> |Eligió **Aceptar**.  <br/> |
   
1. Para habilitar la auditoría de los documentos y elementos que están sujetos a esta directiva, seleccione **Habilitar auditoría**y, a continuación, especifique los eventos que desea auditar.
    
    Para habilitar la auditoría
    
||||||1.* no **|En la página Editar directiva, ** **en** **auditoría** **\>** **Habilitar la auditoría** **, y, a continuación, seleccione las casillas de verificación junto a los eventos que desee mantener una auditoría rastros for.* **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |**Para solicitar a los usuarios que inserten estos códigos de barras en los documentos,** **Elija** **Solicitar a los usuarios que inserten un código de barras antes de guardar o imprimir** **.** <br/> |
||||||**3.** <br/> |**Elija** **Aceptar** ** para aplicar la característica de auditoría a la directiva. ** <br/> |
|||||||La característica de directiva de auditoría permite a las organizaciones crear y analizar registros de auditoría para documentos y elementos de lista como listas de tareas, listas de problemas, grupos de discusión y calendarios. Esta característica de directiva proporciona un registro de auditoría que registra eventos, como cuando se ven, edita o elimina contenido.  <br/> |
|||||||Cuando la auditoría está habilitada como parte de una directiva de administración de información, los administradores pueden ver los datos de auditoría en informes de uso de directivas que se basan en Microsoft Excel y que resumen el uso actual. Los administradores pueden usar estos informes para determinar cómo se utiliza la información dentro de la organización. Estos informes también pueden ayudar a las organizaciones a comprobar y documentar el cumplimiento o a investigar problemas potenciales.  <br/> |
|||||||El registro de auditoría graba la siguiente información: nombre del evento, fecha y hora del evento y nombre de sistema del usuario que realizó la acción.  <br/> |
   
1. Cuando los códigos de barras se habilitan como parte de una directiva, son agregados a las propiedades de documento y que se muestra en el área de encabezado del documento al que se aplica el código de barras. Al igual que las etiquetas, los códigos de barras también pueden quitarse manualmente de un documento. Puede especificar si se deben pedir a los usuarios para incluir el código de barras al imprimir o guardar un elemento o si el código de barras debe insertarse manualmente mediante la ficha **Insertar** en 2010 Office programas de la versión. 
    
    Para habilitar códigos de barras
    
||||||1.* no **|**En la página Editar directiva, en **códigos de barras** \> **Habilitar códigos de barras**.**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |Para solicitar a los usuarios para insertar estos códigos de barras en los documentos, elija **solicitar a los usuarios que inserten un código de barras antes de guardar o imprimir**.  <br/> |
||||||**3.** <br/> |Elija **Aceptar** para aplicar la característica de código de barras a la directiva.  <br/> |
|||||||
 La directiva de código de barras genera códigos de barras estándar de código 39. Cada imagen de código de barras incluye texto bajo el símbolo de código de barras que representa el valor de código de barras. Esto permite que los datos de código de barras para usarse incluso cuando el examen de hardware no está disponible. Los usuarios pueden escribir manualmente el número de código de barras en el cuadro Buscar para buscar el elemento en un sitio.  <br/> |
   
1. Para requerir que los documentos que están sujetos a esta directiva tengan etiquetas, elija **Habilitar etiquetas**y, a continuación, especifique la configuración que desee para los rótulos.
    
    Para habilitar las etiquetas
    
||||||**1.**|** Para requerir a los usuarios agregar una etiqueta a un documento, elija **solicitar a los usuarios que inserten una etiqueta antes de guardar o imprimir**.  <br/> > [!NOTE]> Si desea que las etiquetas sean opcionales, no Active esta casilla de verificación.        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> |Para bloquear una etiqueta de modo que no se puede cambiar una vez que se ha insertado, elija **impedir cambios en las etiquetas después de que se hayan agregado**.  <br/>  Esta configuración impide que el texto del rótulo de actualización una vez que la etiqueta se ha insertado en un elemento dentro de una aplicación de cliente, por ejemplo, Word, Excel y PowerPoint. Si desea que la etiqueta se actualice cuando se actualizan las propiedades de este documento o elemento, no seleccione esta casilla de verificación.<br/> |
||||||3.  <br/> |En el cuadro Formato de etiqueta, escriba el texto para la etiqueta tal como desea que se muestre. Las etiquetas pueden contener hasta 10 referencias de columna, cada uno de los cuales puede tener hasta 255 caracteres de longitud. Para crear el formato de la etiqueta, realice lo siguiente:  <br/> Escriba los nombres de las columnas que desea incluir en la etiqueta en el orden en que desea que aparezca. Los nombres de columna en entre llaves ({}), tal como se muestra en el ejemplo en la página Editar directiva.  <br/> Escriba palabras que identifiquen las columnas fuera de las llaves, tal como se muestra en el ejemplo en la página Editar directiva.  <br/> |
||||||4.  <br/> |Para agregar un salto de línea, escriba **\n** donde desea que aparezca el salto de línea.  <br/> |
||||||5.  <br/> |Seleccione el tamaño de fuente y el estilo que desee y especificar si desea que la etiqueta de una posición izquierda, centro, derecha o en el documento.  <br/>  Seleccione una fuente y un estilo que están disponibles en equipos de los usuarios. El tamaño de la fuente afecta a la cantidad de texto que se puede mostrar en la etiqueta.  <br/> |
||||||6.  <br/> |Escriba el alto y el ancho de la etiqueta. Alto de etiqueta puede oscilar entre pulgadas.25 a 20 pulgadas y ancho de la etiqueta puede oscilar entre pulgadas.25 a 20 pulgadas. Texto de la etiqueta siempre se centra verticalmente dentro de la imagen de la etiqueta.  <br/> |
||||||7.  <br/> |Elija **Actualizar** para obtener una vista previa del contenido de la etiqueta.  <br/> |
   
1. Elija **Aceptar**.
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a>Crear una directiva para una lista, una biblioteca o una carpeta (directiva de retención basada en ubicación)
<a name="__create_a_policy"> </a>

Puede definir una directiva de retención que se aplica únicamente a una lista específica, biblioteca o carpeta. Sin embargo, si crea una directiva de retención de este modo, no se puede volver a usar esta directiva en otras listas, bibliotecas, carpetas o sitios, y no se puede aplicar una directiva de colección de sitios a una directiva de ubicación basada.
  
Si desea aplicar una sola directiva de retención a todos los tipos de contenido en una única ubicación, probablemente deseará usar retención basada en la ubicación. En la mayoría de los otra casos, desea comprobar que se ha especificado una directiva de retención para todos los tipos de contenido.
  
 Cada subcarpeta hereda la directiva de retención de su forma principal, a menos que elija para interrumpir la herencia y definir una nueva directiva de retención en el nivel secundario. 
  
Si desea definir una directiva de administración de información que no sea de retención a una lista o biblioteca, debe definir una directiva de administración de información para cada tipo de contenido de lista individual asociado a esa lista o biblioteca.
  
 Si decide cambiar de tipo de contenido a directivas basadas en ubicación para una lista o biblioteca en cualquier momento, sólo la directiva de retención se usará como la directiva de ubicación. Todas las demás directivas de administración (auditorías, códigos de barras y códigos de barras) se hereda de los tipos de contenido asociados. 
  
 Las directivas de ubicación en función se pueden deshabilitar para una colección de sitios con la desactivación de la característica de biblioteca y retención en función de carpeta. Esto permite a los administradores de colección de sitios para asegurarse de que sus directivas de tipo de contenido no se reemplazan por las directivas de ubicación en función del Administrador de una lista. 
  
Necesita al menos el permiso Administrar listas para cambiar la configuración de directiva de administración de información para una lista o biblioteca.
  
1. Vaya a la lista o biblioteca para la que desea especificar una directiva de administración de información. 
    
2. En la cinta de opciones, elija la pestaña **lista** o **biblioteca de** \> **Configuración de la biblioteca** o la **Configuración de la lista**.
    
    En SharePoint Online, haga clic en **configuración** y, a continuación, haga clic en **configuración de lista** o **configuración de la biblioteca**. 
    
3. En **permisos y administración** \> **configuración de directiva de administración de información**.
  
![Vínculo de las directivas de administración de información en la página de configuración de biblioteca de documentos](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. En la página Configuración de directiva de administración de información, asegúrese de que el origen de la retención de la lista o biblioteca se establece en la biblioteca y carpetas. 
  
Si el **Tipo de contenido** aparece como el origen, haga clic en **Cambiar origen**y, a continuación, haga clic en **biblioteca y carpetas**. Se le avisa de que se pasará por alto las directivas de retención de tipo de contenido. Elija **Aceptar**. 
    
5. En la página Editar directiva, en la **Biblioteca en función de la programación de retención**, escriba una breve descripción para la directiva que está creando. 
    
6. Elija **Agregar una fase de retención...**
    
     Tenga en cuenta que en los registros, puede elegir definir diferentes directivas de retención de registros mediante la selección de las fases de retención diferente de definir para la opción de registros. 
    
7. En el cuadro de diálogo de propiedades de fase, seleccione una opción de período de retención para especificar cuándo se establecen los documentos o elementos a punto de caducar. Realice una de las siguientes opciones:
    
  - Para establecer la fecha de caducidad según una propiedad de fecha, en el **evento** \> **esta etapa se basa en una propiedad de fecha en el elemento**y a continuación, seleccione la acción de documento o elemento (por ejemplo, creado o modificado) y el incremento de tiempo después de esta acción () Por ejemplo, el número de días, meses o años) cuando desee el elemento a punto de caducar. 
    
  - Para usar una fórmula de retención personalizada para determinar la expiración, elija **establecer mediante una fórmula de retención personalizada instalada en este servidor**. 
    
    > [!NOTE]
    >  Esta opción sólo está disponible si se ha configurado una fórmula personalizada por el administrador. 
  
  - En **acción**, especifique qué desea que ocurra cuando caduque el documento o elemento. Para habilitar una acción específica a que se produzca en el documento o elemento (como la eliminación), seleccione una acción de la lista. 
    
8. La opción para **iniciar un flujo de trabajo** está disponible sólo si está definiendo una directiva para una lista, biblioteca o tipo de contenido que ya tiene un flujo de trabajo asociado con él. A continuación, le dará una opción de flujos de trabajo que puede elegir. 
    
9. En **Periodicidad**, seleccione **Repita la acción de esta fase...** y especifique la frecuencia con la que desea que la acción que se repite. 
    
    > [!NOTE]
    >  Esta opción sólo está disponible si se puede repetir la acción que ha seleccionado. Por ejemplo, no se puede establecer la periodicidad de la acción de **Eliminar de forma permanente**. 
  
10. Elija **Aceptar**.
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a>Aplicar una directiva de colección de sitios a un tipo de contenido
<a name="__apply_a_site"> </a>

Si ya se han creado directivas de administración de información para su sitio como directivas de colección de sitios, puede aplicar una de las directivas a un tipo de contenido. De esta forma, puede aplicar la misma directiva a varios tipos de contenido en una colección de sitios que no comparten el mismo tipo de contenido primario.
  
 Si desea aplicar directivas a varios tipos de contenido en una colección de sitios y tiene configurado un servicio de metadatos administrados, puede usar el tipo de publicación de contenido para publicar salida las directivas de administración de la información a varias colecciones de sitios. Vea la sección [aplicar una directiva a tipos de contenido en colecciones de sitios](create-info-mgmt-policies.md#__apply_a_policy) para obtener más información. 
  
1. Vaya a la lista o biblioteca que contiene el tipo de contenido al que desea aplicar una directiva.
    
2. En la cinta de opciones, elija la pestaña **lista** o **biblioteca de** \> **Configuración de la biblioteca** o la **Configuración de la lista**.
    
    En SharePoint Online, haga clic en **configuración** y, a continuación, haga clic en **configuración de lista** o **configuración de la biblioteca**. 
    
3. En **permisos y administración** \> **configuración de directiva de administración de información**.
  
![Vínculo de las directivas de administración de información en la página de configuración de biblioteca de documentos](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Compruebe que el origen de la directiva se establece a **Los tipos de contenido**y en **Las directivas de tipo de contenido** , seleccione el tipo de contenido que desea aplicar la directiva. 
    
5. En **Especificar directiva** \> **utilizar una directiva de colección de sitios**y, a continuación, seleccione la directiva que desea aplicar en la lista. 
    
    > [!NOTE]
    >  Si la opción **utilizar una directiva de colección de sitios** no está disponible, no hay directivas de colección de sitios se han definido para la colección de sitios. 
  
6. Elija **Aceptar**.
    
     Si la lista o biblioteca que está trabajando con admite la administración de varios tipos de contenido, en **Tipos de contenido** puede elegir el tipo de contenido para el que desea especificar una directiva de administración de información. Esto le llevará directamente al paso 5. 
    
## <a name="apply-a-policy-across-site-collections"></a>Aplicar una directiva a través de colecciones de sitios
<a name="__toc260646789"> </a>

Compartir tipos de contenido en colecciones de sitios mediante el uso de una aplicación de servicio de metadatos administrados para establecer la publicación de tipo de contenido. Publicación de tipo de contenido le ayudará a administración de contenido y los metadatos coherentemente entre los sitios porque pueden crear tipos de contenido y actualiza de forma centralizada, y las actualizaciones se pueden publicar para varias suscripciones de las colecciones de sitios o aplicaciones Web.
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a>Crear una plantilla a partir de una directiva existente para usar en colecciones de sitios
<a name="__toc262125409"> </a>

Puede definir una directiva de administración de información y, a continuación, crear una plantilla desde la que utilice según sea necesario a través de varias colecciones de sitios. Este método se puede usar si desea tener una copia de seguridad de las directivas de información o también se puede utilizar como un método alternativo al uso de publicación de tipo de contenido para aplicar una directiva a través de colecciones de sitios. Crear una plantilla o una copia de seguridad de la directiva de exportación de la directiva de una colección de sitios y, a continuación, importarlo a una ubicación de guardado o a otra colección de sitios.
  
> [!IMPORTANT]
>  Si está utilizando la exportación e importación de la característica como una forma de realizar un conjunto de plantillas de directiva, tenga en cuenta que existe un identificador único en el archivo .xml de directiva. Por este motivo, no se puede importar el esa directiva a un sitio más de una vez sin cambiar este identificador único. 
  
### <a name="export-a-policy"></a>Exportar una directiva
<a name="__toc260646790"> </a>

1. En la página principal de la colección del sitio, elija **configuración**![engranaje configuración pequeña que tuvieron lugar de configuración del sitio. ](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **Configuración del sitio**.
    
    En un sitio de SharePoint conectados de grupo, haga clic en **configuración**, haga clic en **Contenido del sitio**y, a continuación, haga clic en **Configuración del sitio**. 
    
2. En la página Configuración del sitio, en **Administración de la colección de sitios** \> **Plantillas de directiva de tipo de contenido**. 
  
![Vínculo de plantilla de directiva de tipo de contenido en la página Configuración del sitio](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Seleccione la directiva que desea exportar \> desplazamiento a la parte inferior \> **Exportar**.
    
4. En el símbolo para guardar o abrir el archivo, elija **Guardar**y, a continuación, seleccione una ubicación para guardar el archivo. Asegúrese de seleccionar una ubicación en la que está disponible para las colecciones de sitios que se va a importar la directiva.
    
5. Cuando se muestra el cuadro de diálogo Descarga completa, elija **Cerrar**.
    
### <a name="import-a-policy-to-a-different-site-collection"></a>Importar una directiva a otra colección de sitios
<a name="__toc260646791"> </a>

Importación de una directiva de administración de información permite aplicar a varios tipos de contenido en el nivel de sitio o lista dentro de cualquier colección de sitios determinada. Las ventajas de hacerlo son dos: no es necesario volver a definir y aplicar la directiva en cada tipo de contenido, y puede administrar más fácilmente las modificaciones de la directiva al realizar cambios en la directiva en un solo lugar.
  
1. En la página principal de la colección de sitios a la que desea aplicar la directiva, elija **configuración**![engranaje configuración pequeña que tuvieron lugar de configuración del sitio. ](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **Configuración del sitio**.
    
    En un sitio de SharePoint conectados de grupo, haga clic en **configuración**, haga clic en **Contenido del sitio**y, a continuación, haga clic en **Configuración del sitio**. 
    
2. En la página Configuración del sitio, en **Administración de la colección de sitios** \> **Plantillas de directiva de tipo de contenido**.
    
3. En la página directivas \> **importación** \> **Examinar** para buscar el archivo XML para la directiva. 
    
4. Seleccione el archivo XML en el que se ha guardado la directiva \> **Open**. 
    
5. En la importación de una directiva de colección de sitios página \> **importación** para agregar la directiva a la colección de sitios. 
    
La directiva importada ahora se puede aplicar a uno o varios tipos de contenido en el nivel de sitio o lista. 
  
[Directivas de administración de información permiten la organización para controlar cuánto tiempo desea conservar el contenido, en ¿qué personas con contenido de auditoría y para agregar códigos de barras o etiquetas en documentos. Una directiva puede ayudar a exigir el cumplimiento de reglamentaciones gubernamentales y legales o los procesos internos de la empresa. Como administrador, puede configurar una directiva para controlar cómo realizar un seguimiento de documentos y cuánto tiempo desea retener los documentos. Puede crear un puede de directiva de administración de información en tres ubicaciones diferentes en la jerarquía del sitio, desde la más amplia para el más restringido: crear una directiva para usar en varios tipos de contenido dentro de una colección de sitios. Crear una directiva para un tipo de contenido de sitio. Crear una directiva para una lista o biblioteca. Para obtener más información, vea Introducción a las directivas de administración de información.](create-info-mgmt-policies.md#__top)
  

