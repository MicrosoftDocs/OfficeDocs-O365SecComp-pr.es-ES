---
title: Administrar personas de interés en investigaciones de datos (versión preliminar)
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
ms.openlocfilehash: d06dde60ae75cfea1bf1d79f445b613d20a76363
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257678"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a>Administrar personas de interés en investigaciones de datos (versión preliminar)

Las investigaciones de datos suelen incluir a personas de interés. Normalmente son personas que poseen los datos mal colocados, confidenciales o malintencionados que está investigando o que pretenden corregir. En **investigaciones de datos (versión preliminar)**, puede agregarlas para detectar sus orígenes de datos y usarlos en el ámbito de la búsqueda o ver información adicional, como el contacto, la ubicación y los registros de actividad. 


## <a name="add-people-of-interest"></a>Agregar personas de interés

En la pestaña **personas de interés** , puede Agregar personas de interés y descubrir sus orígenes de datos, como los buzoNes de Exchange o el sitio de OneDrive para la empresa, que puede usar para limitar la búsqueda. Cuando el objetivo es que los usuarios de interés, las búsquedas sean más exactas y precisas, ya que la herramienta vuelve a procesar los datos no indizados, como imágenes o tipos de archivo no admitidos. También puede ver su información de contacto, la información de ubicación y los registros de actividad que puede usar para iniciar las comunicaciones o investigar sus actividades. 

Para agregar personas de interés a una investigación:

1. En la página **investigaciones de datos (vista previa)** , vaya a su investigación.
 
2. Una vez que haya seleccionado una investigación, vaya a la pestaña **personas de interés** y haga clic en **+ Agregar personas de interés**. 
 
3. Elija las personas que desea agregar a la investigación. Puede empezar a escribir para buscar y seleccionar los usuarios de Azure Active Directory de su organización.
 
4. Una vez que haya finalizado la lista de personas de interés, haga clic en **siguiente** para asignar sus orígenes de datos. 

5. Opcional Para cada persona, seleccione **Exchange** para agregar el buzón de correo de Exchange principal de una persona y **onedrive** para agregar el sitio principal de onedrive para la empresa de la persona.

6. Opcional Haga clic en **siguiente** para agregar otros orígenes de datos que desee asociar a las personas de su interés.

7. Opcional Seleccione **Actualizar** para asignar ubicaciones de contenido, como buzones de correo, sitios y equipos a una persona. 

8. Opcional En el control flotante:
   
    -  **Buzones de Exchange** : haga clic en **elegir usuarios, grupos o equipos** y, a continuación, haga clic en **elegir usuarios, grupos o equipos** de nuevo. Para agregar más buzones, use el cuadro de búsqueda para buscar los buzones de usuario y los grupos de distribución. También puede Agregar buzones de correo que se usan para almacenar un grupo de Office 365 o una información de equipo de Microsoft. Active la casilla de verificación usuario, grupo, equipo, haga clic en **elegir**y, a continuación, haga clic en **listo**.

        > [!NOTE]
        > Al hacer clic en elegir usuarios, grupos o equipos para especificar los buzones, el selector de buzones que se muestra está vacío. Esto se ha diseñado así para mejorar el rendimiento. Para agregar personas a esta lista, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda.
     
     - **Sitios de SharePoint** : haga clic en **elegir sitios** y, a continuación, haga clic en **elegir sitios** de nuevo para especificar sitios adicionales de SharePoint y OneDrive para la empresa que wwant agregar a una persona. También puede Agregar la dirección URL del sitio de SharePoint para un grupo de Office 365 o un equipo de Microsoft. Escriba la dirección URL de cada sitio que quiera asignar. Haga clic en **elegir**y, a continuación, en **listo**.
     - **Microsoft Teams** : haga clic en **elegir Teams** y, a continuación, haga clic en **elegir Teams** de nuevo para ver una lista de los grupos de Microsoft Teams de los que la persona es miembro de hoy. Seleccione los equipos que desea agregar a la persona. Una vez seleccionado, el sistema identificará automáticamente & seleccionar el sitio de SharePoint y el buzón de grupo asociados a ese equipo de Microsoft. Haga clic en **elegir**y, a continuación, en **listo**.
        
      > [!NOTE]
      > Para agregar Microsoft Teams, tendrá que agregar por separado el buzón de correo y el sitio de SharePoint, como se muestra más arriba.

Una vez que haya terminado de asignar orígenes de datos a personas de interés, puede ver el Resumen de los buzones de correo totales, los sitios y los equipos que acaba de agregar. Si asigna otros orígenes de datos a personas de interés y el ámbito de la búsqueda por personas de interés, la asignación de documentos a personas de interés permanecerá a lo largo de la investigación, lo que facilita la organización de las pruebas o la generación de informes por parte de personas de interés. . 

## <a name="view-additional-people-of-interest-information"></a>Ver más personas de información de interés

En la pestaña **personas de interés** , haga clic en la persona que adeed. En un control flotante, verás:

- Información de contacto

  - **Nombre para mostrar**: el nombre de Peron que aparece en la libreta de direcciones. Suele ser la combinación del nombre, la inicial del segundo nombre y el apellido.
  - **Correo/SMTP**: la dirección SMTP de la persona, por ejemplo, Jeff@contoso.onmicrosoft.com.  
  - **Título**: puesto.
  - **Departamento**: el nombre del Departamento en el que trabaja la persona.
  - **Administrador**: el administrador de la persona. El Administrador recibe cualquier comunicación de elevación para esta persona.
  
- Información de ubicación

  - **City**: la ciudad en la que se encuentra la persona.
  - **State**: el estado o la provincia en la que se encuentra la persona.
  - **País o región**: el país o región en el que se encuentra la persona; por ejemplo, "US" o "UK".
  - **Office**: la ubicación de la oficina de la persona.

- Estado de procesamiento

  - **Estado**de indización: estado de indización profunda de los orígenes de datos
  - **Hora de la última actualización**de la indización: marca de tiempo de la última vez que se activó el trabajo de indización en profundidad.
  - **Orígenes de datos**: muestra el número de buzones de correo, sitios y equipos asignados a la persona.

- Actualizar índice
    - Puede volver a indizar los orígenes de datos de esta persona. 

- Ver actividad 

    - Puede ver y buscar registros de actividad del usuario. Para obtener más información, consulte [View People of Interest Activity](view-people-of-interest-activity.md) . 
