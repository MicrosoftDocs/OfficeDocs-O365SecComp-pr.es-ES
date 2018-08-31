---
title: Información general sobre las directivas de eliminación de documentos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/12/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- SPO160
ms.assetid: 55e8d858-f278-482b-a198-2e62d6a2e6e5
description: Su organización puede ser requerida para retener documentos durante un período de tiempo a causa de cumplimiento de normas, legal, u otros requisitos empresariales. Sin embargo, si su organización mantiene documentos más de necesarios, crear riesgos legales innecesarios. Con una directiva de eliminación de documentos, puede reducir proactivamente riesgo mediante la eliminación de documentos en un sitio después de un período de tiempo específico, por ejemplo, puede eliminar documentos de OneDrive de los usuarios para profesionales de sitios de cinco años después de que se crearon los documentos.
ms.openlocfilehash: 495dd781c56e25e884d47f72a7e48410ea340208
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013664"
---
# <a name="overview-of-document-deletion-policies"></a>Información general sobre las directivas de eliminación de documentos

> [!IMPORTANT]
> Más adelante, se recomienda usar una directiva de retención o etiquetas creadas en la seguridad &amp; centro de cumplimiento en lugar de una directiva de eliminación de documentos. Las directivas de eliminación de documentos seguirán funcionando codo con codo con las directivas de retención, pero si desea conservar o eliminar contenido en cualquier lugar en Office 365, se recomienda que use una directiva de retención. Para obtener más información, vea [utilizar una directiva de retención en lugar de estas características](retention-policies.md#use-a-retention-policy-instead-of-these-features).
  
Su organización puede ser requerida para retener documentos durante un período de tiempo a causa de cumplimiento de normas, legal, u otros requisitos empresariales. Sin embargo, si su organización mantiene documentos más de necesarios, crear riesgos legales innecesarios. Con una directiva de eliminación de documentos, puede reducir proactivamente riesgo mediante la eliminación de documentos en un sitio después de un período de tiempo específico, por ejemplo, puede eliminar documentos de OneDrive de los usuarios para profesionales de sitios de cinco años después de que se crearon los documentos.
  
Las directivas de eliminación de documentos son eficaces aún flexible — por ejemplo, se puede:
  
- Permitir a los propietarios de sitios elegir directivas que usted cree y administre de forma centralizada. También puede permitir que los propietarios de sitios anulen una directiva si deciden que no se aplica a su contenido.
    
- Aplicar una sola directiva obligatoria a todos los sitios de una colección, como todos los sitios de OneDrive para la Empresa, o aplicar una directiva a todas las colecciones de sitios creadas a partir de una plantilla de colección de sitios determinada, como la plantilla Sitio de grupo.
    
- Proporcionar una directiva predeterminada con una regla predeterminada que se aplicará automáticamente sin necesidad de que los propietarios de los sitios realicen ninguna acción.
    
- Crear una directiva que incluya varias reglas de eliminación entre las que podrá elegir el propietario de un sitio.
    
Puede crear y administrar las directivas de eliminación de documentos mediante el centro de directiva de eliminación de documentos, que puede encontrar en **retención** en la seguridad de Office 365 &amp; centro de cumplimiento. Como alternativa, puede crear el centro de directiva manualmente mediante la [creación de la colección de sitios](https://go.microsoft.com/fwlink/p/?LinkID=404342) y elija **Centro de cumplimiento de directivas** en la ficha de **empresa** . Cada inquilino puede tener un solo centro de directiva de eliminación de documento y se podrá crear automáticamente si inicia desde la seguridad &amp; centro de cumplimiento. 
  
![Página de inicio de Centro de directivas de eliminación de documentos](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="when-to-use-document-deletion-policies"></a>Cuándo usar directivas de eliminación de documentos

Además de las directivas de eliminación de documentos, Office 365 proporciona estas directivas de retención para el contenido de los sitios:
  
- [Administración de registros](https://go.microsoft.com/fwlink/p/?LinkID=404250)
    
- [Directivas de administración de información para los tipos de contenido, las listas y bibliotecas](https://go.microsoft.com/fwlink/p/?LinkID=404239)
    
- [Directivas del sitio](https://go.microsoft.com/fwlink/p/?LinkID=404242)
    
Cada tipo de directiva funciona mejor para un tipo específico de datos o de sitio. Por ejemplo, su organización puede tener un sitio muy estructurado que usa tipos de contenido diferentes, como un sitio financiero para contratos o una knowledge base para artículos. En este caso, puede usar directivas de tipo de contenido. También es posible que su organización necesite conservar documentos legales, en cuyo caso puede usar tipos de contenido y un centro de registros para implementar un plan de archivos.
  
Las directivas de eliminación de documentos no reemplazar registros información o administración de directivas de administración, que funcionan mejor con datos estructurados y tipos de contenido. En su lugar, debe usar las directivas de eliminación de documentos cuando necesite a grandes rasgos administrar la eliminación automática de datos no estructurados, como OneDrive para sitios de negocio y sitios de grupo.
  
![Diagrama con opciones de retención para contenido de sitio](media/IP-Retention-policies-for-site-content.png)
  
Si aplica una directiva de eliminación de documentos a un sitio que ya usa directivas de tipo de contenido o directivas de administración de información para una lista o biblioteca, dichas directivas se ignorarán mientras la directiva de eliminación de documentos esté activa. Esto significa que debe planear que un sitio use solamente las directivas destinadas a contenido estructurado o no estructurado, pero no ambos. Para obtener más información sobre cómo las directivas de eliminación de documentos invalidan otras directivas, vea [Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md).
  
A diferencia de lo que ocurre con otras directivas, las directivas de eliminación de documentos solo funcionan en las bibliotecas de documentos, no en las listas.
  
## <a name="deletion-policies-and-rules"></a>Reglas y directivas de eliminación

Una directiva de eliminación de documentos contiene una o varias reglas de eliminación que especifican:
  
- El período de tiempo hasta la eliminación.
    
- Si se va a calcular la fecha de eliminación desde que se creó el documento o desde que se modificó por última vez.
    
- Si se va a eliminar el documento de forma permanente o se va a enviar a la Papelera de reciclaje.
    
Si una directiva contiene más de una regla, los propietarios de los sitios pueden seleccionar la regla que mejor convenga a su contenido.
  
![Página para nueva regla de eliminación](media/IP-New-deletion-rule.png)
  
## <a name="policies-and-assignments"></a>Directivas y asignaciones

Después de crear una directiva de eliminación de documentos, puede asignar a una plantilla de la colección de sitios, por ejemplo, puede asignar una directiva a la OneDrive para la plantilla de negocio para que incluya el sitio de OneDrive de cada usuario. Al asignar una directiva a una plantilla de la colección de sitios, esto se aplica a todas las colecciones de sitios ya creadas a partir de esa plantilla, además de las colecciones de sitios creados a partir de esa plantilla en el futuro.
  
![Página Seleccionar una plantilla con la opción OneDrive](media/IP-Choose-a-template.png)
  
También puede asignar una directiva a una colección de sitios determinada, lo que reemplaza a cualquier otra directiva que se haya asignado a la plantilla de esa colección de sitios. Por ejemplo, puede asignar directivas a la plantilla Sitio de grupo, pero luego debe anularlas mediante la aplicación de un conjunto de directivas diferente a una colección de sitios determinada creada a partir de esa plantilla.
  
### <a name="one-mandatory-policy-or-several-policies-to-choose-from"></a>Una directiva obligatoria o varias directivas para elegir

Cuando asigna una directiva, puede elegir hacerla obligatoria. Si es así, solo se podrá asignar esa directiva y se aplicará a todos los sitios de la colección de sitios. Los propietarios de sitios no pueden anular una directiva obligatoria, lo que significa que los documentos del sitio estarán sujetos a la directiva de eliminación pase lo que pase.
  
En lugar de hacer una sola directiva obligatoria, también puede asignar varias directivas a una colección de sitios. Esto permite que cada propietario de un sitio elija qué directiva quiere aplicar a su sitio, o incluso anular todas. Por ejemplo, puede crear una directiva para documentos empresariales generales y otra directiva para documentos financieros que tengan una programación de retención diferente. El propietario de un sitio suele saber mejor que nadie el contenido incluido en su sitio y, por tanto, la directiva de eliminación de documentos que hay que aplicar. Cada sitio puede tener solamente una directiva aplicada.
  
### <a name="one-rule-or-several-rules-to-choose-from"></a>Una regla o varias reglas para elegir

A su vez, cada directiva puede contener muchas reglas, por ejemplo, una directiva de eliminación de documentos de negocios general puede tener dos reglas:
  
- Documentos que no necesiten retención según las obligaciones legales o las necesidades empresariales actuales no se deben conservar durante más de un año desde su creación.
    
- Los documentos necesarios para un uso empresarial activo y continuado que se necesiten durante más de un año no deben conservarse durante más de tres años desde su creación.
    
Un propietario del sitio puede determinar que su sitio contiene empresarial general documentos, seleccione esta directiva de eliminación y, a continuación, seleccione la regla correspondiente de la directiva. Sólo puede seleccionar una regla de la directiva que se aplica actualmente al sitio (no de cualquier directiva) y la regla se aplica a todas las bibliotecas de documentos en el sitio.
  
## <a name="the-relationship-of-site-collections-policies-and-rules"></a>Relación entre colecciones de sitios, directivas y reglas

La relación básica es la siguiente:
  
Una colección de sitios o una plantilla de la colección de sitios puede tener una o varias directivas asignadas a ella, y cada una de dichas directivas puede tener una o varias reglas. Sin embargo, puede haber sólo una directiva que está activa por sitio, y puede haber sólo una regla de eliminación que está activa en cualquier momento para las bibliotecas dentro del sitio.
  
![Diagrama con relación entre directivas](media/IP-Two-policies-four-rules.png)
  
## <a name="document-deletion-policies-are-inherited"></a>Las directivas de eliminación de documentos se heredan

Igual que los permisos, la navegación y muchas otras características del sitio, las directivas de eliminación de documentos se heredan. Los propietarios de un sitio pueden seleccionar una directiva de eliminación de documentos para su sitio; de esta forma, todos los subsitios heredan la directiva del sitio primario. Un propietario de un subsitio puede interrumpir la herencia si selecciona otra combinación de directiva y regla, y esa directiva se aplicará a todos los subsitios hasta que se interrumpa la herencia de nuevo.
  
## <a name="assigning-document-deletion-policies-for-the-first-time"></a>Asignar directivas de eliminación de documentos por primera vez

Es importante comprender que el período de tiempo especificado para un documento de directiva de eliminación significa el tiempo desde que el documento se ha creado o modificado, no el tiempo desde que se asignó la directiva. Por ejemplo, podría crear una directiva de eliminación de documentos que se elimina de forma permanente documentos dos años después de que se crearon y, a continuación, asignar esa directiva a una plantilla de la colección de sitios desde la que varias colecciones de sitios se crearon cuatro o cinco años. En este caso, es probable que las colecciones de sitios existentes contienen muchos documentos que ya son anteriores a los dos años especificados por la directiva de eliminación, esto significa que una gran cantidad de contenido se eliminará pronto después de asignar la directiva de eliminación de documentos para la primera tiempo.
  
Cuando se asigna la directiva por primera vez, se evalúan todos los documentos del sitio. Si cumplen los criterios, se eliminarán. Esto se aplica a todos los documentos existentes, no solo a los documentos nuevos creados desde que se asignó la directiva. Y recuerde que el período de tiempo corresponde a la antigüedad de cada documento, no al tiempo desde que se asignó la directiva por primera vez.
  
Por lo tanto, antes de asignar una directiva a un sitio por primera vez, primero debería considerar la antigüedad del contenido existente y cuál será el impacto de dicha directiva. También es recomendable comunicar la nueva directiva a los propietarios de sitios antes de asignarla, para darles tiempo a evaluar el posible impacto.
  
## <a name="time-lag-for-propagating-policies"></a>Intervalo de tiempo en la propagación de directivas

Después de asignar directivas a una colección de sitios, los propietarios de los sitios usan el vínculo **Directivas de eliminación de documentos** de la página **Configuración del sitio** para ver y aplicar directivas disponibles para el sitio. 
  
El vínculo de **Las directivas de eliminación de documentos** no aparecerá a menos que las directivas se han asignado a la colección de sitios. Además, el vínculo no aparece inmediatamente después de que las directivas se han asignado al sitio, puede demorar hasta 24 horas desde cuando las directivas se asignan a cuando aparece el vínculo de **Las directivas de eliminación de documentos** . 
  
## <a name="permissions"></a>Permisos

Los miembros de su equipo de cumplimiento normativo que vayan a usar el centro de directivas de eliminación de documentos necesitan permisos para el centro de directivas y para las colecciones de sitios en las que se aplicarán las directivas. Le recomendamos que haga lo siguiente:
  
1. Crear un grupo de seguridad que contiene todos los usuarios del centro de directiva de eliminación de documentos, más probable es que su equipo de administración de directivas de cumplimiento de normas. Para obtener más información, vea [Grupos de seguridad de Manage Mail-Enabled](https://go.microsoft.com/fwlink/p/?LinkID=404345) . 
    
2. En el centro de directiva de eliminación de documentos, asignar la colección de sitios permisos de propietario para el grupo de seguridad. Para obtener más información, vea [permisos para los administradores de colección de sitios](https://go.microsoft.com/fwlink/p/?LinkID=404346) . 
    
3. En cada colección de sitios en que necesite asignar directivas de eliminación de documentos, asigne permisos de propietario de colección de sitios al grupo de seguridad.
    
## <a name="how-document-deletion-policies-work-with-hold-policies"></a>Funcionamiento de las directivas de eliminación de documentos con las directivas de retención

Una directiva de retención asegura que todo el contenido se mantenga durante un período de tiempo determinado, mientras que una directiva de eliminación de documentos asegura que todo el contenido se elimina después de un período de tiempo determinado.
  
Si necesita conservar documentos durante un período fijo de tiempo, puede usar una directiva de retención junto con una directiva de eliminación. Por ejemplo, puede retener documentos durante tres años después de modificarlos y, luego, configurar una directiva de eliminación para eliminarlos tres años después de su última modificación.
  
Tenga en cuenta que una directiva de eliminación no puede reemplazar a una retención. Si un sitio está en retención y una directiva de eliminación de documentos elimina un documento, el documento se conservará en la biblioteca de conservación de documentos de la misma forma que si el documento se hubiera eliminado de forma manual.
  
## <a name="see-also"></a>Vea también

[Aplicar o quitar una directiva de eliminación de documentos de un sitio](apply-or-remove-a-document-deletion-policy-for-a-site.md)

[Crear una directiva de eliminación de documentos](create-a-document-deletion-policy.md)


