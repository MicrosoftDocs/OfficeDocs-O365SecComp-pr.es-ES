---
title: Preguntas más frecuentes sobre la importación de archivos PST a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: 'Preguntas más frecuentes para los administradores sobre el uso del servicio de importación de Office 365 para importar los archivos PST de organizaiton a los buzones de Office 365. '
ms.openlocfilehash: 9ca2e206a1d06c1398181c51e41b4dc68d8d965c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218410"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>Preguntas más frecuentes sobre la importación de archivos PST a Office 365

**Este artículo está destinado a los administradores. ¿Desea importar los archivos PST a su propio buzón? Consulte [importar el correo electrónico, los contactos y el calendario desde un archivo. pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
Estas son algunas de las preguntas más frecuentes sobre el uso del servicio de importación de Office 365 para importar archivos PST en masa a los buzones de Office 365. Para obtener más información acerca de cómo importar archivos PST, vea [información general sobre la importación de archivos PST a Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).
  
## <a name="using-network-upload-to-import-pst-files"></a>Uso de la carga de red para importar archivos PST

Para obtener instrucciones paso a paso, consulte [usar la carga de red para importar archivos PST a Office 365](use-network-upload-to-import-pst-files.md).
  
 **¿Qué permisos se necesitan para crear trabajos de importación en el servicio de importación de Office 365?**
  
Debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online para importar archivos PST a los buzones de correo de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización. O bien, puede crear un nuevo grupo de roles, asignar el rol exportar importación y, a continuación, agregarse a usted mismo o a otros usuarios como miembro. Para obtener más información, vea las secciones "agregar un rol a un grupo de roles" o "crear un grupo de roles" en [Manage role Groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Además, para crear trabajos de importación en el centro de &amp; seguridad y cumplimiento de Office 365, debe cumplirse una de las siguientes condiciones:
  
- Debe tener asignado el rol destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos administración de la organización y roles de administración de destinatarios.
    
    O bien
    
- Debe ser administrador global de la organización de Office 365.
    
> [!TIP]
> Considere la posibilidad de crear un nuevo grupo de roles en Exchange online que esté destinado específicamente a importar archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles Mailbox Import Export y mail Recipients al nuevo grupo de roles y, a continuación, agregue members. 
  
 **¿Dónde está disponible la carga en la red?**
  
La carga de red está disponible actualmente en Estados Unidos, Canadá, Brasil, Reino Unido, Francia, Europa, India, este asiático, sudeste asiático, Japón, República de Corea y Australia. La carga de red estará disponible próximamente en más regiones.
  
 **¿Cuál es el precio de la importación de archivos PST mediante la carga de red?**
  
El uso de la carga de red para importar archivos PST es gratuito.
  
Esto también significa que después de eliminar los archivos PST del área de almacenamiento de Azure, ya no se muestran en la lista de archivos para un trabajo de importación completado en el centro de administración de Office 365. Aunque un trabajo de importación todavía puede aparecer en la página **importar datos a Office 365** , es posible que la lista de archivos PST esté vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **¿Qué versión del formato de archivo PST se admite para importar a Office 365?**
  
Hay dos versiones del formato de archivo PST: ANSI y Unicode. Se recomienda importar archivos que usen el formato de archivo PST Unicode. Sin embargo, los archivos que usan el formato de archivo PST ANSI, como los idiomas que usan un juego de caracteres de doble byte (DBCS), también se pueden importar a Office 365. Para obtener más información acerca de la importación de archivos PST ANSI, consulte el paso 4 en [usar la carga en la red para importar los archivos PST de su organización a Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).
  
Además, los archivos PST de Outlook 2007 y versiones posteriores pueden importarse a Office 365.
  
 **Después de cargar los archivos PST en el área de almacenamiento de Azure, ¿cuánto tiempo se conservan en Azure antes de que se eliminen?**
  
Cuando use el método de carga de red para importar archivos PST, puede cargarlos en un contenedor de blobs de Azure denominado **ingestiondata**. Si no hay ningún trabajo de importación en curso en la página **importar** del centro &amp; de seguridad y cumplimiento), se eliminarán todos los archivos PST del contenedor de **ingestiondata** en Azure a los 30 días de la creación del trabajo de importación más reciente en la seguridad &amp;Centro de cumplimiento. Esto significa que, además, tiene que crear un nuevo trabajo de importación &amp; en el centro de seguridad y cumplimiento (descrito en el paso 5 de las instrucciones de carga de red) en un plazo de 30 días después de cargar los archivos PST a Azure. 
  
Esto también significa que después de eliminar los archivos PST del área de almacenamiento de Azure, ya no se muestran en la lista de archivos para un trabajo de importación completado en &amp; el centro de seguridad y cumplimiento. Aunque un trabajo de importación puede seguir en la lista de la página **importar** en &amp; el centro de seguridad y cumplimiento, es posible que la lista de archivos PST esté vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **¿Cuánto tiempo se tarda en importar un archivo PST en un buzón?**
  
Depende de la capacidad de la red, pero normalmente tarda varias horas en cargar cada terabyte (TB) de datos en el área de almacenamiento de Azure de su organización. Una vez que se han copiado los archivos PST en el área de almacenamiento de Azure, se importa un archivo PST a un buzón de correo de Office 365 a una velocidad de al menos 24 GB al día. Si esta tasa no satisface sus necesidades, puede considerar otros métodos para migrar datos de correo electrónico a Office 365. Para obtener más información, vea [formas de migrar varias cuentas de correo electrónico a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Si se importan diferentes archivos PST a distintos buzones de destino, el proceso de importación se produce en paralelo; es decir, cada pareja de PST/buzón se importa de forma simultánea. Del mismo modo, si se importan varios archivos PST al mismo buzón, se importarán de forma simultánea.
  
 **¿Hay un límite de tamaño de mensaje al importar archivos PST?**
  
Afirma. Si un archivo PST contiene un elemento de buzón de más de 150 MB, el elemento se omitirá durante el proceso de importación.
  
 **¿Se conservan las propiedades de los mensajes, como Cuándo se envió o recibió el mensaje, la lista de destinatarios y otras propiedades, que se conservan cuando se importan los archivos PST a un buzón de Office 365?**
  
Afirma. Los metadatos del mensaje original no se modifican durante el proceso de importación.
  
 **¿Hay un límite para el número de niveles de una jerarquía de carpetas para un archivo PST que deseo importar a un buzón?**
  
Afirma. No puede importar un archivo PST con 300 o más niveles de carpetas anidadas.
  
 **¿Puedo usar la carga en la red para importar archivos PST a un buzón inactivo en Office 365?**
  
Sí, esta capacidad ya está disponible.
  
 **¿Puedo usar la carga en la red para importar archivos PST a un buzón de archivo en línea en una implementación híbrida de Exchange?**
  
Sí, esta capacidad ya está disponible.
  
 **¿Puedo usar la carga en la red para importar archivos PST a carpetas públicas en Exchange Online?**
  
No, no puede importar archivos PST a carpetas públicas.
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Uso del envío de unidades para importar archivos PST

Para obtener instrucciones paso a paso, consulte [usar el envío de unidades para importar archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
 **¿Qué permisos se necesitan para crear trabajos de importación en el servicio de importación de Office 365?**
  
Debe tener asignado el rol importación y exportación de buzones para importar los archivos PST a los buzones de correo de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización. O bien, puede crear un nuevo grupo de roles, asignar el rol exportar importación y, a continuación, agregarse a usted mismo o a otros usuarios como miembro. Para obtener más información, vea las secciones "agregar un rol a un grupo de roles" o "crear un grupo de roles" en [Manage role Groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Además, para crear trabajos de importación en el centro de &amp; seguridad y cumplimiento de Office 365, debe cumplirse una de las siguientes condiciones:
  
- Debe tener asignado el rol destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos administración de la organización y roles de administración de destinatarios.
    
    O bien
    
- Debe ser administrador global de la organización de Office 365.
    
> [!TIP]
> Considere la posibilidad de crear un nuevo grupo de roles en Exchange online que esté destinado específicamente a importar archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles Mailbox Import Export y mail Recipients al nuevo grupo de roles y, a continuación, agregue members. 
  
 **¿Dónde está disponible el envío de unidades?**
  
El envío de unidades está disponible actualmente en Estados Unidos, Canadá, Brasil, Reino Unido, Europa, India, Asia oriental, sudeste asiático, Japón, República de Corea y Australia. El envío de la unidad estará disponible en más de una vez en cuanto a las regiones.
  
 **¿Qué contratos de licencia comercial admiten el envío de unidades?**
  
El envío de unidades para importar archivos PST a Office 365 está disponible a través de un contrato Enterprise de Microsoft (EA). El envío de unidades no está disponible a través de un contrato de productos y servicios de Microsoft (MPSA).
  
 **¿Cuál es el precio de usar el envío de unidades para importar archivos PST a Office 365?**
  
El costo de usar el envío de unidades para importar archivos PST a Office 365 buzones es de $2 USD por GB de datos. Por ejemplo, si envía una unidad de disco duro que contiene 1.000 GB (1 TB) de archivos PST, el costo es de $2.000 USD. Puede trabajar con un partner para pagar la cuota de importación. Para obtener información sobre cómo buscar un partner, consulte [buscar a Office 365 partner o](https://go.microsoft.com/fwlink/p/?LinkId=785197)revendedor.
  
 **¿Qué tipo de discos duros son compatibles con el envío de unidades?**
  
Con el servicio de importación de Office 365 solo se admiten unidades de estado sólido de 2,5 pulgadas (SSDs) o unidades de disco duro de 2,5 o 3,5 pulgadas SATA II/III. Puede usar unidades de disco duro de hasta 10 TB. Para los trabajos de importación, solo se procesará el primer volumen de datos de la unidad de disco duro. El volumen de datos debe estar formateado con NTFS. Al copiar datos en una unidad de disco duro, puede adjuntarlos directamente con un conector de SSD de 2,5 pulgadas o SATA II/III de 2,5 o 3,5 pulgadas, o puede adjuntarlo externamente con un adaptador USB de una unidad de disco de 2,5 pulgadas o un adaptador USB de 2,5 o 3,5 de pulgada SATA II/III.
  
> [!IMPORTANT]
> Las unidades de disco duro externas que vienen con un adaptador USB integrado no son compatibles con el servicio de importación de Office 365. Además, no se puede usar el disco en la grafía de una unidad de disco duro externa. No envíe discos duros externos. 
  
 **¿Cuántas unidades de disco duro puedo enviar para un solo trabajo de importación?**
  
Puede enviar un máximo de 10 unidades de disco duro para un solo trabajo de importación.
  
 **Después de enviar la unidad de disco duro, ¿cuánto tiempo tarda en llegar al centro de datos de Microsoft?**
  
Esto depende de algunas cosas, como su proximidad al centro de datos de Microsoft y el tipo de opción de envío que usó para enviar la unidad de disco duro (por ejemplo, entrega al día siguiente, entrega en dos días o entrega de la base de datos). Con la mayoría de los destinatarios, puede usar el número de seguimiento para realizar un seguimiento del estado de su entrega.
  
 **Una vez que el disco duro llega al centro de datos de Microsoft, ¿cuánto tiempo se tarda en cargar los archivos PST a Azure?**
  
Una vez que se recibe el disco duro en el centro de datos de Microsoft, se tardará entre 7 y 10 días laborables para cargar los archivos PST en el área de almacenamiento de Microsoft Azure de su organización. Los archivos PST se cargarán en un contenedor de blobs de Azure denominado **ingestiondata**. 
  
 **¿Cuánto tiempo se tarda en importar un archivo PST en un buzón?**
  
Una vez que se cargan los archivos PST en el área de almacenamiento de Azure, Office 365 analiza los datos de los archivos PST (de forma segura y segura) para identificar la antigüedad de los elementos y los diferentes tipos de mensajes incluidos en los archivos PST. Cuando se complete este análisis, tendrá la opción de importar todos los datos de los archivos PST o establecer filtros a ese control de los datos que se van a importar. Después de iniciar el trabajo de importación, se importa un archivo PST a un buzón de correo de Office 365 a una velocidad de al menos 24 GB al día. Si esta tasa no satisface sus necesidades, puede considerar otros métodos para importar datos de correo electrónico a Office 365. Para obtener más información, vea [formas de migrar varias cuentas de correo electrónico a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Si se importan diferentes archivos PST a distintos buzones de destino, el proceso de importación se produce en paralelo; es decir, cada pareja de PST/buzón se importa de forma simultánea. Del mismo modo, si se importan varios archivos PST al mismo buzón, se importarán de forma simultánea.
  
 **Después de que Microsoft cargue los archivos PST en Azure, ¿cuánto tiempo se conservan en Azure antes de que se eliminen?**
  
Todos los archivos PST de la ubicación de almacenamiento de Azure de su organización (en el contenedor de blobs denominado **ingestiondata** ), se eliminarán 30 días después de que se haya creado el trabajo &amp; de importación más reciente en la página **importar** del centro de seguridad y cumplimiento. 
  
Esto también significa que después de eliminar los archivos PST del área de almacenamiento de Azure, ya no se muestran en la lista de archivos para un trabajo de importación completado en &amp; el centro de seguridad y cumplimiento. Aunque un trabajo de importación puede seguir en la lista de la página **importar** en &amp; el centro de seguridad y cumplimiento, es posible que la lista de archivos PST esté vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **¿Qué versión del formato de archivo PST se admite para importar a Office 365?**
  
Hay dos versiones del formato de archivo PST: ANSI y Unicode. Se recomienda importar archivos que usen el formato de archivo PST Unicode. Sin embargo, los archivos que usan el formato de archivo PST ANSI, como los idiomas que usan un juego de caracteres de doble byte (DBCS), también se pueden importar a Office 365. Para obtener más información acerca de la importación de archivos PST ANSI, consulte el paso 3 de [usar el envío de unidades para importar archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Además, los archivos PST de Outlook 2007 y versiones posteriores pueden importarse a Office 365.
  
 **¿Hay un límite de tamaño de mensaje al importar archivos PST?**
  
Afirma. Si un archivo PST contiene un elemento de buzón de más de 150 MB, el elemento se omitirá durante el proceso de importación.
  
 **¿Se conservan las propiedades de los mensajes, como Cuándo se envió o recibió el mensaje, la lista de destinatarios y otras propiedades, que se conservan cuando se importan los archivos PST a un buzón de Office 365?**
  
Afirma. Los metadatos del mensaje original no se modifican durante el proceso de importación
  
 **¿Hay un límite para el número de niveles de una jerarquía de carpetas para un archivo PST que deseo importar a un buzón?**
  
Afirma. No puede importar un archivo PST con 300 o más niveles de carpetas anidadas.
  
 **¿Puedo usar el envío de unidades para importar archivos PST a un buzón inactivo en Office 365?**
  
Sí, esta capacidad ya está disponible.
  
 **¿Puedo usar el envío de unidades para importar archivos PST a un buzón de archivo en línea en una implementación híbrida de Exchange?**
  
Sí, esta capacidad ya está disponible.
  
 **¿Puedo usar el envío de unidades para importar archivos PST a carpetas públicas en Exchange Online?**
  
No, no puede importar archivos PST a carpetas públicas.
  
 **¿Puede Microsoft borrar el disco duro antes de que lo envíe de nuevo?**
  
No, Microsoft no puede eliminar los discos duros antes de enviarlos a los clientes. Las unidades de disco duro se devuelven en el mismo estado en el que se encontraban cuando Microsoft las recibió.
  
 **¿Puede Microsoft purgar la unidad de disco duro en lugar de enviarla de nuevo a mí?**
  
No, Microsoft no puede destruir el disco duro. Las unidades de disco duro se devuelven en el mismo estado en el que se encontraban cuando Microsoft las recibió.
  
 **¿Qué servicios de Courier son compatibles con el envío de devolución?**
  
Si es un cliente de Estados Unidos o Europa, Microsoft usa FedEx para devolver la unidad de disco duro. Para todas las demás regiones, Microsoft usa DHL.
  
 **¿Cuáles son los gastos de envío de devolución?**
  
Los gastos de envío deVueltos varían en función de la proximidad al centro de datos de Microsoft al que se envió el disco duro. Microsoft cobrará su cuenta de FedEx o DHL para devolver el disco duro. El costo del envío de la devolución es su responsabilidad.
  
 **¿Puedo usar un servicio de envío de correo personalizado, como el envío personalizado de FedEx, para enviar mi unidad de disco duro a Microsoft?**
  
Sí.
  
 **Si tengo que enviar mi unidad de disco duro a otro país, ¿tengo que hacer algo?**
  
La unidad de disco duro que envía a Microsoft puede tener que cruzar fronteras internacionales. Si este es el caso, es responsable de garantizar que el disco duro y los datos que contiene se importan o exportan de acuerdo con la legislación aplicable. Antes de enviar un disco duro, consulte a sus asesores para comprobar que la unidad y los datos pueden enviarse legalmente al centro de datos de Microsoft especificado. Esto le ayudará a asegurarse de que llega a Microsoft de manera oportuna.
