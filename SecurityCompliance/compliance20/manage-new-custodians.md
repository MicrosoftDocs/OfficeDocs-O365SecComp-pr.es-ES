---
title: Administrar los custodios en un caso de eDiscovery avanzado (vista previa)
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
ms.openlocfilehash: 6a21240f71c64f244ee42c3d3a2ed9d75381edaa
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241873"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a>Administrar los custodios en un caso de eDiscovery avanzado (vista previa)

La ficha custodios contiene una lista de todos los custodios que se puede ordenar en el caso. Después de agregar custodios a un caso, los detalles de cada custodio se recopilarán de forma automática desde Azure Active Directory.

![Administrar custodios](../media/CustodianDetails.PNG)

## <a name="viewing-custodian-details"></a>Visualización de detalles de custodios

La página de control flotante que contiene los detalles de custodios aparece después de agregar un custodio a un caso y seleccionarlos **** en la lista de la ficha custodios. Desde aquí, puede ver todos los detalles relacionados con el custodio. La página de control flotante contiene los siguientes campos:

- Información de contacto

  - **Nombre para mostrar**: nombre que se muestra en la libreta de direcciones del custodio. Suele ser la combinación del nombre del custodio, la inicial del segundo nombre y el apellido.
  - **Correo/SMTP**: la dirección SMTP de la custodio, por ejemplo, Jeff@contoso.onmicrosoft.com.  
  - **Title**: el puesto del custodio.
  - **Departamento**: nombre del Departamento en el que trabaja el custodio.
  - **Administrador**: el administrador del custodio. El administrador designado recibirá todas las comunicaciones de escalado para este custodio.
  
- Información de ubicación

  - **City**: la ciudad en la que se encuentra el custodio.
  - **State**: el estado o provincia de la dirección del custodio.
  - **País o región**: el país o región en el que se encuentra el custodio; por ejemplo, "US" o "UK".
  - **Oficina**: la ubicación de la oficina en el lugar de trabajo del custodio.

- Información del caso

  - **Estado de suspensión**: indica si el custodio se ha puesto en retención. 
  - **Estado de comunicación**: indica si el custodio ha emitido un aviso de retenciones. Si se ha emitido un aviso al custodio, este se marcará como *publicado*. Si no se ha emitido un aviso al custodio, este estado no se *publicará*. 
  - **Status**: el estado del custodio en el caso. Estará *activo* si el custodio todavía está en espera para el caso. Si se quita un custodio de un caso, su estado cambiará a *lanzado*. 

- Estado de procesamiento

  - **Estado**de indización: indica el estado del trabajo de indización profunda.  
  - **Fecha y hora de la última actualización**de la indización: indica el fecha de Cuándo se desencadenó por última vez el trabajo de indización en profundidad.
  - **Orígenes de datos**: muestra el número de buzones de correo, sitios y equipos que se han seleccionado para el custodio.

## <a name="editing-a-custodian"></a>Edición de un custodio

A medida que avanza el caso, es posible que descubra que puede haber orígenes de datos adicionales relacionados con un custodio específico & su caso. En otros escenarios, es posible que desee quitar determinados orígenes de datos que se han revisado y considerados como no relevantes.

Para actualizar un custodio y los orígenes de datos seleccionados:

1. Seleccione un caso existente de la exhibición de documentos electrónicos **_GT_ Advanced eDiscovery (Preview)**.
  
2. En el caso, haga clic **** en la ficha custodios.
  
3. Seleccione los custodios de la lista y haga clic en **editar fuentes**.

    ![Edición de orígenes de datos](../media/EditCustodianDataSource.PNG)
  
4. Para actualizar las selecciones para las ubicaciones de Exchange y OneDrive, haga clic en **Elegir orígenes de datos**.
  
5. Agregar o quitar buzones de correo de Microsoft Teams, SharePoint o Exchange asigne el usuario haciendo clic para **seleccionar orígenes de datos adicionales**. Para obtener más información sobre cómo asignar orígenes de datos a un custodio, consulte [Add custodios to a case](add-custodians-to-case.md).
  
6. Para actualizar el estado de conservación de custodios, haga clic en **realizar suspensiones de custodia**y habilite o deshabilite la retención para los custodios.

> [!TIP]
> Puede seleccionar varios custodios para realizar acciones en masa, como volver a indexar, liberar o editar un conjunto de custodios.

## <a name="resolving-custodian-processing-errors"></a>Resolver errores de procesamiento de custodios

En la mayoría de los flujos de trabajo legales, después de agregar custodios para una investigación específica, se buscará un subconjunto de los datos de los usuarios. Debido a los tamaños de archivo grandes o posibles daños, algunos elementos de los orígenes de datos de los custodios pueden indizarse parcialmente. Mediante el uso de la función de indización profunda de eDiscovery avanzado (versión preliminar), estos elementos parcialmente indizados se pueden corregir automáticamente volviendo a rastrear y indizar estos elementos a petición. 

Cuando se agrega un custodio a un caso, sus datos se "indizarán automáticamente" de forma automática, lo que permite a los usuarios dejar estos elementos parcialmente indizados en lugar de tener que descargar, corregir y volver a ejecutar búsquedas fuera de Office 365. Durante el ciclo de vida de un caso, un usuario puede corregir elementos o agregar nuevos orígenes de datos para un custodio determinado. Esto puede requerir que se actualice el índice de custodios. 

Para desencadenar un proceso de reindización para tratar los elementos parcialmente indizados:

1. Vaya a **eDiscovery _GT_ Advanced eDiscovery (Preview)** y seleccione un caso existente.

2. En el caso, haga clic en para la **ficha custodios**. 

3. Seleccione los custodios que se deben reindizar y, a continuación, haga clic en ![Actualizar índice](../media/UpdateIndex.PNG) en la página de flotante.

4. Compruebe el estado del índice de custodios haciendo clic en el vínculo de la columna **Estado de trabajo** de **** indización en la ficha custodios.  

5. También se puede realizar un seguimiento del estado del proceso de reindización en la pestaña **trabajos** .

Para obtener más información acerca de cómo volver a indizar y corregir los elementos parcialmente indizados, vea [corregir errores de procesamiento](processing-data-for-case.md).

## <a name="releasing-a-custodian-from-a-case"></a>Liberar un custodio de un caso

Un custodio se publica en situaciones en las que se cierra un caso, ya que un custodio ya no está obligado a preservar el contenido de un caso, o cuando se considera que un custodio ya no es relevante para un caso en particular. 

Si libera un custodio después de que se publique un aviso de retención, se enviará una notificación de publicación al custodio. Además, también se eliminarán todos los retenciones de privación que se hayan atribuido a los custodios emitidos.

Si el custodio se puso en una retención silenciosa, donde no se emitieron notificaciones legales de retención, se eliminarán todos los retenciones de privación que se hayan atribuido a los custodios emitidos.  

Para liberar un custodio: 

1.  Vaya a la **** pestaña custodios.

2.  Selecciona el custodio de la lista y haz clic en ![Liberar custodio](../media/ReleaseCustodian.PNG) en la página de flotante.

    El estado del custodio en la ficha **custodios** está establecido en **lanzado** y el estado de la **retención** en la página de control flotante cambia a inactivo. **** 

> [!TIP]
> Un custodio puede estar involucrado de manera simultánea en varias cuestiones legales de retención. Cuando se publica un custodio desde un caso, las suspensiones y notificaciones en otros asuntos no se verán afectadas.

## <a name="related-information"></a>Información relacionada

 - [Corrección de errores al procesar los datos](error-remediation.md) 
- [Trabajar con las comunicaciones](managing-custodian-communications.md)
