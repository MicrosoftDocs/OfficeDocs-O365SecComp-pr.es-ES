---
title: Información general sobre el administrador del plan de archivos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 'El administrador del plan de archivos proporciona funciones avanzadas de administración para las directivas de retención y proporciona una forma integrada para recorrer las etiquetas y la actividad de etiquetas de contenido para todo su ciclo de vida: incluyendo la creación, colaboración, declaración de registro, retención y por último disposición.'
ms.openlocfilehash: f104e5ea0046af1e8cdee39b1e7dc5f47524e707
ms.sourcegitcommit: d9f695650e26e4125b00b6281717b4d5b63fc401
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2019
ms.locfileid: "31824439"
---
# <a name="overview-of-file-plan-manager"></a>Información general sobre el administrador del plan de archivos

El administrador del plan de archivos proporciona funciones avanzadas de administración para las directivas de retención y proporciona una forma integrada para recorrer las etiquetas y la actividad de etiquetas de contenido para todo su ciclo de vida: incluyendo la creación, colaboración, declaración de registro, retención y por último disposición.

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
> Debido a los comentarios de los clientes, hemos eliminado la característica que crea las etiquetas de retención predeterminadas y la directiva de etiquetas mencionadas anteriormente. Solo verá esta directiva y estas etiquetas si usó el administrador del plan de archivos antes del 11 de abril de 2019.

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

### <a name="label-file-plan-descriptors-columns"></a>Columnas de descriptores del plan de archivos de las etiquetas

Ahora puede incluir más información en la configuración de las etiquetas de retención. Insertar descriptores del plan de archivos en las etiquetas mejorará la administración y la organización de su plan de archivos.

Para comenzar, el administrador del plan de archivos proporciona algunos valores de fábrica para: función o departamento, categoría, tipo de autoridad y aprovisionamiento o cita. Puede agregar nuevos archivos valores descriptores del plan de archivos al crear o editar una etiqueta de retención.

Esta es una vista del paso de descriptores del plan de archivos al crear o editar una etiqueta de retención.

![Descriptores del plan de archivos](media/file-plan-descriptors.png)

Esta es una vista de las columnas de descriptores del plan de archivos en la pestaña de etiquetas del administrador del plan de archivos.

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a>Exportar etiquetas del plan de archivos

Desde el administrador del plan de archivos, puede exportar los detalles de todas las etiquetas de retención a un archivo .csv para facilitar el revisiones de cumplimiento periódicas con partes interesadas del gobierno de datos de su organización.

Para exportar todas las etiquetas de retención, vaya al **Administrador del plan de archivos** \> **Acciones del plan de archivos** \> **Exportar etiquetas**.

![Opción para exportar el plan de archivos](media/file-plan-export-labels-option.png)

Se abrirá un archivo *.csv que contiene todas las etiquetas de retención existentes.

![Archivo CSV que muestra todas las etiquetas de retención](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a>Importar etiquetas en el plan de archivos

Desde el administrador del plan de archivos, puede importar en masa nuevas etiquetas así como modificar las etiquetas de retención existentes.

Para importar nuevas etiquetas de retención y realizar actualizaciones en etiquetas de retención existentes, vaya a **Administrador del plan de archivos** \> **Acciones del plan de archivos** \> **Importar etiquetas**.

![Opción para importar el plan de archivos](media/file-plan-import-labels-option.png)

![Opción para descargar una plantilla de plan de archivos en blanco](media/file-plan-blank-template-option.png)

Descargue una plantilla en blanco (o empiece desde una exportación de su plan actual del archivo).

![Plantilla en blanco del plan de archivos abierta en Excel](media/file-plan-blank-template.png)

Rellene la plantilla (próximamente publicaremos la información de referencia acerca de los valores válidos para las entradas).

![Plantilla del plan de archivos con información rellenada](media/file-plan-filled-out-template.png)

Cargue la plantilla rellenada y el administrador del plan de archivos validará las entradas y mostrará las estadísticas de importación.

![Estadísticas de importación del plan de archivos](media/file-plan-import-statistics.png)

Una vez completada la importación, vuelva al administrador del plan de archivos para asignar nuevas etiquetas a las directivas nuevas o existentes.

![Opción para publicar etiquetas](media/file-plan-publish-labels-option.png)

