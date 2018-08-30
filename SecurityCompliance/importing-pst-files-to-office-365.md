---
title: Información general de importación de los archivos PST de organización a Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: 'Para los administradores: Aprenda a usar el servicio de importación en la seguridad de Office 365 &amp; centro de cumplimiento para importación masiva datos de correo electrónico (archivos PST) a los buzones de usuario en Exchange Online. Este tema proporciona las preguntas más frecuentes y explica cómo funciona el proceso de importación de PST.'
ms.openlocfilehash: 1cbe5627ffb906b6a87541f4c4582a2806562ca4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536494"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a>Información general de importación de los archivos PST de organización a Office 365

> [!NOTE]
> En este artículo está dirigido a administradores. ¿Está intentando importar archivos PST en su propio buzón? Consulte el [correo electrónico de importación, contactos y calendario desde un archivo .pst de Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)

Puede usar el servicio de importación en la seguridad de Office 365 &amp; los archivos de centro de cumplimiento a rápidamente-importación masiva PST a buzones de Exchange Online en la organización de Office 365. Hay dos formas puede importar archivos PST a Office 365:
   
- **Carga de red** ![Cargar en la nube](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) -cargar los archivos PST a través de la red a una ubicación de almacenamiento temporal de Azure en la nube de Microsoft. A continuación, usar el servicio Office 365 importar para importar los datos de PST a buzones de correo en la organización de Office 365. 

- **Unidad de trasvase de registros** ![Disco duro](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) -, copie los archivos PST en una unidad de disco duro cifrado BitLocker y, a continuación, enviar físicamente la unidad a Microsoft. Cuando Microsoft recibe la unidad de disco duro, personal del centro de datos carga los datos en una ubicación de almacenamiento temporal de Azure en la nube de Microsoft. A continuación, usar el servicio Office 365 importar para importar los datos a los buzones de correo en la organización de Office 365.

## <a name="step-by-step-instructions"></a>Instrucciones paso a paso
  
Vea uno de los siguientes temas para obtener instrucciones paso a paso para la importación masiva de archivos PST de su organización a Office 365. 
   
- [Usar la carga en la red para importar archivos PST en Office 365](use-network-upload-to-import-pst-files.md)
- [Usar el envío de unidades para importar los archivos PST a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>Cómo funciona la importación de los archivos PST

Aquí es una ilustración y una descripción del proceso de importación de PST completo. La ilustración muestra el flujo de trabajo principal y resalta las diferencias entre la carga de red y la unidad de métodos de envío.
  
![Flujo de trabajo del proceso de importación de PST](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **Descarga el archivo PST importar herramientas y la ubicación de almacenamiento de Azure clave Private** - el primer paso es descargar la clave de acceso y la herramienta usada para cargar los archivos PST o copiarlos en una unidad de disco duro. Obtener estos desde la página de **importación** de la seguridad de Office 365 &amp; centro de cumplimiento. La clave proporciona usted (o personal del centro de datos de Microsoft en el caso de trasvase de registros de unidad) con los permisos necesarios para cargar los archivos PST en una ubicación de almacenamiento de Azure privada y segura. Esta clave de acceso es única para la organización y ayuda a impedir el acceso no autorizado a los archivos PST después de que se cargan a la nube de Microsoft. Tenga en cuenta que la importación de los archivos PST a Office 365 no requiere a tiene una suscripción de Azure independiente a su organización. 
    
2. **Cargar o copiar el archivo PST archivos** - el siguiente paso depende de si utiliza el trasvase de registros de unidad o de carga de red para importar los archivos PST. En ambos casos, debe usar la herramienta y la clave de almacenamiento seguro que obtuvo en el paso anterior.
    
    - **Carga de red** La herramienta AzCopy.exe (descargada en el paso 1) se usa para cargar y almacenar los archivos PST en una ubicación de almacenamiento de Azure en la nube de Microsoft. Tenga en cuenta que la ubicación de almacenamiento de Azure que carga los archivos PST a reside en el mismo Microsoft centro de datos regional donde se encuentra su organización de Office 365. 
    
      Para cargarlas, los archivos PST que desea importar a Office 365 tienen que estar ubicada en un recurso compartido de archivos o un servidor de archivos en su organización.
    
    - **Unidad de trasvase de registros** La herramienta WAImportExport.exe (descargada en el paso 1) se usa para copiar los archivos PST en la unidad de disco duro. Esta herramienta cifra la unidad de disco duro con BitLocker y, a continuación, copia los archivos pst en la unidad de disco duro. Al igual que la carga de red, los archivos PST que se desean copiar en la unidad de disco duro tienen que estar ubicada en un recurso compartido de archivos o un servidor de archivos en su organización.
    
3. **Crear un archivo de asignación de importación de PST** - después de que se han cargado en la ubicación de almacenamiento de Azure o copiado en una unidad de disco duro los archivos PST, el siguiente paso es crear un archivo (CSV) de valores separados por comas que especifica qué archivos PST de buzones de correo de usuario se importará a (un se puede importar un archivo PST ND a su buzón de archivo o buzón principal de un usuario). El servicio Office 365 importar utilizará la información para importar los archivos PST. 
    
4. **Trabajo de importación de crear un archivo PST** - el siguiente paso es crear un trabajo de importación de PST en la página **Importar** en la seguridad &amp; centro de cumplimiento y enviar el archivo de asignación de importación de PST creado en el paso anterior. Para la carga de red (debido a que los archivos PST se han cargado en Azure) Office 365 analiza los datos en los archivos PST y, a continuación, le proporciona una oportunidad para definir filtros que controlan qué datos realmente obtiene importados a los buzones especificados en el archivo de asignación de importación de PST. 
    
    Para el envío de unidad, unos adicionales hechos en este punto en el proceso.
    
    - Enviar por físicamente la unidad de disco duro a un centro de datos de Microsoft (la dirección de envío para el centro de datos de Microsoft se muestra cuando se crea el trabajo de importación)
    
    - Cuando Microsoft recibe la unidad de disco duro, personal del centro de datos van a cargar los archivos pst en la unidad de disco duro a la ubicación de almacenamiento de Azure para su organización. Como se explica anteriormente, se cargan los archivos PST en una ubicación de almacenamiento de Azure que reside en el mismo centro de datos regional de Microsoft donde se encuentra su organización de Office 365.
    
      > [!NOTE]
      > Los archivos PST en la unidad de disco duro se cargan en Azure dentro de 7 a 10 días de negocio una vez que Microsoft recibe la unidad de disco duro. 
  
      Al igual que el proceso de carga de red, Office 365, a continuación, analiza los datos en los archivos PST y le proporciona una oportunidad para definir filtros que controlan qué datos realmente obtiene importados a los buzones especificados en el archivo de asignación de importación de PST.
    
    - Microsoft incluye la unidad de disco duro a usted. 
    
5. **Filtrar los datos de PST que se va a importar a buzones de correo** - una vez creado el trabajo de importación (y después de que se cargan los archivos PST de un trabajo de trasvase de registros de la unidad en la ubicación de almacenamiento de Azure) Office 365 analiza los datos en los archivos PST (segura y) por identificación de la antigüedad de los elementos y los tipos de mensaje diferentes incluidos en los archivos PST. Cuando se completa el análisis y están listos para importar los datos, tiene la opción para importar todos los datos contenidos en los archivos PST o puede recortar los datos que se importan mediante la configuración de filtros que controlan qué datos obtiene importados. 
    
6. **Iniciar el trabajo de importación de PST** - una vez iniciado el trabajo de importación, Office 365 utiliza la información en el archivo de asignación de importación de PST para importar los archivos PST desde la ubicación de almacenamiento de Azure a buzones de usuario. Información de estado sobre el trabajo de importación (incluida la información acerca de cada archivo PST que se están importando) se muestra en la página **Importar** en la seguridad &amp; centro de cumplimiento. Cuando finalice el trabajo de importación, el estado del trabajo se establece en **completa**.
  
## <a name="why-import-email-data-to-office-365"></a>¿Por qué importar datos de correo electrónico a Office 365?

- Importación de archivos PST a buzones de usuario es una forma de migrar correo electrónico de su organización a Office 365.
    
- Puede usar la característica de [Importación inteligente](filter-data-when-importing-pst-files.md) para filtrar los elementos en los archivos PST que realmente obtengan importa a los buzones de correo de destino. Esto permite recortar los datos que se importan mediante la configuración de filtros que controla qué datos obtiene importados. 
    
- Importación de datos de correo electrónico a Office 365 ayuda a las necesidades de cumplimiento de normas de dirección de la organización que le permite:
    
  - Habilitar [buzones de archivo](enable-archive-mailboxes.md) y [el archivo ilimitado](unlimited-archiving.md) a proporcionar a los usuarios espacio de almacenamiento de buzones de correo adicionales. 
    
  - Colocar buzones en [Suspensión por litigio](https://go.microsoft.com/fwlink/?linkid=841243) a conservar el contenido. 
    
  - Use la [herramienta de búsqueda de contenido](content-search.md) para buscar contenido de los buzones. 
    
  - Use los [casos de exhibición de documentos electrónicos](ediscovery-cases.md) para administrar las investigaciones legales de su organización 
    
  - Use [las directivas de retención](retention-policies.md) de la seguridad &amp; centro de cumplimiento para controlar cuánto tiempo se conserva el contenido de los buzones y, a continuación, en eliminar contenido después de que expire el período de retención. 
    
- Importar datos a Office 365 ayuda a proteger contra la pérdida de datos. Datos de correo electrónico que se importan a Office 365 hereda las características de alta disponibilidad de Exchange Online.
    
- Datos de correo electrónico en Office 365 están disponibles para los usuarios de todos los dispositivos porque está almacenado en la nube.
    
## <a name="importing-sharepoint-data-to-office-365"></a>Importación de datos de SharePoint a Office 365

También puede importar archivos y documentos a cuentas de OneDrive y sitios de SharePoint en la organización de Office 365. Para obtener más información, vea [cargar contenido local a SharePoint Online mediante los cmdlets de PowerShell](https://docs.microsoft.com/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a>Preguntas más frecuentes acerca de cómo importar archivos PST a Office 365
  
A continuación presentamos algunas preguntas frecuentes acerca del uso del servicio Office 365 importar para importación masiva de archivos PST a buzones de correo de Office 365. 
  
- [Uso de carga de red para importar archivos PST](#using-network-upload-to-import-pst-files)
  
- [Uso de trasvase de registros de unidad para importar archivos PST](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>Uso de carga de red para importar archivos PST

 **¿Qué permisos son necesarios para crear trabajos de importación en el servicio de Office 365 importar?**
  
Se debe asignar la función de importación de exportación de buzones de correo en Exchange en línea para importar archivos PST a buzones de Office 365. De forma predeterminada, este rol no está asignado a ningún grupo de funciones en Exchange Online. Puede agregar la función de exportación de importación de buzón de correo para el grupo de roles de administración de la organización. O bien, puede crear un nuevo grupo de roles, asignar el rol de buzón de correo importar exportar y, a continuación, agregue a usted o a otros usuarios como un miembro. Para obtener más información, vea el "Agregar un rol a un grupo de roles" o la "crear un grupo de roles" secciones en [función de administrar grupos en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Además crear la importación de trabajos en la seguridad de Office 365 &amp; debe ser verdadero centro de cumplimiento, uno de los siguientes:
  
- Se debe tener asignado el rol de destinatarios de correo en Exchange Online. De forma predeterminada, este rol se asigna a los grupos de funciones de administración de la organización y administración de destinatarios.
    
    O bien
    
- Debe ser un administrador global de la organización de Office 365.
    
> [!TIP]
> Considere la posibilidad de crear un nuevo grupo de funciones en Exchange Online diseñada específicamente para la importación de los archivos PST a Office 365. Para el nivel mínimo de privilegios necesarios para importar los archivos PST, asigne las funciones de importación de exportación de buzones de correo y destinatarios de correo para el nuevo grupo de roles y, a continuación, agregar a miembros. 
  
 **¿Dónde está disponible la carga de red?**
  
Carga de red está actualmente disponible en los Estados Unidos, Canadá, Brasil, el Reino Unido, Europa, India, Asia oriental, sureste de Asia, Japón, República de Corea y Australia. Carga de red estará disponible en las regiones más pronto.
  
 **¿Cuál es el precio de importación de los archivos PST mediante el uso de carga de red?**
  
Uso de carga de red para importar archivos PST es gratuito.
  
Esto también significa que después de que se eliminan los archivos PST desde el área de almacenamiento de Azure, está ya no se muestran en la lista de archivos para un trabajo de importación completadas en el centro de administración de Office 365. Aunque un trabajo de importación puede seguir apareciendo en la página **Importar datos a Office 365** , la lista de los archivos PST podría estar vacía al ver los detalles de los trabajos de importación más antiguos. 
  
 **¿Qué versión del formato de archivo PST se admite para la importación a Office 365?**
  
Hay dos versiones del formato de archivo PST: ANSI y Unicode. Se recomienda importar los archivos que usan el formato de archivo PST Unicode. Sin embargo, los archivos que usan el formato de archivo PST ANSI, como los de los idiomas que usan un carácter de doble byte (DBCS) de establecer, también se pueden importar a Office 365. Para obtener más información acerca de cómo importar archivos PST ANSI, consulte el paso 4 en la [red de uso cargar para importar archivos PST a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).
  
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
  
### <a name="using-drive-shipping-to-import-pst-files"></a>Uso de trasvase de registros de unidad para importar archivos PST

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
  
Después de la unidad de disco duro se recibe en el centro de datos de Microsoft, se tardará entre 7 y 10 días de negocio para cargar los archivos PST en el área de almacenamiento de información de Microsoft Azure para su organización. Los archivos PST se cargará en un contenedor de Azure blob denominado `ingestiondata`. 
  
 **¿Cuánto tiempo tarda para importar un archivo PST a un buzón de correo?**
  
Después de que se cargan los archivos PST en el área de almacenamiento de Azure, Office 365 analiza los datos en los archivos PST (de forma segura) para identificar la antigüedad de los elementos y los tipos de mensaje diferentes incluidos en los archivos PST. Una vez completado este análisis, tendrá la opción de importar todos los datos en los archivos PST o establecimiento de filtros para que controlar qué datos obtiene importados. Después de iniciar el trabajo de importación, se importa un archivo PST a un buzón de Office 365 a una velocidad de al menos 24 GB por día. Si esta velocidad no satisface sus necesidades, es posible que tenga en cuenta otros métodos para importar datos de correo electrónico a Office 365. Para obtener más información, vea [formas de migrar cuentas de correo electrónico a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
Si se importan diferentes archivos PST a buzones de correo de destino diferente, el proceso de importación se produce en paralelo; en otras palabras, cada par de PST y buzón de correo se importa simultáneamente. Del mismo modo, si se importan varios archivos PST en el mismo buzón, se importará simultáneamente.
  
 **¿Después de que Microsoft carga Mis archivos PST en Azure, cuánto se conservan en Azure antes de que se eliminan?**
  
Todos los archivos PST en la ubicación de almacenamiento de Azure para su organización (en el contenedor de blob denominado `ingestiondata`), se eliminan los 30 días después de que se creó el trabajo de importación más reciente en la página **Importar** en la seguridad &amp; centro de cumplimiento. 
  
Esto también significa que después de que se eliminan los archivos PST desde el área de almacenamiento de Azure, está ya no se muestran en la lista de archivos para un trabajo de importación completadas en la seguridad &amp; centro de cumplimiento. Aunque un trabajo de importación puede seguir apareciendo en la página **Importar** en la seguridad &amp; centro de cumplimiento, la lista de los archivos PST podría estar vacía al ver los detalles de los trabajos de importación más antiguos. 
  
 **¿Qué versión del formato de archivo PST se admite para la importación a Office 365?**
  
Hay dos versiones del formato de archivo PST: ANSI y Unicode. Se recomienda importar los archivos que usan el formato de archivo PST Unicode. Sin embargo, los archivos que usan el formato de archivo PST ANSI, como los de los idiomas que usan un carácter de doble byte (DBCS) de establecer, también se pueden importar a Office 365. Para obtener más información acerca de cómo importar archivos PST ANSI, vea el paso 3 en [Usar unidad de envío para importar los archivos PST de organización a Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
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
