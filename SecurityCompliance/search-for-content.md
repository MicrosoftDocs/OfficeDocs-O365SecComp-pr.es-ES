---
title: Buscar contenido en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/4/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.assetid: df2d1e0f-b476-42c9-aade-4a260b24f193
description: Use la herramienta de búsqueda de contenido eDiscovery en el centro de seguridad & cumplimiento para encontrar rápidamente el correo electrónico en buzones de Exchange, documentos en sitios de SharePoint y ubicaciones de OneDrive, y conversaciones de mensajería instantánea en Skype empresarial.
ms.openlocfilehash: fc0bea90ce9cbfc27f894985c7d3083756ab108a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261358"
---
# <a name="search-for-content-in-office-365"></a>Buscar contenido en Office 365

Use la herramienta de búsqueda de contenido en el centro de seguridad & cumplimiento para encontrar rápidamente el correo electrónico en buzones de Exchange, documentos en sitios de SharePoint y ubicaciones de OneDrive, y conversaciones de mensajería instantánea en Skype empresarial. Puede usar la herramienta de búsqueda de contenido para buscar correos electrónicos, documentos y conversaciones de mensajería instantánea en las herramientas de colaboración de Office 365, como Microsoft Teams y Office 365 groups.
  
## <a name="search-for-content"></a>Buscar contenido

El primer paso consiste en empezar a usar la herramienta de búsqueda de contenido para elegir las ubicaciones de contenido donde buscar y configurar una consulta de palabras clave para buscar elementos específicos. O bien, puede dejar la consulta en blanco y devolver todos los elementos de las ubicaciones de destino.
  
- [Crear y ejecutar](content-search.md) una búsqueda de contenido 
    
- [Crear consultas de búsqueda y usar condiciones](keyword-queries-and-search-conditions.md) para restringir la búsqueda 
    
- [Configurar el filtrado de permisos de búsqueda](permissions-filtering-for-content-search.md) para que un administrador de exhibición de documentos electrónicos solo pueda buscar en subconjuntos de buzones o sitios de la organización 
    
- [Ejecutar una búsqueda de lista](csv-file-for-an-id-list-content-search.md) de identificadores para buscar mensajes de correo electrónico específicos 
    
- [Buscar buzones de correo basados en la nube](search-cloud-based-mailboxes-for-on-premises-users.md) para usuarios locales en Office 365

- [Ver las estadísticas de palabras clave](view-keyword-statistics-for-content-search.md) para los resultados de una búsqueda y, a continuación, refinar la consulta si es necesario 
    
- [Buscar datos de terceros](use-content-search-to-search-third-party-data-that-was-imported.md) que su organización haya importado a Office 365 
    
- [Edición en masa](bulk-edit-content-searches.md) de las ubicaciones de consultas y contenido para varias búsquedas 
    
- [Conservar](https://docs.microsoft.com/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) los destinatarios de CCO para poder buscarlos 

## <a name="perform-actions-on-content-you-find"></a>Realizar acciones en el contenido que encuentra

Después de ejecutar una búsqueda y redefinirla según sea necesario, el siguiente paso consiste en hacer algo con los resultados devueltos por la búsqueda. Puede exportar y descargar los resultados en su equipo local o en el caso de un ataque de correo electrónico en su organización, puede eliminar los resultados de una búsqueda de los buzones de los usuarios.
  
- [Exportar los resultados de una búsqueda de contenido](export-search-results.md) y descargarlos en el equipo local 
    
- [Buscar y eliminar mensajes de correo electrónico](search-for-and-delete-messages-in-your-organization.md) , como mensajes que contengan un virus, datos adjuntos peligrosos o mensajes de suplantación de identidad 
    
- [Exportar un informe](export-a-content-search-report.md) sobre los resultados de una búsqueda de contenido sin exportar los resultados reales 
    
- [Aumentar la velocidad de descarga](increase-download-speeds-when-exporting-ediscovery-results.md) al exportar los resultados de la búsqueda 
    
## <a name="learn-more-about-content-search"></a>Obtenga más información sobre la búsqueda de contenido

La búsqueda de contenido es fácil de usar, pero también es una herramienta eficaz. En segundo plano, hay muchas cosas en marcha. Cuanto más conozca y comprenda su comportamiento y sus limitaciones, cuanto más le conviene, podrá usarla para las necesidades de búsqueda e investigación de su organización. Obtenga información sobre:
  
- [Elementos parcialmente indizados en Exchange y SharePoint](partially-indexed-items-in-content-search.md) , y cómo incluirlos o excluirlos cuando se exportan y se descargan los resultados de la búsqueda 
    
- [Investigar elementos indizados parcialmente](investigating-partially-indexed-items-in-ediscovery.md) y determinar la exposición de su organización a ellos 
    
- [Límites de la herramienta de búsqueda de contenido](limits-for-content-search.md), como el número máximo de búsquedas que se pueden ejecutar al mismo tiempo y el número máximo de ubicaciones de contenido que se pueden incluir en una sola búsqueda. 
    
- [Resultados de búsqueda estimados y reales](differences-between-estimated-and-actual-ediscovery-search-results.md) y los motivos por los que puede haber diferencias entre ellos cuando se exportan y se descargan los resultados de la búsqueda 
    
- [Desduplicación en los resultados](de-duplication-in-ediscovery-search-results.md) de la búsqueda que puede habilitar al exportar mensajes de correo electrónico que son el resultado de una búsqueda 
    
## <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para escenarios avanzados

A veces tiene que realizar tareas de búsqueda de contenido más avanzadas, complejas y repetitivas. En estos casos, es más fácil y rápido usar comandos de PowerShell en el centro de seguridad & cumplimiento. Para facilitar esta tarea, hemos creado una serie de scripts de PowerShell del centro de cumplimiento de & de seguridad que le ayudarán a completar tareas complejas relacionadas con la búsqueda de contenido.
  
- [Buscar en carpetas de sitio y buzones específicas](use-content-search-for-targeted-collections.md) (denominada *colección de destino* ) cuando tiene la certeza de que los elementos que responden a un caso se encuentran en esa carpeta 
    
- Buscar una lista de usuarios en [el buzón y en la ubicación de OneDrive](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) 
    
- [Crear, informar sobre y eliminar varias búsquedas](create-report-on-and-delete-multiple-content-searches.md) para identificar y reactivar datos de búsqueda de forma rápida y eficaz 
    
- [Clonar una búsqueda de contenido](clone-a-content-search.md) y comparar rápidamente los resultados de las diferentes consultas de búsqueda de palabras clave que se ejecutan en las mismas ubicaciones de contenido; o use el script para ahorrar tiempo sin tener que volver a especificar un gran número de ubicaciones de contenido al crear una nueva búsqueda 
    

