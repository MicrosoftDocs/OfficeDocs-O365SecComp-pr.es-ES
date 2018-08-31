---
title: Administrar permisos de aplicación con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Permisos de aplicación de seguridad de la aplicación de nube de Office 365 le ayudan a administrar las aplicaciones de que los usuarios descargar para su uso con datos de Office 365
ms.openlocfilehash: 7bda35bbbf3a16cd1d386adcb03b1c7c4176913a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536587"
---
# <a name="manage-app-permissions-using-office-365-cloud-app-security"></a>Administrar permisos de aplicación con Office 365 Cloud App Security

Administración avanzada de seguridad de Office 365 es ahora de seguridad de la aplicación de nube de Office 365.
  
|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Comenzar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |¡Están aquí!  <br/> [Pasos siguientes](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
Personas love aplicaciones y descargue con frecuencia, especialmente las aplicaciones que la gente piense va a ahorrar tiempo al hacer que sea más fácil obtener en su trabajo o escuela información. Sin embargo, algunas aplicaciones potencialmente podrían ser un riesgo de seguridad para la organización, dependiendo de qué información tienen acceso a y cómo tratar esa información. Con la [Seguridad de la aplicación de nube de Office 365](office-365-cas-overview.md), si es un administrador global o de seguridad, puede administrar los permisos de aplicación para su organización. Puede ver las personas de aplicaciones están usando con datos de Office 365, ¿qué permisos de esas aplicaciones tienen y mucho más. 
  
En este artículo se describe dónde debe acudir para administrar los permisos de la aplicación, cómo aprobar o prohibir una aplicación y cómo crear una consulta de la aplicación.
  
## <a name="how-to-find-the-manage-app-permissions-page"></a>Cómo encontrar la página de permisos de aplicación de administrar
<a name="findappperms"> </a>

> [!NOTE]
> Permisos de aplicación se administran en el portal de seguridad de la aplicación de nube de Office 365. Debe ser un administrador global o administrador de seguridad para llevar a cabo la siguiente tarea. Para obtener más información vea más [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md). 
  
1. Vaya a [https://protection.office.com](https://protection.office.com) e iniciar sesión con su cuenta de trabajo o escuela para Office 365. (Esto le llevará a la seguridad &amp; centro de cumplimiento.) 
    
2. Vaya a **las alertas de** \> **avanzada de administrar las alertas**.
    
3. Haga clic en (o puntee) **vaya a la seguridad de la aplicación de nube de Office 365**.
    
    ![En la seguridad &amp; centro de cumplimiento, elija Administrar alertas avanzadas para ir a la seguridad de la aplicación de nube de Office 365](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    > [!NOTE]
    > Si la seguridad de la aplicación de nube de Office 365 no está activado todavía, puede hacer en esta página. Vea [prepararse para la seguridad de la aplicación de nube de Office 365](get-ready-for-office-365-cas.md). 
  
4. Elija **investigar** \> **permisos de aplicación**.
    
    ![En el portal de O365 CAS, elija investigar.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
## <a name="what-youll-see-on-the-manage-app-permissions-page"></a>Lo que verá en la página de permisos de aplicación de administrar
<a name="whatsonpage"> </a>

En la siguiente tabla se describe los controles y las opciones disponibles en la página de permisos de aplicación de administrar.
  
|**Elemento**|**Descripción**|
|:-----|:-----|
|Icono básica en la barra de consulta de aplicación  <br/> ![Icono que indica la vista de consulta básica para consultar los permisos de aplicación](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|Seleccione esta opción para cambiar a la vista avanzada.  <br/> (Si ve **básica**, está usando la vista avanzada)  <br/> |
|Icono avanzadas en la barra de consulta de aplicación  <br/> ![Icono que indica la vista de consulta para consultar los permisos de aplicación avanzada](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|Seleccione esta opción para cambiar a la vista básica.  <br/> (Si ve **Opciones avanzadas**, se utiliza la vista básica).  <br/> |
|Abrir o cerrar todos los iconos de detalles en la lista de aplicaciones  <br/> ![Haga clic en este icono para abrir o cerrar todos los detalles de todas las aplicaciones](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|Seleccione este icono para ver más o menos detalles acerca de cada aplicación.  <br/> |
|Icono de exportación en la lista de aplicaciones  <br/> ![Haga clic en este icono para exportar un archivo csv de todas las aplicaciones](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|Seleccione este icono para exportar un archivo CSV que contiene una lista de aplicaciones, el número de usuarios para cada aplicación, los permisos asociados con la aplicación, nivel de permisos, estado de la aplicación y usar nivel de la Comunidad.  <br/> |
|Name  <br/> |Utilícelo para ver el nombre de una aplicación, seleccione el nombre para ver más información, como su descripción, publisher, sitio Web de la aplicación e identificador de aplicación.  <br/> |
|Autorizado por  <br/> |Se usa para ver el número de usuarios ha autorizado una aplicación para tener acceso a su cuenta de Office 365. Seleccione el número para ver más información, como una lista de cuentas de usuario.  <br/> |
|Nivel de permisos  <br/> ![Icono que indica el nivel de permisiions para una aplicación](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|Se usa para ver el nivel de acceso una aplicación tiene a los datos de Office 365. Los niveles de permisos indican **bajo**, **medio**o **alto**, donde **bajo** podría indicar que la aplicación sólo tiene acceso a perfiles y el nombre de un usuario. Seleccione el nivel para ver más información, como los permisos concedidos a la aplicación, el uso de la Comunidad y la actividad relacionada en el [registro de gobierno](suspend-or-restore-an-account-in-ocas.md).<br/> |
|Estado de la aplicación ( **expulsados**, **aprobado**o **sin determinar**)  <br/> ![Iconos de permisos de aplicación después de que se está permitido, bloqueado o ninguna acción ha sido tomado por un administrador](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)|Use esta opción para marcar una aplicación como aprobado o expulsados o deje como indeterminado.  <br/> |
   
## <a name="mark-an-app-as-approved"></a>Marcar una aplicación como aprobados
<a name="approveapp"> </a>

En la página **Administrar permisos de aplicación** , busque la aplicación que desee aprobar y elija el icono **aplicación marca como aprobada** . 
  
![Elija la aplicación de marca como icono aprobada](media/dd1b7690-441a-48c9-9c3a-58466513c63d.png)
  
El icono se vuelve verde y la aplicación está aprobada para todos los usuarios de Office 365.
  
> [!NOTE]
> Cuando una aplicación se marca como aprobados, no hay ningún efecto en el usuario final. Marcar visualmente las aplicaciones que están aprobadas ayuda a separarlas desde aplicaciones que aún no se han revisado todavía. 
  
## <a name="ban-an-app"></a>Expulsar a una aplicación
<a name="banapp"> </a>

1. En la página **Administrar permisos de aplicación** , busque la aplicación que desea prohibir y elija el icono **aplicación marcar como no permitidas** . 
    
    ![Elija la aplicación de marca como icono prohibido](media/b9b1c5f6-fde7-46d5-8589-1564d05702b3.png)
  
2. Elija si desea que los usuarios sepan que se ha prohibido su aplicación.
    
    (Recomendado) Para permitir que los usuarios sepan, seleccione **los usuarios de notificar quién conceden acceso a esta aplicación prohibido**y agregar o editar un mensaje de notificación personalizado.
    
    Para no permitir que los usuarios sepan, desactive **los usuarios de notificar quién conceden acceso a esta aplicación no permitida**.
    
    ![La plantilla de correo para una aplicación no permitida](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)
  
3. Elija la **aplicación de prohibición**.
    
## <a name="create-an-app-query"></a>Crear una consulta de aplicación
<a name="createapp"> </a>

1. En la barra de consulta de aplicación, si ve **Opciones avanzadas**, haga clic en (o puntee) que vaya a la vista avanzada. (Si ve Basic, está utilizando la vista avanzada; mantener su vista como está).
    
2. Use la lista **Seleccione un filtro** para elegir una opción. En la siguiente tabla se resume las opciones de filtrado disponibles. 
    
|**Use este filtro**|**Para mostrar**|
|:-----|:-----|
|**Aplicación** <br/> |Aplicaciones con algunos nombres  <br/> |
|**Estado de la aplicación** <br/> |Aplicaciones en función de su estado (aprobado, expulsados o sin determinar)  <br/> |
|**Uso de la Comunidad** <br/> |En función de la Comunidad de aplicaciones utilizan niveles (raras, Uncommon o común)  <br/> |
|**Nivel de permisos** <br/> |En función de determinados niveles de permisos de aplicaciones  <br/> |
|**Permisos** <br/> |Aplicaciones que requieren determinados permisos  <br/> |
|**Publicador** <br/> |Aplicaciones de ciertos editores  <br/> |
|**Usuario** <br/> |Aplicaciones que un usuario determinado autorizado  <br/> |
   
3. Seleccione **es igual a** o **no es igual a**y, a continuación, especifique un valor para el filtro.
    
4. Para agregar más filtros, seleccione el signo más)![Agregar un icono de filtro para consultar aplicaciones](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)) y, a continuación, repita los pasos 2 y 3.
    
5. Para quitar un filtro, seleccione la x (![Quitar un icono de filtro para consultar aplicaciones](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)) junto a un nombre de filtro.
    
Los filtros se aplican automáticamente, y la lista de aplicaciones se actualiza en consecuencia.
  
## <a name="next-steps"></a>Pasos siguientes
<a name="nextsteps"> </a>

- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- Revise los [registros de tráfico Web y orígenes de datos de seguridad de la aplicación de nube de Office 365](web-traffic-logs-and-data-sources-for-ocas.md)
    
- Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)
    

