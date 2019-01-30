---
title: Ver la actividad de auditoría de custodia
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8219ae8a061f6d08dd37da5b7f2974dd86c68f04
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608344"
---
# <a name="viewing-custodian-audit-activity"></a>Visualización de la actividad de auditoría de custodia

¿Necesita encontrar si un usuario ve un documento específico o purga un elemento desde su buzón? Exhibición de documentos electrónicos avanzada (vista previa) ahora se integra con la herramienta de búsqueda de registro de auditoría existente en el centro de cumplimiento de seguridad &. Mediante esta experiencia incrustada, puede usar la herramienta de administración de custodia de exhibición de documentos electrónicos avanzada (vista previa) para facilitar la investigación por acceso fácilmente y busca la actividad custodia dentro de su caso.

## <a name="before-you-begin"></a>Antes de empezar

Se debe asignar el rol registros de auditoría con permiso de vista o los registros de auditoría en Exchange Online para buscar el registro de auditoría de Office 365. De forma predeterminada, estas funciones se asignan a la administración de cumplimiento y grupos de roles de administración de la organización en la página de permisos en el centro de administración de Exchange. Para conceder a un usuario la capacidad de buscar en el registro de auditoría de exhibición de documentos electrónicos avanzada (vista previa) con el nivel mínimo de privilegios, puede crear un grupo de roles personalizados en Exchange Online, agregar el rol registros de auditoría con permiso de vista o los registros de auditoría y, a continuación, agregar el usuario como un miembro de la nueva gr de rol luir. Para obtener más información, vea Administrar grupos de funciones en Exchange Online.

> [!IMPORTANT]
> Si asigna a un usuario de la función de registros de auditoría con permiso de vista o los registros de auditoría en la página de permisos en el centro de cumplimiento de seguridad &, no podrá buscar en el registro de auditoría de Office 365. Se debe asignar los permisos en Exchange Online. Esto es debido a que el cmdlet subyacente que sirven para buscar el registro de auditoría es un cmdlet de Exchange Online.

## <a name="step-1-create-an-advanced-ediscovery-preview-audit-log-search"></a>Paso 1: Crear una búsqueda de registro de auditoría de exhibición de documentos electrónicos avanzada (vista previa)

   1. Seleccione un caso existente de la **seguridad & centro de cumplimiento > avanzada exhibición de documentos electrónicos (vista previa)**.
   
   2. Vaya a la ficha de **custodia** y seleccione a custodia.
   
   3. Una vez que haya seleccionado una custodia, haga clic en **Ver la actividad de custodia** desde el panel de detalles.
   
   4. Configurar los criterios de búsqueda siguientes:
      
      r. **actividades** - haga clic en la lista desplegable para mostrar las actividades que puede buscar. Después de ejecutar la búsqueda, se muestran sólo los registros de auditoría de las actividades seleccionadas. Selección de **Mostrar los resultados de todas las actividades** mostrará los resultados para todas las actividades que cumplen los otros criterios de búsqueda.
      
      b. la **fecha de inicio y fecha de finalización** - seleccionar un rango de fecha y hora para mostrar los eventos que se produjeron dentro de ese período. De forma predeterminada, se seleccionan los últimos siete días. La fecha y hora se presentan en formato de hora Universal coordinada (UTC). El intervalo de fechas máximo que puede especificar es un año.
      
      c. **custodia** - haga clic en este cuadro y, a continuación, seleccione una custodia específica para mostrar búsqueda resultados para. Registros de auditoría para la actividad seleccionada realizado por los usuarios que seleccione en este cuadro se muestran en la lista de resultados.
    
    1. Haga clic en **Buscar** para ejecutar la búsqueda con los criterios de búsqueda. Se cargan los resultados de búsqueda y, después de unos momentos se muestran en los resultados en la página de búsqueda de actividades de custodia. 

## <a name="step-2-view-the-audit-log-search-results"></a>Paso 2: Ver los resultados de búsqueda de registro de auditoría

Los resultados de una búsqueda de registro de auditoría se muestran en los resultados en la página de registro de auditoría de custodia. Un máximo de 5.000 eventos (más recientes) se muestran en incrementos de 150 eventos. Para mostrar más eventos puede utilizar la barra de desplazamiento en el panel de resultados o puede presionar MAYÚS + fin para mostrar los eventos de 150 a continuación.

Los resultados contienen la siguiente información sobre cada evento devuelto por la búsqueda.
- **Fecha**: la fecha y hora (en formato UTC) cuando se produjo el evento.

- **Dirección IP**: la dirección IP del dispositivo que se usó cuando se registró la actividad. La dirección IP se muestra en formato de dirección de un IPv4 o IPv6.

- **Usuario**: el usuario (o la cuenta de servicio) que realizó la acción que desencadenó el evento.

- **Actividad**: la actividad realizada por el usuario. Este valor corresponde a las actividades que ha seleccionado en la lista desplegable de actividades. Para un evento desde el registro de auditoría de administración de Exchange, el valor de esta columna es un cmdlet de Exchange.

- **Elemento**: el objeto que se creó o modificó como resultado de la actividad correspondiente. Por ejemplo, el archivo que se pueden ver ni modificar o la cuenta de usuario que se ha actualizado. No todas las actividades tienen un valor en esta columna.

- **Ver todos los detalles**: detalles adicionales acerca de una actividad. Una vez más, no todas las actividades tendrá un valor.

## <a name="step-3-filter-the-search-results"></a>Paso 3: Filtrar los resultados de búsqueda

Además de ordenación, también puede filtrar los resultados de una búsqueda de registro de auditoría. Esto puede ayudar a filtrar rápidamente los resultados para un usuario específico o una actividad. 

Para filtrar los resultados:

 1. Crear y ejecutar una búsqueda de registro de auditoría.
  
2. Cuando se muestran los resultados, haga clic en **filtrar los resultados**.
 
3. Se muestran los cuadros de palabra clave en cada encabezado de columna.
  
4. Haga clic en uno de los cuadros en un encabezado de columna y escriba una palabra o frase, dependiendo de la columna que se va a filtrar. Los resultados se reajustar dinámicamente para mostrar los eventos que coinciden con el filtro.
  
5. Para borrar un filtro, haga clic en la **X** en el cuadro filtro o simplemente haga clic en **Ocultar filtrado**.

## <a name="export-the-search-results-to-a-file"></a>Exportar los resultados de búsqueda a un archivo

Puede exportar los resultados de una búsqueda de registro de auditoría a un archivo de (CSV) de valores separados por comas en el equipo local. Puede abrir este archivo en Microsoft Excel y usar características como la búsqueda, la ordenación, el filtrado y la división de una sola columna (que contiene las celdas de valor múltiple) en varias columnas.

1. Ejecutar una búsqueda de registro de auditoría y, a continuación, revise los criterios de búsqueda hasta que tenga los resultados deseados.
  
2. Haga clic en resultados de la exportación y seleccione una de las siguientes opciones:

    - **Guardar carga resultados:** Elija esta opción para exportar sólo las entradas que se muestran en **los resultados** en la página de **búsqueda de registro de auditoría de custodia** . El archivo CSV que se descarga contiene las mismas columnas (y datos) que se muestra en la página (fecha, usuario, actividad, elemento y obtener información detallada). Se incluye una columna adicional (titulada **más**) en el archivo CSV que contiene más información de la entrada de registro de auditoría. Debido a que se va a exportar los mismos resultados que se cargan (y visibles) en la página de búsqueda de registro de auditoría, se exportan un máximo de 5000 entradas.
        
    - **Descargar todos los resultados:** Elija esta opción para exportar todas las entradas del registro de auditoría de Office 365 que cumplen los criterios de búsqueda de. Para un amplio conjunto de resultados de la búsqueda, elija esta opción para descargar todas las entradas del registro de auditoría además de los resultados de 5.000 que se pueden mostrar en la página de búsqueda de **registro de auditoría de custodia** de. Esta opción descargará los datos sin procesar desde el registro de auditoría a un archivo CSV y contiene información adicional de la entrada de registro de auditoría en una columna denominada AuditData. Puede tardar más tiempo en descargar el archivo si elige esta opción de exportación debido a que el archivo puede ser mucho mayor que el que se descarga si elige la opción otra.
    
      > [!IMPORTANT]
      > Puede descargar un máximo de 50.000 entradas a un archivo CSV de una búsqueda de registro de auditoría único. Si se descargan 50.000 entradas en el archivo CSV, probablemente se puede suponer que hay más de 50.000 eventos que cumplen los criterios de búsqueda. Para exportar más de este límite, intente usar un intervalo de fechas para reducir el número de entradas de registro de auditoría. Debe ejecutar varias búsquedas con más pequeños intervalos de fechas para exportar las entradas de más de 50.000.
        

3. Después de seleccionar una opción de exportación, se muestra un mensaje en la parte inferior de la ventana que le pregunta si desea abrir el archivo CSV, guárdelo en la carpeta de descargas o guárdelo en una carpeta específica

[!NOTE] 
 Para obtener más información acerca de la visualización, filtrado o exportar los resultados de búsqueda de registro de auditoría, consulte:
   - Ver la lista de actividades auditadas 
   - Antes de comenzar: Los registros de auditoría unificadas
 