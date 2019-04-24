---
title: Ver actividad de auditoría de custodios
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: defc89f1d54238e62f947fd197e7a866380ee601
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241052"
---
# <a name="view-custodian-audit-activity"></a>Ver actividad de auditoría de custodios

¿Necesita saber si un usuario ha visto un documento específico o ha purgado un elemento de su buzón? La exhibición avanzada de documentos electrónicos (versión preliminar) ahora está integrada con la herramienta de búsqueda de registros de auditoría existente en el centro de seguridad & cumplimiento. Con esta experiencia insertada, puede usar la herramienta de administración de custodios de eDiscovery avanzado (preView) para facilitar la investigación mediante el fácil acceso y la búsqueda en la actividad de custodios en su caso.

## <a name="before-you-begin"></a>Antes de empezar

Debe tener asignado el rol registros de auditoría con permiso de vista o registros de auditoría en Exchange Online para buscar en el registro de auditoría de 365 de Office. De forma predeterminada, estos roles se asignan a los grupos de roles administración de cumplimiento y administración de la organización en la página permisos del centro de administración de Exchange. Para dar a un usuario la capacidad de buscar el registro de auditoría de eDiscovery avanzado (vista previa) con el nivel mínimo de privilegios, puede crear un grupo de roles personalizado en Exchange Online, agregar el rol registros de auditoría con permiso de vista o registros de auditoría y, a continuación, agregar el usuario como miembro del nuevo rol gr Oup. Para obtener más información, vea Administrar grupos de roles en Exchange Online.

> [!IMPORTANT]
> Si asigna a un usuario el rol registros de auditoría con permiso de vista o registros de auditoría en la página permisos del centro de seguridad & cumplimiento, estos no podrán buscar en el registro de auditoría de Office 365. Debe asignar los permisos en Exchange Online. Esto se debe a que el cmdlet subyacente usado para buscar en el registro de auditoría es un cmdlet de Exchange Online.

## <a name="step-1-create-an-advanced-ediscovery-preview-audit-log-search"></a>Paso 1: crear una búsqueda avanzada de registros de auditoría de eDiscovery (vista previa)

   1. Seleccione un caso existente en el **centro de seguridad _AMP_ cumplimiento de _GT_ Advanced eDiscovery (versión preliminar)**.
   
   2. Navegue a la **** pestaña custodios y seleccione un custodio.
   
   3. Una vez que haya seleccionado un custodio, haga clic en  ![Ver la actividad de custodio](../media/ViewCustodianActivity.PNG)  en el panel de detalles.
   
   4. Configure los siguientes criterios de búsqueda:
      
      a. **Actividades** : haga clic en la lista desplegable para mostrar las actividades que puede buscar. Después de ejecutar la búsqueda, solo se muestran los registros de auditoría de las actividades seleccionadas. Al seleccionar **Mostrar resultados para todas las actividades** , se mostrarán los resultados de todas las actividades que cumplan los otros criterios de búsqueda.

      ![Lista de actividades](../media/CustodianActivityAudit.PNG)
      
      b. Fecha de **Inicio y fecha** de finalización: Seleccione un intervalo de fechas y horas para mostrar los eventos que se produjeron dentro de ese período. Los últimos siete días están seleccionados de forma predeterminada. La fecha y la hora se presentan en formato de hora universal coordinada (UTC). El intervalo de fechas máximo que puede especificar es un año.
      
      c. **Custodios** : haga clic en este cuadro y seleccione un custodio específico para mostrar los resultados de la búsqueda. Los registros de auditoría para la actividad seleccionada realizada por los usuarios que seleccione en este cuadro se muestran en la lista de resultados.
      
   5. Haga clic en   ![Botón buscar](../media/SearchButton.PNG)  para ejecutar la búsqueda con los criterios de búsqueda. Los resultados de la búsqueda se cargan y, después de unos segundos, se muestran en resultados en la página de búsqueda de actividades de custodio. 

## <a name="step-2-view-the-audit-log-search-results"></a>Paso 2: ver los resultados de la búsqueda de registros de auditoría

Los resultados de una búsqueda de registro de auditoría se muestran en resultados en la página de registro de auditoría de custodio. Un máximo de 5.000 (más reciente) se muestran en incrementos de 150 eventos. Para mostrar más eventos, puede usar la barra de desplazamiento en el panel resultados o puede presionar Mayús + fin para mostrar los siguientes 150 eventos.

Los resultados contienen la siguiente información sobre cada evento devuelto por la búsqueda.
- **Fecha**: fecha y hora (en formato UTC) cuando se produjo el evento.

- **Dirección IP**: la dirección IP del dispositivo que se usó cuando se registró la actividad. La dirección IP se muestra en el formato de dirección IPv4 o IPv6.

- **Usuario**: el usuario (o cuenta de servicio) que llevó a cabo la acción que desencadenó el evento.

- **Activity**: la actividad realizada por el usuario. Este valor corresponde a las actividades que ha seleccionado en la lista desplegable de actividades. Para un evento del registro de auditoría de administración de Exchange, el valor de esta columna es un cmdlet de Exchange.

- **Elemento**: el objeto que se ha creado o modificado como resultado de la actividad correspondiente. Por ejemplo, el archivo que se vio o modificó, o la cuenta de usuario que se actualizó. No todas las actividades tienen un valor en esta columna.

- **Detalles**: detalles adicionales sobre una actividad. De nuevo, no todas las actividades tendrán un valor.

## <a name="step-3-filter-the-search-results"></a>Paso 3: filtrar los resultados de la búsqueda

Además de la ordenación, también puede filtrar los resultados de una búsqueda de registros de auditoría. Esto puede ayudarle a filtrar rápidamente los resultados de un usuario o actividad específicos. 

Para filtrar los resultados:

 1. Cree y ejecute una búsqueda de registros de auditoría.
  
2. Cuando se muestren los resultados, haga clic en **filtrar resultados**.
 
3. Los cuadros de palabras clave se muestran debajo de cada encabezado de columna.
  
4. Haga clic en uno de los cuadros debajo de un encabezado de columna y escriba una palabra o frase en función de la columna en la que esté filtrando. Los resultados se volverán a ajustar dinámicamente para mostrar los eventos que coinciden con el filtro.
  
5. Para borrar un filtro, haga clic en la **X** en el cuadro filtro o simplemente haga clic en **ocultar filtrado**.

## <a name="export-the-search-results-to-a-file"></a>Exportar los resultados de la búsqueda a un archivo

Puede exportar los resultados de una búsqueda de registro de auditoría a un archivo de valores separados por comas (CSV) en el equipo local. Puede abrir este archivo en Microsoft Excel y usar características como buscar, ordenar, filtrar y dividir una sola columna (que contiene celdas de varios valores) en varias columnas.

1. Ejecute una búsqueda de registro de auditoría y, a continuación, revise los criterios de búsqueda hasta que tenga los resultados deseados.
  
2. Haga clic en exportar resultados y seleccione una de las siguientes opciones:

    - **Guardar los resultados cargados:** Elija esta opción para exportar solo las entradas que se muestran en **resultados** en la página de **búsqueda de registro de auditoría** de custodios. El archivo CSV que se descarga contiene las mismas columnas (y datos) que se muestran en la página (fecha, usuario, actividad, elemento y detalles). Una columna adicional (que se titula **más**) se incluye en el archivo CSV que contiene más información de la entrada del registro de auditoría. Como está exportando los mismos resultados que se cargan (y visibles) en la página de búsqueda de registros de auditoría, se exporta un máximo de 5.000 entradas.
        
    - **Descargar todos los resultados:** Elija esta opción para exportar todas las entradas del registro de auditoría de Office 365 que cumplan los criterios de búsqueda. Para un conjunto grande de resultados de búsqueda, elija esta opción para descargar todas las entradas del registro de auditoría, además de los resultados de 5.000 que se pueden mostrar en la página de búsqueda del **registro de auditoría de custodio** . Con esta opción se descargan los datos sin procesar del registro de auditoría en un archivo CSV y se incluye información adicional de la entrada del registro de auditoría en una columna denominada AuditData. La descarga del archivo puede tardar más tiempo si elige esta opción de exportación, ya que es posible que el archivo sea mucho mayor que el que se ha descargado si elige la otra opción.
    
      > [!IMPORTANT]
      > Puede descargar un máximo de 50.000 entradas en un archivo CSV desde una sola búsqueda de registro de auditoría. Si se descargan 50.000 entradas en el archivo CSV, probablemente se da por hecho que hay más de 50.000 eventos que cumplen los criterios de búsqueda. Para exportar más de este límite, pruebe a usar un intervalo de fechas para reducir el número de entradas del registro de auditoría. Es posible que deba ejecutar varias búsquedas con intervalos de fecha más pequeños para exportar más de 50.000 entradas.
        

3. Después de seleccionar una opción de exportación, se muestra un mensaje en la parte inferior de la ventana donde se le pide que abra el archivo CSV, que lo guarde en la carpeta downloads o lo guarde en una carpeta específica

Para obtener más información acerca de cómo ver, filtrar o exportar los resultados de la búsqueda de registros de auditoría, vea [Buscar en el registro de auditoría en el centro de seguridad _AMP_ cumplimiento de Office 365](../search-the-audit-log-in-security-and-compliance.md).
