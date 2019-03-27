---
title: Filtrar datos al importar archivos PST a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
description: 'Use la nueva característica de importación inteligente en el servicio de importación de Office 365 para filtrar los elementos que realmente se importan a los buzones de correo de destino. La importación inteligente le permite decidir de forma proactiva qué datos importar y qué dejar detrás. La importación inteligente también proporciona información sobre los datos que va a importar a Office 365. '
ms.openlocfilehash: 60177908f48c6de28578f8d8ba6329fb1bf8cb47
ms.sourcegitcommit: c0d4fe3e43e22353f30034567ade28330266bcf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30900039"
---
# <a name="filter-data-when-importing-pst-files-to-office-365"></a>Filtrar datos al importar archivos PST a Office 365

Use la nueva característica de importación inteligente en el servicio de importación de Office 365 para filtrar los elementos de los archivos PST que realmente se importan a los buzones de correo de destino. Aquí se muestra cómo funciona:
  
- Después de crear y enviar un trabajo de importación de PST, los archivos PST se cargan en un área de almacenamiento de Azure en la nube de Microsoft.
    
- Office 365 analiza los datos de los archivos PST, de forma segura, mediante la identificación de la antigüedad de los elementos del buzón y los distintos tipos de mensajes incluidos en los archivos PST.
    
- Una vez que se ha completado el análisis y los datos están listos para importar, tiene la opción de importar todos los datos de los archivos PST tal cual o recortar los datos que se importan mediante la configuración de filtros que controlan los datos que se importan. Por ejemplo, puede elegir entre:
    
  - Importa sólo los elementos de una antigüedad determinada.
    
  - Importar los tipos de mensajes seleccionados.
    
  - Excluir los mensajes enviados o recibidos por personas específicas.
    
- Después de configurar las opciones de filtro, Office 365 importa solo los datos que cumplan los criterios de filtrado en los buzones de correo de destino especificados en el trabajo de importación.
    
En el gráfico siguiente se muestra el proceso de importación inteligente y se resaltan las tareas que se realizan y las tareas realizadas por Office 365.
  
![Proceso de importación inteligente en Office 365](media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a>Antes de empezar

- En los pasos de este tema se supone que ha creado un trabajo de importación de PST en el servicio de importación de Office 365 mediante carga de red o envío de unidades. Para obtener instrucciones paso a paso, consulte uno de los siguientes temas:
    
  - [Usar la carga en la red para importar archivos PST en Office 365](use-network-upload-to-import-pst-files.md)
    
  - [Usar el envío de unidades para importar los archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- Después de crear un trabajo de importación mediante la carga en la red, el estado del trabajo de importación en la página importar en &amp; el centro de seguridad y cumplimiento de Office 365 se establece en **análisis en curso**, lo que significa que Office 365 está analizando los datos de los archivos PST que se cargado. Haga ****![clic en](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) actualizar actualización para actualizar el estado del trabajo de importación. 
    
- Para la unidad de envío de trabajos de importación, Office 365 analizará los datos después de que el personal del centro de datos de Microsoft reciba el disco duro y cargue los archivos PST en el área de almacenamiento de Azure de su organización.
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a>Filtrar datos que se importan a los buzones

Después de crear un trabajo de importación de PST, siga estos pasos para filtrar los datos antes de importarlos a Office 365.
  
1. Vaya a [https://protection.office.com/](https://protection.office.com/) e inicie sesión con las credenciales de una cuenta de administrador en la organización de Office 365. 
    
2. en el panel izquierdo del centro &amp; de seguridad y cumplimiento de Office 365, haga clic en **importación**de gobierno \> de **datos** .
    
    Los trabajos de importación de la organización aparecen en la página **importar** . Tenga en cuenta que el valor de **análisis completado** en la columna **Estado** indica los trabajos de importación analizados por Office 365 y que están listos para que los importe. 
    
    ![El estado completo del análisis indica que Office 365 ha analizado los datos de los archivos PST](media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. Haga clic en **listo para importar a Office 365** para el trabajo de importación que desea completar. 
    
    Se muestra una página emergente con información sobre los archivos PST y otra información sobre el trabajo de importación.
    
4. Haga clic en **importar a Office 365**.
    
    Se mostrará la página **filtrar los datos** . Contiene datos sobre los datos de los archivos PST para el trabajo de importación, incluida la información sobre la antigüedad de los datos. 
    
    ![La página filtrar los datos muestra datos de los archivos PST para el trabajo de importación](media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. En función de si desea recortar los datos que se importaron a Office 365, en **¿desea filtrar los datos?**, siga uno de estos procedimientos:
    
    a. Haga clic en **sí, deseo filtrarla antes** de importarla para recortar los datos que se van a importar y, a continuación, haga clic en **siguiente**.
    
    La página **importar datos a office 365** se muestra con información detallada de los datos del análisis que ha realizado Office 365. 
    
    ![Office 365 muestra información detallada sobre los datos de análisis de los archivos PST](media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    El gráfico de esta página muestra la cantidad de datos que se van a importar. La información sobre cada tipo de mensaje que se encuentra en los archivos PST se muestra en el gráfico. Puede desplazar el cursor sobre cada barra para mostrar información específica acerca de ese tipo de mensaje. También hay una lista desplegable con valores de antigüedad diferentes basados en el análisis de los archivos PST. Cuando selecciona una antigüedad en la lista desplegable, el gráfico se actualiza para mostrar la cantidad de datos que se importarán para la antigüedad seleccionada. 
    
    b. Para configurar los filtros de adición para reducir la cantidad de datos que se importan, haga clic en **más opciones de filtrado**.
    
    ![Configure los filtros de la página más opciones para recortar los datos que se importan](media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    Puede configurar estos filtros:
    
      - **Edad** : Seleccione una antigüedad para que solo se importen los elementos que sean más recientes que la edad especificada. Consulte la sección [More Information](#more-information) para obtener una descripción de cómo Office 365 determina los depósitos de antigüedad para el filtro de **antigüedad** . 
    
      - **Tipo** : esta sección muestra todos los tipos de mensajes que se encontraron en los archivos PST para el trabajo de importación. Puede desactivar una casilla junto a un tipo de mensaje que quiera excluir. Tenga en cuenta que no puede excluir el otro tipo de mensaje. Consulte la sección [More Information](#more-information) para obtener una lista de los elementos de buzón que se incluyen en la otra categoría. 
    
      - **Usuarios** : puede excluir los mensajes enviados o recibidos por personas específicas. Para excluir a las personas que aparecen en el campo de:, a: campo o al campo CC: de los mensajes, haga clic en **excluir usuarios** junto al tipo de destinatario. Escriba la dirección de correo electrónico (dirección SMTP) de la persona ****![, haga clic](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) en Agregar nuevo icono para agregarlas a la lista de usuarios excluidos para el tipo de destinatario y, a continuación, haga clic en **Guardar** para guardar la lista de usuarios excluidos. 
    
        > [!NOTE]
        > Office 365 no muestra datos que se deriven de la configuración del filtro de **personas** . Sin embargo, si establece este filtro para excluir los mensajes enviados o recibidos por personas específicas, dichos mensajes se excluirán durante el proceso de importación real. 
  
    c. Haga clic en **aplicar** en la página **más opciones de filtrado** , volar hacia fuera, para guardar la configuración del filtro. 
    
    Los datos que se encuentran en la página **importar datos a Office 365** se actualizan en función de la configuración del filtro, incluida la cantidad total de datos que se importarán según la configuración del filtro. Tenga en cuenta que también se muestra un resumen de la configuración del filtro. Puede hacer clic en **Editar** junto a un filtro para cambiar la configuración si es necesario. 
    
    ![La información de datos se actualiza en función de la configuración del filtro.](media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    d. Haga clic en **Siguiente**.
    
    Se muestra una página de estado que muestra la configuración del filtro. De nuevo, puede editar cualquiera de las opciones de configuración del filtro.
    
    e. Haga clic en **importar datos** para iniciar la importación. Tenga en cuenta que se muestra la cantidad total de datos que se van a importar. 
    
    O bien
    
    a. Haga clic en **no, deseo importar todo** para importar todos los datos de los archivos PST a Office 365 y, a continuación, haga clic en **siguiente**.
    
    b. En la página **importar datos a Office 365** , haga clic en **importar datos** para iniciar la importación. Tenga en cuenta que se muestra la cantidad total de datos que se van a importar. 
    
6. En la página **importar** , haga clic en](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) **Actualizar** ![actualización. El estado del trabajo de importación se muestra en la columna **Estado** . 
    
7. Haga clic en importar el trabajo para mostrar información más detallada, como el estado de cada archivo PST y la configuración de filtro que ha configurado.

  
## <a name="more-information"></a>Más información

- ¿Cómo determina Office 365 los incrementos del filtro de antigüedad? Cuando Office 365 analiza un archivo PST, busca en la marca de tiempo de envío o de recepción de cada elemento (si un elemento tiene una marca de tiempo enviada y recibida, se selecciona la fecha más antigua). Después, Office 365 examina el valor del año para esa marca de tiempo y lo compara con la fecha actual para determinar la antigüedad del elemento. A continuación, estas edades se usan como los valores de la lista desplegable para el filtro de **antigüedad** . Por ejemplo, si un archivo PST tiene mensajes de 2016, 2015 y 2014, los valores del filtro de **antigüedad** serían **1 año**, **2 años**y **3 años**.
    
- En la siguiente tabla se enumeran los tipos de mensajes que se incluyen en la **otra** categoría del filtro **tipo** en la página **más opciones** (vea el paso 5B del procedimiento anterior). Actualmente, no puede excluir elementos de la categoría "Other" al importar archivos PST a Office 365. 
    
    |**Id. de clase de mensajes**|**Elementos de buzón que usan esta clase de mensaje**|
    |:-----|:-----|
    |IPM.Activity  <br/> |Entradas del Diario  <br/> |
    |IPM.Document  <br/> |Documentos y archivos (no adjuntos a un mensaje de correo electrónico)  <br/> |
    |IPM. Archivo  <br/> |(igual que IPM. Documento  <br/> |
    |IPM. Note.IMC.Notification  <br/> |Informes enviados por Internet Mail Connect, que es la puerta de enlace de Exchange Server a Internet  <br/> |
    |IPM. Note. Microsoft. fax  <br/> |Mensajes de fax  <br/> |
    |IPM. Note. rules. OOF. template. Microsoft  <br/> |Mensajes de respuesta automática de fuera de la oficina  <br/> |
    |IPM. Note.Rules.ReplyTemplate.Microsoft  <br/> |Respuestas enviadas por una regla de bandeja de entrada  <br/> |
    |IPM.OLE.Class  <br/> |Excepciones para una serie periódica  <br/> |
    |IPM. Recall.Report  <br/> |Informes de recuperación de mensajes  <br/> |
    |IPM.Remote  <br/> |Mensajes de correo remotos  <br/> |
    |IPM. Informe  <br/> |Informes de estado de elementos  <br/> |
