---
title: Corrección de errores al procesar datos para una investigación
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f8e253a3d38f0f4846485e3b88ea09914d9978ce
ms.sourcegitcommit: 6eb51931242d07abde2e37f1bd57d13bc724f0de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "34547955"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a>Corrección de errores al procesar datos para una investigación

La corrección de errores permite que los investigadores puedan rectificar los problemas de datos que impiden que las investigaciones de datos (vista previa) procesen correctamente el contenido. Por ejemplo, no se pueden procesar archivos protegidos con contraseña, ya que los archivos están bloqueados o cifrados. Mediante la corrección de errores, los investigadores pueden descargar archivos con estos errores, quitar la protección con contraseña y cargar los archivos corregidos.

Use el siguiente flujo de trabajo para corregir los archivos con errores en los casos de investigación de datos (vista previa).

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Crear una sesión de corrección de errores para corregir los archivos con errores de procesamiento

>[!NOTE]
>Si el Asistente para la corrección de errores se cierra en cualquier momento durante el siguiente procedimiento, puede volver a la sesión de corrección de errores desde **** la pestaña procesando; para ello, seleccione **corrección de errores** en el menú desplegable **Ver** .

1. En la pestaña **procesamiento** en un caso de investigación de datos (vista previa), seleccione **errores** en el menú desplegable **vista** .

2. Seleccione los errores que desea corregir haciendo clic en el botón de opción situado junto a tipo de error o tipo de archivo.  En el siguiente ejemplo, estamos corrigiendo un archivo protegido con contraseña.

3. Haga clic en **+ nuevo error de corrección**.

    ![Corrección de errores](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    La sesión de corrección de errores comenzará, a partir de una fase de preparación, en la que los archivos con errores se copian en una ubicación segura de Azure para que se puedan descargar.

    ![Preparación de la corrección de errores](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Una vez completada la preparación, haga clic en **siguiente: descargar archivos** para continuar con la descarga.

    ![Descargar archivos](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Para descargar archivos, especifique la **ruta de destino de la descarga**; se trata de una ruta de acceso en el equipo local en la que se debe descargar el archivo.  La ruta de acceso predeterminada,%USERPROFILE%\Downloads\errors, apunta a la carpeta descargas del usuario que ha iniciado sesión; Esto se puede cambiar si es necesario.

    >[!NOTE]
    >Le recomendamos que use una ruta de acceso de archivo local en lugar de una ruta de acceso de red remota para obtener un rendimiento óptimo.

    > [!NOTE]
    > Si no ha instalado AzCopy, puede instalarlo desde aquí:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

6. Copie el comando predefinido; para ello, haga clic en **copiar al**portapapeles. Inicie un símbolo del sistema de Windows, pegue el comando y, a continuación, presione **entrar**.  

    Los archivos se descargarán.

    ![Preparación de la corrección de errores](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > Si tiene problemas al ejecutar este comando, consulte [solucionar problemas de AzCopy en EDiscovery avanzado](../compliance20/troubleshooting-azcopy.md).

7. Después de descargar los archivos, puede corregirlos con una herramienta adecuada. Para los archivos protegidos con contraseña, hay varias herramientas de averiguación de contraseñas que puede usar. Si conoce las contraseñas de los archivos, puede abrirlas y quitar la protección con contraseña.
    
   > [!NOTE]
    > Es importante que mantenga intactos la estructura de directorios y los nombres de archivo de los archivos corregidos.  Todas las convenciones de nomenclatura usadas en los archivos y carpetas descargados hacen posible asociar los archivos de remdiated con el original.

8. Ahora, vuelva a investigaciones de datos (versión preliminar) y haga clic en **siguiente: cargar archivos**.  Se desplazará al siguiente paso en el que ahora puede cargar los archivos.

    ![Cargar archivos](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Especifique la ubicación de los archivos corregidos en el cuadro **de texto Ruta de acceso a la ubicación del archivo** y, a continuación, haga clic en **copiar al**portapapeles.

10. Pegue el comando en un símbolo del sistema de Windows y presione **entrar** para cargar los archivos.

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Por último, vuelva a investigaciones de datos (versión preliminar) y haga clic en **siguiente: procesar archivos**.

12. Cuando se complete el procesamiento.  Puede volver al conjunto de trabajo y ver el archivo corregido.

## <a name="what-happens-when-files-are-remediated"></a>Qué sucede cuando se corrigen los archivos

Cuando se cargan los archivos corregidos, se conservan los metadatos originales, con la excepción de los siguientes campos: 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- Texto
- WordCount
- WorkingsetId

Para obtener una definición de todos los campos de metadatos de documentos en las investigaciones de datos (versión preliminar), vea [Document Metadata Fields](document-metadata-fields.md).