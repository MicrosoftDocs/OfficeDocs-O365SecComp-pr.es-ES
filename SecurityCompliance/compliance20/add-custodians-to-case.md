---
title: Agregar custodios a un caso de eDiscovery avanzado
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
ms.openlocfilehash: 8cc3d7db959c31c4657bb8c0d270f014e598e143
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155342"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Agregar custodios a un caso de eDiscovery avanzado

Use la herramienta de administración de custodios integrada en eDiscovery avanzado para coordinar sus flujos de trabajo en la administración de custodios y para identificar los orígenes de datos relevantes y relevantes asociados a un caso. Cuando se agrega un custodio, el sistema puede identificar y retener automáticamente el buzón de Exchange y la cuenta de OneDrive para la empresa. Durante el proceso de detección de la investigación, también puede identificar orígenes de datos adicionales (como buzones, sitios o equipos) a los que un custodio ha tenido acceso o ha contribuido. En esta situación, puede usar la herramienta de administración de custodios para asociar esos orígenes de datos a un custodio específico. Después de agregar custodios a un caso y asociar otro origen de datos con ellos, puede conservar rápidamente los datos y buscar en los datos de las privaciones.

Use el siguiente flujo de trabajo para agregar y administrar custodios en casos avanzados de eDiscovery. 

![Pestaña de administración de custodios](../media/CustodianMgtPage.png)

## <a name="before-you-begin"></a>Antes de empezar

Para agregar custodios a un caso, debe ser miembro del grupo de roles eDiscovery Manager. Esto le proporcionará los permisos necesarios para agregar custodios a un caso y realizar una retención en los orígenes de datos de Private.


## <a name="step-1-add-potential-custodians"></a>Paso 1: agregar custodios potenciales

El primer paso es identificar y agregar custodios al caso.

1. En la Página principal de **EDiscovery avanzado** , haga clic en el caso al que quiera agregar custodios. 
 
2. Haga clic **** en la ficha custodios y, a continuación, haga clic en **+ Agregar custodios**.

3. Busque los custodios que se agregarán al caso. Escriba la primera parte del nombre de una persona para mostrar a los usuarios de Azure Active Directory de la organización. Cuando encuentre la persona correcta, haga clic en su nombre para agregarla a la lista.

   ![Identificar custodios potenciales](../media/AddCustodianStep1.png)
 
4. Una vez que haya agregado todos los custodios pertinentes, haga clic en **siguiente** para seleccionar los orígenes de datos principales de los custodios.
  
## <a name="step-2-select-custodian-data-sources"></a>Paso 2: seleccionar orígenes de datos custodios

Una vez agregados los custodios, la herramienta de custodio le ayudará a identificar los orígenes de datos principales que posee cada custodio; concretamente, estas ubicaciones de datos son el buzón de Exchange y la cuenta de OneDrive del custodio. 

Para identificar los orígenes de datos de custodios: 

1. Para seleccionar el buzón de Exchange para todos los custodios, haga clic en la casilla de verificación **Exchange** situada en la parte superior de la columna. Tenga en cuenta que puede anular la selección de la casilla de verificación de cualquier custodio específico para quitar un buzón de correo como una ubicación de privación. Como alternativa, puede dejar la casilla de verificación **Exchange** en la parte superior de la columna desactivada y, a continuación, seleccionar la casilla para los custodios individuales. 
 
   ![Seleccionar orígenes de datos de Private](../media/AddCustodianStep2.png)
 
2. Repita lo mismo para las cuentas de OneDrive de los custodios. 

    Después de seleccionar los orígenes de datos de custodios, el sistema intenta identificar y comprobar automáticamente estos orígenes de datos y, a continuación, los agrega al caso como orígenes de datos asociados con los custodios.
 
4. Haga clic en **siguiente** para empezar a asociar orígenes de datos adicionales a los custodios en el caso.

## <a name="step-3-associate-additional-data-sources-to-a-custodian"></a>Paso 3: asociar orígenes de datos adicionales a un custodio

Según el caso que esté investigando, es posible que también necesite buscar (y conservar contenido en) buzones de correo a los que puede tener acceso un custodio específico, Office 365 grupos de los que un custodio es actualmente miembro o los sitios a los que también tiene acceso un custodio. Por lo tanto, además de los principales orígenes de datos del custodio que especificó en el paso anterior, también puede asociar orígenes de datos de Office 365 adicionales con un custodio en el caso. 

Para asignar buzones de correo, sitios o equipos a un custodio específico:

1. En la página **seleccionar orígenes de datos adicionales** , haga clic en **Agregar** en la fila del custodio específico. 
  
   ![Asignar orígenes de datos adicionales](../media/AddCustodianStep3.PNG)

2. En la página de flotante, puede especificar un origen de datos de cualquiera de los servicios de Office 365 siguientes:
  
   -  **Correo electrónico de Exchange** : haga clic en **elegir usuarios, grupos o equipos** y, a continuación, haga clic en **elegir usuarios, grupos o equipos** de nuevo. Use el cuadro de búsqueda para encontrar los buzones de correo que desea asociar con el custodio. Para especificar los buzones que se asignarán al custodio seleccionado, use el cuadro de búsqueda para buscar los buzones de usuario y los grupos de distribución. También puede asignar el buzón asociado para un grupo de Office 365 o un equipo de Microsoft. Active la casilla de verificación usuario, grupo, equipo, haga clic en **elegir**y, a continuación, haga clic en **listo**.

        > [!NOTE]
        > Al hacer clic en elegir usuarios, grupos o equipos para especificar los buzones, el selector de buzones que se muestra está vacío. Esto se ha diseñado así para mejorar el rendimiento. Para agregar un buzón de correo a esta lista, escriba un nombre o alias (un mínimo de 3 caracteres) en el cuadro de búsqueda.
     
     - **Sitios de SharePoint** : haga clic en **elegir sitios** y, a continuación, haga clic en **elegir sitios** de nuevo para mostrar una lista de los sitios de SharePoint de la organización. Para asociar un sitio con el custodio, puede seleccionar un sitio de la lista o puede escribir la dirección URL de un sitio diferente o de un sitio asociado con un grupo de Office 365, un equipo de Microsoft o una cuenta de OneDrive.
     
     - **Teams** : haga clic en **elegir** Teams y, a continuación, haga clic en **elegir Teams** de nuevo para mostrar una lista de Microsoft Teams a la que pertenece actualmente el custodio. Seleccione los equipos que quiera agregar a su custodio. Una vez seleccionado, el sistema identificará automáticamente & seleccionar el sitio de SharePoint y el buzón de grupo asociados a ese equipo de Microsoft. Haga clic en **elegir**y, a continuación, en **listo**.

       ![Orígenes de datos de asignación](../media/AddCustodianStep4.PNG)
        
      > [!NOTE]
      > Para asociar un equipo adicional con un custodio, debe agregar por separado el buzón y el sitio asociados con el equipo mediante el **correo de Exchange** y las ubicaciones de los **sitios de SharePoint** .

Una vez que haya terminado de asociar los orígenes de datos adicionales con los custodios, puede ver el número total de buzones de correo, sitios y equipos asociados a cada custodio en la **página seleccionar orígenes de datos adicionales**. Cuando haya finalizado los orígenes de datos relevantes para un custodio específico, esta asociación se mantendrá y se usará durante las fases de recopilación, procesamiento y revisión del flujo de trabajo de eDiscovery.

## <a name="step-4-place-custodians-on-hold"></a>Paso 4: poner los custodios en espera

Una vez que haya finalizado los custodios y los orígenes de datos que se deben agregar al caso, también puede poner algunos o todos los custodios en retención. Cuando se pone un custodio en espera, todo el contenido en todas las ubicaciones de contenido que están asociados a la custodio se conserva hasta que se elimina la retención o se libera el custodio del. En algunos casos, es posible que quiera agregar custodios a un caso sin ponerlos en retención.

Para poner los custodios y los orígenes de datos en espera:

1. En la página **poner una retención en la página de custodios seleccionada** , haga clic en la casilla " **suspensión** " situada en la parte superior de la columna para poner todos los custodios en retención. Tenga en cuenta que puede anular la selección de la casilla de verificación de cualquier custodio específico para quitarlo de la suspensión. Como alternativa, puede dejar la casilla " **mantener presionado** " en la parte superior de la columna desactivada y, a continuación, activar la casilla para los custodios individuales. 
 
   ![Retenciones de posición](../media/AddCustodianStep5.PNG)

2. Compruebe las selecciones de retención de custodios y haga clic en **Finalizar**.

Si no coloca una retención en una custodia, el custodio y sus orígenes de datos asociados se agregarán al caso, pero el contenido de dichos orígenes de datos no se colocará en retención.

Una vez que un custodio se coloca en retención, se creará automáticamente una directiva de retención de custodios que contiene todas las fuentes de la Private. Para ver esta directiva:

1. En la página **principal** del caso, haga clic en la pestaña **suspensiones** y, a continuación, haga clic en **CustodianHold-GUID**  

2. En la página flotante, haga clic en **Editar suspensión** para ver todos los orígenes de datos de custodios que se encuentran en suspensión.

