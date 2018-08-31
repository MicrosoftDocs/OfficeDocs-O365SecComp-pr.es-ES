---
title: Aplicar o quitar una directiva de eliminación de documentos de un sitio
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: Las organizaciones suelen estar sujetas a normas de cumplimiento, leyes u otras regulaciones que las obligan a conservar sus documentos durante un período de tiempo. Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal. Por esta razón, su organización puede haber creado una directiva de eliminación de documentos para el sitio como, por ejemplo, en el caso de que los documentos empresariales de carácter general deban eliminarse cinco años después de su creación.
ms.openlocfilehash: abee0da7adfba6f653743d503f8b30770ee93c40
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536607"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a>Aplicar o quitar una directiva de eliminación de documentos de un sitio

Las organizaciones suelen estar sujetas a normas de cumplimiento, leyes u otras regulaciones que las obligan a conservar sus documentos durante un período de tiempo. Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal. Por esta razón, su organización puede haber creado una directiva de eliminación de documentos para el sitio como, por ejemplo, en el caso de que los documentos empresariales de carácter general deban eliminarse cinco años después de su creación.
  
Dependiendo de la organización, una directiva de eliminación de documentos puede ser:
  
- **Obligatorio** Propietario de un sitio no puede anular una directiva obligatoria, que se aplica automáticamente al sitio. 
    
- **Predeterminada** Una directiva predeterminada se aplica automáticamente a un sitio, pero el propietario de dicho sitio puede: 
    
  - Elegir otra directiva, si la hay.
    
  - Anular la directiva si no está relacionada con el contenido del sitio.
    
- **Ni obligatoria ni predeterminada** En este caso, no se aplica ninguna directiva al sitio automáticamente, y el propietario debe aplicarla de forma manual. 
    
Una directiva de eliminación de documentos puede contener más de una regla; por ejemplo, una regla puede especificar que los documentos se deberán eliminar un año después de la creación y otra que la eliminación de documentos deberá tener lugar un año después de la última modificación. Si una directiva contiene más de una regla, puede seleccionar la que se ajuste mejor al sitio. La regla de eliminación se aplicará a todas las bibliotecas del sitio. Solo puede haber una directiva y una regla activas en un sitio al mismo tiempo. Al igual que ocurre con las directivas, es posible establecer una regla como predeterminada para que se aplique automáticamente al aplicar la directiva.
  
Por último, las directivas de eliminación de documentos son heredadas. Cuando se selecciona una directiva o regla para un sitio, todos los subsitios heredan esa selección, a menos que el propietario de un subsitio interrumpa la herencia seleccionando una directiva o regla distinta. Cuando seleccione una directiva o regla, tenga en cuenta el contenido de los subsitios del sitio.
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a>Ver las directivas de eliminación de documentos disponibles en una colección de sitios

Su organización puede asignar distintas directivas a colecciones de sitios diferentes. En el nivel de colección de sitios, el propietario de una colección de sitios puede ver todas las directivas de eliminación de documentos disponibles para esa colección concreta. Las directivas pueden estar disponibles para la plantilla de la colección de sitios (y, por tanto, para todas las colecciones de sitios creadas a partir de esta plantilla) o para esta colección de sitios específica.
  
1. En el sitio de nivel superior en la colección de sitios, en la esquina superior derecha, elija **configuración** [icono de engranaje] \> **Configuración del sitio**.
    
2. En **administración de colección de sitios** \> **directivas de eliminación de documentos**.
    
    > [!NOTE]
    > El vínculo de **Las directivas de eliminación de documentos** no aparecerá a menos que las directivas se han asignado a la colección de sitios. Además, el vínculo no aparece inmediatamente después de que las directivas se han asignado al sitio, puede demorar hasta 24 horas desde cuando las directivas se asignan a cuando aparece el vínculo de **Las directivas de eliminación de documentos** . 
  
3. En esta página, puede ver lo siguiente:
    
  - Las directivas asignadas actualmente y las reglas asociadas. Seleccione una directiva para ver las reglas en el panel derecho.
    
  - Si existe una directiva predeterminada, se muestra **Sí** en la columna **Predeterminada**. 
    
  - Si la directiva se ha asignado como **Obligatoria**, se muestra un mensaje debajo de la lista.
    
Esta lista es solo para consulta, para que el propietario de la colección de sitios pueda ver todas las directivas y reglas disponibles. Para aplicar una directiva, consulte la sección siguiente.
  
![Ver las directivas de eliminación de documentos asignadas a una colección de sitios](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a>Aplicar o quitar una directiva de eliminación de documentos de un sitio

Como propietario del sitio o propietario de la colección de sitios, su organización puede haber creado directivas que puede aplicar al sitio o anular por completo.
  
1. En la esquina superior derecha, elija **configuración** [icono de engranaje] \> **Configuración del sitio**.
    
2. En **administración de sitios** \> **directivas de eliminación de documentos**.
    
    > [!NOTE]
    > El vínculo de **Las directivas de eliminación de documentos** no aparecerá a menos que las directivas se han asignado a la colección de sitios. Además, el vínculo no aparece inmediatamente después de que las directivas se han asignado al sitio, puede demorar hasta 24 horas desde cuando las directivas se asignan a cuando aparece el vínculo de **Las directivas de eliminación de documentos** . 
  
3. Realice una de las acciones siguientes:
    
  - **Para aplicar una directiva** Seleccione una directiva de \> seleccione una regla en esa directiva \> **Guardar**.
    
    Solo puede haber una directiva y una regla activas en un sitio al mismo tiempo. Su organización puede proporcionar varias directivas y reglas para elegir o solo una directiva o regla.
    
    ![Seleccione la opción de directiva](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - **Para anular una directiva** Elija **voluntaria: tenga en cuenta eliminar** \> **Guardar**.
    
    Como propietario de un sitio, puede anular una directiva de eliminación de documentos si considera que la directiva no puede aplicarse al contenido del sitio. Sin embargo, no puede anular una directiva marcada como **Obligatoria**.
    
    ![Opción alta de salida](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a>Las directivas de eliminación de documentos invalidan otras directivas

Un sitio puede usar otras directivas para la retención y eliminación de contenido:
  
- Directivas de tipo de contenido para la colección de sitios.
    
- Directivas de administración de la información para una lista o biblioteca.
    
Si se aplica una directiva de eliminación de documentos a un sitio que ya usa las directivas de tipo de contenido o las directivas de administración de información para una lista o biblioteca, dichas directivas se omiten mientras la directiva de eliminación de documentos se encuentra en vigor. Si se omiten las otras directivas, verá el mensaje "El contenido de este sitio usa las directivas de eliminación de documentos".
  
Esto quiere decir que debe configurar un sitio de forma que solo utilice directivas creadas para contenido estructurado (directivas de administración de información y directivas de tipo de contenido) o contenido no estructurado (directivas de eliminación de documentos), pero no ambos. Si anula una directiva de eliminación de documentos, no se mostrará la advertencia y los demás tipos de directivas seguirán funcionando con normalidad.
  
Las directivas del sitio no se verán afectadas por las directivas de eliminación de documentos.
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a>Determinar si se están ignorando las directivas de tipo de contenido

Si el sitio estaba en uso las directivas de tipo de contenido y ver ahora este mensaje, esas directivas ya no están en vigor. Para restaurar las directivas de tipo de contenido, puede quitar la directiva de eliminación de documentos de su sitio, tal y como se ha descrito anteriormente, si hay una opción de anular. Si no hay ninguna opción para excluir, la directiva de eliminación de documentos es obligatoria y debe ponerse en contacto con el responsable de cumplimiento de normas en su organización.
  
1. En la esquina superior derecha, elija **configuración** [icono de engranaje] \> **Configuración del sitio**.
    
2. En **administración de sitios** \> **plantillas de directiva de tipo de contenido**.
    
    ![Advertencia en el sitio que se usan las directivas de eliminación de documentos](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a>Determinar si se están ignorando las directivas de administración de información

Si el sitio estaba en uso las directivas de administración de información y ahora verá este mensaje, esas directivas ya no están en vigor. Para restaurar las directivas de administración de información, puede quitar la directiva de eliminación de documentos de su sitio, tal y como se ha descrito anteriormente, si hay una opción de anular. Si no hay ninguna opción para excluir, la directiva de eliminación de documentos es obligatoria y debe ponerse en contacto con el responsable de cumplimiento de normas en su organización.
  
- Para una lista o biblioteca, en la cinta de opciones \> ficha **biblioteca** \> **Configuración de la biblioteca** \> en **permisos y administración** \> **Configuración de directiva de administración de información**.
    
    ![Advertencia en el sitio que se usan las directivas de eliminación de documentos](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a>Vea también

[Información general sobre las directivas de eliminación de documentos](document-deletion-policies.md)
  
[Crear una directiva de eliminación de documentos](create-a-document-deletion-policy.md)

