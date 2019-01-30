---
title: Administración de custodia en un caso de exhibición de documentos electrónicos avanzada (vista previa)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 742f6bc35b67071fba528e6a0ce543ecc6915762
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608401"
---
# <a name="managing-custodians-in-an-advanced-ediscovery-preview-case"></a>Administración de custodia en un caso de exhibición de documentos electrónicos avanzada (vista previa)

La ficha de custodia contiene una lista se puede ordenar de todos los la custodia en el caso. Después de agregar a un caso de custodia, automáticamente se recopilarán obtener información detallada sobre cada custodia de Azure Active Directory.

## <a name="viewing-custodian-details"></a>Visualización de detalles de custodia

La página emergente que contiene detalles de custodia aparece después de agregar a una custodia a un caso y selecciónelos en la lista en la ficha de **custodia** . Desde aquí, puede ver todos los detalles relacionados con ese custodia. La página emergente contiene los siguientes campos:

- Información de contacto

  - **Nombre para mostrar**: el nombre mostrado en la libreta de direcciones para la custodia. Suele ser la combinación de nombre de la custodia, medio inicial y el nombre.
  - **Correo/SMTP**: dirección SMTP el para la custodia, por ejemplo, jeff@contoso.onmicrosoft.com.  
  - **Título**: título del trabajo de la custodia.
  - **Departamento**: el nombre del departamento en el que trabaja la custodia.
  - **Administrador**: Administrador de custodia. El administrador designado recibirá las comunicaciones de escalación para este custodia.
  
- Información de ubicación

  - **Ciudad**: la ciudad donde se encuentra la custodia.
  - **Estado**: el estado o provincia de dirección de la custodia.
  - **País o región**: el país o región en el que se encuentra; la custodia Por ejemplo, "US" o "UK".
  - **Office**: la ubicación de la oficina en lugar de la custodia de negocio.

- Información de casos

  - **Estado de suspensión**: indica si se ha asignado la custodia en espera. 
  - **Estado de las comunicaciones**: indica si se ha emitido la custodia un aviso de suspensión. Si se ha emitido un aviso a la custodia, esto se marcarán como *publicados*. Si no se ha emitido la custodia un aviso, a continuación, en este estado puede ser *Reactivar publicado*. 
  - **Estado**: el estado de la custodia dentro de las mayúsculas y minúsculas. Estará *activa* si la custodia todavía está en espera para el caso. Si se quita una custodia de un caso, su estado cambiará a *liberado*. 

- Estado de procesamiento

  - **Estado de indización**: indica el estado del trabajo de indización profundo.  
  - **Indización de última vez actualizado**: indica la fecha de cuando se desencadenó por última vez el trabajo de indización profundo.
  - **Orígenes de datos**: muestra el número de buzones de correo, los sitios y los equipos que se han seleccionado para la custodia.

## <a name="updating-a-custodian"></a>Actualización de custodia

Medida que avanza el caso, es posible que descubra que pueden haber orígenes de datos adicionales relevantes para una & de custodia específico su caso. En otros escenarios, es posible que desee quitar determinados orígenes de datos que se han revisado y se considera como no relevantes.

Para actualizar una custodia y los orígenes de datos seleccionados:

1. Seleccione un caso existente de la **exhibición de documentos electrónicos > avanzada exhibición de documentos electrónicos (vista previa)**.
  
2. En el caso, haga clic en la ficha de **custodia** .
  
3. Seleccione el custodian(s) de la lista y haga clic en **Editar orígenes**.
  
4. Actualizar las selecciones de ubicaciones de Exchange y OneDrive haciendo clic en **Elegir orígenes de datos**.
  
5. Agregar o quitar Exchange, SharePoint o los equipos de los buzones de correo asignan al usuario haciendo clic para **Seleccionar los orígenes de datos adicionales**. Para obtener más información acerca de cómo asignar datos orígenes custodia, vea [Agregar custodia a una exhibición de documentos electrónicos avanzada (vista previa) caso](add-custodians-to-case.md).
  
6. Para actualizar el estado de suspensión de custodia, haga clic en **realizar custodia suspensiones**y habilitar o deshabilitar la suspensión de custodia.

> [!TIP]
> Puede seleccionar varios custodia para realizar acciones masivas, como volver a indizar, soltar o edición de un conjunto de custodia.

## <a name="resolving-custodian-processing-errors"></a>Resolución de errores de procesamiento de custodia

En la mayoría Legal flujos de trabajo después de custodia se agrega para una investigación específica, un subconjunto de datos de los usuarios se buscará. Debido a los tamaños de archivo grandes o daños posibles, algunos de los elementos dentro de los orígenes de datos de custodia podrían indizarse parcialmente. Uso de la capacidad de indización profundo de exhibición de documentos electrónicos avanzada (vista previa), estos elementos indizados parcialmente pueden ser automáticamente corrigió por volver a rastrear e indizar estos elementos a petición. 

Cuando se agrega una custodia a un caso, sus datos automáticamente "profundo indizará", lo que permite a los usuarios dejar estas parcialmente indiza elementos en contexto en lugar de tener que descargar, corregir y volver a ejecutar búsquedas fuera de Office 365. Durante el ciclo de vida de un caso, un usuario puede corregir los elementos o agregar nuevos orígenes de datos para una determinada custodia. Esto puede requerir la actualización del índice de custodia. 

Para desencadenar un proceso de volver a indización a dirección parcialmente elementos indizados:

1. Vaya a la **exhibición de documentos electrónicos > avanzada exhibición de documentos electrónicos (vista previa)** y seleccione un caso existente.

2. En el caso, haga clic en **ficha de custodia**. 

3. Seleccione el custodian(s) que se debe volver a indizar y, a continuación, haga clic en **Actualizar índice** en la página emergente.

4. Compruebe el estado del índice de custodia haciendo clic en el vínculo en la columna **estado del trabajo de indización** en la ficha de **custodia** .  

5. También puede realizar un seguimiento del estado para el proceso de indización volver a en la ficha **trabajos** .

Para obtener más información acerca de los elementos indizados parcialmente volver a indización y solucionar, vea [fijación de procesamiento de errores en la exhibición de documentos electrónicos avanzada (vista previa)](processing-data-for-case.md).

## <a name="releasing-a-custodian-from-a-case"></a>Liberación de custodia de un caso

Custodia está publicada en situaciones donde se cierra un caso, custodia ya no está bajo obligación de conservar el contenido de un caso, o cuando una custodia se considera que no ya sea relevante a un determinado caso. 

Si liberar a custodia después de que se ha publicado un aviso de suspensión, se enviará un aviso de versión a la custodia. Además, también se quitará cualquier suspensiones custodia atribuidas a la custodia de lanzamiento.

Si se realizó la custodia de una suspensión silenciosa, donde no se emitieron las notificaciones de retención legal, a continuación, se quitará cualquier suspensiones custodia atribuidas a la custodia de lanzamiento.  

Para liberar a una custodia: 

1.  Vaya a la ficha de **custodia** .

2.  Seleccione a la custodia de la lista y haga clic en **custodia de versión** en la página emergente.

    Se establece el estado de la custodia en la ficha de **custodia** a **liberado** y el **estado de suspensión** en la página emergente se cambia a **inactivo**. 

> [!TIP]
> Custodia ser simultáneamente es posible implicados en materia de retención legal varias. Cuando se suelta una custodia desde un caso, las suspensiones y notificaciones a través de otros asuntos no se verán afectadas.

## <a name="related-information"></a>Información relacionada

 - Atributos de usuario en Active Directory 
 - [Corrección de error al procesar los datos](error-remediation.md) 
 - [Trabajar con las comunicaciones](managing-custodian-communications.md)
