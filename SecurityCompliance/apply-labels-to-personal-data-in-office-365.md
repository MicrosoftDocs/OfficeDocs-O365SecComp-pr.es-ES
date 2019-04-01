---
title: Aplicar etiquetas a datos personales en Office 365
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
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
description: Aprenda a usar etiquetas de Office como parte de su plan de protección RGPD.
ms.openlocfilehash: 32f94e02dac81abaef46ef5495701e5037ff8c6b
ms.sourcegitcommit: 54d58da1777eb83adb82826d1bb1adb94903c8e1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955203"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a>Aplicar etiquetas a datos personales en Office 365

 Use este tema si utiliza las etiquetas de clasificación como parte de su plan de protección de RGPD. 

Si utiliza etiquetas para la protección de datos personales de Office 365, Microsoft recomienda que empiece con [etiquetas de retención](labels.md). Con las etiquetas de retención, puede:
- Usar el Gobierno de datos avanzado para aplicar automáticamente etiquetas con tipos de información confidencial u otros criterios.
- Usar etiquetas de retención con la prevención de pérdida de datos para aplicar la protección. 
- Usar etiquetas con eDiscovery y Búsqueda de contenido. 

Cloud App Security actualmente no admite etiquetas de retención, pero puede usar tipos de información confidencial de Office 365 con Cloud App Security para supervisar los datos personales que residen en otras aplicaciones SaaS.

Actualmente se recomiendan las [etiquetas de confidencialidad](sensitivity-labels.md) para la aplicación de etiquetas a archivos locales y en otros proveedores y servicios en la nube. Estas también se recomiendan para los archivos de Office 365 que requieren el cifrado de Azure Information Protection (AIP) para la protección de datos, como archivos de secreto comercial.

En este momento, no se recomienda usar Azure Information Protection para aplicar el cifrado a archivos en Office 365 con datos que están sujetos al RGPD. Los servicios de Office 365 actualmente no pueden leer archivos cifrados AIP. Por ello, el servicio no puede encontrar datos confidenciales en dichos archivos.

Pueden aplicarse etiquetas de confidencialidad a correo en Exchange Online que funcionan con la prevención de pérdida de datos de Office 365. 

![Etiquetas de Office 365 y de Azure Information Protection](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)


En la ilustración:

-   Use las etiquetas de retención para los datos personales y archivos secretos empresariales muy regulados en SharePoint Online y OneDrive para la Empresa.
-   Los tipos de información confidencial de Office 365 pueden usarse en Office 365 y con Cloud App Security para supervisar datos personales que residen en otras aplicaciones SaaS.
-   Use las etiquetas de confidencialidad para archivos secretos empresariales muy regulados, correo electrónico de Exchange Online, archivos en otros servicios SaaS, archivos en centros de datos locales y archivos de otros proveedores en la nube.


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a>Uso de etiquetas de retención y tipos de información confidencial en Microsoft 365 para la protección de información

En la ilustración siguiente se muestra cómo pueden aprovecharse las etiquetas de retención y los tipos de información confidencial en las directivas de etiquetas, de prevención de pérdida de datos y de Cloud App Security.

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
<td align="left">Etiquetas de retención. Ejemplos: personal, público, datos de clientes, datos de recursos humanos, confidencial, extremadamente confidencial</td>
<td align="left"><p>Aplicar automáticamente esta etiqueta...</p>
<p>Datos de cliente</p>
<p>...a documentos que coincidan con estos tipos de información confidencial...</p>
<p>&lt;lista de ejemplos de información confidencial disponibles&gt;</p></td>
<td align="left"><p>Aplicar esta protección...</p>
<p>&lt;definir la protección&gt;</p>
<p>...a documentos con esta etiqueta...</p>
<p>Datos de cliente</p></td>
<td align="left"><p>Enviar alerta cuando los archivos con estos atributos...</p>
<p>Elija uno o varios atributos: atributo PII predefinido, el tipo de información confidencial de Office 365, la etiqueta de confidencialidad (AIP), expresión personalizada</p>
<p>. . . en cualquier aplicación de SaaS autorizada se comparten fuera de la organización</p><p>Nota: las etiquetas de retención actualmente no se admiten en Cloud App Security.</td>
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
<td align="left"></td>
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

Crear etiquetas y directivas en el centro de seguridad o el centro de cumplimiento.

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
<td align="left"><p>Los miembros de su equipo de cumplimiento que vayan a crear etiquetas necesitan permisos para usar el centro de seguridad y/o el centro de cumplimiento. Vaya a los permisos en el centro de seguridad o el centro de cumplimiento y modifique los miembros del grupo Administrador de cumplimiento.</p>
<p>Vea <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Proporcionar acceso a los usuarios al centro de seguridad y/o el centro de cumplimiento</a>.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Crear etiquetas de retención.</p></td>
<td align="left">Vaya a Clasificaciones en el centro de seguridad o el centro de cumplimiento, elija Etiquetas de retención y cree las etiquetas para su entorno.</td>
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
