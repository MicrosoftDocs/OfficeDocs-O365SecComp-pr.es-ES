---
title: Overview of importing your organization PST files to Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: 'Para administradores: Obtenga información sobre cómo usar el servicio de importación en el centro &amp; de seguridad y cumplimiento de Office 365 para importar de forma masiva datos de correo electrónico (archivos PST) a los buzones de usuario en Exchange Online. En este tema se proporcionan preguntas más frecuentes y se explica cómo funciona el proceso de importación de PST.'
ms.openlocfilehash: b6f32a6b5552773c197003ddac41c138539bb6ef
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218050"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a>Overview of importing your organization PST files to Office 365

> [!NOTE]
> Este artículo está destinado a los administradores. ¿Está intentando importar archivos PST a su propio buzón? Consulte [importar el correo electrónico, los contactos y el calendario desde un archivo. pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)

Puede usar el servicio de importación en el centro de seguridad &amp; y cumplimiento de Office 365 para importar rápidamente archivos PST en masa a buzones de Exchange online en su organización de Office 365. Hay dos formas en las que puede importar archivos PST a Office 365:
   
- **Carga de red** ![Carga](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) en la nube: Cargue los archivos PST a través de la red en una ubicación de almacenamiento temporal de Azure en la nube de Microsoft. A continuación, se usa el servicio de importación de Office 365 para importar los datos PST a los buzones de la organización de Office 365. 

- **Envío de unidades** ![Disco](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) duro: Copie los archivos PST en una unidad de disco duro cifrada con BitLocker y envíe físicamente la unidad a Microsoft. Cuando Microsoft recibe la unidad de disco duro, el personal del centro de datos carga los datos en una ubicación temporal de almacenamiento de Azure en la nube de Microsoft. A continuación, se usa el servicio de importación de Office 365 para importar los datos a los buzones de la organización de Office 365.

## <a name="step-by-step-instructions"></a>Instrucciones paso a paso
  
Consulte uno de los siguientes temas para obtener instrucciones detalladas paso a paso para importar de forma masiva los archivos PST de su organización a Office 365. 
   
- [Usar la carga en la red para importar archivos PST en Office 365](use-network-upload-to-import-pst-files.md)
- [Usar el envío de unidades para importar los archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>Cómo funciona la importación de archivos PST

A continuación, se muestra una ilustración y una descripción del proceso de importación de PST completo. La ilustración muestra el flujo de trabajo principal y resalta las diferencias entre la carga de red y los métodos de envío de unidad.
  
![Flujo de trabajo del proceso de importación de PST](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **Descargue las herramientas de importación de PST y la clave en una ubicación de almacenamiento de Azure privada** : el primer paso consiste en descargar la herramienta y la clave de acceso usadas para cargar los archivos PST o copiarlos en una unidad de disco duro. Puede obtenerlos en la página **importar** del centro de seguridad &amp; y cumplimiento de Office 365. La clave le proporciona (o personal del centro de datos de Microsoft en el caso de la unidad de envío) con los permisos necesarios para cargar archivos PST en una ubicación de almacenamiento segura y privada de Azure. Esta clave de acceso es única para su organización y ayuda a impedir el acceso no autorizado a los archivos PST una vez que se cargan en la nube de Microsoft. Tenga en cuenta que la importación de archivos PST a Office 365 no requiere que la organización tenga una suscripción a Azure independiente. 
    
2. **Cargue o copie los archivos PST** : el siguiente paso depende de si usa la carga en la red o el envío de unidades para importar archivos PST. En ambos casos, usará la herramienta y la clave de almacenamiento seguro que obtuvo en el paso anterior.
    
    - **Carga de red** La herramienta AzCopy. exe (descargada en el paso 1) se usa para cargar y almacenar los archivos PST en una ubicación de almacenamiento de Azure en la nube de Microsoft. Tenga en cuenta que la ubicación de almacenamiento de Azure que carga los archivos PST reside en el mismo centro de información regional de Microsoft en el que se encuentra la organización 365 de Office. 
    
      Para cargarlos, los archivos PST que desea importar a Office 365 deben encontrarse en un recurso compartido de archivos o en un servidor de archivos de la organización.
    
    - **Envío de unidades** La herramienta herramienta waimportexport. exe (descargada en el paso 1) se usa para copiar los archivos PST en la unidad de disco duro. Esta herramienta cifra la unidad de disco duro con BitLocker y, a continuación, copia los archivos PST en la unidad de disco duro. Como la carga en la red, los archivos PST que desea copiar en la unidad de disco duro deben encontrarse en un recurso compartido de archivos o en un servidor de archivos de la organización.
    
3. **Crear un archivo de asignación** de importaciones de PST: una vez que los archivos PST se cargan en la ubicación de almacenamiento de Azure o se copian en una unidad de disco duro, el siguiente paso es crear un archivo de valores separados por comas (CSV) que especifica a qué buzones de usuario se importarán los archivos PST (un ND un archivo PST se puede importar en el buzón de correo principal de un usuario o en su buzón de archivo. El servicio de importación de Office 365 usará la información para importar los archivos PST. 
    
4. **Crear un trabajo de importación de PST** : el siguiente paso consiste en crear un trabajo de importación de PST en la página &amp; **importar** del centro de seguridad y cumplimiento y enviar el archivo de asignación de importaciones de PST creado en el paso anterior. Para la carga en la red (debido a que los archivos PST se cargaron en Azure), Office 365 analiza los datos de los archivos PST y, a continuación, le ofrece la oportunidad de establecer filtros que controlan qué datos se importan realmente a los buzones especificados en el archivo de asignación de importaciones de PST. 
    
    Para el envío de unidades, algunas cosas adicionales se producen en este punto del proceso.
    
    - La unidad de disco duro se envía físicamente a un centro de datos de Microsoft (la dirección de envío del centro de datos de Microsoft se muestra cuando se crea el trabajo de importación)
    
    - Cuando Microsoft reciba el disco duro, el personal del centro de datos cargará los archivos PST en la unidad de disco duro en la ubicación de almacenamiento de Azure de su organización. Como se ha explicado anteriormente, los archivos PST se cargan en una ubicación de almacenamiento de Azure que reside en el mismo centro de información regional de Microsoft en el que se encuentra la organización de Office 365.
    
      > [!NOTE]
      > Los archivos PST de la unidad de disco duro se cargan en Azure en un plazo de 7 a 10 días laborables después de que Microsoft reciba el disco duro. 
  
      Al igual que el proceso de carga de red, Office 365 analiza entonces los datos de los archivos PST y le ofrece la oportunidad de establecer filtros que controlan qué datos se importan realmente a los buzones especificados en el archivo de asignación de importaciones de PST.
    
    - Microsoft envía la unidad de disco duro de vuelta. 
    
5. **Filtrar los datos PST que se importarán a** los buzones: una vez que se crea el trabajo de importación (y después de que se carguen los archivos PST de un trabajo de envío de unidades en la ubicación de almacenamiento de Azure), Office 365 analiza los datos de los archivos PST (de forma segura) identificación de la antigüedad de los elementos y los distintos tipos de mensajes incluidos en los archivos PST. Cuando se completa el análisis y los datos están listos para importar, tiene la opción de importar todos los datos contenidos en los archivos PST o puede recortar los datos que se importan al establecer filtros que controlan qué datos se importan. 
    
6. **Inicie el trabajo de importación de PST** : una vez iniciado el trabajo de importación, Office 365 usa la información del archivo de asignación de importaCIONES de PST para importar los archivos PST de la ubicación de Azure Storage a los buzones de usuario. La información de estado sobre el trabajo de importación (incluida la información sobre cada uno de los archivos PST **** que se importa) se &amp; muestra en la página importar del centro de seguridad y cumplimiento. Una vez finalizado el trabajo de importación, el estado del trabajo se establece en **completado**.
  
## <a name="why-import-email-data-to-office-365"></a>¿Por qué importar datos de correo electrónico a Office 365?

- La importación de archivos PST a los buzones de usuario es una forma de migrar el correo electrónico de su organización a Office 365.
    
- Puede usar la característica de [importación inteligente](filter-data-when-importing-pst-files.md) para filtrar los elementos de los archivos PST que realmente se importan a los buzones de correo de destino. Esto le permite recortar los datos que se importan mediante la configuración de filtros que controlan los datos que se importan. 
    
- La importación de datos de correo electrónico a Office 365 ayuda a satisfacer las necesidades de cumplimiento de la organización, ya que permite:
    
  - Habilite los buzones de [archivo](enable-archive-mailboxes.md) y el [archivado ilimitado](unlimited-archiving.md) para dar a los usuarios espacio de almacenamiento adicional en el buzón. 
    
  - Coloque los buzones en [retención por juicio](https://go.microsoft.com/fwlink/?linkid=841243) para conservar el contenido. 
    
  - Use la [herramienta de búsqueda de contenido](content-search.md) para buscar el contenido del buzón. 
    
  - Usar [casos de eDiscovery](ediscovery-cases.md) para administrar las investigaciones legales de la organización 
    
  - Use [directivas de retención](retention-policies.md) en el &amp; centro de seguridad y cumplimiento para controlar el tiempo que se conserva el contenido del buzón y, a continuación, elimine el contenido una vez que expire el período de retención. 
    
- Importar datos a Office 365 ayuda a proteger contra la pérdida de datos. Los datos de correo electrónico que se importan a Office 365 heredan las características de alta disponibilidad de Exchange Online.
    
- Los datos de correo electrónico de Office 365 están disponibles para los usuarios en todos los dispositivos porque se almacenan en la nube.
    
## <a name="importing-sharepoint-data-to-office-365"></a>Importación de datos de SharePoint a Office 365

También puede importar archivos y documentos a los sitios de SharePoint y las cuentas de OneDrive en su organización de Office 365. Para obtener más información, vea los siguientes artículos:

- [Migrar a SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [Presentación de la herramienta de migración de SharePoint](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [Migrar a SharePoint Online con PowerShell](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [Migrar el contenido del recurso compartido de archivos a SharePoint Online con el cuadro de datos de Azure](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a>Preguntas más frecuentes acerca de la importación de archivos PST a Office 365
  
Estas son algunas de las preguntas más frecuentes sobre el uso del servicio de importación de Office 365 para importar archivos PST en masa a los buzones de Office 365. 
  
- [Uso de la carga de red para importar archivos PST](#using-network-upload-to-import-pst-files)
  
- [Uso del envío de unidades para importar archivos PST](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>Uso de la carga de red para importar archivos PST

 **¿Qué permisos se necesitan para crear trabajos de importación en el servicio de importación de Office 365?**
  
Debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online para importar archivos PST a los buzones de correo de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización. O bien, puede crear un nuevo grupo de roles, asignar el rol exportar importación y, a continuación, agregarse a usted mismo o a otros usuarios como miembro. Para obtener más información, vea las secciones "agregar un rol a un grupo de roles" o "crear un grupo de roles" en [Manage role Groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Además, para crear trabajos de importación en el centro de &amp; seguridad y cumplimiento de Office 365, debe cumplirse una de las siguientes condiciones:
  
- Debe tener asignado el rol destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos administración de la organización y roles de administración de destinatarios.
    
    O bien
    
- Debe ser administrador global de la organización de Office 365.
    
> [!TIP]
> Considere la posibilidad de crear un nuevo grupo de roles en Exchange online que esté destinado específicamente a importar archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles Mailbox Import Export y mail Recipients al nuevo grupo de roles y, a continuación, agregue members. 
  
 **¿Dónde está disponible la carga en la red?**
  
La carga de red está disponible actualmente en Estados Unidos, Canadá, Brasil, Reino Unido, Europa, India, Asia oriental, sudeste asiático, Japón, República de Corea y Australia. La carga de red estará disponible próximamente en más regiones.
  
 **¿Cuál es el precio de la importación de archivos PST mediante la carga de red?**
  
El uso de la carga de red para importar archivos PST es gratuito.
  
Esto también significa que después de eliminar los archivos PST del área de almacenamiento de Azure, ya no se muestran en la lista de archivos para un trabajo de importación completado en el centro de administración de Office 365. Aunque un trabajo de importación todavía puede aparecer en la página **importar datos a Office 365** , es posible que la lista de archivos PST esté vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **¿Qué versión del formato de archivo PST se admite para importar a Office 365?**
  
Hay dos versiones del formato de archivo PST: ANSI y Unicode. Se recomienda importar archivos que usen el formato de archivo PST Unicode. Sin embargo, los archivos que usan el formato de archivo PST ANSI, como los idiomas que usan un juego de caracteres de doble byte (DBCS), también se pueden importar a Office 365. Para obtener más información acerca de la importación de archivos PST ANSI, consulte el paso 4 en usar la carga en la [red para importar archivos PST a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).
  
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
  
### <a name="using-drive-shipping-to-import-pst-files"></a>Uso del envío de unidades para importar archivos PST

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
  
Una vez que se recibe el disco duro en el centro de datos de Microsoft, se tardará entre 7 y 10 días laborables para cargar los archivos PST en el área de almacenamiento de Microsoft Azure de su organización. Los archivos PST se cargarán en un contenedor de blobs de Azure `ingestiondata`denominado. 
  
 **¿Cuánto tiempo se tarda en importar un archivo PST en un buzón?**
  
Una vez que se cargan los archivos PST en el área de almacenamiento de Azure, Office 365 analiza los datos de los archivos PST (de forma segura y segura) para identificar la antigüedad de los elementos y los diferentes tipos de mensajes incluidos en los archivos PST. Cuando se complete este análisis, tendrá la opción de importar todos los datos de los archivos PST o establecer filtros a ese control de los datos que se van a importar. Después de iniciar el trabajo de importación, se importa un archivo PST a un buzón de correo de Office 365 a una velocidad de al menos 24 GB al día. Si esta tasa no satisface sus necesidades, puede considerar otros métodos para importar datos de correo electrónico a Office 365. Para obtener más información, vea [formas de migrar varias cuentas de correo electrónico a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Si se importan diferentes archivos PST a distintos buzones de destino, el proceso de importación se produce en paralelo; es decir, cada pareja de PST/buzón se importa de forma simultánea. Del mismo modo, si se importan varios archivos PST al mismo buzón, se importarán de forma simultánea.
  
 **Después de que Microsoft cargue los archivos PST en Azure, ¿cuánto tiempo se conservan en Azure antes de que se eliminen?**
  
Todos los archivos PST de la ubicación de almacenamiento de Azure de su organización (en `ingestiondata`el contenedor de blobs denominado) se eliminarán 30 días después de que se haya creado el trabajo de &amp; importación más reciente en la página **importar** del centro de seguridad y cumplimiento. 
  
Esto también significa que después de eliminar los archivos PST del área de almacenamiento de Azure, ya no se muestran en la lista de archivos para un trabajo de importación completado en &amp; el centro de seguridad y cumplimiento. Aunque un trabajo de importación puede seguir en la lista de la página **importar** en &amp; el centro de seguridad y cumplimiento, es posible que la lista de archivos PST esté vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **¿Qué versión del formato de archivo PST se admite para importar a Office 365?**
  
Hay dos versiones del formato de archivo PST: ANSI y Unicode. Se recomienda importar archivos que usen el formato de archivo PST Unicode. Sin embargo, los archivos que usan el formato de archivo PST ANSI, como los idiomas que usan un juego de caracteres de doble byte (DBCS), también se pueden importar a Office 365. Para obtener más información acerca de la importación de archivos PST ANSI, consulte el paso 3 de [usar el envío de unidades para importar los archivos PST de la organización a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
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
