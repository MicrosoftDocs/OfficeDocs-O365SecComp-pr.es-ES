---
title: Preguntas más frecuentes acerca de cómo importar archivos PST a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: 'Preguntas más frecuentes para los administradores acerca de cómo utilizar el servicio de Office 365 importar para importar los archivos PST de su organizaiton a buzones de Office 365. '
ms.openlocfilehash: 7230e68f896766df643f12b2a132f987670e9afa
ms.sourcegitcommit: eecf6f3aafbf460ee2ff9988f2b055e62b1fdb9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454057"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>Preguntas más frecuentes acerca de cómo importar archivos PST a Office 365

**En este artículo está dirigido a administradores. ¿Desea importar los archivos PST en su propio buzón? Consulte el [correo electrónico de importación, contactos y calendario desde un archivo .pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
Estas son algunas preguntas más frecuentes sobre cómo utilizar el servicio de importación de Office 365 para importación masiva de archivos PST a buzones de correo de Office 365. Para obtener más información acerca de cómo importar archivos PST, vea [información general de importación de los archivos PST a Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).
  
## <a name="using-network-upload-to-import-pst-files"></a>Uso de carga de red para importar archivos PST

Para obtener instrucciones detalladas, consulte [Use network cargar para importar archivos PST a Office 365](use-network-upload-to-import-pst-files.md).
  
 **¿Qué permisos son necesarios para crear trabajos de importación en el servicio de Office 365 importar?**
  
Se debe asignar la función de importación de exportación de buzones de correo en Exchange en línea para importar archivos PST a buzones de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de funciones en Exchange Online. Puede agregar la función de exportación de importación de buzón de correo para el grupo de roles de administración de la organización. O bien, puede crear un nuevo grupo de roles, asignar el rol de buzón de correo importar exportar y, a continuación, agregue a usted o a otros usuarios como un miembro. Para obtener más información, vea el "Agregar un rol a un grupo de roles" o la "crear un grupo de roles" secciones en [función de administrar grupos en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Además crear la importación de trabajos en la seguridad de Office 365 &amp; debe ser verdadero centro de cumplimiento, uno de los siguientes:
  
- Se debe tener asignado el rol de destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de funciones de administración de la organización y administración de destinatarios.
    
    O bien
    
- Debe ser un administrador global de la organización de Office 365.
    
> [!TIP]
> Considere la posibilidad de crear un nuevo grupo de funciones en Exchange Online diseñada específicamente para la importación de los archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar los archivos PST, asigne las funciones de importación de exportación de buzones de correo y destinatarios de correo para el nuevo grupo de roles y, a continuación, agregar a miembros. 
  
 **¿Dónde está disponible la carga de red?**
  
Carga de red está actualmente disponible en los Estados Unidos, Canadá, Brasil, el Reino Unido, Francia, Europa, India, Asia oriental, sureste de Asia, Japón, República de Corea y Australia. Carga de red estará disponible en las regiones más pronto.
  
 **¿Cuál es el precio de importación de los archivos PST mediante el uso de carga de red?**
  
Uso de carga de red para importar archivos PST es gratuito.
  
Esto también significa que después de que se eliminan los archivos PST desde el área de almacenamiento de Azure, está ya no se muestran en la lista de archivos para un trabajo de importación completadas en el centro de administración de Office 365. Aunque un trabajo de importación puede seguir apareciendo en la página **Importar datos a Office 365** , la lista de los archivos PST podría estar vacía al ver los detalles de los trabajos de importación más antiguos. 
  
 **¿Qué versión del formato de archivo PST se admite para la importación a Office 365?**
  
Hay dos versiones del formato de archivo PST: ANSI y Unicode. Se recomienda importar los archivos que usan el formato de archivo PST Unicode. Sin embargo, los archivos que usan el formato de archivo PST ANSI, como los de los idiomas que usan un carácter de doble byte (DBCS) de establecer, también se pueden importar a Office 365. Para obtener más información acerca de cómo importar archivos PST ANSI, consulte el paso 4 en la [red de uso cargar para importar los archivos PST de su organización a Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).
  
Además, se pueden importar los archivos PST de Outlook 2007 y versiones posteriores a Office 365.
  
 **¿Después de que cargan Mis archivos PST en el área de almacenamiento de Azure, cuánto se conservan en Azure antes de que se eliminan?**
  
Cuando se usa el método de carga de red para importar archivos PST, se carga a un contenedor de Azure blob denominado **ingestiondata**. Si no hay ningún trabajo de importación en curso en la página **Importar** en la seguridad &amp; centro de cumplimiento), a continuación, se eliminan todos los archivos PST en el contenedor **ingestiondata** de Azure 30 días después de que se creó el trabajo de importación más reciente en la seguridad &amp;Centro de cumplimiento. Esto significa también tiene que crear un nuevo trabajo de importación en la seguridad &amp; centro de cumplimiento (se describe en el paso 5 en las instrucciones de carga de red) dentro de 30 días de PST de cargar archivos en Azure. 
  
Esto también significa que después de que se eliminan los archivos PST desde el área de almacenamiento de Azure, está ya no se muestran en la lista de archivos para un trabajo de importación completadas en la seguridad &amp; centro de cumplimiento. Aunque un trabajo de importación puede seguir apareciendo en la página **Importar** en la seguridad &amp; centro de cumplimiento, la lista de los archivos PST podría estar vacía al ver los detalles de los trabajos de importación más antiguos. 
  
 **¿Cuánto tiempo tarda para importar un archivo PST a un buzón de correo?**
  
Depende de la capacidad de la red, pero normalmente tiene varias horas para cada terabyte (TB) de datos que se cargan en el área de almacenamiento de Azure para su organización. Una vez copiados los archivos PST al área de almacenamiento de Azure, se importa un archivo PST a un buzón de Office 365 a una velocidad de al menos 24 GB por día. Si esta velocidad no satisface sus necesidades, es posible que tenga en cuenta otros métodos para migrar datos de correo electrónico a Office 365. Para obtener más información, vea [formas de migrar cuentas de correo electrónico a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Si se importan diferentes archivos PST a buzones de correo de destino diferente, el proceso de importación se produce en paralelo; en otras palabras, cada par de PST y buzón de correo se importa simultáneamente. Del mismo modo, si se importan varios archivos PST en el mismo buzón, se importará simultáneamente.
  
 **¿Hay un límite de tamaño de mensaje al importar los archivos PST?**
  
Sí. Si un archivo PST contiene un elemento de buzón de correo que es mayor que 150 MB, se omitirá el elemento durante el proceso de importación.
  
 **¿Son propiedades del mensaje, por ejemplo, cuando el mensaje se envió o recibió, la lista de destinatarios y otras propiedades, que se conserva cuando se importan archivos PST a un buzón de Office 365?**
  
Sí. Los metadatos del mensaje original no ha cambiado durante el proceso de importación.
  
 **¿Hay un límite para el número de niveles en una jerarquía de carpetas de un archivo PST que va a importar a un buzón de correo?**
  
Sí. No se puede importar un archivo PST que tiene 300 o más niveles de carpetas anidadas.
  
 **¿Puedo usar la carga de red para importar archivos PST a un buzón de correo inactivo en Office 365?**
  
Sí, esta capacidad está ahora disponible.
  
 **¿Puedo usar la carga de red para importar archivos PST a un buzón de archivo en línea en una implementación híbrida de Exchange?**
  
Sí, esta capacidad está ahora disponible.
  
 **¿Puedo usar carga de red para importar archivos PST a las carpetas públicas en Exchange Online?**
  
No, no se puede importar archivos PST a las carpetas públicas.
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Uso de trasvase de registros de unidad para importar archivos PST

Para obtener instrucciones detalladas, consulte [Usar unidad de envío para importar archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
 **¿Qué permisos son necesarios para crear trabajos de importación en el servicio de Office 365 importar?**
  
Se debe tener asignado el rol de buzón de correo importar exportar para importar archivos PST a buzones de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de funciones en Exchange Online. Puede agregar la función de exportación de importación de buzón de correo para el grupo de roles de administración de la organización. O bien, puede crear un nuevo grupo de roles, asignar el rol de buzón de correo importar exportar y, a continuación, agregue a usted o a otros usuarios como un miembro. Para obtener más información, vea el "Agregar un rol a un grupo de roles" o la "crear un grupo de roles" secciones en [función de administrar grupos en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Además crear la importación de trabajos en la seguridad de Office 365 &amp; debe ser verdadero centro de cumplimiento, uno de los siguientes:
  
- Se debe tener asignado el rol de destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de funciones de administración de la organización y administración de destinatarios.
    
    O bien
    
- Debe ser un administrador global de la organización de Office 365.
    
> [!TIP]
> Considere la posibilidad de crear un nuevo grupo de funciones en Exchange Online diseñada específicamente para la importación de los archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar los archivos PST, asigne las funciones de importación de exportación de buzones de correo y destinatarios de correo para el nuevo grupo de roles y, a continuación, agregar a miembros. 
  
 **¿Dónde se está publicando disponible unidad?**
  
Envío de la unidad está disponible actualmente en los Estados Unidos, Canadá, Brasil, el Reino Unido, Europa, India, Asia oriental, sureste de Asia, Japón, República de Corea y Australia. Envío de unidad estará disponible en las regiones más pronto.
  
 **¿Qué contratos de licencia comerciales son compatibles con el trasvase de registros de unidad?**
  
Unidad de envío para importar archivos PST a Office 365 está disponible a través de un contrato Enterprise de Microsoft (EA). Unidad de trasvase de registros no está disponible a través de un Microsoft Products y un contrato de servicios (MPSA).
  
 **¿Cuál es el precio para el uso de unidad de envío para importar archivos PST a Office 365?**
  
El costo de utilizar el trasvase de unidad para importar archivos PST a buzones de correo de Office 365 es tan sólo 2 dólares por GB de datos. Por ejemplo, si incluye una unidad de disco duro que contiene 1.000 GB (1 TB) de los archivos PST, el costo es $2.000 USD. Puede trabajar con un socio de pago de la cuota de importación. Para obtener información acerca de cómo buscar a un socio, vea [encontrar su socio de Office 365 o revendedor](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **¿Qué tipo de disco duros unidades son compatibles para el envío de unidad?**
  
Unidades de sólo 2,5 pulgadas de estado sólido (SSD) o 2,5 o 3,5 pulgadas SATA II/III interno unidades de disco duro compatibles para su uso con el servicio de importación de Office 365. Puede usar unidades de disco duro hasta 10 TB. Para los trabajos de importación, se procesarán solo el primer volumen de datos en la unidad de disco duro. El volumen de datos debe tener el formato NTFS. Cuando se copian datos a una unidad de disco duro, puede adjuntarlo directamente con un SSD de 2,5 pulgadas o 2,5 o 3,5 pulgadas conector SATA II/III o puede adjuntar externamente mediante un SSD de 2,5 pulgadas externo o adaptador de SATA II/III USB 2,5 o 3,5 pulgadas.
  
> [!IMPORTANT]
> Unidades de disco duro externas que vienen con un adaptador USB integrado no son compatibles con el servicio de importación de Office 365. Además, no se puede utilizar el disco dentro de mayúsculas y minúsculas de una unidad de disco duro externa. Por favor, no se suministran unidades de disco duro externas. 
  
 **¿Cuántas unidades de disco duro puedo enviar para un trabajo de importación único?**
  
Puede enviar un máximo de 10 unidades de disco duro para un trabajo de importación único.
  
 **Después de se suministran mi unidad de disco duro, ¿cuánto tiempo se tarda en obtener en el centro de datos de Microsoft?**
  
Que depende de varios factores, como la proximidad al centro de datos de Microsoft y qué tipo de opción de envío utilizado para el envío de la unidad de disco duro (por ejemplo, entrega el día siguiente, dos días entrega o entrega de tierra). Con la mayoría de los destinatarios, puede usar el número de seguimiento para realizar un seguimiento del estado de la entrega.
  
 **Después de que la unidad de disco duro llega en el centro de datos de Microsoft, ¿cuánto tiempo tarda para cargar los archivos PST en Azure?**
  
Después de la unidad de disco duro se recibe en el centro de datos de Microsoft, se tardará entre 7 y 10 días de negocio para cargar los archivos PST en el área de almacenamiento de información de Microsoft Azure para su organización. Los archivos PST se cargarán en un contenedor de Azure blob denominado **ingestiondata**. 
  
 **¿Cuánto tiempo tarda para importar un archivo PST a un buzón de correo?**
  
Después de que se cargan los archivos PST en el área de almacenamiento de Azure, Office 365 analiza los datos en los archivos PST (de forma segura) para identificar la antigüedad de los elementos y los tipos de mensaje diferentes incluidos en los archivos PST. Una vez completado este análisis, tendrá la opción de importar todos los datos en los archivos PST o establecimiento de filtros para que controlar qué datos obtiene importados. Después de iniciar el trabajo de importación, se importa un archivo PST a un buzón de Office 365 a una velocidad de al menos 24 GB por día. Si esta velocidad no satisface sus necesidades, es posible que tenga en cuenta otros métodos para importar datos de correo electrónico a Office 365. Para obtener más información, vea [formas de migrar cuentas de correo electrónico a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Si se importan diferentes archivos PST a buzones de correo de destino diferente, el proceso de importación se produce en paralelo; en otras palabras, cada par de PST y buzón de correo se importa simultáneamente. Del mismo modo, si se importan varios archivos PST en el mismo buzón, se importará simultáneamente.
  
 **¿Después de que Microsoft carga Mis archivos PST en Azure, cuánto se conservan en Azure antes de que se eliminan?**
  
Todos los archivos PST en la ubicación de almacenamiento de Azure para su organización (en el contenedor de blob denominado **ingestiondata** ), se eliminan los 30 días después de que se creó el trabajo de importación más reciente en la página **Importar** en la seguridad &amp; centro de cumplimiento. 
  
Esto también significa que después de que se eliminan los archivos PST desde el área de almacenamiento de Azure, está ya no se muestran en la lista de archivos para un trabajo de importación completadas en la seguridad &amp; centro de cumplimiento. Aunque un trabajo de importación puede seguir apareciendo en la página **Importar** en la seguridad &amp; centro de cumplimiento, la lista de los archivos PST podría estar vacía al ver los detalles de los trabajos de importación más antiguos. 
  
 **¿Qué versión del formato de archivo PST se admite para la importación a Office 365?**
  
Hay dos versiones del formato de archivo PST: ANSI y Unicode. Se recomienda importar los archivos que usan el formato de archivo PST Unicode. Sin embargo, los archivos que usan el formato de archivo PST ANSI, como los de los idiomas que usan un carácter de doble byte (DBCS) de establecer, también se pueden importar a Office 365. Para obtener más información acerca de cómo importar archivos PST ANSI, vea el paso 3 en [Usar unidad de envío para importar archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Además, se pueden importar los archivos PST de Outlook 2007 y versiones posteriores a Office 365.
  
 **¿Hay un límite de tamaño de mensaje al importar los archivos PST?**
  
Sí. Si un archivo PST contiene un elemento de buzón de correo que es mayor que 150 MB, se omitirá el elemento durante el proceso de importación.
  
 **¿Son propiedades del mensaje, por ejemplo, cuando el mensaje se envió o recibió, la lista de destinatarios y otras propiedades, que se conserva cuando se importan archivos PST a un buzón de Office 365?**
  
Sí. Los metadatos del mensaje original no ha cambiado durante el proceso de importación
  
 **¿Hay un límite para el número de niveles en una jerarquía de carpetas de un archivo PST que va a importar a un buzón de correo?**
  
Sí. No se puede importar un archivo PST que tiene 300 o más niveles de carpetas anidadas.
  
 **¿Puedo usar el trasvase de registros de unidad para importar archivos PST a un buzón de correo inactivo en Office 365?**
  
Sí, esta capacidad está ahora disponible.
  
 **¿Puedo usar el trasvase de registros de unidad para importar archivos PST a un buzón de archivo en línea en una implementación híbrida de Exchange?**
  
Sí, esta capacidad está ahora disponible.
  
 **¿Puedo usar el trasvase de registros de unidad para importar archivos PST a las carpetas públicas en Exchange Online?**
  
No, no se puede importar archivos PST a las carpetas públicas.
  
 **¿Puede borrar Microsoft mi unidad de disco duro antes de enviarlos a mí?**
  
No, Microsoft no puede borrar unidades de disco duro antes de enviarlos a los clientes. Unidades de disco duro se devuelven en el mismo estado en que estaban cuando se recibieron por Microsoft.
  
 **¿Puede purgar mi unidad de disco duro en lugar de envío de vuelta al me de Microsoft?**
  
No, Microsoft no puede destruir el disco duro. Unidades de disco duro se devuelven en el mismo estado en que estaban cuando se recibieron por Microsoft.
  
 **¿Qué servicios de correos son compatibles para los gastos de envío?**
  
Si usted es un cliente en los Estados Unidos o Europa, Microsoft utiliza FedEx para devolver la unidad de disco duro. Para todas las demás regiones, Microsoft utiliza DHL.
  
 **¿Cuáles son los costos de trasvase de registros devueltos?**
  
Devolver los gastos de envío varían en función de su proximidad al centro de datos de Microsoft que se incluyen en la unidad de disco duro. Microsoft bill su cuenta FedEx o DHL para devolver la unidad de disco duro. El costo de los gastos de envío es su responsabilidad.
  
 **¿Puedo usar un servicio de trasvase de registros de courier personalizados, como FedEx personalizado trasvase de registros, para enviar mi unidad de disco duro a Microsoft?**
  
Sí.
  
 **Si tiene que enviar mi unidad de disco duro a otro país, ¿hay algo tengo que hacer?**
  
La unidad de disco duro que se envían a Microsoft que tenga que cruzar fronteras internacionales. Si éste es el caso, está responsable para garantizar que se importan o exportan con arreglo a la legislación vigente de la unidad de disco duro y los datos que contiene. Antes de enviar una unidad de disco duro, compruebe con sus asesores para comprobar que los datos y la unidad pueden legalmente se van a enviar al centro de datos de Microsoft especificado. Esto le ayudará a asegurarse de que llega Microsoft de manera oportuna.
