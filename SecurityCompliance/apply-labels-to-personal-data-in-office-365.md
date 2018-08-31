---
title: Aplicar etiquetas a datos personales en Office 365
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
ms.service: o365-solutions
localization_priority: Priority
ms.custom: ''
ms.assetid: ''
search.appverid:
- MET150
description: Aprenda a usar etiquetas de Office como parte de su plan de protección RGPD.
ms.openlocfilehash: 35fc3be6f2c98d6b7f6c4d6f6150eeef6d552437
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272345"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a>Aplicar etiquetas a datos personales en Office 365

 Este tema puede serle útil si utiliza etiquetas de Office como parte de su plan de protección RGPD. Actualmente puede crear etiquetas en el Centro de seguridad y cumplimiento de Office 365 y en Azure Information Protection. Con el tiempo estas tecnologías se unirán en una experiencia de etiquetado y clasificación unificada y podrá hacer mucho más.

Si utiliza etiquetas para la protección de datos personales de Office 365, Microsoft le recomienda que empiece con las etiquetas de Office. Puede usar Gobierno de datos avanzado para aplicar automáticamente etiquetas basándose en tipos de información confidencial u otros criterios. También puede usar etiquetas de Office con la prevención de pérdida de datos para aplicar protección, y usarlas con eDiscovery y Búsqueda de contenido. Pronto podrá usar las etiquetas y tipos de información confidencial con Cloud App Security para supervisar datos personales en otras aplicaciones SaaS.

Las etiquetas de Azure Information Protection actualmente se recomiendan para aplicar etiquetas a archivos locales, y en otros proveedores y servicios en la nube. También se recomiendan para los archivos de Office 365 que requieren el cifrado de Azure Rights Management (Azure RMS) para proteger datos, como archivos de secreto empresarial.

En este momento, no se recomienda usar Azure Information Protection para aplicar el cifrado de Azure RMS a archivos de Office 365 con datos que están sujetos al RGPD. Los servicios de Office 365 actualmente no pueden leer archivos cifrados de RMS. Por lo tanto, el servicio no puede encontrar los datos confidenciales en estos archivos.

Pueden aplicarse las etiquetas de Azure Information Protection al correo en Exchange Online y estas son compatibles con la prevención de pérdida de datos de Office 365. Próximamente, la clasificación unificada y el motor de etiquetas permitirán usar las mismas etiquetas para correo electrónico y archivos, incluyendo etiquetar y proteger el correo electrónico en tránsito automáticamente.

![Etiquetas de Office 365 y de Azure Information Protection](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)

En la ilustración:

-   Use las etiquetas de Office 365 para los datos personales y archivos secretos empresariales muy regulados en SharePoint Online y OneDrive para la Empresa.

-   Use las etiquetas de Azure Information Protection (AIP) para archivos secretos empresariales muy regulados, correo electrónico de Exchange Online, archivos en otros servicios SaaS, archivos en centros de datos locales y archivos de otros proveedores en la nube.

-   Próximamente: ambos tipos de etiquetas convergerán en una experiencia de clasificación y etiquetado unificada.

## <a name="use-office-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a>Uso de etiquetas y tipos de información confidencial de Office en Microsoft 365 para la protección de información

En la ilustración siguiente se muestra cómo pueden aprovecharse las etiquetas y los tipos de información confidencial de Office en las directivas de etiquetas, de prevención de pérdida de datos y de Cloud App Security.

![Etiquetas y tipos de información confidencial de Office](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

Por motivos de accesibilidad, en la tabla siguiente se incluyen los mismos ejemplos que en la ilustración.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Elementos de clasificación</strong></th>
<th align="left"><strong>Directivas de etiqueta: 2 ejemplos</strong></th>
<th align="left"><strong>Directivas de prevención de pérdida de datos: 2 ejemplos</strong></th>
<th align="left"><strong>Directivas de Cloud App Security para todas las aplicaciones SaaS: 1 ejemplo</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Etiquetas de Office. Ejemplos: personal, público, datos de clientes, datos de recursos humanos, confidencial, extremadamente confidencial</td>
<td align="left"><p>Aplicar automáticamente esta etiqueta...</p>
<p>Datos de cliente</p>
<p>...a documentos que coincidan con estos tipos de información confidencial...</p>
<p>&lt;lista de ejemplos de información confidencial disponibles&gt;</p></td>
<td align="left"><p>Aplicar esta protección...</p>
<p>&lt;definir la protección&gt;</p>
<p>...a documentos con esta etiqueta...</p>
<p>Datos de cliente</p></td>
<td align="left"><p>Enviar alerta cuando los archivos con estos atributos...</p>
<p>&lt;atributo DCP predefinido o expresión personalizada&gt;</p>
<p>...en cualquier aplicación de SaaS autorizada que se comparte fuera de la organización</p></td>
</tr>
<tr class="even">
<td align="left">Tipos de información confidencial. Ejemplos: número nacional de Bélgica, número de tarjeta de crédito, número de carnet de identidad de Croacia, documento de identidad nacional de Finlandia</td>
<td align="left"><p>Publicar estas etiquetas para los usuarios para aplicar manualmente...</p>
<p>&lt;seleccionar etiquetas&gt;</p>
<p>...a estas ubicaciones...</p>
<p>&lt;todas las ubicaciones o elegir ubicaciones específicas&gt;</p></td>
<td align="left"><p>Aplicar esta protección...</p>
<p>&lt;definir la protección&gt;</p>
<p>...a documentos que coincidan con estos tipos de información confidencial&gt;</p></td>
<td align="left">Nota: Los atributos que estarán disponibles próximamente para Cloud App Security incluyen los tipos de información confidencial y las etiquetas unificadas de Office 365 en Office 365 y Azure Information Protection.</td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a>Asignar prioridades a las directivas de etiqueta de aplicación automática

Para los datos personales que están sujetos a RGPD, Microsoft recomienda aplicar etiquetas automáticamente mediante tipos de información confidencial que gestione en su entorno. Es importante que las directivas de aplicación automática de etiquetas estén bien diseñadas y probadas para asegurar que se produce el comportamiento esperado.

El orden en que las directivas de aplicación automática se crean y si los usuarios también aplican estas etiquetas afectan al resultado. Por lo tanto, es importante planear cuidadosamente la distribución. Esto es lo que necesita saber.

### <a name="one-label-at-a-time"></a>Una etiqueta de cada vez

Solo puede aplicar una etiqueta a un documento.

### <a name="older-auto-apply-policies-win"></a>Las directivas de aplicación automática antiguas tienen prioridad

Si hay varias reglas que asignan una etiqueta de aplicación automática y el contenido cumple las condiciones de varias reglas, se asigna la etiqueta de la regla más antigua. Por este motivo, es importante planear minuciosamente las directivas de etiqueta antes de configurarlas. Si una organización necesita un cambio en la prioridad de las directivas de etiqueta, tendrá que eliminarlas y volver a crearlas.

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a>Las etiquetas de usuario aplicadas manualmente tienen prioridad sobre las etiquetas aplicadas automáticamente

Las etiquetas de usuario aplicadas manualmente tienen prioridad sobre las etiquetas aplicadas automáticamente. Las directivas de aplicación automática no pueden reemplazar una etiqueta que ya ha aplicado un usuario. Los usuarios pueden reemplazar las etiquetas que se aplican automáticamente.

### <a name="auto-assigned-labels-can-be-updated"></a>Las etiquetas asignadas automáticamente pueden actualizarse

Las directivas de etiqueta más recientes o las actualizaciones de directivas existentes pueden actualizar etiquetas asignadas automáticamente.

Asegúrese de que su plan para implementar etiquetas incluye:

-   Dar prioridad al orden en que se crean las directivas de aplicación automática.

-   Permita el tiempo suficiente para que las etiquetas se apliquen automáticamente antes de implementarlas para que los usuarios las apliquen manualmente. Pueden ser necesarios hasta siete días para que las etiquetas se apliquen a todo el contenido que coincida con las condiciones.

### <a name="example-priority-for-creating-the-auto-apply-policies"></a>Prioridad de ejemplo para crear directivas de aplicación automática

<table>
<thead>
<tr class="header">
<th align="left"><strong>Etiquetas</strong></th>
<th align="left"><strong>Orden de prioridad para crear directivas de aplicación automática</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Recursos humanos: datos de empleado</td>
<td align="left">1</td>
</tr>
<tr class="even">
<td align="left">Datos de cliente</td>
<td align="left">2</td>
</tr>
<tr class="odd">
<td align="left">Extremadamente confidencial</td>
<td align="left">3</td>
</tr>
<tr class="even">
<td align="left">Recursos humanos: datos de sueldo</td>
<td align="left">4</td>
</tr>
<tr class="odd">
<td align="left">Confidencial</td>
<td align="left">5</td>
</tr>
<tr class="even">
<td align="left">Público</td>
<td align="left">6</td>
</tr>
<tr class="odd">
<td align="left">Personal</td>
<td align="left">Directiva que no es de aplicación automática</td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a>Crear etiquetas y aplicar directivas de etiqueta automáticamente

Cree etiquetas y directivas en el Centro de seguridad y cumplimiento.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Paso</strong></th>
<th align="left"><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Conceda permisos a los miembros de su equipo de cumplimiento.</p></td>
<td align="left"><p>Los miembros de su equipo de cumplimiento que vayan a crear etiquetas necesitan permisos para usar el Centro de seguridad y cumplimiento. Vaya a los permisos en el Centro de seguridad y cumplimiento y modifique los miembros del grupo Administrador de cumplimiento.</p>
<p>Consulte <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento de Office 365</a>.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Cree etiquetas de Office.</p></td>
<td align="left">Vaya a Clasificaciones en el Centro de seguridad y cumplimiento, elija Etiquetas y cree las etiquetas en su entorno.</td>
</tr>
<tr class="odd">
<td align="left"><p>Cree directivas de aplicación automática para etiquetas.</p></td>
<td align="left">Vaya a Clasificación en el Centro de seguridad y cumplimiento, elija Directivas de etiqueta y cree las directivas de aplicación automática de etiquetas. Asegúrese de crear estas directivas en el orden de la prioridad.</td>
</tr>
</tbody>
</table>

La siguiente ilustración muestra cómo crear una etiqueta de aplicación automática para la etiqueta Datos de cliente.

![Crear y aplicar una etiqueta de datos de cliente](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

En la ilustración:

-   Se crea la etiqueta "Datos de cliente".

-   Se listan los tipos de información confidencial deseados para RGPD: número nacional de Bélgica, número de tarjeta de crédito, número de carnet de identidad de Croacia, documento de identidad nacional de Finlandia

-   Crear una directiva de aplicación automática asigna la etiqueta "Datos de cliente" a cualquier archivo que contenga uno de los tipos de información confidencial que agregue a la directiva.
