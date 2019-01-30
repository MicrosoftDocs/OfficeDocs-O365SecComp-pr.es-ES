---
title: Corrección de error al procesar los datos
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
ms.openlocfilehash: 82e6d44ded64d586611f429f9b3eebe4f47e9898
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608402"
---
# <a name="error-remediation-when-processing-data"></a>Corrección de error al procesar los datos

Corrección de error permite a los administradores de la exhibición de documentos electrónicos la posibilidad de corregir los problemas de datos que impiden que procesar correctamente el contenido de exhibición de documentos electrónicos avanzada (vista previa). Por ejemplo, los archivos que están protegidos con contraseña no se puede procesar ya que los archivos estén bloqueados o se cifran. Con corrección de error, los administradores de exhibición de documentos electrónicos pueden descargar archivos con estos errores, quitar la protección con contraseña y cargar los archivos corregidos con pruebas.

Use el siguiente flujo de trabajo para corregir los archivos con errores en los casos de exhibición de documentos electrónicos avanzada (vista previa).

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Creación de una sesión de corrección de error para corregir los archivos con errores de procesamiento

>[!NOTE]
>Si el en cualquier momento durante el procedimiento siguiente, se cierra el Asistente para la corrección de error, puede volver a la sesión de corrección de error desde la ficha **procesamiento** mediante la selección de **correcciones de Error** en el menú desplegable **vista** .

1. En la ficha **de procesamiento** en un caso de exhibición de documentos electrónicos avanzada (vista previa), seleccione **errores** en el menú desplegable **vista** .

2. Seleccione los errores que desea corregir haciendo clic en el botón de opción situado junto al tipo de error o el tipo de archivo.  En el siguiente ejemplo, nos estamos solucionar relativos a un archivo protegido con contraseña.

3. Haga clic en **+ nuevo corrección de error**.

    ![Corrección de error](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    La sesión de corrección de error comenzará, empezando por una fase de preparación, donde los archivos con errores que se mueven a una ubicación segura de Azure para ser descargado.

    ![Preparación de la corrección de error](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Una vez finalizada la preparación, haga clic en **siguiente: descargar archivos** para continuar con la descarga.

    ![Descargar archivos](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Para descargar los archivos, especifique la **ruta de acceso de destino para su descarga**; Esto es una ruta de acceso en el equipo local donde se debe descargar el archivo.  La ruta de acceso predeterminada, % USERPROFILE%\Downloads\errors, señala a la carpeta de descargas del usuario que ha iniciado sesión; Esto se puede cambiar según sea necesario.

    >[!NOTE]
    >Se recomienda usar una ruta de acceso de archivo local en lugar de una ruta de acceso de red remoto para un rendimiento óptimo.

    > [!NOTE]
    > Si no ha instalado AzCopy, se pueden instalar desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

6. Copie el comando predefinido, haga clic en **Copiar al Portapapeles**. Inicie un símbolo del sistema de windows, pegue el comando y, a continuación, presione **ENTRAR**.  

    Los archivos se descargarán.

    ![Preparación de la corrección de error](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > Si tiene problemas al ejecutar este comando, vea https://go.microsoft.com/fwlink/?linkid=2038117 sugerencias para resolver problemas.

7. Después de descargar los archivos, puede corregir con una herramienta apropiada. Para archivos protegidos con contraseña, hay un número de contraseñas de herramientas que puede utilizar. Si conoce las contraseñas de los archivos, puede abrirlos y quitar la protección con contraseña.
    > [!NOTE]
    > TI es importante que mantenga los nombres de archivo y la estructura de directorio de los archivos corregidos con pruebas permanecen.  Convenciones de nomenclatura de todos los que se usan en los archivos descargados y carpetas hacen posible asociar los archivos de remdiated al original.

8. Ahora, vuelva a la exhibición de documentos electrónicos avanzada (vista previa) y haga clic en **siguiente: cargar archivos**.  Se moverán con el paso siguiente donde puede cargar los archivos.

    ![Cargar archivos](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Especifique la ubicación de los archivos corregidos con pruebas en el cuadro de texto **ruta de acceso a la ubicación de archivos** , a continuación, haga clic en **Copiar a clibpboard**.

10. Pegue el comando en un símbolo del sistema de Windows y presione **ENTRAR** para cargar los archivos.

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Por último, volver a la exhibición de documentos electrónicos avanzada (vista previa) y haga clic en **siguiente: procesar archivos**.

12. Cuando el procesamiento se complete.  Puede devolver el conjunto de trabajo y ver el archivo corregidos con pruebas.

## <a name="what-happens-when-files-are-remediated"></a>¿Qué sucede cuando se modifiquen los archivos

Cuando se cargan archivos corregidos con pruebas, los metadatos originales se conservan con la excepción de los siguientes campos: 

- DocumentExtractedUrl
- ExtractedTextSize
- HasText
- IsErrorRemediate
- IsParentExtractedUrl
- ItemExtractedUrl
- LoadId
- ProcessingErrorMessage
- Procesamiento
- Text
- WordCount
- WorkingsetId

Para una definición de todos los campos de metadatos de documento de exhibición de documentos electrónicos avanzada (vista previa), vea [los campos de metadatos del documento](document-metadata-fields.md).