---
title: Administrar aplicaciones de OAuth con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Las aplicaciones de OAuth en Office 365 Cloud App Security ayudan a administrar las aplicaciones que los usuarios descargan para usar con datos de Office 365
ms.openlocfilehash: 0d9916414d55abb73fd99eaf30c3b6df0648b191
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862592"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a>Administrar aplicaciones de OAuth con Office 365 Cloud App Security

|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |[Iniciar la implementación](turn-on-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Siguientes pasos](#next-steps)<br/> |
   
Las personas adoran aplicaciones y las descargan con frecuencia, especialmente las aplicaciones que los usuarios creen que ahorrarán tiempo al facilitar la obtención de información profesional o educativa. Sin embargo, algunas aplicaciones podrían ser un riesgo para la seguridad de la organización, en función de la información a la que tengan acceso y de cómo controlan dicha información. Con [Office 365 Cloud App Security](office-365-cas-overview.md), si es un administrador global o de seguridad, puede administrar las aplicaciones de OAuth para su organización. Puede ver las aplicaciones que usan los usuarios con datos de Office 365, los permisos que tienen las aplicaciones y mucho más. 
  
En este artículo se describe dónde dirigirse a administrar aplicaciones de OAuth, cómo aprobar, prohibir o informar de una aplicación y cómo crear una consulta de aplicación.
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a>Cómo encontrar la página Administrar aplicaciones de OAuth

> [!NOTE]
> Las aplicaciones de OAuth se administran en el portal de seguridad de aplicaciones de nube de Office 365. Debe ser administrador global o administrador de seguridad para realizar la siguiente tarea. Para obtener más información, vea [permisos en el centro &amp; de seguridad y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md). 
  
1. Vaya al portal de Cloud App Security ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) e inicie sesión.
  
2. Elija **investigar** \> **aplicaciones de OAuth**.<br/>![En el portal de CAS de O365, elija investigar.](media/OCAS-OAuthApps.png)<br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a>Lo que verá en la página Administrar aplicaciones de OAuth

En la tabla siguiente se describen los controles y las opciones disponibles en la página Administrar aplicaciones de OAuth.
  
|**Elemento**|**Descripción**|
|:-----|:-----|
|Icono básico en la barra de consulta de la aplicación  <br/> ![Icono que indica la vista de consulta básica para la consulta](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|Seleccione esta opción para cambiar a la vista avanzada.  <br/> (Si ve **Basic**, está usando la vista avanzada)  <br/> |
|Icono avanzado en la barra de consulta de la aplicación  <br/> ![Icono que indica la vista de consulta avanzada para la consulta](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|Seleccione esta opción para cambiar a la vista básica.  <br/> (Si ve **avanzado**, está usando la vista básica).  <br/> |
|Icono de abrir o cerrar todos los detalles en la lista de aplicaciones  <br/> ![Haga clic en este icono para abrir o cerrar todos los detalles de todas las aplicaciones](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|Seleccione este icono para ver más o menos detalles sobre cada aplicación.  <br/> |
|Icono exportar en la lista de aplicaciones  <br/> ![Haga clic en este icono para exportar un archivo CSV de todas las aplicaciones](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|Seleccione este icono para exportar un archivo CSV que contenga una lista de aplicaciones, el número de usuarios de cada aplicación, los permisos asociados con la aplicación, el nivel de permisos, el estado de la aplicación y el nivel de uso de la comunidad.  <br/> |
|Nombre  <br/> |Use esta para ver el nombre de una aplicación. Seleccione el nombre para ver más información, como su descripción, editor, sitio web de la aplicación e identificador de la aplicación.  <br/> |
|Autorizado por  <br/> |Use esta para ver cuántos usuarios han autorizado una aplicación para tener acceso a su cuenta de Office 365. Seleccione el número para ver más información, como una lista de cuentas de usuario.  <br/> |
|Nivel de permisos  <br/> ![Icono que indica el nivel de permisiions de una aplicación](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|Use esta para ver cuánto acceso tiene una aplicación con los datos de Office 365. Los niveles de permisos indican **bajo**, **medio**o **alto**, donde **bajo** puede indicar que la aplicación solo tiene acceso al perfil y el nombre de un usuario. Seleccione el nivel para ver más información, como los permisos concedidos a la aplicación, el uso de la comunidad y la actividad relacionada en el [registro de gobierno](suspend-or-restore-an-account-in-ocas.md).  <br/> |
|Última autorización <br/> |Use esta para ver la fecha y la hora en que una aplicación de OAuth recibió la última autorización para obtener acceso a los datos de Office 365 de la organización. <br/>  |
|Acciones<br/>![Aplicaciones de OAuth](media/OCAS-OAuthAppApproveBanReport.png)<br/> |Use esta opción para ver o marcar una aplicación como aprobada o prohibida, informar de una aplicación de OAuth a Microsoft o dejarla como indeterminada.  <br/> |
   
## <a name="mark-an-app-as-approved"></a>Marcar una aplicación como aprobada

En la página **Administrar aplicaciones de OAuth** , busque la aplicación que quiera aprobar y elija el icono **marcar la aplicación como aprobada** . 
  
![Elija el icono marcar aplicación como aprobada](media/OCAS-MarkOAuthApproved.png)
  
El icono se vuelve de color verde y la aplicación se aprueba para todos los usuarios de Office 365.
  
> [!NOTE]
> Al marcar una aplicación como aprobada, no tiene efecto en el usuario final. Marcar visualmente las aplicaciones aprobadas ayuda a separarlas de las aplicaciones que todavía no se han revisado. 
  
## <a name="ban-an-app"></a>Prohibir una aplicación

1. En la página **Administrar aplicaciones de OAuth** , busque la aplicación que quiera prohibir y elija el icono **marcar la aplicación como prohibida** .<br/>![Elija el icono marcar aplicación como prohibida](media/OCAS-MarkOAuthBanned.png)
  
2. En el cuadro mensaje de notificación, mantenga el texto existente como está o personalice el texto. Elige si deseas que los usuarios sepan que la aplicación se ha vetado. <br/>![La plantilla de correo para una aplicación prohibida](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. Elija **prohibición de aplicación**.

## <a name="report-an-oauth-app-to-microsoft"></a>Informar de una aplicación de OAuth a Microsoft

Si quiere enviar una aplicación de OAuth a Microsoft para su análisis, puede informar de esa aplicación.

1. En la página **Administrar aplicaciones de OAuth** , busque la aplicación que quiera enviar para su análisis.

2. Elija los puntos suspensivos verticales y, a continuación, elija **aplicación de informes...**.<br/>![Informar de una aplicación de OAuth](media/OCAS-MarkOAuthReported.png)<br/>

3. En el cuadro de diálogo **informar de esta aplicación** , use la lista desplegable para indicar su preocupación. De forma predeterminada, **esta aplicación está** seleccionada como malintencionada. Sin embargo, puede elegir una de las otras opciones disponibles. <br/>![Informar de una aplicación de OAuth](media/OCAS-ReportOAuthApp.png)<br/>

4. Recomenda Mantenga la opción de ponerse en contacto con usted seleccionado y confirme (o modifique) la dirección de correo electrónico que aparece en la lista.

5. Choose **Submit**. 
    
## <a name="create-an-app-query"></a>Crear una consulta de aplicación

Se recomienda usar la vista avanzada, que tiene el siguiente aspecto: 

![Vista avanzada](media/OCAS-OAuthAppsAdvQueryView.png)

En la barra de consulta de la aplicación, si ve **avanzadas**, está usando la vista básica. Haga clic en (o puntee) **avanzada** para ir a la vista avanzada. 

![Vista básica](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. En la barra de consulta, use la lista **seleccionar un filtro** para elegir una opción. 
    - **Aplicación** Aplicaciones con determinados nombres
    - **Estado** de la aplicación Aplicaciones basadas en su estado (aprobada, prohibida o no determinada)
    - **Uso** de la comunidad Aplicaciones basadas en los niveles de uso de la comunidad (inusual, poco frecuente o común)
    - **Nivel de permisos** Aplicaciones basadas en determinados niveles de permisos 
    - **Permisos** Aplicaciones que requieren determinados permisos
    - **Publicador**  Aplicaciones de determinados editores
    - **Usuario** Aplicaciones que un usuario concreto ha autorizado
   
2. Seleccione **es igual** a o no **es igual**a y, a continuación, especifique un valor para el filtro.
    
3. Para agregar más filtros, seleccione el signo más (![Agregar un icono de filtro para consultar aplicaciones](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)) y, a continuación, repita los pasos 2 y 3.
    
4. Para quitar un filtro, seleccione la x (![Quitar un icono de filtro para consultar aplicaciones](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)) que se encuentra junto a un nombre de filtro.
    
Los filtros se aplican automáticamente y la lista de aplicaciones se actualiza en consecuencia.
  
## <a name="next-steps"></a>Pasos siguientes

- [Revisar y realizar acciones en las alertas](review-office-365-cas-alerts.md)
    
- Revisar los [orígenes de datos y los registros de tráfico web para Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)
    
- Revisar las [actividades de uso de Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    

