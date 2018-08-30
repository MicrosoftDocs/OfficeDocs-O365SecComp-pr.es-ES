---
title: Búsqueda de contenido en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/4/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.assetid: df2d1e0f-b476-42c9-aade-4a260b24f193
description: Usar la herramienta de exhibición de documentos electrónicos de búsqueda de contenido en la seguridad de Office 365 &amp; centro de cumplimiento para encontrar rápidamente el correo electrónico en los buzones de Exchange, los documentos en sitios de SharePoint y las ubicaciones de OneDrive y las conversaciones de Skype para la empresa de mensajería instantánea.
ms.openlocfilehash: b9595f66633cca762ea74eaa9402f50ec08c2d7c
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23229982"
---
# <a name="search-for-content-in-office-365"></a>Búsqueda de contenido en Office 365

Use la herramienta de búsqueda de contenido en la seguridad &amp; centro de cumplimiento para encontrar rápidamente el correo electrónico en los buzones de Exchange, los documentos en sitios de SharePoint y las ubicaciones de OneDrive y las conversaciones de Skype para la empresa de mensajería instantánea. Puede usar la herramienta de búsqueda de contenido para buscar correo electrónico, los documentos y las conversaciones de herramientas de colaboración de Office 365, como Microsoft Teams y Office 365 grupos de mensajería instantánea.
  
## <a name="search-for-content"></a>Buscar contenido

El primer paso es iniciar el uso de la herramienta de búsqueda de contenido para elegir las ubicaciones de contenido para buscar y configurar una consulta de palabra clave para buscar elementos específicos. O bien, puede dejar en blanco la consulta y devolver todos los elementos en las ubicaciones de destino.
  
- [Crear y ejecutar](content-search.md) una búsqueda de contenido 
    
- [Generar consultas de búsqueda y utilizar condiciones](keyword-queries-and-search-conditions.md) para acotar la búsqueda 
    
- [Configurar los permisos de búsqueda filtrado](permissions-filtering-for-content-search.md) para que un administrador de exhibición de documentos electrónicos sólo puede buscar el subconjunto de buzones de correo o sitios de la organización 
    
- [Ejecutar una búsqueda de identificador de lista](csv-file-for-an-id-list-content-search.md) para buscar mensajes de correo electrónico específicos 
    
- [Los buzones de correo basados en la nube de búsqueda](search-cloud-based-mailboxes-for-on-premises-users.md) para los usuarios locales en Office 365

- [Ver las estadísticas de palabra clave](view-keyword-statistics-for-content-search.md) para los resultados de una búsqueda y, a continuación, refinar la consulta si es necesario 
    
- [Búsqueda de datos de terceros](use-content-search-to-search-third-party-data-that-was-imported.md) que su organización ha importado a Office 365 
    
- [Edición en masa de](bulk-edit-content-searches.md) la consulta y ubicaciones para varias búsquedas de contenido 
    
## <a name="perform-actions-on-content-you-find"></a>Realizar acciones en el contenido que encuentre

Después de ejecutar una búsqueda y refinar según sea necesario, el siguiente paso es hacer algo con los resultados devueltos por la búsqueda. Puede exportar y descargar los resultados en el equipo local o en el caso de un ataque de correo electrónico en la organización, puede eliminar los resultados de una búsqueda de buzones de usuario.
  
- [Exportar los resultados de una búsqueda de contenido](export-search-results.md) y descargarlos en el equipo local 
    
- [Buscar y eliminar mensajes de correo electrónico](search-for-and-delete-messages-in-your-organization.md) , como los mensajes que el contenido de un virus, datos adjuntos peligrosos o los mensajes de suplantación de identidad 
    
- [Exportar un informe](export-a-content-search-report.md) sobre los resultados de una búsqueda de contenido, sin necesidad de exportar los resultados reales 
    
- [Aumentar la velocidad de descarga](increase-download-speeds-when-exporting-ediscovery-results.md) al exportar los resultados de búsqueda 
    
## <a name="learn-more-about-content-search"></a>Encontrará más información acerca de la búsqueda de contenido

Búsqueda de contenido es fácil de usar, pero también es una herramienta eficaz. Un segundo plano, no hay mucho. Más conocimientos sobre él y comprender su comportamiento y sus limitaciones, más correcta se van a usarlo para las necesidades de búsqueda y de investigación de su organización. Obtenga información acerca de:
  
- [Parcialmente indizar los elementos de Exchange y SharePoint](partially-indexed-items-in-content-search.md) y cómo incluir o excluir ellos al exportar y descargar los resultados de búsqueda 
    
- [Investigar los elementos indizados parcialmente](investigating-partially-indexed-items-in-ediscovery.md) y determinar la exposición de su organización a ellos 
    
- [Límites de la herramienta de búsqueda de contenido](limits-for-content-search.md), como el número máximo de búsquedas que se pueden ejecutar al mismo tiempo y el número máximo de ubicaciones de contenido que puede incluir en una sola búsqueda 
    
- [Estimado y los resultados de búsqueda reales](differences-between-estimated-and-actual-ediscovery-search-results.md) y los motivos por qué puede haber diferencias entre ellos al exportar y descargar los resultados de búsqueda 
    
- [La desduplicación en los resultados de búsqueda](de-duplication-in-ediscovery-search-results.md) que se pueden activar al exportar mensajes de correo electrónico que son los resultados de una búsqueda 
    
## <a name="use-scripts-for-advanced-scenarios"></a>Utilizar secuencias de comandos para escenarios avanzados

A veces tendrá que realizar tareas de búsqueda de contenido más avanzados, complejas y repetitivas. En estos casos, es más fácil y rápida para usar comandos de PowerShell en la seguridad &amp; centro de cumplimiento. Para ayudar a facilitar este proceso, hemos creado un número de la seguridad de &amp; secuencias de comandos de PowerShell de centro de cumplimiento que le ayudarán a completar tareas relacionadas con la búsqueda de contenido complejas.
  
- [Buzón de correo específico de búsqueda y carpetas del sitio](use-content-search-for-targeted-collections.md) (denominado un *destino colección* ) cuando esté seguro de que los elementos con capacidad de respuesta a un caso de se encuentran en esa carpeta 
    
- [Buscar en el buzón de correo y la ubicación de OneDrive](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) para obtener una lista de usuarios 
    
- [Crear un informe sobre y eliminar varias búsquedas](create-report-on-and-delete-multiple-content-searches.md) para rápida y eficazmente identificar y extraer datos de búsqueda 
    
- [Clonación de una búsqueda de contenido](clone-a-content-search.md) y comparar rápidamente los resultados de las consultas de búsqueda de palabra clave diferentes ejecutar en las mismas ubicaciones de contenido; o use el script para ahorrar tiempo al no tener que volver a escribir un gran número de ubicaciones de contenido cuando se crea una nueva búsqueda 
    

