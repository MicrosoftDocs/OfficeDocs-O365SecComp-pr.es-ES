---
title: Información general sobre el administrador del plan de archivos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 'El administrador del plan de archivos proporciona funciones avanzadas de administración para las etiquetas de retención, directivas de etiquetas de retención y proporciona una forma integrada para recorrer las etiquetas y la actividad de etiquetas de contenido para todo su ciclo de vida: incluyendo la creación, colaboración, declaración de registro, retención y, por último, eliminación.'
ms.openlocfilehash: 38bfb1e6a6cde931804e518660ddf6c2b45205b0
ms.sourcegitcommit: f443de08971da2fe200a159b8efbed40effba125
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "36430017"
---
# <a name="overview-of-file-plan-manager"></a>Información general sobre el administrador del plan de archivos

El administrador del plan de archivos proporciona funciones avanzadas de administración para las etiquetas de retención, directivas de etiquetas de retención y proporciona una forma integrada para recorrer las etiquetas y la actividad de etiquetas de contenido para todo su ciclo de vida: incluyendo la creación, colaboración, declaración de registro, retención y, por último, eliminación.

![Página del plan de archivos](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a>Acceder al administrador del plan de archivos

Hay dos requisitos para obtener acceso al administrador del plan de archivos, son:
- Una suscripción de Office 365 Enterprise E5
- El usuario tiene asignado uno de los siguientes roles del Centro de seguridad y cumplimiento:
    - Administrador de retención
    - Administrador de retención con permiso de vista

## <a name="default-retention-labels-and-label-policy"></a>Etiquetas de retención predeterminadas y directiva de etiquetas

Si no hay etiquetas de retención en el Centro de seguridad y cumplimiento, la primera vez que elija **Plan de archivos** en la parte izquierda, se creará una directiva de etiquetas denominada **Directiva de publicación predeterminada de gobierno de datos**. 

Esta directiva de etiqueta contiene tres etiquetas de retención:

- **Procedimientos operativos**
- **General comercial**
- **Acuerdo de contrato**

Estas etiquetas de retención se configuran solo para retener el contenido, no eliminarlo. Esta directiva de etiquetas se publicará en toda la organización y puede deshabilitarse o quitarse. 

Puede determinar quién ha abierto el administrador del plan de archivos y desencadenado la experiencia de primera ejecución. Para ello, revise el registro de auditoría de las actividades **Directiva de retención creada** y **Configuración de retención para una directiva de retención creada**.

> [!NOTE]
> Debido a los comentarios de los clientes, hemos eliminado la característica que crea las etiquetas de retención predeterminadas y la directiva de etiquetas de retención mencionadas anteriormente. Solo verá las etiquetas de retención y la directiva de etiqueta de retención si abrió el administrador del plan de archivos antes del 11 de abril de 2019.

## <a name="navigating-your-file-plan"></a>Navegar por el plan de archivos

El administrador del plan de archivos facilita ver y revisar la configuración de todas las directivas y etiquetas de retención en una vista.

Tenga en cuenta que las etiquetas de retención creadas fuera del plan de archivos estarán disponibles en el plan de archivos y viceversa.

En la pestaña **Etiquetas del plan de archivos**, están disponibles la siguiente información adicional y funciones:

### <a name="label-settings-columns"></a>Columnas de configuración de etiqueta

- **En base a** identifica el tipo de desencadenador que iniciará el período de retención. Los valores válidos son:
    - Evento
    - Fecha de creación
    - Fecha de última modificación
    - Fecha de etiquetado
- **Registro** identifica si el elemento se convertirá en un registro declarado cuando se aplique la etiqueta. Los valores válidos son:
    - No
    - Sí
    - Sí (Normativa)
- **Retención** identifica el tipo de retención. Los valores válidos son:
    - Conservar
    - Conservar y eliminar
    - Eliminar
- **Disposición** identifica qué ocurrirá con el contenido al final del período de retención. Los valores válidos son:
    - null
    - Ninguna acción
    - Eliminación automática
    - Revisión necesaria (también conocido como revisión de disposición)

![Configuración de etiqueta en el plan de archivos](media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a>Columnas de descriptores del plan de archivos de las etiquetas de retención

Ahora puede incluir más información en la configuración de las etiquetas de retención. Insertar descriptores del plan de archivos en las etiquetas de retención mejorará la administración y la organización de su plan de archivos.

Para comenzar, el administrador del plan de archivos proporciona algunos valores de fábrica para: función o departamento, categoría, tipo de autoridad y aprovisionamiento o cita. Puede agregar nuevos archivos valores descriptores del plan de archivos al crear o editar una etiqueta de retención.

Esta es una vista del paso de descriptores del plan de archivos al crear o editar una etiqueta de retención.

![Descriptores del plan de archivos](media/file-plan-descriptors.png)

Esta es una vista de las columnas de descriptores del plan de archivos en la pestaña de etiquetas del administrador del plan de archivos.

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a>Exportar todas las etiquetas de retención existentes para analizar y/o realizar revisiones sin conexión

Desde el administrador del plan de archivos, puede exportar los detalles de todas las etiquetas de retención a un archivo .csv para facilitar el revisiones de cumplimiento periódicas con partes interesadas del gobierno de datos de su organización.

Para exportar todas las etiquetas de retención, vaya al **Administrador del plan de archivos** \> **Acciones del plan de archivos** \> **Exportar etiquetas**.

![Opción para exportar el plan de archivos](media/file-plan-export-labels-option.png)

Se abrirá un archivo *.csv que contiene todas las etiquetas de retención existentes.

![Archivo CSV que muestra todas las etiquetas de retención](media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a>Importar las etiquetas de retención en el plan de archivos

Desde el administrador del plan de archivos, puede importar en masa nuevas etiquetas de retención así como modificar las etiquetas de retención existentes.

Para importar nuevas etiquetas de retención y actualizar las etiquetas de retención existentes, vaya a **Administrador del plan de archivos** \> **Acciones del plan de archivos** \> **Importar etiquetas**.

![Opción para importar el plan de archivos](media/file-plan-import-labels-option.png)

![Opción para descargar una plantilla de plan de archivos en blanco](media/file-plan-blank-template-option.png)

Descargue una plantilla en blanco (o empiece desde una exportación de su plan actual del archivo).

![Plantilla en blanco del plan de archivos abierta en Excel](media/file-plan-blank-template.png)

Complete la plantilla. En esta tabla se muestran los valores válidos.

|**Property**|**Tipo**|**Valores válidos**|
|:-----|:-----|:-----|
|LabelName|Cadena|Si el valor contiene espacios, escríbalo entre comillas (").|
|Comment|Cadena|Si el valor contiene espacios, escríbalo entre comillas ("). |
|Notes|Cadena|Personalizado|
|IsRecordLabel|Cadena|$True: La etiqueta es una etiqueta de registro.</br>$False: La etiqueta no es una etiqueta de registro. Este es el valor predeterminado.|
|RetentionAction|Cadena|Delete</br>Keep</br>KeepAndDelete |
|RetentionDuration|Cadena|Esta propiedad especifica la cantidad de días que se va a conservar el contenido. Los valores válidos son:</br>Un número entero positivo.</br>El valor es ilimitado.|
|RetentionType|Cadena|Esta propiedad especifica si se calcula la duración de retención desde la fecha de creación de contenidos, desde la fecha etiquetado o desde la fecha de la última modificación. Los valores válidos son:</br>CreationAgeInDays</br>EventAgeInDays</br>ModificationAgeInDays</br>TaggedAgeInDays |
|ReviewerEmail|SmtpAddress[]|Esta propiedad especifica la dirección de correo electrónico del revisor para las acciones de retención Delete y KeepAndDelete. Puede especificar varias direcciones de correo electrónico separadas por comas.|
|ReferenceId|Cadena|Personalizado|
|DepartmentName|Cadena|Personalizado|
|Categoría|Cadena|Personalizado|
|SubCategory|Cadena|Personalizado|
|AuthorityType|Cadena|Personalizado|
|CitationName|Cadena|Personalizado|
|CitationUrl|Cadena|Personalizado|
|CitationJurisdiction|Cadena|Personalizado|
|Regulatory|Cadena|Personalizado|
|EventType|Cadena|Esta propiedad especifica la regla de retención que está asociada a la etiqueta. Puede usar cualquier valor que identifique de forma exclusiva la regla. Por ejemplo:</br>Nombre</br>Nombre completo (DN)</br>GUID </br>Puede usar el cmdlet [Get-RetentionComplianceRule](https://docs.microsoft.com/es-ES/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) para ver las reglas de retención disponibles.|

![Plantilla del plan de archivos con información rellenada](media/file-plan-filled-out-template.png)

Cargue la plantilla rellenada y el administrador del plan de archivos validará las entradas y mostrará las estadísticas de importación.

![Estadísticas de importación del plan de archivos](media/file-plan-import-statistics.png)

En caso de que se produzca un error de validación, la importación del plan de archivo seguirá validando todas las entradas del archivo de importación y mostrará todos los errores que hacen referencia a los números de línea/fila en el archivo de importación. Copie los resultados de error mostrados para que pueda volver fácilmente al archivo de importación y corregir los errores. 

Una vez completada la importación, vuelva al administrador del plan de archivos para asociar las nuevas etiquetas de retención a las directivas de etiquetas de retención nuevas o existentes.

![Opción para publicar etiquetas](media/file-plan-publish-labels-option.png)

