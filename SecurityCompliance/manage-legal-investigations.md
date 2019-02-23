---
title: Administración de investigaciones legales en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: Use casos de exhibición de documentos electrónicos en &amp; el centro de seguridad y cumplimiento de Office 365 para administrar la investigación legal de su organización. Si tiene una suscripción a E5, puede analizar más datos de caso con las capacidades de análisis de texto, aprendizaje de la máquina y Codificación predictiva de eDiscovery avanzado.
ms.openlocfilehash: 5b3feb16b638235d46f67f6aa16ce49e1e7c11d5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214400"
---
# <a name="manage-legal-investigations-in-office-365"></a>Administración de investigaciones legales en Office 365

Las organizaciones tienen muchas razones para responder a un caso legal en el que participan determinados ejecutivos u otros empleados de la organización. Esto puede implicar la rápida búsqueda y la retención de información específica de la investigación en el correo electrónico, los documentos, las conversaciones de mensajería instantánea y otras ubicaciones de contenido que usan los usuarios en sus tareas de trabajo cotidianas. Puede realizar estas y muchas otras actividades similares mediante las herramientas de caso de exhibición de documentos electrónicos del centro &amp; de seguridad y cumplimiento de Office 365.
  
[Administración de investigaciones legales con casos de eDiscovery](#manage-legal-investigations-with-ediscovery-cases)
  
[Analizar datos de casos con Office 365 Advanced eDiscovery](#analyze-case-data-using-office-365-advanced-ediscovery)
  
**¿Desea saber cómo administra Microsoft sus investigaciones de eDiscovery?** A continuación se describen las [notas del producto](https://go.microsoft.com/fwlink/?linkid=852161) que puede descargar y que explican cómo usamos las mismas herramientas de búsqueda e investigación de Office 365 para administrar nuestro flujo de trabajo de eDiscovery interno.
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Administración de investigaciones legales con casos de eDiscovery

los casos de eDiscovery le permiten controlar quién puede crear, acceder y administrar casos de eDiscovery en su organización. Use casos para agregar miembros y controlar los tipos de acciones que pueden realizar, poner una retención en las ubicaciones de contenido relevantes para un caso legal y usar la herramienta de búsqueda de contenido para buscar en las ubicaciones en espera el contenido que pueda responder a su caso. A continuación, también puede exportar y descargar los resultados para seguir investigando por revisores externos. Si su organización de Office 365 tiene una suscripción a E5, también puede preparar los resultados de búsqueda para el análisis en la exhibición avanzada de documentos electrónicos.
  
- [Administrar el flujo de trabajo de eDiscovery](ediscovery-cases.md) mediante la creación y el uso de casos de eDiscovery para cada investigación legal que la organización tiene que llevar a cabo 
    
- [Asignar permisos de exhibición](assign-ediscovery-permissions.md) de documentos electrónicos para controlar quién puede crear y administrar casos de eDiscovery en su organización 
    
- [Configurar límites de cumplimiento](set-up-compliance-boundaries.md) para controlar las ubicaciones de contenido del usuario que los administradores de eDiscovery pueden buscar 
    
- [Buscar contenido](search-for-content.md) en la organización 
    
- [Preparar el contenido del caso para la exhibición avanzada de](prepare-search-results-for-advanced-ediscovery.md) documentos electrónicos para poder realizar análisis con las eficaces herramientas analíticas de eDiscovery avanzado, como el reconocimiento óptico de caracteres, el subprocesamiento de correo electrónico y la codificación predictiva 
    
### <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para escenarios avanzados

Al igual que en la sección anterior que enumeraba scripts para escenarios de búsqueda de contenido &amp; , también hemos creado algunos scripts de PowerShell del centro de cumplimiento de seguridad para ayudarle a administrar casos de eDiscovery.
  
- [Crear un informe de suspensión de exhibición](create-a-report-on-holds-in-ediscovery-cases.md) de documentos electrónicos que contenga información sobre todas las retenciones asociadas con casos de eDiscovery en su organización 
    
- [Agregar buzones de correo y ubicaciones de OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) para una lista de usuarios a una suspensión de exhibición de documentos electrónicos 
  
## <a name="analyze-case-data-using-office-365-advanced-ediscovery"></a>Analizar datos de casos con Office 365 Advanced eDiscovery

Office 365 Advanced eDiscovery se basa en la búsqueda de contenido y en las capacidades de eDiscovery descritas en las secciones anteriores. Después de crear un caso de exhibición de documentos electrónicos, poner ubicaciones de custodios en suspensión y recopilar datos que puedan responder al caso, puede seguir analizando los datos con el análisis de texto, el aprendizaje de la máquina y las capacidades de Codificación predictiva de Advanced. exhibición. Esto puede ayudar a su organización a procesar rápidamente miles de mensajes de correo electrónico, documentos y otros tipos de datos para encontrar los elementos que son más relevantes para un caso específico. Además, hemos Unificado la administración de casos y la exhibición avanzada de documentos electrónicos para que pueda administrar sin problemas el &amp; mismo caso en el centro de seguridad y cumplimiento.
  
> [!NOTE]
> Para analizar los datos de un usuario con la exhibición avanzada de documentos electrónicos, el usuario (el custodio de los datos) debe tener asignada una licencia de Office 365 E5. Como alternativa, se puede asignar una licencia independiente de eDiscovery avanzado a los usuarios con una licencia de Office 365 E1 o E3. Los administradores y los responsables de cumplimiento que se asignan a los casos y usan la exhibición avanzada de documentos electrónicos para analizar los datos no necesitan una licencia E5. 
  
### <a name="get-started"></a>Introducción

La forma más rápida de empezar a usar eDiscovery avanzado es crear un caso y preparar los resultados de la búsqueda &amp; en el centro de seguridad y cumplimiento, cargar los resultados en la exhibición avanzada de documentos electrónicos y, a continuación, ejecutar el análisis rápido para analizar los datos de caso y, a continuación, exportar el resultados de la revisión externa.
  
- [Obtener información general rápida sobre](quick-setup-for-advanced-ediscovery.md) el flujo de trabajo de eDiscovery avanzado 
    
- [Configure usuarios y casos](set-up-users-and-cases-in-advanced-ediscovery.md) para la exhibición avanzada de documentos electrónicos creando un caso, asignando permisos de exhibición de documentos electrónicos y agregando miembros de &amp; caso, todo mediante el centro de seguridad y cumplimiento 
    
- [Preparar y cargar los datos de búsqueda](prepare-data-for-advanced-ediscovery.md) en el caso de eDiscovery avanzado 
    
- [Cargar datos que no son de Office 365](import-non-office-365-data-into-advanced-ediscovery.md) en un caso para analizarlos en la exhibición avanzada de documentos electrónicos 
    
- [Usar el análisis](use-express-analysis-in-advanced-ediscovery.md) rápido para analizar rápidamente los datos en un caso y, a continuación, exportar fácilmente los resultados 
    
### <a name="analyze-data"></a>Analizar datos

Una vez que los datos de búsqueda se cargan en el caso de la exhibición avanzada de documentos electrónicos, usará el módulo analizar para empezar a analizarlo. La primera parte del proceso de análisis consiste en organizar los archivos en grupos de archivos únicos, duplicados y casi duplicados (también conocido como similitud de documentos). A continuación, organizará de nuevo los datos en grupos estructurados jerárquicamente de subprocesos y temas de correo electrónico y, opcionalmente, puede configurar omitir filtros de texto para excluir determinados textos del análisis. A continuación, ejecutará el análisis y verá los resultados.
  
- [Obtenga información sobre la similitud de documentos](understand-document-similarity-in-advanced-ediscovery.md) para prepararse para analizar datos en eDiscovery avanzado. 
    
- [Configurar las opciones](set-analyze-options-in-advanced-ediscovery.md) para casi duplicados, temas y subprocesos de correo electrónico y, a continuación, ejecutar el módulo ANALYZE 
    
- [Configure omitir filtros de texto](set-ignore-text-in-advanced-ediscovery.md) para excluir texto y cadenas de texto del análisis; Estos filtros también omitirán el texto al ejecutar el análisis de relevancia 
    
- [Ver los resultados](view-analyze-results-in-advanced-ediscovery.md) del proceso de análisis 
    
- [Configurar opciones avanzadas](set-analyze-advanced-settings-in-advanced-ediscovery.md) para el proceso de análisis 
    
### <a name="set-up-relevance-training"></a>Configurar la formación de relevancia

La codificación predictiva (denominada relevancia) en eDiscovery avanzado le permite entrenar al sistema sobre lo que está buscando, permitiéndole tomar decisiones (sobre si algo es relevante o no) en un pequeño conjunto de documentos.
  
- [Obtenga información sobre la configuración](manage-relevance-setup-in-advanced-ediscovery.md) de la formación de relevancia, la etiquetación de archivos que son relevantes para un caso y la definición de problemas de casos. 
    
- [Definir los problemas de caso](define-issues-and-assign-users.md) y asignar cada problema a un usuario que vaya a entrenar los archivos 
    
- [Agregar archivos importados a la carga actual o nueva](set-up-loads-to-add-imported-files.md) que se agregarán al aprendizaje de relevancia; una carga es un nuevo lote de archivos que se agregan a un caso y que luego se usan para el entrenamiento de relevancia. 
    
- [Definir palabras clave](define-highlighted-keywords-and-advanced-options.md) resaltadas que se pueden agregar al aprendizaje de relevancia; Esto le ayuda a identificar mejor los archivos relevantes para un caso 
    
### <a name="run-the-relevance-module"></a>Ejecutar el módulo de relevancia

Una vez configurada la formación, ya está listo para ejecutar el módulo de relevancia y evaluar la efectividad de la configuración de entrenamiento esto da como resultado una clasificación de relevancia que le ayuda a decidir si necesita realizar más aprendizajes o si está listo para empezar a etiquetar archivos como relevante para el caso.
  
- [Obtenga más información sobre el proceso de relevancia](use-relevance-in-advanced-ediscovery.md) y el proceso iterativo de evaluación, etiquetado, seguimiento y reentrenamiento en función del conjunto de archivos de muestra. 
    
- [Obtenga más información acerca](assessment-in-relevance-in-advanced-ediscovery.md) de la evaluación, donde un experto familiarizado con el caso revisa un conjunto de archivos de casos y determina la efectividad del entrenamiento de relevancia. 
    
- [Evaluar los archivos de casos](tagging-and-assessment-in-advanced-ediscovery.md) para calcular la eficacia (denominada *riqueza* ) de la configuración de entrenamiento y, a continuación, etiquete los archivos según sea relevante o no sean relevantes para su caso; Esto le ayudará a determinar si la formación actual es suficiente o si debe ajustar la configuración del entrenamiento. 
    
- [Lleve a cabo el entrenamiento de relevancia](tagging-and-relevance-training-in-advanced-ediscovery.md) una vez que se haya completado la evaluación y, después, vuelva a etiquetar los archivos según sea relevante o no sean relevantes para los problemas que ha definido en el caso 
    
- [Realizar un seguimiento del](track-relevance-analysis-in-advanced-ediscovery.md) proceso de análisis de relevancia para determinar si el entrenamiento de relevancia ha logrado su objetivo de evaluación (conocido como *Estado de formación estable* ) o si se necesita más formación; también puede ver los resultados de relevancia para cada problema de caso 
    
- [Tomar decisiones basadas en el análisis de relevancia](decision-based-on-the-results-in-advanced-ediscovery.md) para determinar el tamaño del conjunto resultante de archivos de casos que se pueden exportar para revisión 
    
- [Probar la calidad del análisis de relevancia](test-relevance-analysis-in-advanced-ediscovery.md) para validar las decisiones de selección realizadas durante el proceso de relevancia 
    
### <a name="export-results"></a>Exportar resultados

El último paso para analizar los datos de casos en eDiscovery avanzado es exportar los resultados del análisis para una revisión externa.
  
- [Obtener información sobre cómo exportar datos de casos](export-case-data-in-advanced-ediscovery.md)
    
- [Exportar datos de casos](export-results-in-advanced-ediscovery.md)
    
- [Ver el historial del lote y exportar resultados pasados](view-batch-history-and-export-past-results.md)
    
- [Exportar campos de informes](export-report-fields-in-advanced-ediscovery.md)
    
### <a name="other-advanced-ediscovery-tools"></a>Otras herramientas avanzadas de eDiscovery

EDiscovery avanzado proporciona herramientas y capacidades adicionales aparte del análisis de datos de casos, el análisis de relevancia y la exportación de datos.
  
- [Ejecutar informes de eDiscovery avanzado](run-reports-in-advanced-ediscovery.md)
    
- [Definir la configuración de casos y espacios empresariales](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [Utilidades avanzadas de eDiscovery](use-advanced-ediscovery-utilities.md)
