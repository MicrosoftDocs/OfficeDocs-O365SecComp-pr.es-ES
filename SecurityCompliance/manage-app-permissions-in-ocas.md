---
title: Administrar aplicaciones de OAuth con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Aplicaciones de OAuth de seguridad de la aplicación de nube de Office 365 le ayudan a administrar las aplicaciones de que los usuarios descargar para su uso con datos de Office 365
ms.openlocfilehash: ae32e3c6b15f4ad4794a3dd08c3992adaeba655c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603691"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a>Administrar aplicaciones de OAuth con Office 365 Cloud App Security

|Evaluación **\>**|Planeación de **\>**|Implementación **\>**|Utilización de ***|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Comenzar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |¡Están aquí!  <br/> [Pasos siguientes](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
Personas love aplicaciones y descargue con frecuencia, especialmente las aplicaciones que la gente piense va a ahorrar tiempo al hacer que sea más fácil obtener en su trabajo o escuela información. Sin embargo, algunas aplicaciones potencialmente podrían ser un riesgo de seguridad para la organización, dependiendo de qué información tienen acceso a y cómo tratar esa información. Con la [Seguridad de la aplicación de nube de Office 365](office-365-cas-overview.md), si es un administrador global o de seguridad, puede administrar aplicaciones de OAuth para su organización. Puede ver las personas de aplicaciones están usando con datos de Office 365, ¿qué permisos de esas aplicaciones tienen y mucho más. 
  
En este artículo se describe dónde ir a la administración de aplicaciones de OAuth, cómo aprobar, prohibir o informar de una aplicación y cómo crear una consulta de la aplicación.
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a>Cómo encontrar la página de aplicaciones de administración de OAuth

> [!NOTE]
> Aplicaciones de OAuth se administran en el portal de seguridad de la aplicación de nube de Office 365. Debe ser un administrador global o administrador de seguridad para llevar a cabo la siguiente tarea. Para obtener más información vea más [permisos en la seguridad de Office 365 &amp; centro de cumplimiento](permissions-in-the-security-and-compliance-center.md). 
  
1. Vaya al portal de seguridad de la aplicación en la nube ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e iniciar sesión.
  
2. Elija **investigar** \> **aplicaciones de OAuth**.<br/>![En el portal de O365 CAS, elija investigar.](media/OCAS-OAuthApps.png)<br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a>Lo que verá en la página de aplicaciones de administración de OAuth

En la siguiente tabla se describe los controles y las opciones disponibles en la página de aplicaciones de administración de OAuth.
  
|**Elemento**|**Descripción**|
|:-----|:-----|
|Icono básica en la barra de consulta de aplicación  <br/> ![Icono que indica la vista de consulta básica para consultar](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|Seleccione esta opción para cambiar a la vista avanzada.  <br/> (Si ve **básica**, está usando la vista avanzada)  <br/> |
|Icono avanzadas en la barra de consulta de aplicación  <br/> ![Icono que indica la vista de consulta avanzada para consultar](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|Seleccione esta opción para cambiar a la vista básica.  <br/> (Si ve **Opciones avanzadas**, se utiliza la vista básica).  <br/> |
|Abrir o cerrar todos los iconos de detalles en la lista de aplicaciones  <br/> ![Haga clic en este icono para abrir o cerrar todos los detalles de todas las aplicaciones](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|Seleccione este icono para ver más o menos detalles acerca de cada aplicación.  <br/> |
|Icono de exportación en la lista de aplicaciones  <br/> ![Haga clic en este icono para exportar un archivo csv de todas las aplicaciones](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|Seleccione este icono para exportar un archivo CSV que contiene una lista de aplicaciones, el número de usuarios para cada aplicación, los permisos asociados con la aplicación, nivel de permisos, estado de la aplicación y usar nivel de la Comunidad.  <br/> |
|Nombre  <br/> |Utilícelo para ver el nombre de una aplicación, seleccione el nombre para ver más información, como su descripción, publisher, sitio Web de la aplicación e identificador de aplicación.  <br/> |
|Autorizado por  <br/> |Se usa para ver el número de usuarios ha autorizado una aplicación para tener acceso a su cuenta de Office 365. Seleccione el número para ver más información, como una lista de cuentas de usuario.  <br/> |
|Nivel de permisos  <br/> ![Icono que indica el nivel de permisiions para una aplicación](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|Se usa para ver el nivel de acceso una aplicación tiene a los datos de Office 365. Los niveles de permisos indican **bajo**, **medio**o **alto**, donde **bajo** podría indicar que la aplicación sólo tiene acceso a perfiles y el nombre de un usuario. Seleccione el nivel para ver más información, como los permisos concedidos a la aplicación, el uso de la Comunidad y la actividad relacionada en el [registro de gobierno](suspend-or-restore-an-account-in-ocas.md).<br/> |
|Autorizado por última vez <br/> |Se usa para ver la fecha y hora de que una aplicación de OAuth por última vez se ha autorizado para tener acceso a datos de Office 365 de su organización. <br/>  |
|Acciones<br/>![Aplicaciones de OAuth](media/OCAS-OAuthAppApproveBanReport.png)<br/> |Use esta opción para ver o para marcar una aplicación como aprobado o expulsados, informar de una aplicación de OAuth a Microsoft, o deje como indeterminado.  <br/> |
   
## <a name="mark-an-app-as-approved"></a>Marcar una aplicación como aprobados

En la página **aplicaciones de administración de OAuth** , busque la aplicación que desee aprobar y elija el icono **aplicación marca como aprobada** . 
  
![Elija la aplicación de marca como icono aprobada](media/OCAS-MarkOAuthApproved.png)
  
El icono se vuelve verde y la aplicación está aprobada para todos los usuarios de Office 365.
  
> [!NOTE]
> Cuando una aplicación se marca como aprobados, no hay ningún efecto en el usuario final. Marcar visualmente las aplicaciones que están aprobadas ayuda a separarlas desde aplicaciones que aún no se han revisado todavía. 
  
## <a name="ban-an-app"></a>Expulsar a una aplicación

1. En la página **aplicaciones de administración de OAuth** , busque la aplicación que desea prohibir y elija el icono **aplicación marcar como no permitidas** .<br/>![Elija la aplicación de marca como icono prohibido](media/OCAS-MarkOAuthBanned.png)
  
2. En el cuadro de mensaje de notificación, mantener el texto existente tal cual o personalizar el texto. Elija si desea que los usuarios sepan que se ha prohibido su aplicación. <br/>![La plantilla de correo para una aplicación no permitida](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. Elija la **aplicación de prohibición**.

## <a name="report-an-oauth-app-to-microsoft"></a>Informar a Microsoft de una aplicación de OAuth

Si desea enviar una aplicación de OAuth a Microsoft para su análisis, puede informar de esa aplicación.

1. En la página **aplicaciones de administración de OAuth** , busque la aplicación que desea enviar para su análisis.

2. Elija el botón de puntos suspensivos vertical y, a continuación, elija **informe App...**.<br/>![Notificar a una aplicación de OAuth](media/OCAS-MarkOAuthReported.png)<br/>

3. En el cuadro de diálogo **informe de esta aplicación** , use la lista desplegable para indicar su preocupación. De forma predeterminada, está seleccionada **esta aplicación es malintencionada** . Sin embargo, puede elegir en una de las otras opciones disponibles.<br/>![Notificar a una aplicación de OAuth](media/OCAS-ReportOAuthApp.png)<br/>

4. (Recomendado) Mantenga la opción ponerse en contacto con el que ha seleccionado, y confirme la dirección de correo electrónico que aparecen (o editar).

5. Elija **Enviar**. 
    
## <a name="create-an-app-query"></a>Crear una consulta de aplicación

Se recomienda usar la vista avanzada, que tiene este aspecto: 

![Vista avanzada](media/OCAS-OAuthAppsAdvQueryView.png)

En la barra de consulta de la aplicación, si ve **Opciones avanzadas**, está utilizando la vista básica. Haga clic en **Avanzadas** para ir a la vista avanzada (o puntee). 

![Vista básica](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. En la barra de la consulta, use la lista **Seleccione un filtro** para elegir una opción. 
    - **Aplicación** Aplicaciones con algunos nombres
    - **Estado de la aplicación** Aplicaciones en función de su estado (aprobado, expulsados o sin determinar)
    - **Use la Comunidad** En función de la Comunidad de aplicaciones utilizan niveles (raras, Uncommon o común)
    - **Nivel de permisos** En función de determinados niveles de permisos de aplicaciones 
    - **Permisos** Aplicaciones que requieren determinados permisos
    - **Publisher**  Aplicaciones de ciertos editores
    - **Usuario** Aplicaciones que un usuario determinado autorizado
   
2. Seleccione **es igual a** o **no es igual a**y, a continuación, especifique un valor para el filtro.
    
3. Para agregar más filtros, seleccione el signo más)![Agregar un icono de filtro para consultar aplicaciones](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)) y, a continuación, repita los pasos 2 y 3.
    
4. Para quitar un filtro, seleccione la x (![Quitar un icono de filtro para consultar aplicaciones](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)) junto a un nombre de filtro.
    
Los filtros se aplican automáticamente, y la lista de aplicaciones se actualiza en consecuencia.
  
## <a name="next-steps"></a>Pasos siguientes

- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- Revise los [registros de tráfico Web y orígenes de datos de seguridad de la aplicación de nube de Office 365](web-traffic-logs-and-data-sources-for-ocas.md)
    
- Revise las [actividades de uso para la seguridad de la aplicación de nube de Office 365](utilization-activities-for-ocas.md)
    

