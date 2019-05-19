---
title: Crear una directiva de eliminación de documentos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 41b2ed73-eb8d-4429-945e-a8197894585a
description: Las organizaciones suelen necesitar conservar algunos documentos durante cierto período de tiempo para satisfacer el cumplimiento de ciertas normas legales u otras regulaciones. Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal.
ms.openlocfilehash: e8f85f4cc9ae541d8a962dfb270e5216c912ac7d
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153922"
---
# <a name="create-a-document-deletion-policy"></a>Crear una directiva de eliminación de documentos

> [!IMPORTANT]
> En el futuro, le recomendamos que use una directiva de retención o etiquetas de retención creadas en el centro de cumplimiento de Microsoft 365, el centro de seguridad &amp; de Microsoft 365 o el centro de seguridad de Office 365 en lugar de una directiva de eliminación de documentos. Las directivas de eliminación de documentos seguirán funcionando en paralelo con las directivas de retención, pero si necesita conservar o eliminar contenido en cualquier lugar de Office 365, le recomendamos que use una directiva de retención. Para obtener más información, vea [usar una directiva de retención en lugar de estas características](retention-policies.md#use-a-retention-policy-instead-of-these-features). 
  
Las organizaciones suelen necesitar conservar algunos documentos durante cierto período de tiempo para satisfacer el cumplimiento de ciertas normas legales u otras regulaciones. Sin embargo, conservar los documentos durante más tiempo de lo necesario puede exponer a la organización a riesgos de carácter legal.
  
Con una directiva de eliminación de documentos, puede reducir el riesgo de forma proactiva eliminando los documentos de un sitio después de un período de tiempo específico (por ejemplo, puede eliminar documentos de los sitios de OneDrive para la empresa de los usuarios cinco años después de que se crearon los documentos). 
  
Después de crear una directiva de eliminación de documentos, puede asignarla a una plantilla de colección de sitios, de forma que la directiva estará disponible para todas las colecciones de sitios creadas a partir de esa plantilla. También puede asignar una directiva a una colección de sitios determinada, lo que reemplaza a cualquier otra directiva que se haya asignado a la plantilla para esa colección de sitios.
  
![Página de inicio de Centro de directivas de eliminación de documentos](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="policy-templates"></a>Plantillas de directiva

Puede crear una directiva de eliminación de documentos desde cero o puede usar una de las directivas de ejemplo. El Centro de directivas de cumplimiento de normas incluye directivas de ejemplo que puede usar tal cual, o bien puede usarlas como punto de partida y después cambiarles el nombre o modificarlas.
  
![Directivas de eliminación de documentos de muestra](media/IP-Sample-deletion-policies.png)
  
## <a name="examples-of-how-to-use-document-deletion-policies"></a>Ejemplos

Una colección de sitios o una plantilla de colección de sitios puede tener una o varias directivas asignadas, y cada una de estas directivas puede tener una o más reglas. Sin embargo, solo puede haber una Directiva activa por sitio y solo puede haber una regla de eliminación activa en cualquier momento para las bibliotecas dentro del sitio.
  
![Diagrama con relación entre directivas](media/IP-Two-policies-four-rules.png)
  
Además, puede seleccionar una directiva como obligatoria o predeterminada, y puede seleccionar una regla de eliminación como regla predeterminada: 
  
- **Directiva obligatoria** Cuando una directiva se marca como obligatoria, solo se puede asignar una directiva a la colección de sitios o a la plantilla. La Directiva debe estar marcada como predeterminada y se aplicará a todos los sitios. Los propietarios de sitios no pueden optar por no participar de la Directiva.
    
- **Directiva predeterminada** Cuando una directiva está configurada como predeterminada, la Directiva se activa automáticamente en todos los sitios a los que está asignada sin que el propietario del sitio tenga ninguna acción.
    
- **Regla predeterminada** Cuando una regla de eliminación se establece como predeterminada, se aplica automáticamente a todas las bibliotecas de los sitios que usan la Directiva.
    
En los siguientes ejemplos se explica cuándo será conveniente usar una directiva obligatoria, o directivas y reglas predeterminadas.
  
### <a name="example-1-apply-a-single-policy-with-a-single-rule-to-a-site-collection-template"></a>Ejemplo 1: aplicar una sola directiva con una sola regla a una plantilla de colección de sitios

Es posible que quiera aplicar una directiva de eliminación de documentos en una amplia gama de contenido no estructurado, como todos los sitios de OneDrive para la Empresa o todos los sitios de grupo. Si quiere asegurarse de que una sola directiva de eliminación de documentos está activa en todos los sitios creados a partir de una plantilla de colección de sitios, puede:
  
1. Crear una única directiva con una sola regla de eliminación predeterminada.
    
2. Establecer la directiva como obligatoria y predeterminada.
    
3. Asignar la directiva a una plantilla de colección de sitios.
    
En este ejemplo, la regla de eliminación predeterminada se aplicará a todas las bibliotecas en todas las colecciones de sitios creadas a partir de la plantilla, y los propietarios de los sitios no podrán anular la directiva. Esta es la forma más sencilla de aplicar una directiva de eliminación de documentos de forma rígida y completa.
  
![Diagrama con una sola directiva obligatoria](media/IP-Example-1-doc-deletion-policies.png)
  
### <a name="example-2-apply-a-single-policy-with-several-rules-to-a-site-collection-template"></a>Ejemplo 2: aplicar una sola directiva con varias reglas a una plantilla de colección de sitios

Los propietarios de los sitios son los que mejor conocen el tipo de contenido que contienen sus sitios, por lo que puede optar por permitir que ellos elijan la regla de eliminación que mejor se aplique a su sitio. También es aconsejable permitir que los propietarios de sitios puedan anular una directiva completamente.
  
Podrá seguir creando y administrando las directivas centralmente. También puede seleccionar una directiva y una regla como predeterminadas, para que una directiva siempre esté en vigor hasta que el propietario del sitio elija otra o no participe en ella. Si quiere proporcionar dicha flexibilidad a los propietarios de los sitios, puede:
  
1. Crear una sola directiva con varias reglas de eliminación y establecer una regla como predeterminada.
    
2. Establecer la directiva como la directiva predeterminada.
    
3. Asignar la directiva a una plantilla de colección de sitios.
    
Los propietarios de los sitios pueden seleccionar una de las reglas de eliminación alternativas, anular la directiva, o no hacer nada y estar sujetos a la directiva y la regla predeterminadas.
  
![Diagrama con una directiva que tiene muchas reglas](media/IP-Example-2-doc-deletion-policies.png)
  
### <a name="example-3-apply-several-policies-with-one-or-more-rules-to-a-site-collection"></a>Ejemplo 3: aplicar varias directivas con una o varias reglas a una colección de sitios

En este ejemplo se proporciona la máxima flexibilidad a los propietarios de sitios ya que podrán elegir entre varias directivas y, después de seleccionar una directiva, a menudo podrán elegir entre varias reglas. Una directiva y una regla se establecen como predeterminadas, de forma que una directiva siempre estará en vigor hasta que el propietario del sitio elija otra o no participe en ella. Tenga en cuenta que si no establece una directiva y una regla como predeterminadas, no habrá directivas ni reglas activas en las bibliotecas de documentos del sitio hasta que el propietario las elija y aplique.
  
A diferencia de lo que ocurre en los dos ejemplos anteriores, estas directivas se asignan a una colección de sitios específica, no a la plantilla de la colección de sitios. Esto significa que las directivas pueden personalizarse de forma más específica según el contenido de una colección de sitios determinada.
  
Las directivas y las reglas se heredan. Los propietarios de los sitios pueden seleccionar una directiva y una regla para su sitio; de esta forma, todos los subsitios heredan la directiva del sitio primario. Sin embargo, un propietario de un subsitio puede interrumpir la herencia si selecciona otra directiva y otra regla, que a su vez se aplicarán a todos los subsitios hasta que se interrumpa la herencia de nuevo.
  
Para configurar este escenario, puede:
  
1. Crear varias directivas que contengan una o varias reglas.
    
2. Establecer una directiva y una regla como predeterminadas.
    
3. Asignar las directivas a una colección de sitios especifica.
    
Además, las directivas y reglas se adaptan a una colección de sitios determinada, en la que los propietarios de los sitios podrán interrumpir la herencia si seleccionan la directiva y la regla que mejor se adapten a su sitio.
  
![Diagrama con muchas directivas y reglas](media/IP-Example-3-doc-deletion-policies.png)
  
## <a name="create-a-document-deletion-policy"></a>Crear una directiva de eliminación de documentos

1. En el centro de &amp; cumplimiento de Office 365Security, vaya a **retención**de **Administración** \> de datos. En **eliminar**, haga clic en **Administrar directivas de eliminación de documentos para SharePoint Online y OneDrive para la empresa**. Se abrirá el Centro de directivas de eliminación de documentos en una nueva pestaña del explorador.
    
    La primera vez que se desplace desde &amp; el centro de seguridad y cumplimiento hasta el centro de directivas de eliminación de documentos, el centro de directivas se creará automáticamente. Como alternativa, puede crear manualmente el centro de directivas [creando la colección de sitios](http://go.microsoft.com/fwlink/p/?LinkID=404342) y eligiendo **centro de directivas de cumplimiento** en la pestaña **empresa** . 
    
2. Elija **directivas de eliminación**.
    
    ![Opción Directivas de eliminación](media/IP-Deletion-Policies-option.png)
  
3. Elija **Elemento nuevo**.
    
4. Escriba un nombre y una descripción para la directiva. Los propietarios de los sitios pueden seleccionar una directiva para su sitio según el nombre y la descripción. Por lo tanto, incluya información suficiente para que elijan la directiva correcta.
    
5. Para crear una regla, elija **Nuevo**.
    
6. Escriba un nombre y elija las siguientes opciones:
    
  - Elija si la regla eliminará los documentos de forma permanente o los enviará a la Papelera de reciclaje. La Papelera de reciclaje proporciona una red de seguridad de segundo nivel antes de eliminar permanentemente un elemento de un sitio. Para obtener más información acerca de la papelera de reciclaje, vea [vaciar la papelera de reciclaje o restaurar los archivos](http://go.microsoft.com/fwlink/p/?LinkID=404348).
    
  - Elija si la fecha de eliminación se calcula a partir de la fecha en que se creó o la fecha en que se modificó por última vez un documento.
    
  - Escriba un número de días, meses o años como el período de tiempo tras el cual se eliminará un documento.
    
  - Elija si la regla es una regla predeterminada. La primera regla que cree se establece automáticamente como la regla predeterminada. Una regla predeterminada se aplica automáticamente a todas las bibliotecas de los sitios que usan la directiva.
    
![Página para nueva regla de eliminación](media/IP-New-deletion-rule.png)
  
7. Haga clic en **Guardar **.
    
8. Cree reglas adicionales si quiere que los propietarios de los sitios puedan elegir distintas reglas para aplicar a su sitio. La regla predeterminada, si la hay, se aplicará si el propietario del sitio no realiza ninguna acción.
    
9. Para quitar una regla de una directiva, seleccione la regla, haga clic en **eliminar**y, a continuación, haga clic en **Aceptar**.
    
    > [!NOTE]
    > Si elimina una regla y la Directiva no contiene ninguna regla predeterminada, no se aplicará ninguna regla a esa Directiva; es decir, no se eliminará ningún documento. 
  
![Mensaje de confirmación para eliminar regla de directiva](media/IP-Remove-rule-from-policy-message.png)
  
## <a name="assign-the-document-deletion-policy-to-a-site-collection-template"></a>Asignar la directiva de eliminación de documentos a una plantilla de colección de sitios

Al asignar una directiva a una plantilla de colección de sitios, hace que la directiva esté disponible para todas las colecciones de sitios creadas a partir de esa plantilla, tanto las existentes como las que se creen en el futuro.
  
Es importante comprender que el período de tiempo especificado para una directiva de eliminación de documentos significa el tiempo desde que se creó o modificó el documento, no el tiempo desde que se asignó la Directiva. Cuando asigna la Directiva por primera vez, se evalúan todos los documentos del sitio y, si cumplen los criterios, se eliminarán. Esto se aplica a todos los documentos existentes, no solo a los nuevos documentos creados desde que se asignó la Directiva.
  
1. En el centro &amp; de seguridad y cumplimiento, vaya a **retención**de **Administración** \> de datos. En **eliminar**, haga clic en **Administrar directivas de eliminación de documentos para SharePoint Online y OneDrive para la empresa**. Se abrirá el Centro de directivas de eliminación de documentos en una nueva pestaña del explorador.
    
2. Elija **Asignaciones de directivas para plantillas**.
    
    ![Opción de asignaciones de directivas para plantillas](media/IP-Policy-Assignments-for-Templates-option.png)
  
3. Elija **Elemento nuevo**.
    
4. Siga uno de estos pasos:
    
  - Para asignar la directiva a una plantilla de colección de sitios como la plantilla Sitio de grupo, seleccione **Asignar a plantilla de colección de sitios** y, a continuación, seleccione la plantilla de colección de sitios.
    
  - Para asignar la Directiva a una única unidad de negocio de los usuarios, elija **asignar a plantilla de OneDrive para la empresa**, resaltado a continuación.
    
    > [!NOTE]
    > Cuando asigne una directiva a una plantilla de colección de sitios, dicha directiva estará disponible para las colecciones de sitios existentes creadas a partir de esa plantilla y para las que se creen en el futuro. 
  
![Página Seleccionar una plantilla con la opción OneDrive](media/IP-Choose-a-template.png)
  
5. Haga clic en **Guardar **.
    
    > [!NOTE]
    > Cada plantilla puede tener solamente un conjunto de directivas asignadas. Si ve un error que indica que esta plantilla ya tiene directivas asignadas, seleccione **Cancelar** \> **asignar a colección de sitios** en el panel de \> navegación izquierdo para ver y administrar el conjunto de directivas que ya están sin. 
  
6. Elija **Administrar directivas asignadas**, seleccione las directivas que quiere asignar y, a continuación, elija si una directiva es la directiva predeterminada. Cuando se establece una directiva predeterminada, todos los sitios asignados automáticamente a la directiva tienen la directiva activa sin necesidad de que el propietario del sitio realice ninguna acción.
    
    ![Página Agregar y administrar directivas](media/IP-Add-and-manage-policies-page.png)
  
7. Haga clic en **Guardar **.
    
8. Si quiere aplicar la directiva en todos los sitios sin permitir que los propietarios de sitios puedan anularla, elija **Marcar directiva como obligatoria**. Cuando establezca una directiva como obligatoria, solo podrá asignarse esa directiva a la plantilla de colección de sitios. La directiva también debe marcarse como predeterminada.
    
    Si esta opción está atenuada, elija **Administrar directivas asignadas** y asegúrese de que al menos una directiva esté asignada y establecida como predeterminada. 
    
9. Haga clic en **Guardar **.
    
## <a name="assign-the-document-deletion-policy-to-a-site-collection"></a>Asignar la directiva de eliminación de documentos a una colección de sitios

Al asignar una directiva a una colección de sitios determinada, hace que la directiva solo esté disponible para esa colección de sitios específica. Esto significa que las directivas se pueden adaptar según el contenido de la colección de sitios. Además, las directivas asignadas a una colección de sitios específica invalidará todas las directivas asignadas a la plantilla para esa colección de sitios. Por ejemplo, una directiva asignada a la colección de sitios del departamento de ventas (creada a partir de la plantilla Sitio de grupo) invalidará cualquier directiva asignada a la plantilla Sitio de grupo.
  
Es importante comprender que el período de tiempo especificado para una directiva de eliminación de documentos significa el tiempo desde que se creó o modificó el documento, no el tiempo desde que se asignó la Directiva. Cuando asigna la Directiva por primera vez, se evalúan todos los documentos del sitio y, si cumplen los criterios, se eliminarán. Esto se aplica a todos los documentos existentes, no solo a los nuevos documentos creados desde que se asignó la Directiva.
  
1. En el centro &amp; de seguridad y cumplimiento, vaya a **retención**de **Administración** \> de datos. En **eliminar**, elija **Administrar directivas de eliminación de documentos para SharePoint Online y OneDrive para la empresa**. Se abrirá el Centro de directivas de eliminación de documentos en una nueva pestaña del explorador.
    
2. Elija **Asignaciones de directivas para colecciones de sitios**.
    
    ![Opción de asignaciones de directivas para colecciones de sitios](media/IP-Policy-Assignments-for-Site-Collections-option.png)
  
3. Elija **Elemento nuevo**.
    
4. Elija **elegir una colección de sitios**. Busque la colección de sitios por nombre o dirección URL, seleccione la colección de sitios y haga clic en **Guardar**.
    
    > [!NOTE]
    > Cada colección de sitios puede tener solamente un conjunto de directivas asignadas. Si ve un error que indica que esta colección de sitios ya tiene directivas asignadas, elija **Cancelar** \> **asignar a colección de sitios** y seleccione una colección de sitios para ver y administrar el conjunto de directivas que ya están asignadas. 
  
![Página Seleccionar una colección de sitios](media/IP-Choose-a-site-collection-page.png)
  
5. Elija **Administrar directivas asignadas**, seleccione las directivas que quiere asignar y, a continuación, elija si una directiva es la directiva predeterminada. Cuando se establece una directiva predeterminada, todos los sitios asignados automáticamente a la directiva tienen la directiva activa sin necesidad de que el propietario del sitio realice ninguna acción.
    
    ![Página Agregar y administrar directivas](media/IP-Add-and-manage-policies-page.png)
  
6. Haga clic en **Guardar **.
    
7. Si quiere aplicar la directiva en todos los sitios sin permitir que los propietarios de sitios puedan anularla, elija **Marcar directiva como obligatoria**. Cuando establezca una directiva como obligatoria, solo podrá asignarse esa directiva a la colección de sitios. La directiva también debe marcarse como predeterminada.
    
    Si esta opción está atenuada, elija **Administrar directivas asignadas** y asegúrese de que al menos una directiva esté asignada y establecida como predeterminada. 
    
8. Haga clic en **Guardar **.
    
## <a name="delete-a-policy-assignment"></a>Eliminar una asignación de directivas

Cuando se elimina una asignación, las directivas asignadas ya no se aplicarán a ninguno de los sitios de la colección de sitios o la plantilla de colección de sitios.
  
1. En el centro &amp; de seguridad y cumplimiento, vaya a **retención**de **Administración** \> de datos. En **eliminar**, elija **Administrar directivas de eliminación de documentos para SharePoint Online y OneDrive para la empresa**. Se abrirá el Centro de directivas de eliminación de documentos en una nueva pestaña del explorador.
    
2. Elija **Asignaciones de directivas para plantillas** o **Asignaciones de directivas para colecciones de sitios**.
    
3. Seleccione el elemento de asignación y haga clic en **Eliminar elemento**.
    
    ![Comando Eliminar elemento para asignación de directiva](media/IP-Delete-policy-assignment.png)
  
## <a name="delete-a-policy"></a>Eliminar una directiva

No se puede eliminar una directiva que está en uso. Antes de poder eliminar una directiva, primero debe eliminar todas las asignaciones a las colecciones de sitios y las plantillas de colección de sitios que incluyan dicha Directiva; consulte la sección anterior.
  
1. En el centro &amp; \> de seguridad y cumplimiento, elija **retención** de **Administración** \> de \> datos en el panel de navegación izquierdo, en **eliminar** \> **Administrar directivas de eliminación de documentos para SharePoint Online y OneDrive para la empresa**. Se abrirá el Centro de directivas de eliminación de documentos en una nueva pestaña del explorador.
    
2. Elija * * directivas de eliminación * *.
    
    ![Opción Directivas de eliminación](media/IP-Deletion-Policies-option.png)
  
3. Seleccione la directiva.
    
4. En la pestaña \> **** \> elementos de la cinta de opciones, **Quite Directiva**.
    
    ![Botón Quitar directiva en cinta](media/IP-Remove-Policy-button-on-Ribbon.png)
  
5. Si la Directiva está en uso, se le preguntará si desea quitar la Directiva de todas las colecciones de sitios en las que se usa. Si está seguro, haga clic en **Aceptar**.
    
    ![Mensaje para confirmar eliminación de directiva](media/IP-Delete-policy-confirmation.png)
  
## <a name="see-also"></a>Vea también


  [Overview of document deletion policies](document-deletion-policies.md) (Información general sobre las directivas de eliminación de documentos)

[Aplicar o quitar una directiva de eliminación de documentos de un sitio](apply-or-remove-a-document-deletion-policy-for-a-site.md)
 

