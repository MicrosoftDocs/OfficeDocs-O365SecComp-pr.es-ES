---
title: Diseño de un esquema de clasificación de datos personales
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Determine si su organización va a implementar etiquetas como parte de su plan de RGPD.
ms.openlocfilehash: 4ec495d82a37742d1315673e2a7d089778cd52e4
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223539"
---
# <a name="architect-a-classification-schema-for-personal-data"></a>Diseño de un esquema de clasificación de datos personales

Los artículos anteriores de esta serie se centran en el uso de tipos de información confidencial para identificar datos personales que están sujetos al RGPD. Los tipos de información confidencial son una forma de clasificación. Esta puede ser toda la clasificación que necesita. Sin embargo, muchas organizaciones implementan una estrategia de gobierno de datos más amplia con etiquetas. Use este tema para decidir si también quiere implementar etiquetas como parte de su plan de RGPD. Si lo hace, este tema proporciona algunas directrices y ejemplos.

Nota: Definir un esquema de clasificación de una organización y configurar directivas, etiquetas y condiciones requiere una cuidadosa planificación y preparación. Es importante tener en cuenta que este no es un proceso de TI. Asegúrese de trabajar con el equipo legal y de cumplimiento para desarrollar un esquema de clasificación y etiquetado de los datos de su organización.

## <a name="decide-if-you-are-using-labels-in-addition-to-sensitive-data-types"></a>Decidir si debe utilizar etiquetas además de tipos de datos confidenciales

Puede tomar uno de los dos métodos para la clasificación de información personal en Office 365. Puede usar cualquiera de estos para protección de RGPD. Si decide usar solo los tipos de información confidencial para clasificación, puede omitir el resto de este tema.

Elija una de las siguientes opciones.

### <a name="option-1-use-only-office-365-sensitive-information-types"></a>Opción 1: Usar solo los tipos de información confidencial de Office 365

-   Los tipos de información confidencial funcionan correctamente para identificar y proteger datos personales sujetos al RGPD y otros tipos de normas.

-   Estos son más fáciles de usar si su organización ya no tiene o no va a implementar un plan de gobierno de datos más amplio con etiquetas.

-   Estas funcionan con reglas DLP (como sucede con las etiquetas de Office).

-   En el futuro funcionarán con Cloud App Security para que pueda detectar información confidencial en otras aplicaciones SaaS.

### <a name="option-2-use-sensitive-information-types--office-labels"></a>Opción 2: Usar tipos de información confidencial y etiquetas de Office

-   Necesitará los tipos de información confidencial para aplicar automáticamente etiquetas a datos personales que están sujetos al RGPD, por lo que son un requisito previo.

-   Usar etiquetas de Office le permite incluir información personal que está sujeta al RGPD en un plan de gobierno de datos más amplio para su organización.

-   Más adelante, las etiquetas de Office convergerán con las etiquetas de Azure Information Protection en una clasificación y motor de etiquetado unificados.

## <a name="develop-a-label-schema-that-includes-personal-data"></a>Desarrollar un esquema de etiqueta que incluya datos personales

Antes de usar las capacidades técnicas para aplicar protección y etiquetas, primero trabaje en toda la organización para definir un esquema de clasificación. Es posible que su organización ya tenga un esquema de clasificación, lo que facilitará agregar datos personales. En este tema se incluye un esquema de clasificación de ejemplo. Puede usarlo como punto de partida, si es necesario.

### <a name="getting-started"></a>Introducción

Para empezar, decida el número y los nombres de las etiquetas que va a implementar. Hágalo sin preocuparse sobre la tecnología que debe usar y cómo se aplicarán las etiquetas. Aplique este esquema de forma universal en su organización, incluyendo a los datos que se encuentran en almacenamiento local y en otros servicios en la nube.

### <a name="recommendations"></a>Recomendaciones 

Al diseñar e implementar directivas, etiquetas y condiciones, tenga en cuenta estas recomendaciones:

-   Use el esquema de clasificación existente (si corresponde): muchas organizaciones ya usan algún tipo de clasificación de datos. Evalúe con cuidado el esquema de la etiqueta existente y, si es posible, úselo tal como está. El uso de etiquetas que son reconocibles para el usuario final impulsará la adopción.

-   Comience con directivas y etiquetas predeterminadas: todas las soluciones incluyen un conjunto de directivas y etiquetas predefinidas. Evalúelas detenidamente teniendo en cuenta los requisitos legales y empresariales y considere usarlas en lugar de crear nuevas.

-   Comience con poco: no hay prácticamente ningún límite en el número de etiquetas que se pueden crear. Sin embargo, grandes cantidades de etiquetas y etiquetas secundarias afectarán negativamente la adopción. Si tiene demasiadas opciones, es casi como si no tuviese ninguna opción en absoluto.

-   Use escenarios y casos de uso: identifique los casos de uso comunes dentro de la organización y use los escenarios que se derivan del RGPD para comprobar si la configuración de etiqueta y clasificación prevista funcionará en la práctica.

-   Plantéese cada solicitud para una nueva etiqueta, ¿cada escenario o caso de uso necesita una nueva etiqueta o podemos usar las que ya tenemos? Mantener el número de etiquetas al mínimo mejora la adopción.

-   Use subetiquetas para departamentos clave: algunos departamentos tendrán necesidades específicas que requerirán etiquetas específicas. Defina estas etiquetas como subetiquetas de una etiqueta existente y considere el uso de directivas de ámbito asignadas a grupos de usuarios en lugar de globalmente.

-   Considere usar directivas de ámbito: las directivas destinadas a subconjuntos de usuarios evitarán una "sobrecarga de etiquetas". Una directiva de ámbito permite asignar etiquetas específicas de roles o departamentos específica (sub-) solo a empleados que trabajan para ese departamento concreto.

-   Use nombres de etiqueta significativo: se recomienda no usar argot, estándares o acrónimos como nombres de etiqueta. Intente usar nombres adecuados para el usuario final para mejorar la adopción. En lugar de usar etiquetas como PII, PCI, HIPAA, LBI, MBI y HBI considere nombres como No laborable, General, Confidencial y Extremadamente confidencial.

### <a name="example-classification-schema"></a>Ejemplo de esquema de clasificación

<table>
<thead>
<tr class="header">
<th align="left"><strong>Nombre de etiqueta</strong></th>
<th align="left"><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Personal</td>
<td align="left">Datos no empresariales, únicamente para uso personal.</td>
</tr>
<tr class="even">
<td align="left">Público</td>
<td align="left">Datos profesionales preparados y aprobados específicamente para consumo público.</td>
</tr>
<tr class="odd">
<td align="left">Datos de cliente</td>
<td align="left">Datos profesionales que contienen información de identificación personal. Algunos ejemplos son números de tarjeta de crédito, números de cuentas bancarias y números de la Seguridad Social.</td>
</tr>
<tr class="even">
<td align="left">Datos de recursos humanos</td>
<td align="left">Datos de recursos humanos sobre los empleados de Contoso, como datos de número de empleado y salario.</td>
</tr>
<tr class="odd">
<td align="left">Confidencial</td>
<td align="left">Datos empresariales confidenciales que podrían causar daños a la empresa si se comparten con personas no autorizadas. Algunos ejemplos son: contratos, informes de seguridad, resúmenes de previsión y datos de la cuenta de ventas.</td>
</tr>
<tr class="even">
<td align="left">Extremadamente confidencial</td>
<td align="left">Datos empresariales extremadamente confidenciales que podrían provocar daños a la empresa si se comparten con personas no autorizadas. Algunos ejemplos son: información de empleados y clientes, contraseñas, código fuente e informes financieros previamente anunciados.</td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a>Definir un criterio de búsqueda y de taxonomía en todas las etiquetas

Tras desarrollar un esquema de clasificación de la organización, el siguiente paso es desarrollar criterios de búsqueda y de taxonomía para buscar datos. Para los datos personales, ya ha completado este trabajo mediante la identificación de tipos de información confidencial y también al personalizar o crear nuevos tipos de información confidencial en su entorno.

La siguiente tabla proporciona un esquema de ejemplo, taxonomía y criterios de búsqueda de una organización. Las etiquetas están ordenadas por nivel de confidencialidad de menos confidenciales a más confidenciales para asegurar que los datos que coincidan con varias condiciones de etiqueta se asignan la etiqueta adecuada.

Nota: El ejemplo de configuración se proporciona únicamente con fines ilustrativos y no está pensado como guía de implementación o referencia.

Lo más importante es asegurarse de que el trabajo que dedica para clasificar los datos personales para cumplimiento de RGPD se adaptan a los objetivos de toda la organización.

### <a name="example-schema-taxonomy-and-search-criteria"></a>Esquema de ejemplo, taxonomía y criterios de búsqueda

<table>
<thead>
<tr class="header">
<th align="left"><strong>Etiqueta</strong></th>
<th align="left"><strong>Taxonomía</strong></th>
<th align="left"><strong>Método</strong></th>
<th align="left"><strong>Sintaxis de búsqueda</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Personal</td>
<td align="left">Documentos etiquetados manualmente como personales por el usuario final.</td>
<td align="left">Manual</td>
<td align="left">Documentos etiquetados manualmente como personales por el usuario final.</td>
</tr>
<tr class="even">
<td align="left">Público</td>
<td align="left">Documentos que contienen la frase “Aprobado para publicación ##/####” (que no distingue mayúsculas de minúsculas) donde # representa cualquier dígito.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL: aprobado para publicación*</p>
<p>RegEx: (?i)(\bAprobado para publicación \d{2}\/\d{4}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Datos del cliente</td>
<td align="left">Tipos de información confidencial para datos de ciudadanos de la UE.</td>
<td align="left">Tipos de información confidencial</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Recursos humanos: datos de empleado</td>
<td align="left">Documentos que incluyan el id. de empleado (que distingue entre mayúsculas y minúsculas) en el formato CONTOSO-9##### donde # representa cualquier dígito.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL: CONTOSO-9*</p>
<p>RegEx: (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Recursos humanos: datos de sueldo</td>
<td align="left">Los documentos que incluyen la palabra clave Contoso (no distingue mayúsculas de minúsculas) y la palabra clave compensación o salario (no distingue mayúsculas de minúsculas)</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL: Contoso Y (Salario O Compensación)</p>
<p>RegEx: (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="even">
<td align="left">Confidencial</td>
<td align="left">Documentos que contienen la frase Confidencial de Contoso (no distingue mayúsculas de minúsculas).</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL: Confidencial de Contoso</p>
<p>RegEx: (?i)(\bConfidencial de Contoso\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Extremadamente confidencial</td>
<td align="left">Documentos que incluyen la frase Secreto de Contoso (distingue mayúsculas de minúsculas) o Secreto-C#### donde # representa cualquier dígito.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL: Secreto de Contoso O Secreto-C*</p>
<p>RegEx: (?i)(\bSecreto de Contoso\b)|(\bSecreto-C\d{4}\b)</p></td>
</tr>
</tbody>
</table>
