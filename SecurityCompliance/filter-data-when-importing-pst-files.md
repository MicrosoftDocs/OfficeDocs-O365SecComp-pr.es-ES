---
title: Filtrar datos al importar archivos PST a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
description: 'Usar la nueva característica de importación inteligente en el servicio Office 365 importación para filtrar los elementos que realmente obtengan importa a los buzones de correo de destino. Importación inteligente le permite decidir proactivamente qué importación y qué se va a dejar detrás de los datos. Importación inteligente también proporciona conocimientos sobre los datos que va a importar a Office 365. '
ms.openlocfilehash: 723a2e05a1f5d256e99bcf8497643435d0c98a23
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535607"
---
# <a name="filter-data-when-importing-pst-files-to-office-365"></a>Filtrar datos al importar archivos PST a Office 365

Usar la nueva característica de importación inteligente en el servicio Office 365 importación para filtrar los elementos en los archivos PST que realmente obtengan importa a los buzones de correo de destino. Así es cómo funciona:
  
- Después de crear y enviar un trabajo de importación de archivos PST, se cargan los archivos PST en un área de almacenamiento de Azure en la nube de Microsoft.
    
- Office 365 analiza los datos en los archivos PST, de forma segura, mediante la identificación de la antigüedad de los elementos del buzón de correo y los tipos de mensaje diferentes incluidos en los archivos PST.
    
- Cuando se completa el análisis y están listos para importar los datos, tiene la opción para importar todos los datos en los archivos PST que aparece o recortar los datos que se importan mediante la configuración de filtros que controlan qué datos obtiene importados. Por ejemplo, puede elegir para:
    
  - Importar sólo los elementos de una determinada antigüedad.
    
  - Importar tipos de mensaje seleccionado.
    
  - Excluir los mensajes enviados o recibidos por personas específicas.
    
- Después de configurar la configuración del filtro, Office 365 importa sólo los datos que cumpla los criterios de filtrado a los buzones de correo de destino especificados en el trabajo de importación.
    
El gráfico siguiente muestra el proceso de importación inteligente y resalta las tareas que realizar y las tareas realizadas por Office 365.
  
![El proceso de importación inteligente en Office 365](media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a>Antes de empezar

- Los pasos descritos en este tema se suponen que se ha creado un trabajo de importación de PST en el servicio Office 365 importar mediante el uso de carga de red o de trasvase de registros de unidad. Para obtener instrucciones detalladas, consulte uno de los siguientes temas:
    
  - [Usar la carga en la red para importar archivos PST en Office 365](use-network-upload-to-import-pst-files.md)
    
  - [Usar el envío de unidades para importar los archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- Después de crear un trabajo de importación mediante el uso de carga de red, el estado del trabajo de importación en la importación de página en Office 365 seguridad &amp; centro de cumplimiento se establece en el **análisis en curso**, lo que significa que Office 365 es analizar los datos en los archivos PST que cargado. Haga clic en **Actualizar**![actualizar](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) para actualizar el estado para el trabajo de importación. 
    
- Para la unidad de envío de trabajos de importación, los datos se analizarán por Office 365 después de recibe su unidad de disco duro de personal del centro de datos de Microsoft y carga los archivos PST en el área de almacenamiento de Azure para su organización.
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a>Filtrar los datos que obtienen importados a buzones de correo

Una vez que haya creado un archivo PST trabajo de importación, siga estos pasos para filtrar los datos antes de importarlo a Office 365.
  
1. Vaya a [https://protection.office.com/](https://protection.office.com/) e iniciar sesión con las credenciales para una cuenta de administrador de la organización de Office 365. 
    
2. En el panel izquierdo de la seguridad de Office 365 &amp; centro de cumplimiento, haga clic en **el gobierno de datos** \> **importación**.
    
    Los trabajos de importación para la organización se enumeran en la página **Importar** . Tenga en cuenta que el valor de **Análisis completado** en la columna **estado** indica los trabajos de importación que se han analizado por Office 365 y está listo para importar. 
    
    ![Estado de análisis completado indica que Office 365 analizados por los datos de los archivos PST](media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. Haga clic en **listo para importar a Office 365** para el trabajo de importación que se va a completar. 
    
    Se muestra un marcha página con información acerca de los archivos PST y otra información sobre el trabajo de importación.
    
4. Haga clic en **importar a Office 365**.
    
    Se abrirá la página **filtrar los datos** . Contiene entendimiento de datos acerca de los datos en los archivos PST para el trabajo de importación, incluida información acerca de la antigüedad de los datos. 
    
    ![El filtro de la página de datos muestra los conocimientos de los datos de los archivos PST para el trabajo de importación](media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. En función de si desea o no que recortar los datos que se importan a Office 365, en **que desee filtrar los datos?**, siga uno de los siguientes procedimientos:
    
    r., haga clic en **Sí, deseo filtrarla antes de importar** para recortar los datos que se importan y, a continuación, haga clic en **siguiente**.
    
    Se muestra la página **Importar datos a la página de Office 365** con conocimientos detallada de datos desde el análisis que realizan de Office 365. 
    
    ![Office 365 muestra datos detallados el conocimiento de su análisis de los archivos PST](media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    En el gráfico en esta página se muestra la cantidad de datos que se va a importar. Información sobre cada tipo de mensaje que se encuentran en los archivos PST se muestra en el gráfico. Puede mover el cursor por encima de cada barra para mostrar información específica acerca de ese tipo de mensaje. También es una lista desplegable con valores de edad diferentes basándose en el análisis de los archivos PST. Cuando selecciona una vigencia en la lista desplegable, el gráfico se actualiza para mostrar la cantidad de datos que se va a importar para la antigüedad seleccionada. 
    
    b. para configurar filtros de adición para reducir la cantidad de datos que se importan, haga clic en **más opciones de filtrado**.
    
    ![Configurar los filtros en la página de opciones más para recortar los datos que se importan](media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    Puede configurar estos filtros:
    
      - **Vigencia** - seleccionar una vigencia de modo que sólo los elementos que son más reciente que la edad especificada se va a importar. Vea la sección [obtener más información](filter-data-when-importing-pst-files.md#moreinfo) para obtener una descripción acerca de cómo Office 365 determina los depósitos de antigüedad para el filtro de **antigüedad** . 
    
      - **Tipo** : en esta sección se muestran todos los tipos de mensaje que se han encontrado en los archivos PST para el trabajo de importación. Puede desactivar una casilla junto a un tipo de mensaje que se desea excluir. Tenga en cuenta que no se puede excluir el otro tipo de mensaje. Vea la sección [obtener más información](filter-data-when-importing-pst-files.md#moreinfo) para obtener una lista de los elementos del buzón que se incluyen en la categoría de otra. 
    
      - **Los usuarios** , puede excluir los mensajes que se envían o reciben por personas específicas. Para excluir las personas que aparecen en el campo de: campo a: campo o el campo Cc: campo de mensajes, haga clic en **excluir los usuarios** junto a ese tipo de destinatario. Escriba la dirección de correo electrónico (dirección SMTP) de la persona, haga clic en **Agregar**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) para agregarlos a la lista de usuarios excluidos para ese tipo de destinatario y, a continuación, haga clic en **Guardar** para guardar la lista de usuarios excluidos. 
    
        > [!NOTE]
        > Office 365 no mostrar entendimiento de datos resultantes de la configuración del filtro de **personas** . Sin embargo, si establece este filtro para excluir los mensajes enviados o recibidos por personas específicas, esos mensajes se excluirán durante el proceso de importación real. 
  
    c. Haga clic en **Aplicar** en la marcha de **Opciones de filtrado más** página para guardar la configuración de filtro. 
    
    Los datos de conocimientos en la página **Importar datos a Office 365** se actualizan en función de las opciones de filtro, incluida la cantidad total de datos que se va a importar según la configuración del filtro. Tenga en cuenta que también se muestra un resumen de la configuración del filtro. Puede hacer clic en **Editar** junto a un filtro para cambiar la configuración si es necesario. 
    
    ![Toda la información de datos se actualiza en función de las opciones de filtro](media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    d. Haga clic en **siguiente**.
    
    Una página de estado se mostrará con las opciones de filtro. Una vez más, puede modificar cualquiera de las opciones de filtro.
    
    e. Haga clic en **Importar datos** para iniciar la importación. Tenga en cuenta que se muestra la cantidad total de datos que se va a importar. 
    
    O bien
    
    r., haga clic en **No, deseo importar todo** para importar todos los datos en los archivos PST a Office 365 y, a continuación, haga clic en **siguiente**.
    
    b. en la página **Importar datos a Office 365** , haga clic en **Importar datos** para iniciar la importación. Tenga en cuenta que se muestra la cantidad total de datos que se va a importar. 
    
6. En la página de **importación** , haga clic en **Actualizar** ![actualizar](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png). El estado del trabajo de importación de se muestra en la columna **estado** . 
    
7. Haga clic en la importación el trabajo para mostrar información más detallada, como el estado de cada archivo PST y la configuración del filtro que haya configurado.

  
## <a name="more-information"></a>Más información

- ¿Cómo determina los incrementos para el filtro de antigüedad Office 365? Cuando Office 365 analiza un archivo PST, lo examina la marca de tiempo enviados o recibidos de cada elemento (si un elemento tiene una marca de tiempo enviado y recibido, está seleccionada la fecha más antigua). A continuación, Office 365 se busca en el valor de año para esa marca de hora y la compara con la fecha actual para determinar la antigüedad del elemento. Estos años, a continuación, se utilizan como los valores en la lista desplegable para el filtro de **antigüedad** . Por ejemplo, si un archivo PST tiene los mensajes de 2016, 2015 y 2014, a continuación, en el filtro de **antigüedad de** los valores sería **1 año**, **2 años**y **3 años**.
    
- En la siguiente tabla se enumera los tipos de mensajes que se incluyen en la categoría de **otra** en el filtro de **tipo** sobre la marcha **más opciones de** página (vea el paso 5b en el procedimiento anterior). Actualmente, no se puede excluir elementos de la categoría "Otros" al importar archivos pst a Office 365. 
    
    |**Identificador de clase de mensaje**|**Elementos del buzón que usan esta clase de mensaje**|
    |:-----|:-----|
    |IPM. Actividad  <br/> |Entradas del diario  <br/> |
    |IPM. Documento  <br/> |Documentos y archivos (no se adjunta a un mensaje de correo electrónico)  <br/> |
    |IPM. Archivo  <br/> |(igual que IPM. Documento)  <br/> |
    |IPM. Note.IMC.Notification  <br/> |Informes enviados por Internet Mail Connect, que es la puerta de enlace de Exchange Server a Internet  <br/> |
    |IPM. Note.Microsoft.Fax  <br/> |Mensajes de fax  <br/> |
    |IPM. Note.Rules.Oof.Template.Microsoft  <br/> |Mensajes de respuesta automática de fuera de la oficina  <br/> |
    |IPM. Note.Rules.ReplyTemplate.Microsoft  <br/> |Respuestas enviadas por una regla de bandeja de entrada  <br/> |
    |IPM. OLE. Clase  <br/> |Excepciones de una serie periódica  <br/> |
    |IPM. Recall.Report  <br/> |Informes de recuperación de mensaje  <br/> |
    |IPM. Remoto  <br/> |Mensajes de correo remoto  <br/> |
    |IPM. Informe  <br/> |Informes de estado de elemento  <br/> |
