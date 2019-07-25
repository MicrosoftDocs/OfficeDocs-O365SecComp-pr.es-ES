---
title: Información general sobre la importación de archivos PST de su organización a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: 'Para administradores: infórmese sobre cómo usar el servicio de importación del Centro de seguridad y cumplimiento para importar grandes masas de datos de correo electrónico (archivos PST) a buzones de usuario de Exchange Online. Este tema contiene una sección de Preguntas frecuentes y explica cómo funciona el proceso de importación de PST.'
ms.openlocfilehash: 4682114ad150f818dfe39fe662bc3440d655e4ea
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854674"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a>Información general sobre la importación de archivos PST de su organización a Office 365

> [!NOTE]
> Este artículo está dirigido a administradores. ¿Está intentando importar archivos PST a su propio buzón? Consulte [Importar el correo electrónico, los contactos y el calendario desde un archivo .pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)

Puede usar el servicio de importación del Centro de seguridad y cumplimiento para importar grandes cantidades de archivos PST rápidamente a buzones de Exchange online a su organización de Office 365. Hay dos formas de importar archivos PST a Office 365:
   
- Carga en la red** ![Carga en la nube](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png): Cargue los archivos PST a través de la red en una ubicación temporal de almacenamiento de Azure en la nube de Microsoft. Después, use el servicio de importación de Office 365 para importar los datos PST a los buzones de su organización de Office 365. 

- **Envío de unidad** ![Disco duro](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png): Copie los archivos PST a un disco duro cifrado por BitLocker y envíe físicamente la unidad a Microsoft. Cuando Microsoft reciba la unidad de disco duro, el personal del centro de datos cargará los datos a una ubicación de almacenamiento temporal de Azure en la nube de Microsoft. Después, use el servicio de importación de Office 365 para importar los datos a los buzones de su organización de Office 365.

## <a name="step-by-step-instructions"></a>Instrucciones detalladas
  
Consulte uno de los siguientes temas con instrucciones paso a paso para importar grandes cantidades de archivos PST de su organización a Office 365. 
   
- [Usar la carga en la red para importar archivos PST en Office 365](use-network-upload-to-import-pst-files.md)
- [Use el envío de unidades para importar archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>Cómo funciona la importación de archivos PST

A continuación, le presentamos una ilustración y una descripción del proceso completo de importación de PST. La ilustración muestra el flujo de trabajo principal y resalta las diferencias entre la carga por red y los métodos de envío de unidades.
  
![Flujo de trabajo del proceso de importación de PST](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. Descargar las herramientas de importación de PST y la clave de la ubicación de almacenamiento de Azure privada** El primer paso es descargar la herramienta y la clave de acceso para cargar los archivos PST o copiarlos en una unidad de disco duro. Puede obtenerlas en la página **Importar** en el Centro de cumplimiento y seguridad. La clave le ofrece (a usted o al personal del Centro de datos de Microsoft si se decide por el envío de la unidad) los permisos necesarios para cargar los archivos PST a una ubicación de almacenamiento de Azure privada y segura. Esta clave de acceso es exclusiva de su organización y le ayuda a evitar el acceso no autorizado a archivos PST tras su carga en la nube de Microsoft. Tenga en cuenta que para importar archivos PST a Office 365 su organización no necesita una suscripción de Azure separada. 
    
2. Cargar o copiar los archivos PST**: El siguiente paso depende de si decidió importar los archivos PST mediante la carga en la red o el envío de unidades. En ambos casos, usará la herramienta y la clave de almacenamiento segura que obtuvo en el paso anterior.
    
    - Carga en la red** La herramienta AzCopy.exe (descargada en el paso 1) le permite cargar y almacenar los archivos PST en una ubicación de almacenamiento de Azure en la nube de Microsoft. Tenga en cuenta que la ubicación de almacenamiento de Azure que carga los archivos PST está en el mismo centro de datos de Microsoft local que su organización 365 de Office. 
    
      Para poder cargar los archivos PST que desea importar a Office 365, estos deben encontrarse en un recurso compartido de archivos o en un servidor de archivos de su organización.
    
    - **Envío de discos** La herramienta WAImportExport.exe (descargada en el paso 1) le permite copiar los archivos PST en la unidad de disco duro. Esta herramienta cifra la unidad de disco duro con BitLocker y, a continuación, copia los PST a la unidad de disco duro. Como en la carga por red, los archivos PST que desea copiar al disco duro deben encontrarse en un recurso compartido de archivos o en un servidor de archivos de su organización.
    
3. Crear un archivo de asignación para importar PST**: una vez que los archivos PST se han cargado en la ubicación de almacenamiento de Azure o se han copiado en un disco duro, el siguiente paso es crear un archivo de valores separados por comas (CSV) que especifique qué buzones de usuario se usarán para importar los archivos PST (un archivo PST se puede importar al buzón principal de un usuario o al buzón de archivo). El servicio de importación de Office 365 usará la información para importar los archivos PST. 
    
4. Crear un trabajo de importación de PST**: el siguiente paso es crear un trabajo de importación de PST en la página **Importar** del Centro de cumplimiento y seguridad, y enviar el archivo de asignación de importación de PST creado en el paso anterior. Para la carga en la red (debido a que los archivos PST se han cargado en Azure), Office 365 analiza los datos de los archivos PST y, a continuación, le permite establecer filtros para controlar qué datos se importan a los buzones especificados en el archivo de asignación de importación de PST. 
    
    El método de envío de unidades conlleva algunos pasos adicionales en esta parte del proceso.
    
    - Usted envía físicamente la unidad de disco duro a un centro de datos de Microsoft (la dirección de envío del centro de datos de Microsoft se mostrará cuando se cree el trabajo de importación)
    
    - Cuando Microsoft reciba la unidad de disco duro, el personal del centro de datos cargará los archivos PST de la unidad en la ubicación de almacenamiento de Azure de su organización. Como hemos mencionado antes, sus archivos PST se cargan en una ubicación de almacenamiento de Azure que se encuentra en el mismo centro de datos de Microsoft local que su organización 365 de Office.
    
      > [!NOTE]
      > Cargar los archivos PST de la unidad a la ubicación de Azure lleva de unos 7 a 10 días hábiles después de que Microsoft la reciba. 
  
      Como en la carga por red, Office 365 analiza los datos de los archivos PST y, a continuación, le permite establecer filtros para controlar qué datos se importan a los buzones especificados en el archivo de asignación de importación de PST.
    
    - Microsoft le envía de vuelta la unidad de disco duro. 
    
5. **Filtrar los datos PST que se importarán a los buzones**: después de crear el trabajo de importación (y de que los archivos PST se carguen en la ubicación de almacenamiento de Azure tras el envío del disco), Office 365 analiza de forma segura los datos de los archivos PST. Esto conlleva identificar la antigüedad de los elementos y los diferentes tipos de mensajes incluidos en los archivos PST. Una vez se haya completado el análisis y los datos estén listos para la importación, tiene la opción de importar todos los datos incluidos en los archivos PST o de importar solo algunos de ellos, seleccionándolos mediante filtros. 
    
6. Iniciar el trabajo de importación de PST**: una vez iniciado el trabajo de importación, Office 365 usará la información del archivo de asignación para importar los archivos PST desde la ubicación de almacenamiento de Azure a los buzones de usuario. En la página de **Importar** del Centro de cumplimiento y seguridad se mostrará información de estado sobre el trabajo de importación (incluida información individual de cada archivo PST importado). Cuando finalice el trabajo de importación, el estado del trabajo aparecerá como **Completado**.
  
## <a name="why-import-email-data-to-office-365"></a>¿Por qué importar datos de correo electrónico a Office 365?

- Importar archivos PST a los buzones de usuario es una forma de migrar el correo electrónico de su organización a Office365.
    
- Puede usar la [Importación inteligente](filter-data-when-importing-pst-files.md) para filtrar y seleccionar qué elementos de los archivos PST se importan a los buzones de destino. Esto le permite limitar los datos importados a aquellos que usted seleccione. 
    
- Importar datos de correo a Office365 ayuda a satisfacer las necesidades de cumplimiento de la organización, ya que le permite:
    
  - Habilitar [buzones de archivo](enable-archive-mailboxes.md) y [archivo ilimitado](unlimited-archiving.md) proporciona a los usuarios un mayor espacio de almacenamiento en su buzón. 
    
  - Establezca los buzones en [Suspensión por litigio](https://go.microsoft.com/fwlink/?linkid=841243) para conservar el contenido. 
    
  - Use la [Herramienta de búsqueda de contenido](content-search.md) para buscar en el contenido del buzón. 
    
  - Use casos de eDiscovery](ediscovery-cases.md) para administrar las investigaciones legales de su organización. 
    
  - Use las [directivas de conservación](retention-policies.md) del Centro de cumplimiento y seguridad para establecer cuánto tiempo se debe conservar el contenido del buzón y elimine el contenido cuando expire el período de conservación. 

  - Use las directivas de supervisión](supervision-policies.md) para examinar los mensajes, asegurarse de que son compatibles con los estándares de mensaje y agregar un tipo de clasificación.
    
- Importar datos a Office365 le ayuda a protegerse contra pérdidas de datos. Los datos de correo electrónico que se importan a Office 365 heredan las características de alta disponibilidad de Exchange Online.
    
- Los datos de correo en Office365 están disponibles para los usuarios en todos los dispositivos porque se almacenan en la nube.
    
## <a name="importing-sharepoint-data-to-office-365"></a>Importar datos de SharePoint en Office 365

También puede importar archivos y documentos de los sitios de SharePoint y las cuentas de OneDrive en su organización 365 de Office. Para obtener más información, consulte los siguientes artículos:

- [Migrar a SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [Presentación de la herramienta de migración de SharePoint](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [Migrar a SharePoint Online con PowerShell](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [Migrar su contenido de recursos compartidos a SharePoint Online con Azure Data Box](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a>Preguntas frecuentes sobre la importación de archivos PST a Office 365
  
Estas son algunas de las preguntas más frecuentes sobre el uso del servicio de importación de Office 365 para importar archivos PST en masa a los buzones de Office 365. 
  
- [Uso de la carga en la red para importar archivos PST](#using-network-upload-to-import-pst-files)
  
- [Uso del envío de unidades para importar los archivos PST](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>Uso de la carga en la red para importar archivos PST

 **¿Qué permisos son necesarios para crear trabajos de importación en el servicio de importación de Office 365?**
  
Debe tener asignado el rol importación y exportación de buzón de Exchange Online para importar archivos PST a los buzones de Office 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Mailbox Import Export al grupo de roles Administración de la organización. O puede crear un nuevo grupo de rol, asignar el rol de exportación e importación de buzón y, después, agregarse o agregar a otros usuarios como miembro. Para obtener más información, vea las secciones "Agregar un rol a un grupo de roles" o "Crear un grupo de roles" en [Administrar grupos de roles en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Además, para crear trabajos de importación en el Centro de seguridad y cumplimiento, debe cumplirse uno de estos requisitos:
  
- Debe tener asignado el rol de los destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de roles de administración de la organización y administración de destinatarios.
    
    O bien
    
- Debe ser administrador global en su organización de Office 365. 
    
> [!TIP]
> Puede crear un nuevo grupo de roles en Exchange Online que está pensado específicamente para la importación de archivos PST a Office 365. Para obtener el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles de importación y exportación de buzón y de destinatarios de correo al nuevo grupo de roles y, a continuación, agregue a los miembros. 
  
 **¿Dónde está disponible la carga en la red?**
  
La carga en la red está disponible actualmente en Estados Unidos, Canadá, Brasil, Reino Unido, Europa, India, Asia Oriental, Sudeste asiático, Japón, República de Corea y Australia. La carga en la red estará disponible en más regiones próximamente.
  
 **¿Cuál es el precio de importar archivos PST con la carga en la red?**
  
Using network upload to import PST files is free.
  
Asimismo, después de que los archivos PST se eliminen del área de almacenamiento de Azure, ya no se mostrarán en la lista de archivos para un trabajo de importación completado en el Centro de administración de Microsoft 365. Aunque todavía puede aparecer un trabajo de importación en la página **Importar datos a Office 365**, la lista de archivos PST puede estar vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **¿Qué versión del formato de archivo PST se admite para importarse en Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. Recomendamos la importación de archivos que usen el formato Unicode de archivo PST. En cambio, los archivos que usan el formato ANSI de archivo PST, como pueden ser los de los idiomas que usan un conjunto de caracteres de doble byte (DBCS), también pueden importarse a Office 365. Para obtener más información sobre la importación de archivos PST con formato ANSI, vea el Paso 4 de [Usar la carga en la red para importar los archivos PST en Office 365.
  
Además, los archivos PST de Outlook 2007 y versiones posteriores se pueden importar a Office 365.
  
 **Después de cargar mis archivos PST en el área de almacenamiento de Azure, ¿cuánto tiempo se mantienen en Azure antes de eliminarse?**
  
Cuando use el método de carga en la red para importar archivos PST, cárguelos en un contenedor de blobs de Azure denominado **ingestiondata**. Si no hay ningún trabajo de importación en curso en la página **Importar** en el Centro de seguridad y cumplimiento, todos los archivos PST del contenedor **ingestiondata** de Azure se eliminarán en un plazo de 30 días tras crear el último trabajo de importación en el Centro de seguridad y cumplimiento. Eso significa también tendrá que crear una nueva tarea de importación en el Centro de seguridad y cumplimiento (se describe en el paso 5 de las instrucciones de carga de red) en un plazo de 30 días posteriores a la carga de archivos PST en Azure. 
  
Asimismo, después de que los archivos PST se eliminen del área de almacenamiento de Azure, ya no se mostrarán en la lista de archivos para un trabajo de importación completado en el Centro de seguridad y cumplimiento. Aunque todavía puede aparecer un trabajo de importación en la página **Importar** datos en el Centro de seguridad y cumplimiento, la lista de archivos PST puede estar vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **¿Cuánto tiempo se tarda en importar un archivo PST en un buzón?**
  
Depende de la capacidad de la red, pero normalmente cada terabyte (TB) de datos tarda algunas horas en cargarse en el área de almacenamiento de Azure para su organización. Después de que los archivos PST se copien en el área de almacenamiento de Azure, un archivo PST se importará a un buzón de Office 365 a una velocidad mínima de 24 GB al día. Si esta tasa no satisface sus necesidades, puede considerar otros métodos para migrar datos de correo electrónico a Office 365. Para obtener más información, vea [Formas de migrar varias cuentas de correo electrónico a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Si se importan distintos archivos PST a diferentes buzones de destino, el proceso de importación se producirá en paralelo; en otras palabras, cada par PST-buzón se importará de forma simultánea. Si se importan varios archivos PST al mismo buzón, se hará de manera simultánea.
  
 **¿Existe un límite de tamaño del mensaje al importar archivos PST?**
  
Sí. Si un archivo PST contiene un elemento de buzón de más de 150 MB, el elemento se ignorará durante el proceso de importación.
  
 **¿Las propiedades de los mensajes, como cuando el mensaje se envía o se recibe, la lista de destinatarios y otras propiedades, se conservan cuando se importan los archivos PST en un buzón de Office 365?**
  
Sí. Ninguno de los metadatos de los mensajes originales cambiará durante el proceso de importación.
  
 **¿Existe algún límite en el número de niveles de una jerarquía de carpetas para un archivo PST que quiero importar a un buzón?**
  
Sí. No puede importar archivos PST que tengan 300 o más niveles de carpetas anidadas.
  
 **¿Puedo usar la carga en la red para importar archivos PST en un buzón inactivo en Office 365?**
  
Sí, esta función está disponible ahora.
  
 **¿Puedo usar la carga en la red para importar archivos PST en un buzón de archivo en línea en una implementación híbrida de Exchange?**
  
Sí, esta función está disponible ahora.
  
 **¿Puedo usar la carga de red para importar archivos PST en carpetas públicas de Exchange Online?**
  
No, no puede importar archivos PST en carpetas públicas.
  
### <a name="using-drive-shipping-to-import-pst-files"></a>Uso del envío de unidades para importar los archivos PST

 **¿Qué permisos son necesarios para crear trabajos de importación en el servicio de importación de Office 365?**
  
Debe tener asignado el rol Importación o exportación de buzón para poder importar archivos PST a los buzones de Office 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Mailbox Import Export al grupo de roles Administración de la organización. O puede crear un nuevo grupo de rol, asignar el rol de exportación e importación de buzón y, después, agregarse o agregar a otros usuarios como miembro. Para obtener más información, vea las secciones "Agregar un rol a un grupo de roles" o "Crear un grupo de roles" en [Administrar grupos de roles en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Además, para crear trabajos de importación en el Centro de seguridad y cumplimiento, debe cumplirse uno de estos requisitos:
  
- Debe tener asignado el rol de los destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de roles de administración de la organización y administración de destinatarios.
    
    O bien
    
- Debe ser administrador global en su organización de Office 365. 
    
> [!TIP]
> Puede crear un nuevo grupo de roles en Exchange Online que está pensado específicamente para la importación de archivos PST a Office 365. Para obtener el nivel mínimo de privilegios necesarios para importar archivos PST, asigne los roles de importación y exportación de buzón y de destinatarios de correo al nuevo grupo de roles y, a continuación, agregue a los miembros. 
  
 **¿Dónde está disponible el envío de unidades?**
  
El envío de unidades está disponible actualmente en Estados Unidos, Canadá, Brasil, Reino Unido, Europa, India, Asia Oriental, Sudeste asiático, Japón, República de Corea y Australia. El envío de unidades estará disponible en más regiones próximamente.
  
 **¿Qué contratos de licencias comerciales admiten el envío de unidades?**
  
El envío de unidades para importar archivos PST en Office 365 está disponible mediante el Contrato Microsoft Enterprise (EA). El envío de unidades no está disponible mediante un Contrato de productos y servicios de Microsoft (MPSA).
  
 **¿Cuál es el precio de usar el envío de unidades para importar archivos PST en Office 365?**
  
El costo de usar el envío de unidades para importar archivos PST en buzones de Office 365 es de 2 USD por GB de datos. Por ejemplo, si envía una unidad de disco duro que contiene 1000 GB (1 TB) de archivos PST, el costo es 2000 USD. Puede colaborar con un asociado para abonar la cuota de importación. Para obtener información sobre cómo buscar un asociado, consulte [Buscar un asociado o distribuidor de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **¿Qué tipo de unidades de disco duro se admiten para el envío de unidades?**
  
El servicio de importación de Office 365 solo se puede usar con unidades de estado sólido de 2,5 pulgadas (SSD) o discos duros internos SATA II/III de 2,5 o 3,5 pulgadas. Puede usar discos duros de hasta 10 TB. Para los trabajos de importación, se procesará solo el primer volumen de datos del disco duro. El volumen de datos debe tener el formato NTFS. Al copiar datos a un disco duro, puede adjuntarlos directamente mediante un conector SSD de 2,5 pulgadas o un conector SATA II o SATA III de 2,5 o 3,5 pulgadas. También puede adjuntarlos de forma externa usando un adaptador USB externo SSD de 2,5 pulgadas o uno SATA II o SATA III de 2,5 o 3,5 pulgadas.
  
> [!IMPORTANT]
> El Servicio de importación de Office 365 no admite los discos duros externos con un adaptador USB integrado. Además, no se puede usar un disco que esté dentro de la carcasa de un disco duro externo. No envíe discos duros externos. 
  
 **¿Cuántas unidades de disco duro puedo enviar para un trabajo de importación único?**
  
Puede enviar un máximo de 10 unidades de disco duro para un único trabajo de importación.
  
 **Después de enviar mi unidad de disco duro, ¿cuánto tiempo tarda en llegar al centro de datos de Microsoft?**
  
Eso depende de varias cosas, como su proximidad al centro de datos de Microsoft y qué tipo de opción de envío ha usado para enviar la unidad de disco duro (es decir, envío en un día, en dos días o entrega mediante red terrestre). Con la mayoría de los transportistas, puede usar el número de seguimiento para realizar un seguimiento del estado de su envío.
  
 **Tras la recepción de mi disco duro en el centro de datos de Microsoft, ¿cuánto tiempo se tarda en cargar los archivos PST en Azure?**
  
Una vez que su disco duro se ha recibido en el centro de datos de Microsoft, se tardará entre 7 y 10 días laborables en cargar sus archivos PST al área de almacenamiento de Microsoft Azure de su organización. Los archivos PST se cargarán en un contenedor blob de Azure denominado `ingestiondata`. 
  
 **¿Cuánto tiempo se tarda en importar un archivo PST en un buzón?**
  
Una vez que los archivos PST se han cargado al área de almacenamiento de Azure, Office 365 analiza los datos que contienen dichos archivos de manera segura y adecuada para identificar la antigüedad de los elementos y los diferentes tipos de mensaje incluidos. Cuando se haya completado este análisis, podrá importar todos los datos de los archivos PST o establecer filtros para determinar qué datos importa. Durante el trabajo de importación, un archivo PST se importa a un buzón de correo de Office 365 a una velocidad de 24 GB al día como mínimo. Si esta tasa no satisface sus necesidades, puede considerar otros métodos para importar datos de correo electrónico a Office 365. Para obtener más información, vea [Formas de migrar varias cuentas de correo electrónico a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Si se importan distintos archivos PST a diferentes buzones de destino, el proceso de importación se producirá en paralelo; en otras palabras, cada par PST-buzón se importará de forma simultánea. Si se importan varios archivos PST al mismo buzón, se hará de manera simultánea.
  
 **Después de que Microsoft cargue mis archivos PST a Azure, ¿cuánto tiempo se conservarán en Azure antes de su eliminación?**
  
Todos los archivos PST de la ubicación de almacenamiento de Azure para su organización (en el contenedor blob denominado `ingestiondata`) se eliminan 30 días después de la creación del trabajo de importación más reciente en la página **Importar** del Centro de seguridad y cumplimiento. 
  
Asimismo, después de que los archivos PST se eliminen del área de almacenamiento de Azure, ya no se mostrarán en la lista de archivos para un trabajo de importación completado en el Centro de seguridad y cumplimiento. Aunque todavía puede aparecer un trabajo de importación en la página **Importar** datos en el Centro de seguridad y cumplimiento, la lista de archivos PST puede estar vacía cuando vea los detalles de los trabajos de importación más antiguos. 
  
 **¿Qué versión del formato de archivo PST se admite para importarse en Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. Recomendamos la importación de archivos que usen el formato Unicode de archivo PST. En cambio, los archivos que usan el formato ANSI de archivo PST, como pueden ser los de los idiomas que usan un conjunto de caracteres de doble byte (DBCS), también pueden importarse a Office 365. Para obtener más información sobre la importación de archivos PST con formato ANSI, vea el Paso 3 de [Usar el envío de unidades para importar los archivos PST de su organización a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Además, los archivos PST de Outlook 2007 y versiones posteriores se pueden importar a Office 365.
  
 **¿Existe un límite de tamaño del mensaje al importar archivos PST?**
  
Sí. Si un archivo PST contiene un elemento de buzón de más de 150 MB, el elemento se ignorará durante el proceso de importación.
  
 **¿Las propiedades de los mensajes, como cuando el mensaje se envía o se recibe, la lista de destinatarios y otras propiedades, se conservan cuando se importan los archivos PST en un buzón de Office 365?**
  
Sí. Los metadatos de los mensajes originales no se modifican durante el proceso de importación.
  
 **¿Existe algún límite en el número de niveles de una jerarquía de carpetas para un archivo PST que quiero importar a un buzón?**
  
Sí. No puede importar archivos PST que tengan 300 o más niveles de carpetas anidadas.
  
 **¿Puedo usar el envío de unidades para importar archivos PST en un buzón inactivo en Office 365?**
  
Sí, esta función está disponible ahora.
  
 **¿Puedo usar el envío de unidades para importar archivos PST en un buzón de archivo en línea en una implementación híbrida de Exchange?**
  
Sí, esta función está disponible ahora.
  
 **¿Puedo usar el envío de unidades para importar archivos PST en carpetas públicas de Exchange Online?**
  
No, no puede importar archivos PST en carpetas públicas.
  
 **¿Puede Microsoft borrar los datos de mi unidad de disco duro antes de que me la envíen de nuevo?**
  
No, Microsoft no puede borrar los datos de las unidades de disco duro antes de enviarlas de nuevo a los clientes. Las unidades de disco duro se le devuelven en el mismo estado en el que se encontraban cuando las recibió Microsoft.
  
 **¿Puede Microsoft destruir mi unidad de disco duro en lugar de enviármela de nuevo?**
  
No, Microsoft no puede destruir la unidad de disco duro. Las unidades de disco duro se le devuelven en el mismo estado que estaban cuando las recibió Microsoft.
  
 **¿Qué servicios de mensajería admiten la devolución?**
  
Si es un cliente de Estados Unidos o Europa, Microsoft usa FedEx para devolver la unidad de disco duro. Para las demás regiones, Microsoft usa DHL.
  
 **¿Cuáles son los costos de la devolución?**
  
Los costos de la devolución varían dependiendo de la proximidad al centro de datos de Microsoft al que ha enviado la unidad. Microsoft facturará la cuenta de DHL o FedEx para devolver su unidad de disco duro. El costo de la devolución es su responsabilidad.
  
 **¿Puedo usar un servicio de envío personalizado, como el envío personalizado de FedEx, para enviar mi unidad de disco duro a Microsoft?**
  
Sí.
  
 **Si tengo que enviar mi unidad a otro país, ¿necesito hacer algo?**
  
La unidad de disco duro que envíe a Microsoft puede tener que atravesar fronteras internacionales. Si este es el caso, es responsable de garantizar que la unidad y los datos que contiene se importen o exporten según las leyes aplicables. Antes de enviar una unidad de disco duro, compruebe con sus asesores que la unidad y los datos pueden enviarse legalmente al centro de datos de Microsoft especificado. Esto ayudará a garantizar que llegan a Microsoft de manera puntual.
