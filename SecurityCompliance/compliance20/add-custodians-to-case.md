---
title: Agregar custodios a un caso de eDiscovery avanzado (versión preliminar)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: fe208f4a9f7927d8481d5c6ec8b901baafb98626
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243598"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a>Agregar custodios a un caso de eDiscovery avanzado (versión preliminar)

Mediante eDiscovery avanzado (versión preliminar), puede aprovechar la herramienta de administración de custodios incorporada para coordinar sus flujos de trabajo en la administración de custodios y para identificar los orígenes de datos relevantes y relevantes dentro de un caso. Cuando se agrega un custodio, el sistema puede identificar automáticamente y realizar suspensiones en el buzón principal de Exchange y en el sitio de OneDrive para la empresa. Al realizar la detección, también puede descubrir y asignar los sitios o buzones de correo adicionales que un custodio haya accediendo en el pasado o Teams de los que un custodio es miembro de hoy.

Use el siguiente flujo de trabajo para agregar y administrar custodios en escenarios de eDiscovery avanzado (vista previa) en el centro de seguridad & cumplimiento. 

![Pestaña de administración de custodios](../media/CustodianMgtPage.png)


## <a name="step-1-identify-potential-custodians"></a>Paso 1: identificar custodios potenciales

El primer paso es identificar los custodios adecuados para su caso. Para agregar custodios a un caso, debe ser miembro del grupo de roles de administradores de eDiscovery o administradores de exhibición de documentos electrónicos.   

![Identificar custodios potenciales](../media/AddCustodianStep1.png)

Para agregar custodios a un caso existente de eDiscovery avanzado (versión preliminar):

1. En la página exhibición avanzada de documentos electrónicos **(vista previa)** , vaya a su caso.
 
2. Una vez que haya seleccionado un caso, vaya a **** la pestaña custodios y haga clic en **+ Agregar custodio**. 
 
3. Elija los custodios que desea agregar al caso. Puede empezar a escribir para buscar y seleccionar los usuarios de Azure Active Directory de su organización.
 
4. Una vez que haya finalizado la lista de custodios, haga clic en **siguiente** para identificar los posibles orígenes de datos. 
  
## <a name="optional-step-2-select-custodian-data-sources"></a>Opcional Paso 2: seleccionar orígenes de datos custodios

Una vez que haya agregado custodios a un caso, puede aprovechar Office 365 para ayudarle a identificar y preservar los principales orígenes de datos de custodios. El siguiente paso de este flujo de trabajo es seleccionar los orígenes de datos que pertenecen a los custodios especificados en el paso 1. 

![Seleccionar orígenes de datos de Private](../media/AddCustodianStep2.png)

Para identificar los orígenes de datos de custodios: 

1. Para cada custodio, seleccione **Exchange** si desea que el sistema identifique y agregue automáticamente el buzón de correo principal de Exchange del custodio. 
 
2. Para cada custodio, seleccione **onedrive** si desea que el sistema identifique y agregue automáticamente la dirección URL principal de onedrive del custodio. 

    Después de realizar las selecciones, el sistema intentará identificar los orígenes de datos automáticamente y agregarlos a su caso.
 
4. Haga clic en **siguiente** para comenzar a asignar orígenes de datos adicionales a su custodio.

## <a name="optional-step-3-map-additional-data-sources"></a>Opcional Paso 3: asignar orígenes de datos adicionales

Según el caso, es posible que también desee agregar buzones que un custodio dado puede haber usado anteriormente, grupos en los que un custodio es actualmente miembro o sitios a los que un custodio tenía acceso en el pasado. Además de los orígenes de datos de custodios principales, puede Agregar orígenes de datos de Office 365 adicionales a un custodio o aprovechar Office 365 para ayudarle a identificar también los orígenes de datos potencialmente relevantes. 

![Asignar orígenes de datos adicionales](../media/AddCustodianStep3.PNG)

Para asignar buzones de correo, sitios o equipos a un custodio específico:
1. Seleccione **Agregar** para asignar ubicaciones de contenido, como buzones de correo, sitios y equipos, a un custodio específico. 

2. En el control flotante, especifique lo siguiente ![: asignar orígenes de datos](../media/AddCustodianStep4.PNG)
  -  **Buzones de Exchange** : haga clic en **elegir usuarios, grupos o equipos** y, a continuación, haga clic en **elegir usuarios, grupos o equipos** de nuevo. Para especificar los buzones que se asignarán al custodio seleccionado, use el cuadro de búsqueda para buscar los buzones de usuario y los grupos de distribución. También puede asignar el buzón asociado para un grupo de Office 365 o un equipo de Microsoft. Active la casilla de verificación usuario, grupo, equipo, haga clic en **elegir**y, a continuación, haga clic en **listo**.

        > [!NOTE]
        > Al hacer clic en elegir usuarios, grupos o equipos para especificar los buzones, el selector de buzones que se muestra está vacío. Esto se ha diseñado así para mejorar el rendimiento. Para agregar personas a esta lista, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda.
     
     - **Sitios de SharePoint** : haga clic en **elegir sitios** y, a continuación, haga clic en **elegir sitios** de nuevo para especificar sitios de SharePoint y OneDrive para la empresa adicionales que quiera asignar al custodio seleccionado. También puede Agregar la dirección URL del sitio de SharePoint para un grupo de Office 365 o un equipo de Microsoft. Escriba la dirección URL de cada sitio que quiera asignar. Haga clic en **elegir**y, a continuación, en **listo**.
     - **Microsoft Teams** : haga clic en **elegir Teams** y, a continuación, haga clic en **elegir Teams** de nuevo para ver una lista de los grupos de Microsoft Teams de los que el custodio es miembro de hoy. Seleccione los equipos que quiera agregar a su custodio. Una vez seleccionado, el sistema identificará automáticamente & seleccionar el sitio de SharePoint y el buzón de grupo asociados a ese equipo de Microsoft. Haga clic en **elegir**y, a continuación, en **listo**.
        
      > [!NOTE]
      > Para agregar Microsoft Teams, tendrá que agregar por separado el buzón de correo y el sitio de SharePoint, como se muestra más arriba.

Una vez que haya terminado de asignar sus orígenes, puede ver los buzones de correo totales, los sitios y los equipos de los custodios que acaba de agregar. Cuando haya finalizado los orígenes de datos relevantes para un custodio específico, esta asignación se mantendrá y se extenderá a los flujos de trabajo de recopilación, procesamiento y revisión de la exhibición de documentos electrónicos. 

## <a name="optional-step-4-place-custodians-on-hold"></a>Opcional Paso 4: poner los custodios en espera

![ReTenciones de posición](../media/AddCustodianStep5.PNG)

Una vez que haya finalizado los custodios y los orígenes de datos que desea agregar a su caso, puede, de manera opcional, poner algunos o todos los custodios en retención. Cuando se pone un custodio en espera, el contenido asignado a ese usuario se conserva hasta que se libere el custodio del caso o hasta que se elimine la retención. En algunos casos, es posible que quiera agregar custodios a un caso sin ponerlos en retención. 

Para poner los custodios y los orígenes de datos seleccionados en espera:

1. Compruebe las selecciones de custodios y seleccione la casilla para poner cada custodio en espera. Una vez que un custodio se coloca en retención, se creará automáticamente una directiva de retención de custodios que contiene todas las fuentes de la Private. Si la opción no está seleccionada, el custodio y los orígenes de datos seleccionados se agregarán al caso, pero el contenido no se conservará.

2. Vaya a la **** pestaña suspensiones y seleccione la **Directiva de retención**de custodios. 

3. Haga clic en **Editar** para ver todos los orígenes de datos de custodios seleccionados.

   
