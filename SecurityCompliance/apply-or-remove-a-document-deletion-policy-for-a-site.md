---
title: Aplicar o quitar una directiva de eliminación de documentos de un sitio
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: Las organizaciones suelen estar sujetas a normas de cumplimiento, leyes u otras regulaciones que las obligan a conservar sus documentos durante un período de tiempo. Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal. Por esta razón, su organización puede haber creado una directiva de eliminación de documentos para el sitio como, por ejemplo, en el caso de que los documentos empresariales de carácter general deban eliminarse cinco años después de su creación.
ms.openlocfilehash: c00298a177ac405181ab2b2d9642b631e60a8a92
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219170"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a>Aplicar o quitar una directiva de eliminación de documentos de un sitio

Las organizaciones suelen estar sujetas a normas de cumplimiento, leyes u otras regulaciones que las obligan a conservar sus documentos durante un período de tiempo. Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal. Por esta razón, su organización puede haber creado una directiva de eliminación de documentos para el sitio como, por ejemplo, en el caso de que los documentos empresariales de carácter general deban eliminarse cinco años después de su creación.
  
Dependiendo de la organización, una directiva de eliminación de documentos puede ser:
  
- **Obligatorio** El propietario de un sitio no puede optar por una directiva obligatoria, que se aplica automáticamente al sitio. 
    
- **Predeterminada** Una directiva predeterminada se aplica automáticamente a un sitio, pero el propietario de dicho sitio puede: 
    
  - Elegir otra directiva, si la hay.
    
  - Anular la directiva si no está relacionada con el contenido del sitio.
    
- **Ni obligatoria ni predeterminada** En este caso, no se aplica ninguna directiva al sitio automáticamente, y el propietario debe aplicarla de forma manual. 
    
Una directiva de eliminación de documentos puede contener más de una regla; por ejemplo, una regla puede especificar que los documentos se deberán eliminar un año después de la creación y otra que la eliminación de documentos deberá tener lugar un año después de la última modificación. Si una directiva contiene más de una regla, puede seleccionar la que se ajuste mejor al sitio. La regla de eliminación se aplicará a todas las bibliotecas del sitio. Solo puede haber una directiva y una regla activas en un sitio al mismo tiempo. Al igual que ocurre con las directivas, es posible establecer una regla como predeterminada para que se aplique automáticamente al aplicar la directiva.
  
Por último, las directivas de eliminación de documentos son heredadas. Cuando se selecciona una directiva o regla para un sitio, todos los subsitios heredan esa selección, a menos que el propietario de un subsitio interrumpa la herencia seleccionando una directiva o regla distinta. Cuando seleccione una directiva o regla, tenga en cuenta el contenido de los subsitios del sitio.
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a>Ver las directivas de eliminación de documentos disponibles en una colección de sitios

Su organización puede asignar distintas directivas a colecciones de sitios diferentes. En el nivel de colección de sitios, el propietario de una colección de sitios puede ver todas las directivas de eliminación de documentos disponibles para esa colección concreta. Las directivas pueden estar disponibles para la plantilla de la colección de sitios (y, por tanto, para todas las colecciones de sitios creadas a partir de esta plantilla) o para esta colección de sitios específica.
  
1. En el sitio de nivel superior de la colección de sitios, en la esquina superior derecha, elija **configuración** del \> **sitio**[icono de engranaje].
    
2. En **directivas de eliminación de documentos**de administración \> de la colección de **sitios** .
    
    > [!NOTE]
    > El vínculo **directivas de eliminación de documentos** no aparecerá a menos que se hayan asignado directivas a la colección de sitios. Además, el vínculo no aparece inmediatamente después de que las directivas se hayan asignado al sitio: puede tardar hasta 24 horas desde el momento en que se asignan las directivas cuando aparece el vínculo **directivas de eliminación de documentos** . 
  
3. En esta página, puede ver lo siguiente:
    
  - Las directivas asignadas actualmente y las reglas asociadas. Seleccione una directiva para ver las reglas en el panel derecho.
    
  - Si existe una directiva predeterminada, se muestra **Sí** en la columna **Predeterminada**. 
    
  - Si la directiva se ha asignado como **Obligatoria**, se muestra un mensaje debajo de la lista.
    
Esta lista es solo para consulta, para que el propietario de la colección de sitios pueda ver todas las directivas y reglas disponibles. Para aplicar una directiva, consulte la sección siguiente.
  
![Ver las directivas de eliminación de documentos asignadas a una colección de sitios](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a>Aplicar o quitar una directiva de eliminación de documentos de un sitio

Como propietario del sitio o propietario de la colección de sitios, su organización puede haber creado directivas que puede aplicar al sitio o anular por completo.
  
1. En la esquina superior derecha, elija **configuración** del \> **sitio**[icono de engranaje].
    
2. En **directivas de eliminación de documentos**de administración \> del **sitio** .
    
    > [!NOTE]
    > El vínculo **directivas de eliminación de documentos** no aparecerá a menos que se hayan asignado directivas a la colección de sitios. Además, el vínculo no aparece inmediatamente después de que las directivas se hayan asignado al sitio: puede tardar hasta 24 horas desde el momento en que se asignan las directivas cuando aparece el vínculo **directivas de eliminación de documentos** . 
  
3. Siga uno de estos pasos:
    
  - **Para aplicar una directiva** Seleccione una directiva \> Seleccione una regla en esa directiva \> **Guardar**.
    
    Solo puede haber una directiva y una regla activas en un sitio al mismo tiempo. Su organización puede proporcionar varias directivas y reglas para elegir o solo una directiva o regla.
    
    ![Selección de la opción de Directiva](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - **Para dejar de participar en una directiva** Elija **no participar: Nota eliminar** \> **Guardar**.
    
    Como propietario de un sitio, puede anular una directiva de eliminación de documentos si considera que la directiva no puede aplicarse al contenido del sitio. Sin embargo, no puede anular una directiva marcada como **Obligatoria**.
    
    ![Opción de cancelación](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a>Las directivas de eliminación de documentos invalidan otras directivas

Un sitio puede usar otras directivas para la retención y eliminación de contenido:
  
- Directivas de tipo de contenido para la colección de sitios.
    
- Directivas de administración de la información para una lista o biblioteca.
    
Si aplica una directiva de eliminación de documentos a un sitio que ya usa directivas de tipo de contenido o directivas de administración de la información para una lista o biblioteca, esas directivas se ignoran mientras la Directiva de eliminación de documentos está en vigor. Si se omiten otras directivas, verá el mensaje "el contenido de este sitio usa directivas de eliminación de documentos".
  
Esto quiere decir que debe configurar un sitio de forma que solo utilice directivas creadas para contenido estructurado (directivas de administración de información y directivas de tipo de contenido) o contenido no estructurado (directivas de eliminación de documentos), pero no ambos. Si anula una directiva de eliminación de documentos, no se mostrará la advertencia y los demás tipos de directivas seguirán funcionando con normalidad.
  
Las directivas del sitio no se verán afectadas por las directivas de eliminación de documentos.
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a>Determinar si se están ignorando las directivas de tipo de contenido

Si el sitio estaba usando directivas de tipo de contenido y ahora ve este mensaje, esas directivas ya no se aplicarán. Para restaurar las directivas de tipo de contenido, puede quitar la Directiva de eliminación de documentos del sitio, tal como se ha descrito anteriormente, si hay una opción de cancelación disponible. Si no existe la opción de no participar, la Directiva de eliminación de documentos es obligatoria y deberá ponerse en contacto con el responsable de cumplimiento de su organización.
  
1. En la esquina superior derecha, elija **configuración** del \> **sitio**[icono de engranaje].
    
2. En **plantillas de directiva de tipo de contenido**de administración \> de **sitio** .
    
    ![ADVERTENCIA en el sitio de que se están usando directivas de eliminación de documentos](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a>Determinar si se están ignorando las directivas de administración de información

Si el sitio estaba usando directivas de administración de la información y ahora ve este mensaje, esas directivas ya no se aplicarán. Para restaurar las directivas de administración de la información, puede quitar la Directiva de eliminación de documentos del sitio, como se ha descrito anteriormente, si hay una opción de cancelación disponible. Si no existe la opción de no participar, la Directiva de eliminación de documentos es obligatoria y deberá ponerse en contacto con el responsable de cumplimiento de su organización.
  
- Para una lista o biblioteca, en la biblioteca \> de la \> ficha **biblioteca** de la cinta de **Opciones Configuración** \> de la **Directiva** **permisos y** \> administración de información de administración.
    
    ![ADVERTENCIA en el sitio de que se están usando directivas de eliminación de documentos](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a>Consulte también

[Información general sobre las directivas de eliminación de documentos](document-deletion-policies.md)
  
[Crear una directiva de eliminación de documentos](create-a-document-deletion-policy.md)

