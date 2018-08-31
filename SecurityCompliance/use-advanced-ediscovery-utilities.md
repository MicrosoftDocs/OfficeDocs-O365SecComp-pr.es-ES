---
title: Usar herramientas de eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Obtenga información acerca de las utilidades de Office 365 avanzada exhibición de documentos electrónicos, incluidos el registro de casos, borrar los datos, errores del proceso, modificar y análisis de transparencia de la relevancia.  '
ms.openlocfilehash: a68c98dd353971fcaa13fdc6b8e12bcf00c2faf0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535679"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a>Usar herramientas de eDiscovery avanzado de Office 365

> [!NOTE]
> Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Las utilidades que se muestran y están disponibles en la exhibición de documentos electrónicos avanzada dependen de los roles de usuario y contexto.
  
## <a name="case-log"></a>Registro de casos

El registro de caso proporciona una lista detallada de las actividades de procesamiento de aplicación, que se puede usar para realizar un seguimiento, solución de problemas y para hacer frente a errores y advertencias. El registro se puede genera y almacena localmente en el host o el servidor o envían directamente a una dirección de correo electrónico.
  
También se puede descargar el archivo de registro para el equipo del cliente. La opción de descarga del cliente puede habilitarse o deshabilitarse según la función de configuración y de usuario.
  
1. En la barra de menús, haga clic en el icono de **rueda dentada** . 
    
2. En el **configuración y utilidades \> utilidades** ficha, seleccione **registro de casos \> el programa de instalación**.
    
3. Seleccione el **nivel de registro** de la siguiente manera: 
    
  - **Estándar**: incluye los datos de registro básico. Esta opción suele ser necesario para la supervisión y debe usarse a menos que se recomienda en caso contrario.
    
  - **Mínimo**: usados para los casos muy grandes y devuelve sólo los datos más recientes.
    
4. Haga clic en **el registro de caso de ejecutar**. Se genera el registro y se muestra la ruta de acceso. En el panel de estado de la tarea, se muestra la información de progreso de tarea para la tarea actual y el apellido.
    
## <a name="clear-data"></a>Borrar datos

Si es necesario eliminar o volver a inicializar los datos de los casos, se debe inicializar la instancia de base de datos. La utilidad de borrar datos elimina especificadas todas las entradas de la base de datos de mayúsculas y minúsculas, archivos de texto, carpeta mayúsculas y acumulados resultados. La función sólo puede realizarse por un administrador.
  
> [!IMPORTANT]
> Esta acción no es reversible y borrará todos los relevancia de etiquetado y análisis realizado por el experto. Guardar una copia de seguridad de datos, si es necesario. Use esta opción con cuidado extremo. Eliminación de archivos clasificados y etiquetados puede afectar a los resultados de la relevancia. 
  
1. En la barra de menús, haga clic en el icono de **rueda dentada** . 
    
2. En el **configuración y utilidades \> utilidades** ficha, seleccione **Borrar los datos \> el programa de instalación**.
    
3. Seleccione una opción inicializar la información:
    
  - **La relevancia**: elimina todo el trabajo realizado en la relevancia, incluida la definición de cargas y la asociación de archivos a las cargas. Elimina todos los ejemplos y etiquetado.
    
  - **Cerca de duplicados y subprocesos de correo electrónico**: elimina toda la información de análisis de cerca de duplicados y subprocesos de correo electrónico.
    
  - **Los temas**: elimina los datos relacionados con los temas.
    
  - **Exportar historial**: elimina la información del historial de lotes de exportación.
    
4. Haga clic en **Borrar datos**. Los datos de escenario está desactivados. En el panel de **estado de la tarea** , se muestra la información de progreso de tarea para la tarea actual y el apellido. 
    
## <a name="modify-relevance"></a>Modificar la relevancia

En esta sección se describe cómo omitir o revertir un ejemplo de la relevancia.
  
1. En la barra de menús, haga clic en el icono de **rueda dentada** . 
    
2. En el **configuración y utilidades \> utilidades** , seleccione **Modificar relevancia**.
    
3. Seleccione una de las opciones: 
    
  - **Ejemplo de omisión actual - para el usuario actual**: Esto va a marcar, como **Omitir**, todos los archivos sin etiquetar en el ejemplo de mayúsculas y minúsculas open del usuario que ejecuta la utilidad. No se realizará el procesamiento de la relevancia en los archivos de etiquetado como **Omitir**.
    
  - **Ejemplo actual de omitir: todos los ejemplos de abiertos**: Esto va a marcar, como **Omitir**, todos los archivos sin etiquetar en todos los ejemplos de todos los usuarios. No se recomienda esta opción si los usuarios actualmente son etiquetas temáticas ejemplos.
    
  - **Deshacer la última muestra**: el último completado la relevancia de ejemplo de entrenamiento se revertirá, independientemente de que sea antes o después del proceso de "Calcular". No se pueden deshacer los cambios de un ejemplo de puesta al día.
    
4. Haga clic en **Ejecutar** para ejecutar. 
    
## <a name="transparency-analysis"></a>Análisis de transparencia

La utilidad de análisis de transparencia permite una vista detallada de los archivos y sus asignado puntuación de relevancia. El informe se puede usar como una comprobación de validez o para comparar la relevancia de un archivo definido por un revisor humano con respecto a la relevancia asignado por avanzada exhibición de documentos electrónicos. 
  
Además de las puntuaciones de la relevancia, exhibición de documentos electrónicos avanzada calcula y asigna pesos de palabra clave que tener en cuenta el contexto de la palabra clave. Se puede asignar la misma palabra en un archivo de pesos diferentes, según el contexto y la ubicación. Cada palabra clave se marca con una escala de aumento de la intensidad de color desde amarillo a naranja oscuro y debido a distintos tonos de gris. Codificación de color se usa para indicar visualmente la palabra s relativa contribución positivo o negativo a la puntuación de relevancia. 
  
En un escenario de casos de varios problemas, se puede generar un informe de análisis de transparencia para cada problema.
  
1. En la barra de menús, haga clic en el icono de **rueda dentada** . 
    
2. En el **configuración y utilidades \> utilidades** ficha, seleccione **análisis de transparencia \> el programa de instalación**.
    
3. En ** identificador de archivo **, escriba el identificador de archivo del archivo para procesar.
    
4. En la lista de **problemas** , seleccione el problema pertinente. 
    
5. Haga clic en **análisis de transparencia**. Una vez finalizada, se muestra el informe de análisis de transparencia para el archivo, que muestra cómo los colores de la palabra clave marcadas correlacionarse con la puntuación de relevancia general.
    
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Definir la configuración de mayúsculas y minúsculas e inquilino](define-case-and-tenant-settings-in-advanced-ediscovery.md)

