---
title: Preparar un archivo CSV para una lista de identificadores de búsqueda de contenido en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: Usar el archivo Results.csv o Items.csv no indizados desde una búsqueda de contenido existente para crear una búsqueda de la lista de identificador que devuelve los mensajes de correo electrónico específica. Las búsquedas de lista de identificador normalmente se utilizan para devolver los elementos del buzón parcialmente indizados.
ms.openlocfilehash: 28e4a66e5c9be1817881004b1e4b3a3e6d4bfdb9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536591"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a>Preparar un archivo CSV para una lista de identificadores de búsqueda de contenido en Office 365

Puede buscar mensajes de correo electrónico del buzón de correo específico y otros elementos de buzón de correo con una lista de identificadores de Exchange. Para crear una búsqueda en la lista ID (anteriormente denominada una búsqueda de destino), enviar un archivo (CSV) de valores separados por comas que identifica los elementos de buzón específico para buscar. Para este archivo CSV se usa el archivo **Results.csv** o el archivo **Items.csv no indizados** que se incluyen al exportar los resultados de búsqueda de contenido o exportar un informe de búsqueda de contenido desde y búsqueda de contenido existente. A continuación, edite uno de estos archivos para indicar los elementos específicos para buscar y, a continuación, crear una nueva búsqueda de la lista de identificador y enviar el archivo CSV. 
  
Aquí es una introducción rápida al proceso de creación de una búsqueda de la lista de ID.
  
1. Crear y ejecutar una búsqueda de contenido nuevo o guiada en la seguridad &amp; centro de cumplimiento.
    
2. Exportar los resultados de búsqueda de contenido o exportar el informe de búsqueda de contenido. Para obtener más información, vea:
    
    - [Exportar los resultados de búsqueda de contenido de la seguridad de Office 365 &amp; centro de cumplimiento](export-search-results.md)
    
    - [Exportar un informe de búsqueda de contenido](export-a-content-search-report.md)
    
3. Editar el archivo **Results.csv** o la **Items.csv sin indizar** e identificar los elementos del buzón específico que desea incluir en la búsqueda de la lista de ID. Vea las [instrucciones](#prepare-the-csv-file-for-an-id-list-search) para la preparación de un archivo CSV para una búsqueda de la lista de ID. 
    
4. Crear una nueva lista de identificador de búsqueda (vea las [instrucciones](#create-an-id-list-search)) y enviar el archivo CSV que ha preparado. La consulta de búsqueda que se crea sólo buscará los elementos seleccionados en el archivo CSV.
    
> [!NOTE]
> Solo se admiten las búsquedas de lista de identificador para los elementos del buzón. No se puede buscar para SharePoint y búsqueda de documentos de OneDrive en un identificador de lista. 
  
 **¿Por qué crear una búsqueda de identificador de lista?** Si no puede determinar que si un elemento responde a una solicitud de exhibición de documentos electrónicos en función de los metadatos en los archivos **Results.csv** o **Items.csv sin indizar** , puede usar una búsqueda de identificador de lista para buscar, obtener una vista previa y, a continuación, exportar ese elemento para determinar si tiene capacidad de respuesta para el caso de que esté investigar. Las búsquedas de lista de identificador normalmente se usan para buscar y devolver un conjunto específico de elementos sin indizar. 
  
## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Preparar el archivo CSV para una búsqueda de la lista de Id.

Después de exportar los resultados de búsqueda o del informe para una búsqueda de contenido, puede realizar los siguientes pasos para preparar el archivo CSV para una búsqueda de la lista de ID. Este archivo CSV identificará todos los elementos de la búsqueda de la lista de ID.
  
Tenga en cuenta que puede usar un archivo CSV de una búsqueda que incluye las cuentas de OneDrive y sitios de SharePoint, pero puede seleccionar *sólo* los elementos de buzón de correo para una búsqueda de la lista de ID. Si selecciona un documento en SharePoint o OneDrive, el archivo CSV se producirá un error validación al crear una búsqueda de la lista de ID. 
  
1. Abra el archivo **Results.csv** o **Items.csv no indizados** en Excel. 
    
2. Insertar una nueva columna y asígnele el nombre **seleccionado**. No importa dónde insertar la columna. Para mayor comodidad, considere la posibilidad de inserción a la izquierda de la primera columna.
    
3. En la columna **seleccionado** , escriba **Sí** en la celda que se corresponde con el elemento que se desea buscar. Repita este paso para cada elemento que se desea buscar. 
    
    > [!IMPORTANT]
    > Cuando abra el archivo CSV en Excel, se cambia el formato de datos para la columna de **ID de documento** a **General**. Esto da como resultado de mostrar el ID de documento para un elemento en la notación científica. Por ejemplo, el documento que se muestra el identificador de "481037338205" como "4.81037E + 11" se debe realizar los siguientes pasos para cambiar el formato de datos de la columna de **ID de documento** a **número** para restaurar el formato correcto para el ID de documento. Si no es así, se producirá un error en la búsqueda de la lista de identificador que usa el archivo CSV. 
  
4. Haga clic en toda la columna de **ID de documento** y seleccione el **Formato de celdas**.
    
5. En el cuadro **categoría** , haga clic en **número**.
    
6. Cambiar el número de posiciones decimales en **0**y, a continuación, haga clic en **Aceptar** para guardar los cambios. Tenga en cuenta que se cambian los valores en la columna de ID de documento a los números. 
    
    Este es un ejemplo de la un archivo CSV que está listo para ser enviado para una búsqueda de contenido de lista de ID.
    
    ![Ejemplo de un archivo CSV para una búsqueda de contenido dirigido](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)
  
7. Guarde el archivo CSV o use **Guardar como** para guardar el archivo con otro nombre de archivo. En ambos casos, asegúrese de guardar el archivo con el formato CSV. 
  
## <a name="create-an-id-list-search"></a>Crear una búsqueda de la lista de Id.

El siguiente paso es crear una nueva lista de identificadores de búsqueda de contenido y enviar el archivo CSV que ha preparado en el paso anterior.
  
> [!IMPORTANT]
> Debe crear una búsqueda de identificador de lista no más de 2 días después de exportar los resultados o el informe de una búsqueda de contenido. Si la búsqueda de resultados o del informe donde exportado desde hace más de 2 días, debe volver a exportar los resultados de búsqueda o el informe para generar archivos CSV actualizados. A continuación, puede preparar uno de los archivos CSV actualizados y usarla para crear una búsqueda de la lista de ID. 
  
1. En la seguridad &amp; centro de cumplimiento, vaya a **búsqueda &amp; investigación** \> **búsqueda de contenido**.
    
2. En la página de **búsqueda** , haga clic en la flecha junto a ![icono Agregar](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nueva búsqueda**y, a continuación, haga clic en **Buscar por identificador de lista**.
    
    ![Haga clic en Buscar por identificador de lista en la lista desplegable de búsqueda nueva](media/e65f9942-09b2-4127-865e-e64029a590df.png)
  
3. En la barra flotante **por identificador de lista de búsqueda** , asigne el nombre de la búsqueda (y, opcionalmente, describirlo) y, a continuación, haga clic en **Examinar** y seleccione el archivo CSV que ha preparado en el paso anterior. 
    
    Office 365 intenta validar el archivo CSV. Si la validación se realiza correctamente, se muestra un mensaje de error que pueden ayudar a solucionar los errores de validación. El archivo CSV debe validarse correctamente para crear una búsqueda de la lista de ID.
    
4. Después de la CSV archivo se valida correctamente, haga clic en **búsqueda** para crear la búsqueda de la lista de ID. 
    
    Este es un ejemplo de los resultados de búsqueda estimado y la consulta que se genera para una búsqueda de la lista de ID.
    
    ![Consulta de búsqueda para una búsqueda de contenido de destino en el panel de detalles](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)
  
    Tenga en cuenta que el número de elementos estimados que se muestran en las estadísticas de la búsqueda de identificador debe coincidir con el número de elementos que seleccionó en el archivo CSV.
    
5. Obtener una vista previa o exportar los elementos devueltos por la búsqueda de la lista de ID.
    
> [!NOTE]
> Si mueve un buzón de correo después de crear una búsqueda de la lista de Id., la consulta para la búsqueda no devuelve los elementos especificados. Esto es debido a que la propiedad **DocumentId** para los elementos del buzón se cambian cuando se mueve un buzón de correo. En la instancia de poco frecuente cuando se mueve un buzón de correo después de crear una búsqueda de identificador de lista, debe crear una nueva búsqueda de contenido (o actualizar los resultados de búsqueda para la búsqueda de contenido existente) y, a continuación, exportar la búsqueda de resultados o del informe para generar archivos CSV actualizados que se pueden usar  Para crear una nueva búsqueda de la lista de ID. 
