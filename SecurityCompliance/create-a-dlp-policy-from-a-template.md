---
title: Crear una directiva DLP a partir de una plantilla
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: 'La forma más sencilla, más comunes para empezar a trabajar con directivas de DLP es utilizar una de las plantillas incluidas en Office 365. '
ms.openlocfilehash: 4e3a5d731538e4998858b5f9f7a296c43e6774ac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536250"
---
# <a name="create-a-dlp-policy-from-a-template"></a>Crear una directiva DLP a partir de una plantilla

La forma más sencilla, más comunes para empezar a trabajar con directivas de DLP es utilizar una de las plantillas incluidas en Office 365. Puede usar una de estas plantillas tal cual o personalizar las reglas para satisfacer los requisitos de cumplimiento de normas específicas de su organización.
  
Office 365 incluye más de 40 plantillas listas para usar que pueden ayudarle a cumplir con una amplia gama de necesidades normativas y de cumplimiento comunes. Por ejemplo, hay plantillas de directivas DLP para:
  
- Ley Gramm-Leach-Bliley (GLBA)
    
- Estándar de seguridad de datos de la industria de las tarjetas de pago (PCI DSS)
    
- Información de identificación personal de Estados Unidos (PII de EE.UU.)
    
- Ley de seguros médicos (HIPAA) de los Estados Unidos
    
Para ajustar una plantilla puede modificar cualquiera de las reglas existentes o agregar nuevas. Por ejemplo, puede agregar nuevos tipos de información confidencial a una regla, modificar los recuentos en una regla para que sea más difícil o fácil de desencadenar, permitir que los usuarios invaliden las acciones en una regla proporcionando una justificación del negocio o cambiar a quién se le envían notificaciones o informes de incidentes. Una plantilla de directiva DLP es un punto de partida flexible para muchos escenarios comunes de cumplimiento.
  
También puede elegir la plantilla personalizada, que no tiene ninguna regla predeterminada, y configurar la directiva DLP desde cero, para cumplir los requisitos de cumplimiento específicos para la organización.
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a>Ejemplo: Identificar la información confidencial a través de todos los OneDrive para sitios profesionales y restringir el acceso para las personas de fuera de la organización

OneDrive para las cuentas de negocio que sea fácil para los usuarios en toda la organización para colaborar y compartir documentos. Pero una preocupación común para los responsables del cumplimiento normativo es información confidencial almacenada en OneDrive para las cuentas de negocio puede compartirse sin darse cuenta con personas fuera de la organización. Una directiva de DLP puede ayudar a mitigar este riesgo.
  
En este ejemplo, creará una directiva de DLP que identifica los datos PII de Estados Unidos, que incluye los números de cuenta de passport de números de identificación de número de identificación fiscal Individual (CIF), números de seguridad Social y Estados Unidos. Podrá comenzar a trabajar con una plantilla y, a continuación, podrá modificar la plantilla para satisfacer los requisitos de cumplimiento de normas de la organización, en concreto, podrá:
  
- Agregar un par de tipos de números de cuenta bancaria confidencial information—U.S. y los números de licencia del controlador de Estados Unidos, por lo que la directiva de DLP protege aún más de sus datos confidenciales.
    
- Asegúrese de la directiva más confidencial, por lo que una sola aparición de información confidencial es suficiente para restringir el acceso de usuarios externos.
    
- Permitir que los usuarios invaliden las acciones por proporcionar una justificación comercial o informar de un falso positivo. De este modo, la directiva de DLP no impedir que personas de la organización de realizar su trabajo, siempre que dispongan de una razón empresarial válida para el uso compartido de la información confidencial.
    
### <a name="create-a-dlp-policy-from-a-template"></a>Crear una directiva DLP a partir de una plantilla

1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión en Office 365 con su cuenta de trabajo o escuela. Ahora está en la seguridad de Office 365 &amp; centro de cumplimiento.
    
3. En la seguridad &amp; centro de cumplimiento \> barra de navegación izquierda \> **prevención de pérdida de datos** \> **Directiva** \> **+ crear una directiva**.
    
    ![Crear un botón de directiva](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Elija la plantilla de directiva DLP que protege los tipos de información confidencial que necesita \> **siguiente**.
    
    En este ejemplo, seleccione **privacidad** \> **datos de Estados Unidos personalmente identificable información (PII)** porque ya incluye la mayoría de los tipos de información confidencial que se desea proteger, se agregará un par más adelante. 
    
    Al seleccionar una plantilla, puede leer la descripción de la derecha para saber lo que protege los tipos de información confidencial de la plantilla.
    
    ![Página para elegir una plantilla de directiva DLP](media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. Nombre de la directiva de \> **siguiente**.
    
6. Para elegir las ubicaciones que desea que la directiva DLP para proteger, realice una de las siguientes opciones:
    
  - Elija **todas las ubicaciones en Office 365** \> **siguiente**.
    
  - Elija **Permitirme elegir ubicaciones específicas** \> **siguiente**. Para este ejemplo, elija esta opción.
    
    Para incluir o excluir una ubicación completa como todos los correos electrónicos de Exchange o todas las cuentas de OneDrive, cambie el **estado** de esa ubicación activado o desactivado. 
    
    Para incluir solo específicos sitios de SharePoint o OneDrive para las cuentas de negocio, cambiar el **estado** a y, a continuación, haga clic en los vínculos en **incluir** elija sitios específicos o las cuentas. Cuando se aplica una directiva a un sitio, las reglas configuradas en que la directiva se aplican automáticamente a todos los subsitios de ese sitio. 
    
    ![Opciones de ubicaciones donde se puede aplicar una directiva DLP](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    En este ejemplo, para proteger información confidencial almacenada en todos los OneDrive para las cuentas de negocio, desactivar el **estado** de **correo electrónico de Exchange** y **sitios de SharePoint**y deje el **estado** en para **las cuentas de OneDrive**.
    
7. Elija **Usar configuración avanzada** \> **siguiente**.
    
8. Una plantilla de directiva DLP contiene reglas predefinidas con las condiciones y acciones que se detectan y actúan sobre tipos específicos de información confidencial. Puede editar, eliminar, o desactivar cualquiera de las reglas existentes o agregar nuevos. Cuando haya terminado, haga clic en **siguiente**.
    
    ![Reglas de expanden en la plantilla de directiva de PII con nosotros](media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    En este ejemplo, la plantilla de datos PII de Estados Unidos incluye dos reglas predefinidas:
    
  - **Bajo volumen de contenido detectado PII de Estados Unidos** Esta regla busca archivos que contienen entre 1 y 10 repeticiones de cada uno de los tres tipos de información confidencial (CIF SSN números y Estados Unidos passport), donde los archivos se comparten con personas fuera de la organización. Si se encuentra, la regla envía una notificación de correo electrónico al administrador de colección de sitios primaria, propietario del documento, y la última persona que modificó el documento. 
    
  - **Gran volumen de contenido detectado PII de Estados Unidos** Esta regla busca los archivos que contiene 10 o más apariciones de cada uno de los mismos tipos de información confidencial tres, donde los archivos se comparten con personas fuera de la organización. Si se encuentra, esta acción también envía una notificación de correo electrónico, además de restringe el acceso al archivo. Para el contenido en un OneDrive para la cuenta de empresa, esto significa que los permisos para el documento están restringidos para todos los usuarios, excepto el Administrador de la colección de sitios primaria, el propietario del documento y la persona que modificó por última vez el documento. 
    
    Para satisfacer los requisitos específicos de su organización, es posible que desea que sea más fácil desencadenador, las reglas para que una sola aparición de información confidencial es suficiente para bloquear el acceso de usuarios externos. Después de examinar estas reglas, comprender que no necesita las reglas de recuento alta y baja: necesita sólo una sola regla que bloquea el acceso si se encuentra cualquier aparición de información confidencial.
    
    Para expandir la regla denominada **bajo volumen de contenido detectado US PII** \> **eliminar la regla**.
    
    ![Eliminar botón regla](media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. Ahora, en este ejemplo, se necesita para agregar dos tipos de información confidencial (números de cuenta bancaria de Estados Unidos y los números de licencia del controlador de Estados Unidos), permiten a las personas reemplazar una regla y cambia el recuento a cualquier aparición. Puede hacer todo esto mediante la edición de una regla, así que seleccione **gran volumen de contenido detectado US PII** \> **Editar regla**.
    
    ![Editar botón regla](media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. Para agregar un tipo de información confidencial, en la sección **condiciones** \> **tipos de agregar o cambiar**. A continuación, en **Agregar o cambiar tipos** \> elija **Agregar** \> seleccione el **Número de cuenta bancaria de Estados Unidos** y el **Número de licencia del controlador de Estados Unidos** \> **Agregar** \> **hecho**.
    
    ![Opción para agregar o cambiar tipos](media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![Agregar o cambiar el panel de tipos](media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. Para cambiar el recuento (el número de instancias de la información confidencial necesaria para desencadenar la regla), en el **recuento de instancias de** \> elegir el valor de **min** para cada tipo de \> escriba 1. El recuento mínimo no puede estar vacío. El recuento máximo puede estar vacío; un valor vacío **max** convertir a **cualquier**.
    
    Cuando haya terminado, el recuento de min para todos los tipos de información confidencial de debe ser **1** y el recuento máximo debe ser **cualquier**. En otras palabras, cualquier aparición de este tipo de información confidencial satisfará esta condición.
    
    ![Recuentos de instancia de tipos de información confidencial](media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. Para la personalización final, no desea que las directivas de DLP para bloquear las personas puedan realizar su trabajo cuando tiene una justificación comercial válido o se encuentra un falso positivo, por lo que desea que la notificación de usuario para incluir opciones para reemplazar la acción de bloqueo.
    
    En la sección **notificaciones de usuario** , puede ver que las notificaciones de correo electrónico y sugerencias de directiva están activadas de forma predeterminada para esta regla en la plantilla. 
    
    En la sección **usuario anula** , puede ver que están encendidos reemplazos para una justificación comercial, pero los reemplazos para informar de falsos positivos no están. Elija **invalidar la regla automáticamente si identificarlo como falso positivo**.
    
    ![Sección de notificaciones de usuario y la sección de invalidaciones de usuario](media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. En la parte superior del editor de reglas, cambie el nombre de esta regla de la predeterminada de **gran volumen de contenido había detectado PII de Estados Unidos** a **cualquier contenido detectado con US PII** debido a que ahora se desencadena por cualquier aparición de sus tipos de información confidencial. 
    
14. En la parte inferior del editor de reglas \> **Guardar**.
    
15. Revise las condiciones y acciones para esta regla \> **siguiente**.
    
    En la derecha, tenga en cuenta el **estado** de modificador para la regla. Si desactiva una directiva completa, también se desactivan todas las reglas de contenidos en la directiva. Sin embargo, aquí se puede desactivar una regla específica sin desactivar la directiva completa. Esto puede resultar útil cuando se necesita para investigar una regla que genera un gran número de falsos positivos. 
    
16. En la página siguiente, leer y comprender lo siguiente y, a continuación, elija si desea activar la regla o probar primero \> **siguiente**.
    
     Antes de crear las directivas de DLP, considere la posibilidad de implantar ellos gradualmente para evaluar su impacto y probar su eficacia antes de aplicarlas totalmente. Por ejemplo, no desea una nueva directiva de DLP por equivocación bloquear el acceso a miles de documentos que las personas que necesitan para realizar su trabajo. 
    
    Si está creando directivas de DLP con un gran impacto potencial, se recomienda seguir esta secuencia:
    
17. Inicie en modo de prueba sin sugerencias de directiva y, a continuación, use los informes DLP para evaluar el impacto. Los informes DLP le sirven para ver el número, la ubicación, el tipo y la gravedad de las coincidencias de directivas. En función de los resultados, puede ajustar las reglas según sea necesario. En el modo de prueba, las directivas DLP no afectarán a la productividad de las personas que trabajan en su organización. 
    
18. Cambie a modo de prueba con notificaciones y sugerencias de directivas para que pueda comenzar a enseñar a los usuarios las directivas de cumplimiento y prepararlos para las reglas que se van a aplicar. En esta fase, también puede solicitar a los usuarios que informen de falsos positivos para que pueda perfeccionar las reglas de los usuarios.
    
19. Activar las directivas de modo que se aplican las reglas y el contenido protegido. Continuar supervisar los informes DLP y los informes de incidentes o notificaciones para asegurarse de que los resultados son lo que piensa. 
    
    ![Opciones para usar el modo de prueba y activar la directiva](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. Revise las opciones para esta directiva \> elija **crear**.
    
Después de crear y activar una directiva de DLP, se implementa para los orígenes de contenido que incluye, como sitios de SharePoint Online o OneDrive para las cuentas de negocio, donde la directiva comienza aplicando sus reglas en el que el contenido de forma automática.
  
## <a name="view-the-status-of-a-dlp-policy"></a>Ver el estado de una directiva DLP

En cualquier momento, puede ver el estado de sus directivas DLP en la página de **Directiva** en la sección de **prevención de pérdida de datos** de la seguridad &amp; centro de cumplimiento. Aquí encontrará información importante, por ejemplo, si una directiva se habilitó o deshabilitó correctamente, o si la directiva está en modo de prueba. 
  
A continuación, se enumeran los distintos estados y su significado.
  
|**Estado**|**Explicación**|
|:-----|:-----|
|**Activando...** <br/> |La directiva se está implementando en los orígenes de contenido que incluye. Aún no se exige la directiva en todos los orígenes.  <br/> |
|**Probando, con notificaciones** <br/> |La directiva está en modo de prueba. No se aplican las acciones en una regla, pero las coincidencias de directiva se recopilan y se pueden ver con los informes de DLP. Las notificaciones sobre las coincidencias de directiva se envían a los destinatarios especificados.  <br/> |
|**Probando, sin notificaciones** <br/> |La directiva está en modo de prueba. No se aplican las acciones en una regla, pero las coincidencias de directiva se recopilan y se pueden ver con los informes de DLP. Las notificaciones sobre las coincidencias de directiva no se envían a los destinatarios especificados.  <br/> |
|**Activo** <br/> |La directiva está activa y se exige. La directiva se implementó correctamente en todos sus orígenes de contenido.  <br/> |
|**Desactivando...** <br/> |La directiva se está quitando de los orígenes de contenido que incluye. La directiva todavía puede estar activa y exigirse en algunos orígenes. La desactivación de una directiva puede tardar hasta 45 minutos.  <br/> |
|**Desactivado** <br/> |La directiva no está activa y no se exige. Se guarda la configuración de la directiva (orígenes, palabras clave, duración, etc.).  <br/> |
|**Eliminando...** <br/> |La directiva está en proceso de eliminación. La directiva no está activa y no se exige.  <br/> |
   
## <a name="turn-off-a-dlp-policy"></a>Desactivar una directiva DLP

Puede editar o desactivar una directiva de DLP en cualquier momento. Desactivación de una directiva deshabilita todas las reglas en la directiva.
  
Para editar o desactivar una directiva de DLP, en la página **Directiva** \> seleccione la directiva de \> **Editar directiva**.
  
![Botón de la directiva de edición](media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
Además, puede desactivar cada regla de forma individual mediante la edición de la directiva y, a continuación, alternar desactiva el **estado** de esa regla, tal y como se ha descrito anteriormente. 
  
## <a name="more-information"></a>Más información

- [Información general sobre directivas de prevención de pérdida de datos](data-loss-prevention-policies.md)
    
- [Enviar notificaciones y mostrar sugerencias para directivas DLP](use-notifications-and-policy-tips.md)
    
- [Crear una directiva DLP para proteger documentos con FCI u otras propiedades](protect-documents-that-have-fci-or-other-properties.md)
    
- [Qué incluyen las plantillas de directiva DLP](what-the-dlp-policy-templates-include.md)
    
- [Inventario de tipos de información confidencial](what-the-sensitive-information-types-look-for.md)
    

