---
title: Buscar y encontrar datos personales
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
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
description: Obtenga información sobre cómo buscar y encontrar datos personales en Office 365.
ms.openlocfilehash: b63cf930a38feab6df815b5350d60184a6339927
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158522"
---
# <a name="search-for-and-find-personal-data"></a>Buscar y encontrar datos personales

Los datos personales se definen muy globalmente en el RGPD como los datos que se refieren a una persona física identificada o identificable que reside de la Unión Europea (UE).

Artículo 4: definiciones

> “datos personales” se refiere a cualquier información sobre una persona física identificada o identificable (“interesado”); una persona identificable natural es una que puede identificarse, directa o indirectamente, especialmente con referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más elementos específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona natural;

Este artículo explica cómo buscar datos personales almacenados en SharePoint Online y OneDrive para la Empresa (que incluye los sitios de todos los grupos de Office 365 y Microsoft Teams).

Buscar datos personales sujetos al RGPD depende de usar tipos de información confidencial en Office 365. Estos definen cómo el proceso automatizado reconoce tipos específicos de información, como números de tarjetas de crédito y números de la Seguridad Social. En este momento, los tipos no pueden usarse para buscar datos en buzones de Exchange en reposo. Sin embargo, sí pueden utilizarse con directivas de prevención de pérdida de datos para buscar datos personales en correo en tránsito.

Aunque actualmente no puede usarse la Búsqueda de contenido para buscar datos personales almacenados en los buzones de Exchange Online, pueden usarse los tipos de información confidencial que establece para que el RGPD busque y proteja información personal cuando se envía por correo electrónico.

## <a name="use-content-search-to-find-personal-data"></a>Usar la Búsqueda de contenido para buscar datos personales

Microsoft recomienda un enfoque de tres fases para buscar datos personales en Office 365. El resto de este tema proporciona una guía para cada una de estas fases.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Paso</strong></th>
<th align="left"><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>1. Buscar tipos de información confidencial</p></td>
<td align="left"><p>Empiece con tipos de información confidencial para buscar datos personales. Cree una consulta de búsqueda de contenido para cada tipo de información confidencial. Ejecute la consulta y analice los resultados.</p>
Si es necesario, agregue parámetros a la consulta para reducir los falsos positivos: <li>Intervalo de recuento</li>
    <li>Intervalo de confianza</li>
    <li>Otras propiedades u operadores para consultas más complejas</li>
<p>Si es necesario, modifique el tipo de información confidencial para mejorar la precisión de su organización:</p>
<p><li>Ajuste el nivel de confianza directamente en los archivos XML.</li></p>
<p><li>Agregue palabras clave.</li></p>
<p><li>Ajuste los requisitos de proximidad de palabras clave.</li></p></td>
</tr>
<tr class="even">
<td align="left"><p>2. Usar el Lenguaje de consulta de palabras clave (KQL) para buscar datos personales adicionales en su entorno</p></td>
<td align="left"><p>Para buscar datos que no se incluyen en los tipos de información confidencial, use el lenguaje de consulta KQL para desarrollar consultas personalizadas.</p>
<p>Compruebe los resultados de estas búsquedas y ajuste la cadena de consulta KQL hasta obtener el resultado esperado.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3. Crear nuevos tipos de información confidencial mediante las consultas KQL</p></td>
<td align="left">Después de optimizar las consultas KQL para encontrar los datos de destino, cree nuevos tipos de información confidencial mediante las consultas. Luego puede usar estos tipos de información confidencial con la Búsqueda de contenido, en las directivas DLP y otras herramientas, y en otras consultas KQL.</td>
</tr>
</tbody>
</table>


## <a name="search-for-sensitive-information-types-using-content-search"></a>Buscar tipos de información confidencial con la Búsqueda de contenido

Comience a buscar información personal mediante los tipos de información confidencial que se incluyen con Office 365. Se muestran en el Centro de seguridad y cumplimiento en Clasificación.

Este tema contiene una lista de algunos tipos de información confidencial que se aplican a los ciudadanos de la Unión Europea. Consulte el centro de seguridad o en el centro de cumplimiento para agregar nuevos tipos que pueden ayudarle con el cumplimiento del RGPD.

Consulte este artículo: [Qué buscan los tipos de información confidencial](https://support.office.com/es-ES/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).

Los tipos de información confidencial definen cómo el proceso automático reconoce tipos de información específicos como números de cuentas bancarias, números de la Seguridad Social y números de tarjeta de crédito. Los tipos de información confidencial también se conocen como condiciones. Un tipo de información confidencial se define por medio de un patrón que puede identificarse mediante una expresión regular o una función. Además, pueden usarse pruebas contundentes como palabras clave y sumas de comprobación para identificar un tipo de información confidencial. El nivel de confianza y la proximidad también se usan en el proceso de evaluación.

En este momento, los tipos de información confidencial no pueden usarse para buscar datos almacenados en buzones.

### <a name="using-content-search-with-sensitive-information-types"></a>Usar la Búsqueda de contenido con tipos de información confidencial

<table>
<thead>
<tr class="header">
<th align="left"><strong>Paso</strong></th>
<th align="left"><strong>Más información</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p>Vaya a Búsqueda de contenido en el Centro de seguridad y cumplimiento</p></td>
<td align="left"><p>En el panel izquierdo del Centro de seguridad y cumplimiento, haga clic en **Búsqueda e investigación** &gt; **Búsqueda de contenido**.</p>
<p>Consulte <a href="https://support.office.com/es-ES/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Ejecutar una Búsqueda de contenido en el Centro de seguridad y cumplimiento de Office 365</a>.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Crear un nuevo elemento de búsqueda para cada tipo de información confidencial</p></td>
<td align="left"><p>Utilice la sintaxis siguiente:</p>
<blockquote>
<p>SensitiveType:”&lt;tipo&gt;”</p>
</blockquote>
<p>Por ejemplo:</p>
<blockquote>
<p>SensitiveType:&quot;Número de pasaporte de Francia&quot;</p>
</blockquote>
<p>Establezca el ámbito de la búsqueda a SharePoint (incluye OneDrive para la Empresa). Asegúrese de que la sintaxis es exacta y no hay errores tipográficos o espacios adicionales.</p>
<p>Consulte <a href="https://support.office.com/es-ES/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Crear una consulta para buscar datos confidenciales almacenados en los sitios</a>.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Revise los resultados de cada búsqueda</p></td>
<td align="left"><p>Busque estos tipos de problemas para determinar si la precisión de la consulta es adecuada:</p>
<p><li>Muchos falsos positivos</li></p>
<p><li>Faltan de instancias de datos conocidas</li></p>
<p>Consulte <a href="https://support.office.com/es-ES/article/Export-Content-Search-results-from-the-Office-365-Security-Compliance-Center-ed48d448-3714-4c42-85f5-10f75f6a4278">Exportar resultados de búsqueda desde el Centro de seguridad y cumplimiento de Office 365</a>.</p>
<p>Nota: si usa Mozilla Firefox o Chrome, es posible que primero deba descargar los informes con Internet Explorer o Edge para instalar el complemento necesario.</p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a>Tipos de información confidencial para datos de ciudadanos de la UE

Empiece con estos tipos de información confidencial. Pronto se añadirán muchos más tipos de información confidencial para datos personales en países de la UE.

> Número nacional de Bélgica
>
> Número de tarjeta de crédito
>
> Número de tarjeta de identidad de Croacia
>
> Número de identificación personal de Croacia (OIB)
>
> Número de tarjeta de identidad nacional checa
>
> Número de identificación personal de Dinamarca
>
> Tarjeta de débito de la UE
>
> Identificación nacional de Finlandia
>
> Número de pasaporte de Finlandia
>
> Número de licencia de conductor de Francia
>
> Tarjeta de identificación nacional de Francia (CNI)
>
> Número de pasaporte de Francia
>
> Número de la Seguridad Social de Francia (INSEE)
>
> Número de licencia de conductor de Alemania
>
> Número de documento de identidad de Alemania
>
> Número de pasaporte de Alemania
>
> Tarjeta de identificación nacional de Grecia
>
> Número de cuenta bancaria internacional (IBAN)
>
> Dirección IP
>
> Número de servicio público personal (PPS) de Irlanda
>
> Número de licencia de conductor de Italia
>
> Número de servicio del ciudadano (BSN) de Países Bajos
>
> Número de identidad de Noruega
>
> Tarjeta de identificación de Polonia
>
> Identificación nacional de Polonia (PESEL)
>
> Pasaporte de Polonia
>
> Número de tarjeta del ciudadano de Portugal
>
> Número de la Seguridad Social de España (NSS)
>
> Identificación nacional de Suecia
>
> Número de pasaporte de Suecia
>
> Número de licencia de conductor de Reino Unido
>
> Número de registro electoral de Reino Unido
>
> Número de Servicio Nacional de Salud de Reino Unido
>
> Número de seguro nacional de Reino Unido (NINO)
>
> Número de pasaporte EE. UU./Reino Unido

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a>Agregue parámetros a una consulta de tipo de información confidencial para afinar los resultados

Puede agregar estos parámetros a una consulta de tipo de información confidencial:

-   Intervalo de recuento: define el número de repeticiones de información confidencial que un documento debe contener antes de que se incluya en los resultados de la consulta.

-   Intervalo de confianza: el nivel de confianza con el que el tipo confidencial detectado coincide en realidad, por ejemplo 85 (85 %).

Sintaxis:

-   SensitiveType:"\<tipo\>|\<intervalo de recuento\>|\<intervalo de confianza\>"

Ejemplos:

-   SensitiveType:"Número de tarjeta de crédito | 5" (devuelve únicamente los documentos que contienen exactamente cinco números de tarjeta de crédito)

-   SensitiveType:"Número de tarjeta de crédito | \*| 85... " (el intervalo de confianza es 85 % o superior)

Nota: "SensitiveType" distingue mayúsculas de minúsculas, pero el resto de la consulta no.

También puede usar propiedades y operadores para mostrar cómo puede refinar las consultas. Para obtener más información y ejemplos, consulte [Crear una consulta para buscar datos confidenciales almacenados en los sitios](https://support.office.com/es-ES/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).
