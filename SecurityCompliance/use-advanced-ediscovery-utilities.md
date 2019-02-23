---
title: Usar herramientas de eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Obtenga información sobre las utilidades de la exhibición avanzada de documentos electrónicos de Office 365, incluidos el registro de casos, datos claros, errores de proceso, modificación de relevancia y análisis de transparencia.  '
ms.openlocfilehash: bd100883804b300e77abcc8a2224cf1a59b53475
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218210"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a>Usar herramientas de eDiscovery avanzado de Office 365

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Las utilidades que se muestran y están disponibles en eDiscovery avanzado dependen de roles de usuario y contexto.
  
## <a name="case-log"></a>Registro de casos

El registro de casos proporciona una lista detallada de las actividades de procesamiento de aplicaciones, que se pueden usar para realizar un seguimiento, solucionar problemas y resolver errores y advertencias. El registro puede generarse y almacenarse de forma local en el host o servidor, o bien enviarse directamente a una dirección de correo electrónico.
  
El archivo de registro también se puede descargar en el equipo del cliente. La opción de descarga del cliente puede estar habilitada o deshabilitada según la configuración y el rol de usuario.
  
1. En la barra de menús, haga clic en el icono de **cogwheel** . 
    
2. En la pestaña **utilidades de \> configuración y utilidades** , seleccione **configuración \> del registro de casos**.
    
3. Seleccione el **nivel de registro** de la siguiente manera: 
    
  - **Standard**: incluye los datos de registro básicos. Esta opción suele ser necesaria para la supervisión y se debe usar a menos que se recomiende lo contrario.
    
  - **Minimal**: se usa para casos muy grandes y solo devuelve los datos más recientes.
    
4. Haga clic en **Ejecutar registro de casos**. Se genera el registro y se muestra la ruta de acceso. La información de progreso de la tarea para la tarea actual y la última se muestra en el panel estado de tarea.
    
## <a name="clear-data"></a>Borrar datos

Si es necesario eliminar o reinicializar los datos de las mayúsculas y minúsculas, se debe inicializar la instancia de base de datos. La utilidad Clear Data elimina todas las entradas especificadas de la base de datos de casos, los archivos de texto, la carpeta Case y los resultados acumulados. La función solo puede ser realizada por un administrador.
  
> [!IMPORTANT]
> Esta acción no es reversible y eliminará todo el etiquetado y el análisis de relevancia que realiza el experto. Guarde una copia de seguridad de los datos, si es necesario. Use esta opción con sumo cuidado. La eliminación de archivos etiquetados y clasificados puede afectar a los resultados de relevancia. 
  
1. En la barra de menús, haga clic en el icono de **cogwheel** . 
    
2. En la ficha **Opciones de \> configuración y utilidades** , seleccione **Borrar \> configuración de datos**.
    
3. Seleccione una opción para la información que se va a inicializar:
    
  - **Relevancia**: elimina todo el trabajo realizado en importancia, incluida la definición de cargas y la Asociación de archivos que se va a cargar. Elimina todas las muestras y el etiquetado.
    
  - **Near-duplicados y subprocesos de correo electrónico**: elimina toda la información de análisis de los subprocesos de correo electrónico casi duplicados.
    
  - **Themes**: elimina los datos relacionados con los temas.
    
  - **Exportar historial**: elimina la información del historial de los lotes de exportación.
    
4. Haga clic en **Borrar datos**. Se borran los datos de mayúsculas y minúsculas. La información de progreso de la tarea para la tarea actual y la última se muestra en el panel **Estado de tarea** . 
    
## <a name="modify-relevance"></a>Modificar relevancia

En esta sección se describe cómo omitir o revertir un ejemplo de relevancia.
  
1. En la barra de menús, haga clic en el icono de **cogwheel** . 
    
2. En la ficha **utilidades de \> configuración y utilidades** , seleccione **modificar relevancia**.
    
3. Seleccione una de las opciones: 
    
  - **Omitir el ejemplo actual: para el usuario actual**: Esto hará **** que se etiqueten todos los archivos sin etiquetar en el ejemplo de caso abierto del usuario que ejecuta la herramienta. El procesamiento de relevancia no se realizará en los archivos etiquetados como **SKIP**.
    
  - **Omitir el ejemplo actual: todas las muestras abiertas**: Esto hará **** que se etiqueten todos los archivos sin etiquetar en todas las muestras abiertas para todos los usuarios. Esta opción no se recomienda si los usuarios están etiquetando ejemplos en este momento.
    
  - **Revertir último ejemplo**: se revertirá el último ejemplo de entrenamiento de relevancia completado, independientemente de si es anterior o posterior al proceso de "cálculo". No se permite reVertir una muestra de puesta al día.
    
4. Haga clic en **Ejecutar** para ejecutar. 
    
## <a name="transparency-analysis"></a>Análisis de transparencia

La utilidad de análisis de transparencia permite una vista detallada de los archivos y su puntuación de relevancia asignada. El informe se puede usar como comprobación de validez o para comparar la relevancia de un archivo definido por un revisor humano en comparación con la relevancia asignada por la exhibición avanzada de documentos electrónicos. 
  
Además de los resultados de relevancia, eDiscovery avanzado calcula y asigna pesos de palabra clave que consideran el contexto de la palabra clave. Se puede asignar a la misma palabra en un archivo diferentes pesos, según el contexto y la ubicación. Cada palabra clave se marca con una escala de color cada vez mayor que va de amarillo a naranja oscuro y a distintos tonos de gris. La codificación en colores se usa para indicar visualmente la contribución positiva o negativa de la palabra relativa a la puntuación de relevancia. 
  
En un escenario de casos de varios problemas, se puede generar un informe de análisis de transparencia para cada problema.
  
1. En la barra de menús, haga clic en el icono de **cogwheel** . 
    
2. En la ficha **utilidades de \> configuración y utilidades** , seleccione **configuración \> de análisis de transparencia**.
    
3. En * * ID de archivo * *, escriba el identificador de archivo del archivo que se va a procesar.
    
4. En la lista de **problemas** , seleccione el problema pertinente. 
    
5. Haga clic en **análisis de transparencia**. Una vez finalizado, se muestra el informe de análisis de transparencia del archivo, que muestra cómo los colores de palabra clave marcados correlacionan con la puntuación de relevancia general.
    
## <a name="see-also"></a>Vea también

[eDiscovery avanzado de Office 365](office-365-advanced-ediscovery.md)
  
[Definir la configuración de casos y espacios empresariales](define-case-and-tenant-settings-in-advanced-ediscovery.md)

