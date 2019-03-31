---
title: Personalizar o crear un nuevo tipo de información confidencial
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Aprenda a modificar o crear nuevos tipos de información confidencial de Office 365 para RGPD.
ms.openlocfilehash: 6810a6b6d9b0ea34ab11cc778c32a76d556d7a17
ms.sourcegitcommit: 54d58da1777eb83adb82826d1bb1adb94903c8e1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955223"
---
# <a name="customize-or-create-a-new-sensitive-information-type"></a>Personalizar o crear un nuevo tipo de información confidencial

En este artículo se proporcionan tres ejemplos para ilustrar cómo modificar o crear nuevos tipos de información confidencial de Office 365 para RGPD.

- Modificar un tipo de información confidencial existente: número de tarjeta de débito de la UE

- Crear un nuevo tipo de información confidencial: dirección de correo electrónico

- Crear un nuevo tipo de información confidencial con archivo XML de ejemplo: número de cliente de Contoso

Consulte también:

- [Crear un tipo de información confidencial personalizado con PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

- [Personalizar un tipo de información confidencial integrado](customize-a-built-in-sensitive-information-type.md)

## <a name="modify-a-sensitive-information-type-to-improve-accuracy"></a>Modificar un tipo de información confidencial para mejorar la precisión

Si usa la Búsqueda de contenido para buscar datos personales con tipos de información confidencial y no obtiene los resultados esperados o la búsqueda devuelve demasiados falsos positivos, considere la posibilidad de modificar el tipo de información confidencial para que funcione mejor con su entorno.

El procedimiento recomendado al crear o personalizar un tipo de información confidencial es crear un tipo de información confidencial nuevo basado en otro existente, asignándole un nombre e identificadores únicos. Por ejemplo, si desea ajustar los parámetros del tipo de información confidencial "Número de tarjeta de débito de la UE", podría asignar a su copia de la regla el nombre "Tarjeta de débito de la UE mejorada" para distinguirla del original.

En el nuevo tipo de información confidencial, simplemente modifique los valores que desea cambiar para mejorar la precisión. Una vez haya terminado, cargue el nuevo tipo de información confidencial y cree una nueva regla DLP (o modifique una existente) para usar el nuevo tipo de información confidencial que acaba de agregar. Pueden ser necesarios varios intentos para modificar la precisión de los tipos de información confidencial, por lo que si conserva una copia del tipo original, podrá volver a él si es necesario en el futuro.

Para personalizar un tipo de información confidencial:

1.  Exporte el paquete de reglas de Microsoft existentes de tipos de información confidencial integradas en Office 365.

2.  Cambie el nombre de este archivo XML y ábralo en el editor de XML.

3.  Aísle el tipo de información confidencial y quite todos los demás.

4.  Use PowerShell para generar dos nuevos GUID para el tipo de información confidencial que desea modificar.

5.  Modificar el Id. y otros elementos básicos para que el tipo de información confidencial sea único (esto incluye reemplazar dos GUID con los nuevos que generó).

6.  Ajuste los requisitos de coincidencia para mejorar la precisión.

    1.  Modificaciones de proximidad: modifique la proximidad del patrón de caracteres para ampliar o reducir la ventana en la que deben encontrarse palabras clave por el tipo de información confidencial.

    2.  Modificaciones de palabra clave: agregue palabras clave a uno de los elementos \<palabra clave\> para proporcionar al tipo de información confidencial evidencias de corroboración más específicas que debe buscar para señalar una coincidencia en esta regla, o quite palabras clave que causan falsos positivos.

    3.  Modificaciones de confianza: modifique la confianza con la que el tipo de información confidencial debe coincidir con los criterios especificados en la definición antes de que se señale e informe de una coincidencia.

7.  Cargue el nuevo tipo de información confidencial.

8.  Vuelva a rastrear el contenido para identificar la información confidencial. Consulte [Solicitar de forma manual que se rastree y se actualice el índice de un sitio](https://support.office.com/es-ES/article/Manually-request-crawling-and-re-indexing-of-a-site-a-library-or-a-list-9AFA977D-39DE-4321-B4CA-8C7C7E6D264E).

## <a name="example-modify-the-eu-debit-card-number-sensitive-information-type"></a>Ejemplo: modificar el tipo de información confidencial “número de tarjeta de débito de la UE”

Mejorar la precisión de reglas DLP en todos los sistemas necesita pruebas con un conjunto de datos de ejemplo y puede requerir de ajustes mediante pruebas y modificaciones repetitivas. Este ejemplo muestra las modificaciones al tipo de información confidencial "Número de tarjeta de débito de la UE" para mejorar su precisión.

Al buscar un número de tarjeta de débito de la UE en nuestro ejemplo, ese números e define estrictamente como 16 dígitos con un patrón complejo y está sujeto a la validación de la suma de comprobación. No se puede modificar este modelo debido a la definición de cadena del tipo de información confidencial. Sin embargo, pueden hacerse los siguientes ajustes para mejorar la precisión de la forma en que la DLP de Office 365 busca este tipo de información confidencial en Office 365.

### <a name="proximity-modification"></a>Modificación de proximidad

Reduciremos la ventana modificando el valor patternProximity en el elemento \<Entidad\> de 300 a 150 caracteres. Esto significa que la evidencia de corroboración, o las palabras clave, deben estar más cerca de nuestro tipo de información confidencial para señalar a una coincidencia con esta regla.

\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\>

### <a name="keyword-modifications"></a>Modificaciones de palabras clave

Algunas palabras clave podrían provocar falsos positivos. Así pues, es posible que desee quitar palabras clave. Estas son las palabras clave en este ejemplo:

\<Keyword id="palabra clave\_tarjeta\_términos\_dict"\>

\<Group\>

\<Term\>tarjeta corporativa\</Term\>

\<Term\>tarjeta de la organización\</Term\>

\<Term\>n.º de cuenta\</Term\>

\<Term\>núm. de cuenta\</Term\>

\<Term\>nº de cuenta\</Term\>

…

\</Group\>

\</Keyword\>

### <a name="confidence-modifications"></a>Modificaciones de confianza

Si quita palabras clave de la definición, normalmente querrá ajustar el nivel de confianza que tiene en que se ha encontrado este tipo de información confidencial reduciendo este valor. El nivel predeterminado del tipo número de tarjeta de débito de la UE es 85.

\<Entity id="48da7072-821e-4804-9fab-72ffb48f6f78" patternsProximity="150" recommendedConfidence="85"\>

\<Pattern confidenceLevel= "85"\>

…

\</Pattern\>

\</Entity\>

## <a name="create-a-new-custom-sensitive-information-type"></a>Crear un nuevo tipo de información confidencial

Para crear un nuevo tipo de información confidencial, empiece con una búsqueda de contenido para:

-   Optimizar una consulta KQL

-   Ver que palabras clave son más útiles

Utilice los resultados para crear un nuevo tipo de información confidencial. Optimice el nuevo tipo de información confidencial en su entorno.

Nota: Próximamente se añadirán muchos nuevos tipos de información confidencial para datos personales de países de la UE. Si necesita crear nuevos tipos de información confidencial, comience por datos personalizados para su entorno de destino.

### <a name="step-1--use-kql-queries-and-key-words-to-find-additional-data-in-your-environment"></a>Paso 1: Use palabras clave y consultas KQL para buscar datos adicionales en su entorno

Es posible que deba crear consultas adicionales para buscar datos personales que están sujeta al RGPD. La Búsqueda de contenido usa el lenguaje de consulta de palabras clave (KQL) para buscar datos. La mayoría de la información confidencial no se detecta con precisión solo con KQL sin tipos de información confidencial. Por lo tanto, el objetivo es probar y optimizar las cadenas KQL con la Búsqueda de contenido y después usarlas para crear y ajustar los nuevos tipos de información confidencial que pueden proporcionar mayor precisión.

Use estos recursos para formular y optimizar consultas con KQL:

-   [Referencia de la sintaxis del lenguaje de consultas de palabras clave (KQL) (DMC)](https://docs.microsoft.com/es-ES/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

-   [Ejecutar una búsqueda de contenido](https://support.office.com/es-ES/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a) 

La Búsqueda de contenido proporciona otro recurso para ayudarle a desarrollar consultas KQL y tipos de información confidencial: palabras clave. ¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave. Esto puede ayudarle a identificar rápidamente qué palabras clave son las más (y menos) eficaces. Para obtener más información acerca de las estadísticas de búsqueda, consulte [Ver las estadísticas de palabra clave de resultados de búsqueda de contenido](https://support.office.com/es-ES/article/View-keyword-statistics-for-Content-Search-results-9701a024-c52e-43f0-b545-9a53478aec04).

Las palabras clave en cada fila están conectadas mediante el operador O en la consulta de búsqueda que se crea. También puede usar una frase de palabras clave (entre paréntesis) en una fila.

Para obtener más información, consulte [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](https://support.office.com/es-ES/article/Keyword-queries-and-search-conditions-for-Content-Search-c4639c2e-7223-4302-8e0d-b6e10f1c3be3).

### <a name="exampleusing-content-search-to-identify-email-addresses"></a>Ejemplo: usar la Búsqueda de contenido para identificar direcciones de correo electrónico

Se considera que las direcciones de correo electrónico son información confidencial relacionada con temas de datos. Este es un ejemplo sencillo para demostrar cómo puede ayudar Búsqueda de contenido.

No se pueden usar conjuntamente KQL y palabras clave. Use estas herramientas por separado para afinar la consulta y determinar las palabras clave que pueden ser útiles en los tipos de información confidencial.

### <a name="kql-query"></a>Consulta KQL

(^|\\b)([a-zA-Z0-9\_\\-\\.]+)@([a-zA-Z0-9\_\\-\\.]+)\\.([a-zA-Z]{2,5})($|\\b)

Notas:

-   Puede usar CERCA y OCERCA para búsquedas de proximidad.

-   Desafortunadamente, KQL no admite consultas con la clase Regex (por ejemplo: IdRef = "Regex\_dirección\_de correo")

### <a name="keywords"></a>Palabras clave

Escriba cada palabra clave en una línea independiente. Palabras clave de ejemplo:

-   dirección de correo electrónico

-   correo

-   contacto

-   remitente

-   destinatario

-   cc

-   cco

En este ejemplo, es posible que descubra que las palabras clave no son necesarias y generan una gran cantidad de falsos positivos.

### <a name="step-2--create-a-new-custom-sensitive-information-type"></a>Paso 2: Crear un nuevo tipo de información confidencial

Después de usar consultas KQL y palabras clave para identificar información confidencial, úselas para crear nuevos tipos de información confidencial. En muchos casos, necesitará la sofisticación de los tipos de información confidencial para alcanzar el nivel correcto de precisión. Después puede usar estos tipos de información confidencial con la Búsqueda de contenido, en las directivas DLP y otras herramientas y en otras consultas KQL.

El procedimiento recomendado es crear un nuevo tipo de información confidencial basado en otro existente. Use el mismo proceso descrito anteriormente en este artículo.

### <a name="example--create-a-new-sensitive-information-for-email-addresses"></a>Ejemplo: Crear un nuevo tipo de información confidencial para: direcciones de correo electrónico 

Seguiremos con la dirección de correo electrónico como ejemplo porque es sencillo. En la siguiente tabla se detallan las modificaciones que se recomiendan para un nuevo tipo de información confidencial de correo electrónico.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Paso</strong></th>
<th align="left"><strong>Modificación</strong></th>
<th align="left"><strong>Sintaxis XML de ejemplo</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Establezca la propiedad IdRef
<p>En el elemento &lt;Entidad&gt;, modifique el elemento &lt;IdMatch&gt; para que su propiedad idRef sea igual a un valor único. Este valor apuntará a un elemento que define la expresión regular para buscar direcciones de correo electrónico.</p></td>
<td align="left">IdRef=&quot;Regex_email_address&quot;</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left"><p>Atributo de proximidad</p>
<p>Empezaremos con un valor patternProximity en el elemento &lt;Entidad&gt; de 300.</p></td>
<td align="left">patternsProximity=&quot;300&quot;</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left"><p>Nivel de confianza</p>
<p>Establezca la propiedad recommendedConfidence en un valor que sienta que representará la confianza de encontrar una coincidencia exacta. Probablemente esto requiera realizar pruebas con un conjunto de datos representativo para obtener un resultado exacto. Como una configuración inicial, establezca este valor en 75.</p></td>
<td align="left"><p>recommendedConfidence=&quot;75&quot;&gt;</p>
<p>El XML resultante de estos tres primeros elementos combinado tiene este aspecto:</p>
<p>&lt;Entity id=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot; patternsProximity=&quot;300&quot; recommendedConfidence=&quot;75&quot;&gt;</p>
<p>&lt;Pattern confidenceLevel=&quot;75&quot;&gt;</p>
<p>&lt;IdMatch idRef=&quot;Regex_email_address&quot; /&gt;</p>
<p>&lt;Any minMatches=&quot;1&quot;&gt;</p>
<p>&lt;Match idRef=&quot;Keyword_email_terms&quot; /&gt;</p>
<p>&lt;/Any&gt;</p>
<p>&lt;/Pattern&gt;</p>
<p>&lt;/Entity&gt;</p></td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left"><p>Elemento Regex</p>
<p>Agregue un nuevo elemento &lt;Regex&gt; situado inmediatamente por debajo del elemento &lt;Entidad&gt; que defina la expresión regular que se usa para identificar la dirección de correo electrónico.</p></td>
<td align="left">&lt;Regex id=&quot;Regex_email_address&quot;&gt;(^|\b)([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})($|\b)&lt;/Regex&gt;</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left"><p>Palabras clave</p>
<p>Agregue un nuevo elemento &lt;Palabra clave&gt; después del elemento &lt;Regex&gt; que defina la lista de direcciones de correo electrónico. Asegúrese de que el valor de Id. del elemento &lt;Palabra clave&gt; coincida con el valor &lt;Match idRef&gt; el elemento &lt;Entity&gt;&lt;Pattern&gt;. Puede seguir agregando sus propias palabras clave si es necesario.</p>
<p>Es probable que no sea necesario que las palabras clave se incluyan en un tipo de información confidencial de correo electrónico. Estas se proporcionan como ejemplo.</p></td>
<td align="left"><p>&lt;Keyword id=&quot;Keyword_email_terms&quot;&gt;</p>
<p>&lt;Group&gt;</p>
<p>&lt;Term&gt;correo electrónico&lt;/Term&gt;</p>
<p>&lt;Term&gt;dirección de correo electrónico&lt;/Term&gt;</p>
<p>&lt;Term&gt;contacto&lt;/Term&gt;</p>
<p>&lt;/Group&gt;</p>
<p>&lt;/Keyword&gt;</p></td>
</tr>
<tr class="even">
<td align="left">6</td>
<td align="left"><p>Elemento LocalizedStrings</p>
<p>En el elemento &lt;LocalizedStrings&gt;&lt;Resource&gt; asegúrese de que tiene un nombre único que identifica el tipo de información confidencial.</p></td>
<td align="left"><p>&lt;LocalizedStrings&gt;</p>
<p>&lt;Resource idRef=&quot;42e6348e-27f0-4774-9604-d470cb3e219a&quot;&gt;</p>
<p>&lt;Name default=&quot;true&quot; langcode=&quot;es-es&quot;&gt;Dirección de correo electrónico&lt;/Name&gt;</p>
<p>&lt;Description default=&quot;true&quot; langcode=&quot;es-es&quot;&gt;Detecta direcciones de correo electrónico.&lt;/Description&gt;</p>
<p>&lt;/Resource&gt;</p>
<p>&lt;/LocalizedStrings&gt;</p></td>
</tr>
</tbody>
</table>

## <a name="create-a-new-sensitive-information-type-with-example-powershell-and-xml-file--contoso-customer-number"></a>Crear un nuevo tipo de información confidencial con PowerShell y archivo XML de ejemplo: número de cliente de Contoso

Contoso usa un número de clientes de Contoso (CCN) para identificar a cada cliente en la base de datos de cliente. Un CCN consta de la siguiente taxonomía:

-   Dos dígitos para representar el año en que se creó el registro. Contoso fue fundado en 2002, por lo tanto, el valor mínimo posible sería 02.

-   Tres dígitos para representar la agencia asociada que creó el registro. Los posibles valores de agencia están comprendidos entre 000 y 999.

-   Un carácter alfa para representar la línea de negocio. Los valores posibles son a-z y debe distinguir mayúsculas de minúsculas.

-   Un número de serie de cuatro dígitos. Los posibles valores de número de serie están comprendidos entre 0000 y 9999.

CNN de ejemplo:

> 15080P9562
>
> 14040O1119
>
> 15020J8317
>
> 14050E2330
>
> 16050E2166
>
> 17040O1118

Contoso siempre hace referencia a los clientes utilizando un CCN en la correspondencia interna, la correspondencia externa, los documentos, etc. Les gustaría crear un tipo de información confidencial para detectar el uso de CCN en Office 365 para poder aplicar protección al uso de esta forma de datos personales.

### <a name="create-a-new-sensitive-information-type-for-contoso-customer-number"></a>Crear un nuevo tipo de información confidencial para el número de cliente de Contoso

<table>
<thead>
<tr class="header">
<th align="left"><strong>Paso</strong></th>
<th align="left"><strong>Acción</strong></th>
<th align="left"><strong>Resultado</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Contoso usa PowerShell y Búsqueda de contenido para buscar documentos que coinciden con un conjunto de ejemplo de CCN.</td>
<td align="left">

<p>#Conectar al Centro de seguridad y &amp; cumplimiento de Office 365</p>
<p>$adminUser = &quot;juanc@contoso.com&quot;</p>
<p>Connect-IPPSSession -UserPrincipalName $adminUser</p>
<p>#Crear &amp; iniciar una búsqueda de datos de ejemplo</p>
<p>$searchName = &quot;Búsqueda de información de cliente de ejemplo&quot;</p>
<p>$searchQuery = &quot;15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118&quot;</p>
<p>New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery</p>
<p>Start-ComplianceSearch -Identity $searchName</p>
</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">Contoso analiza los resultados. Cada vez que se usó el CCN, se usó una fecha con formato de la UE y también se usaron alguna de estas palabras clave en una proximidad de 300 caracteres.</td>
<td align="left">número de cliente, nº de cliente, # de cliente, #cliente, cliente de Contoso</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">Contoso desarrollo el siguiente patrón de expresiones regulares (RegEx) para identificar sus CCN.</td>
<td align="left">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left">Contoso desarrolló el siguiente patrón de expresiones regulares (RegEx) para identificar las fechas de la UE en los formatos utilizados por sus diferentes filiales.</td>
<td align="left">
````xml
(0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?|‌ feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|‌ apr(ile|il)?|abr(il)?|avril|may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|‌ oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?|nov(ember|iembre|embre|embro)?|dec(ember)?|‌ dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}
````
</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left">Contoso usa PowerShell para generar los tres GUID únicos.</td>
<td align="left"><p>#Generar un GUID único para el Id. de RulePack, el Id. de Publisher y el Id. de Entidad</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p>
<p>[guid]::NewGuid().Guid</p></td>
</tr>
<tr class="even">
<td align="left">6</td>
<td align="left">Contoso define los siguientes parámetros para la regla de tipo de elemento confidencial.</td>
<td align="left"><p>Nombre: Número de cliente de Contoso (CCN)</p>
<p>Descripción: Número de cliente de Contoso (CCN) que busca palabras clave adicionales y fechas con formato de la UE</p></td>
</tr>
<tr class="odd">
<td align="left">7</td>
<td align="left">Contoso crea un archivo XML para un nuevo tipo de información confidencial para detectar un número de cliente de Contoso (CCN) y lo guarda en un sistema de archivos local como C:\Scripts\ContosoCCN.xml con codificación UTF-8.</td>
<td align="left">Consulte el archivo XML después de esta tabla.</td>
</tr>
<tr class="even">
<td align="left">8</td>
<td align="left">Contoso crea el tipo de información confidencial con el siguiente PowerShell.</td>
<td align="left"><p>#Conectar al Centro de seguridad y &amp; cumplimiento de Office 365</p>
<p>$adminUser = &quot;juanc@contoso.com&quot;</p>
<p>Connect-IPPSSession -UserPrincipalName $adminUser</p>
<p>#Crear el nuevo tipo de información confidencial</p>
<p>New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path &quot;C:\Scripts\ContosoCCN.xml&quot; -Encoding Byte -ReadCount 0)</p></td>
</tr>
</tbody>
</table>

### <a name="example-xml-file-for-the-new-sensitive-information-type-step-7"></a>Archivo XML de ejemplo para el nuevo tipo de información confidencial (paso 7)
```xml
\<?xml version="1.0" encoding="utf-8"?\>

\<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce"\>

\<RulePack id="130ae63b-a91e-4a12-9e02-a90e36a83d7f"\>

\<Version major="1" minor="0" build="0" revision="0" /\>

\<Publisher id="47148982-defd-42a1-890a-7b9472099f1f" /\>

\<Details defaultLangCode="en"\>

\<LocalizedDetails langcode="en"\>

\<PublisherName\>Contoso Ltd.\</PublisherName\>

\<Name\>Contoso Rule Package\</Name\>

\<Description\>Defines Contoso's custom set of classification rules\</Description\>

\</LocalizedDetails\>

\</Details\>

\</RulePack\>

\<Rules\>

\<!-- Contoso Customer Number (CCN) --\>

\<Entity id="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b" patternsProximity="300" recommendedConfidence="85"\>

\<Pattern confidenceLevel="85"\>

\<IdMatch idRef="Regex\_contoso\_ccn" /\>

\<Match idRef="Keyword\_contoso\_ccn" /\>

\<Match idRef="Regex\_eu\_date" /\>

\</Pattern\>

\</Entity\>

\<Regex id="Regex\_contoso\_ccn"\>[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}\</Regex\>

\<Keyword id="Keyword\_contoso\_ccn"\>

\<Group matchStyle="word"\>

\<Term caseSensitive="false"\>customer number\</Term\>

\<Term caseSensitive="false"\>customer no\</Term\>

\<Term caseSensitive="false"\>customer \#\</Term\>

\<Term caseSensitive="false"\>customer\#\</Term\>

\<Term caseSensitive="false"\>Contoso customer\</Term\>

\</Group\>

\</Keyword\>

\<Regex id="Regex\_eu\_date"\> (0?[1-9]|[12][0-9]|3[0-1])[\\/-](0?[1-9]|1[0-2]|j\\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)?‌ |feb(ruary|ruari|rero|braio|ruar|br)?|f\\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\\x00e4rz|maart‌|apr(ile|il)?|abr(il)?|avril‌ |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)?‌ |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\\x00e9c(embre)?)[ \\/-](19|20)?[0-9]{2}\</Regex\>

\<LocalizedStrings\>

\<Resource idRef="a91f9a2e-6cfc-4622-8c5d-954875aa5b2b"\>

\<Name default="true" langcode="en-us"\>Contoso Customer Number (CCN)\</Name\>

\<Description default="true" langcode="en-us"\>Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date\</Description\>

\</Resource\>

\</LocalizedStrings\>

\</Rules\>

\</RulePackage\>
```
