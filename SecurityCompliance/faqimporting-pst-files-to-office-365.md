---
title: Preguntas más frecuentes sobre la importación de archivos PST a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: 'Preguntas más frecuentes para los administradores sobre el uso del servicio de importación de Office 365 para importar los archivos PST de organizaiton a los buzones de Office 365. '
ms.openlocfilehash: 69767353a574336351b01fdc42a9c6117c5c31ed
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999593"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>Preguntas más frecuentes sobre la importación de archivos PST a Office 365

**Este artículo está destinado a los administradores. ¿Desea importar los archivos PST a su propio buzón? Consulte [importar el correo electrónico, los contactos y el calendario desde un archivo. pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
Estas son algunas de las preguntas más frecuentes sobre el uso del servicio de importación de Office 365 para importar archivos PST en masa a los buzones de Office 365. Para obtener más información acerca de cómo importar archivos PST, vea [información general sobre la importación de archivos PST a Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).
  
## <a name="using-network-upload-to-import-pst-files"></a>Uso de la carga de red para importar archivos PST

Para obtener instrucciones paso a paso, consulte [usar la carga de red para importar archivos PST a Office 365](use-network-upload-to-import-pst-files.md).
  
 **¿Qué permisos se necesitan para crear trabajos de importación en el servicio de importación de Office 365?**
  
Debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online para importar archivos PST a los buzones de correo de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. Para obtener más información, vea las secciones "agregar un rol a un grupo de roles" o "crear un grupo de roles" en [Manage role Groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Además, para crear trabajos de importación en el centro de seguridad & cumplimiento, debe cumplirse una de las siguientes condiciones:
  
- Debe tener asignado el rol destinatarios de correo en Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    O bien
    
- Debe ser administrador global de la organización de Office 365.
    
> [!TIP]
> Considere la posibilidad de crear un nuevo grupo de roles en Exchange online que esté destinado específicamente a importar archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles Mailbox Import Export y mail Recipients al nuevo grupo de roles y, a continuación, agregue members. 
  
 **¿Dónde está disponible la carga en la red?**
  
La carga de red está disponible actualmente en Estados Unidos, Canadá, Brasil, Reino Unido, Francia, Europa, India, este asiático, sudeste asiático, Japón, República de Corea y Australia. Network upload will be available in more regions soon.
  
 **What is the pricing for importing PST files by using network upload?**
  
Using network upload to import PST files is free.
  
Esto también significa que después de eliminar los archivos PST del área de almacenamiento de Azure, ya no se muestran en la lista de archivos para un trabajo de importación completado en el centro de administración de Microsoft 365. Aunque un trabajo de importación todavía puede aparecer en la página **importar datos a Office 365** , es posible que la lista de archivos PST esté vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. Sin embargo, los archivos que usan el formato de archivo PST ANSI, como los idiomas que usan un juego de caracteres de doble byte (DBCS), también se pueden importar a Office 365. Para obtener más información acerca de la importación de archivos PST ANSI, consulte el paso 4 en [usar la carga en la red para importar los archivos PST de su organización a Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Después de cargar los archivos PST en el área de almacenamiento de Azure, ¿cuánto tiempo se conservan en Azure antes de que se eliminen?**
  
Cuando use el método de carga de red para importar archivos PST, puede cargarlos en un contenedor de blobs de Azure denominado **ingestiondata**. Si no hay ningún trabajo de importación en curso en la página **importar** del centro de seguridad & cumplimiento), se eliminarán todos los archivos PST en el contenedor de **ingestiondata** de Azure después de que se haya creado el trabajo de importación más reciente en el & de seguridad. Centro de cumplimiento. Eso también significa que tiene que crear un nuevo trabajo de importación en el centro de seguridad & cumplimiento (que se describe en el paso 5 de las instrucciones de carga de red) en un plazo de 30 días después de cargar los archivos PST a Azure. 
  
Esto también significa que después de eliminar los archivos PST del área de almacenamiento de Azure, ya no se muestran en la lista de archivos para un trabajo de importación completado en el centro de seguridad & cumplimiento. Aunque un trabajo de importación puede seguir en la lista de la página **importar** en el centro de seguridad & cumplimiento, la lista de archivos PST podría estar vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **¿Cuánto tiempo se tarda en importar un archivo PST en un buzón?**
  
It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. Una vez que se han copiado los archivos PST en el área de almacenamiento de Azure, se importa un archivo PST a un buzón de correo de Office 365 a una velocidad de al menos 24 GB al día. Si esta tasa no satisface sus necesidades, puede considerar otros métodos para migrar datos de correo electrónico a Office 365. Para obtener más información, vea [Formas de migrar el correo electrónico de varias cuentas a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Del mismo modo, si se importan varios archivos PST al mismo buzón, se importarán de forma simultánea.
  
 **Is there a message size limit when importing PST files?**
  
Sí. Si un archivo PST contiene un elemento de buzón de más de 150 MB, el elemento se omitirá durante el proceso de importación.
  
 **¿Se conservan las propiedades de los mensajes, como Cuándo se envió o recibió el mensaje, la lista de destinatarios y otras propiedades, que se conservan cuando se importan los archivos PST a un buzón de Office 365?**
  
Sí. Los metadatos del mensaje original no se modifican durante el proceso de importación.
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use network upload to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available. 
  
 **Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **¿Puedo usar la carga en la red para importar archivos PST a carpetas públicas en Exchange Online?**
  
No, no puede importar archivos PST a carpetas públicas.
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Uso del envío de unidades para importar archivos PST

Para obtener instrucciones paso a paso, consulte [usar el envío de unidades para importar archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
 **¿Qué permisos se necesitan para crear trabajos de importación en el servicio de importación de Office 365?**
  
Debe tener asignado el rol importación y exportación de buzones para importar los archivos PST a los buzones de correo de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. Para obtener más información, vea las secciones "agregar un rol a un grupo de roles" o "crear un grupo de roles" en [Manage role Groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Además, para crear trabajos de importación en el centro de seguridad & cumplimiento, debe cumplirse una de las siguientes condiciones:
  
- Debe tener asignado el rol destinatarios de correo en Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    O bien
    
- Debe ser administrador global de la organización de Office 365.
    
> [!TIP]
> Considere la posibilidad de crear un nuevo grupo de roles en Exchange online que esté destinado específicamente a importar archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles Mailbox Import Export y mail Recipients al nuevo grupo de roles y, a continuación, agregue members. 
  
 **¿Dónde está disponible el envío de unidades?**
  
El envío de unidades está disponible actualmente en Estados Unidos, Canadá, Brasil, Reino Unido, Europa, India, Asia oriental, sudeste asiático, Japón, República de Corea y Australia. Drive shipping will be available in more regions soon.
  
 **What commercial licensing agreements support drive shipping?**
  
El envío de unidades para importar archivos PST a Office 365 está disponible a través de un contrato Enterprise de Microsoft (EA). El envío de unidades no está disponible a través de un contrato de productos y servicios de Microsoft (MPSA).
  
 **¿Cuál es el precio de usar el envío de unidades para importar archivos PST a Office 365?**
  
The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. Para obtener información sobre cómo buscar un partner, consulte [buscar a Office 365 partner o](https://go.microsoft.com/fwlink/p/?LinkId=785197)revendedor.
  
 **What kind of hard drives are supported for drive shipping?**
  
Con el servicio de importación de Office 365 solo se admiten unidades de estado sólido de 2,5 pulgadas (SSDs) o unidades de disco duro de 2,5 o 3,5 pulgadas SATA II/III. You can use hard drives up to 10 TB. Para los trabajos de importación, solo se procesará el primer volumen de datos de la unidad de disco duro. The data volume must be formatted with NTFS. Al copiar datos en una unidad de disco duro, puede adjuntarlos directamente con un conector de SSD de 2,5 pulgadas o SATA II/III de 2,5 o 3,5 pulgadas, o puede adjuntarlo externamente con un adaptador USB de una unidad de disco de 2,5 pulgadas o un adaptador USB de 2,5 o 3,5 de pulgada SATA II/III.
  
> [!IMPORTANT]
> Las unidades de disco duro externas que vienen con un adaptador USB integrado no son compatibles con el servicio de importación de Office 365. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives. 
  
 **How many hard drives can I ship for a single import job?**
  
You can ship a maximum of 10 hard drives for a single import job.
  
 **After I ship my hard drive, how long does it take to get to the Microsoft data center?**
  
That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.
  
 **Una vez que el disco duro llega al centro de datos de Microsoft, ¿cuánto tiempo se tarda en cargar los archivos PST a Azure?**
  
Una vez que se recibe el disco duro en el centro de datos de Microsoft, se tardará entre 7 y 10 días laborables para cargar los archivos PST en el área de almacenamiento de Microsoft Azure de su organización. Los archivos PST se cargarán en un contenedor de blobs de Azure denominado **ingestiondata**. 
  
 **¿Cuánto tiempo se tarda en importar un archivo PST en un buzón?**
  
Una vez que se cargan los archivos PST en el área de almacenamiento de Azure, Office 365 analiza los datos de los archivos PST (de forma segura y segura) para identificar la antigüedad de los elementos y los diferentes tipos de mensajes incluidos en los archivos PST. Cuando se complete este análisis, tendrá la opción de importar todos los datos de los archivos PST o establecer filtros a ese control de los datos que se van a importar. Después de iniciar el trabajo de importación, se importa un archivo PST a un buzón de correo de Office 365 a una velocidad de al menos 24 GB al día. Si esta tasa no satisface sus necesidades, puede considerar otros métodos para importar datos de correo electrónico a Office 365. Para obtener más información, vea [Formas de migrar el correo electrónico de varias cuentas a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Del mismo modo, si se importan varios archivos PST al mismo buzón, se importarán de forma simultánea.
  
 **Después de que Microsoft cargue los archivos PST en Azure, ¿cuánto tiempo se conservan en Azure antes de que se eliminen?**
  
Todos los archivos PST de la ubicación de almacenamiento de Azure de su organización (en el contenedor de blobs denominado **ingestiondata** ), se eliminarán 30 días después de que se haya creado el trabajo de importación más reciente en la página de **importación** en el centro de seguridad & cumplimiento. 
  
Esto también significa que después de eliminar los archivos PST del área de almacenamiento de Azure, ya no se muestran en la lista de archivos para un trabajo de importación completado en el centro de seguridad & cumplimiento. Aunque un trabajo de importación puede seguir en la lista de la página **importar** en el centro de seguridad & cumplimiento, la lista de archivos PST podría estar vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. Sin embargo, los archivos que usan el formato de archivo PST ANSI, como los idiomas que usan un juego de caracteres de doble byte (DBCS), también se pueden importar a Office 365. Para obtener más información acerca de la importación de archivos PST ANSI, consulte el paso 3 de [usar el envío de unidades para importar archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Is there a message size limit when importing PST files?**
  
Sí. Si un archivo PST contiene un elemento de buzón de más de 150 MB, el elemento se omitirá durante el proceso de importación.
  
 **¿Se conservan las propiedades de los mensajes, como Cuándo se envió o recibió el mensaje, la lista de destinatarios y otras propiedades, que se conservan cuando se importan los archivos PST a un buzón de Office 365?**
  
Sí. Los metadatos del mensaje original no se modifican durante el proceso de importación
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available.
  
 **Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **¿Puedo usar el envío de unidades para importar archivos PST a carpetas públicas en Exchange Online?**
  
No, no puede importar archivos PST a carpetas públicas.
  
 **Can Microsoft wipe my hard drive before they ship it back to me?**
  
No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **¿Puede Microsoft purgar la unidad de disco duro en lugar de enviarla de nuevo a mí?**
  
No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **¿Qué servicios de Courier son compatibles con el envío de devolución?**
  
If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.
  
 **¿Cuáles son los gastos de envío de devolución?**
  
Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.
  
 **¿Puedo usar un servicio de envío de correo personalizado, como el envío personalizado de FedEx, para enviar mi unidad de disco duro a Microsoft?**
  
Sí.
  
 **If I have to ship my hard drive to another country, is there anything I need to do?**
  
The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.
