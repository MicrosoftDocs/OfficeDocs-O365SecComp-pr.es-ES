---
title: Preguntas más frecuentes sobre el cifrado de servicio con la clave de cliente para Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: Además de la línea de base, el cifrado de nivel de volumen que se ha habilitado a través de BitLocker y Administrador de clave distribuida (DKM), Office 365 ofrece un nivel adicional de cifrado en el nivel de aplicación para el contenido de cliente de Office 365, incluidos los datos de Exchange En línea, Skype para la empresa, SharePoint Online y OneDrive para la empresa. Esto se denomina cifrado de servicio.
ms.openlocfilehash: ceba35233872bb65b7706ed4e11a263057adc6c1
ms.sourcegitcommit: 659b5f5b38ef7e838cdb44eaa38c18e48d922768
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "25575334"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>Preguntas más frecuentes sobre el cifrado de servicio con la clave de cliente para Office 365

Además de la línea de base, el cifrado de nivel de volumen que se ha habilitado a través de BitLocker y Administrador de clave distribuida (DKM), Office 365 ofrece un nivel adicional de cifrado en el nivel de aplicación para el contenido de cliente de Office 365, incluidos los datos de Exchange En línea, Skype para la empresa, SharePoint Online y OneDrive para la empresa. Esto se denomina cifrado de servicio.
  
Clave de cliente se basa en el cifrado de servicio y permite al usuario para proporcionar y teclas de control que se usan para cifrar los datos en reposo en Office 365, tal como se describe en los [Términos de servicios en línea (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx). Clave de cliente le ayudará a cumplir las obligaciones de cumplimiento de normas debido a que controlan las claves de cifrado que usa Office 365 para descifrar los datos.
  
Para proporcionar comentarios en la clave del cliente, incluida la documentación, envíe sus ideas, sugerencias y perspectivas a customerkeyfeedback@microsoft.com.
  
## <a name="what-is-service-encryption-with-customer-key"></a>¿Qué es el cifrado de servicio con la clave de cliente?

Clave de cliente mejora la capacidad de la organización para satisfacer las demandas de los requisitos de cumplimiento de normas que especifican las condiciones de clave con el proveedor de servicios en la nube. Con la clave de cliente, proporcionar y controlar las claves de cifrado para su Office 365 datos almacenados en el nivel de aplicación. Como resultado, es posible que ejercer control y revocar las claves de la organización, debe decidir salir el servicio. Revocar las claves, los datos es que debe recibirlo al servicio. Revocación de clave es el primer paso en la ruta de acceso hacia la eliminación de datos.

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>¿Qué datos Office 365 en reposo está cubiertas por clave de cliente?
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

Se incluyen el contenido del sitio de SharePoint Online y los archivos almacenados en ese sitio y los archivos cargados en OneDrive para la empresa. Se trata el contenido del buzón Exchange Online (cuerpo del correo electrónico, las entradas de calendario y contenido de datos adjuntos de correo electrónico). Se tratan las conversaciones de texto de Skype para la empresa, pero no se tratan las grabaciones de reunión Difundir presentación de Skype y cargas de contenido de reuniones de Skype. Difundir presentación de reunión de Skype y Skype reunión cargas de contenido se cifran junto con el resto del contenido en Office 365, pero que actualmente no ofrecemos control de cliente de las claves de cifrado.
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>¿Cuál es la diferencia entre la clave de cliente y traer su propia clave (BYOK) con protección de la información de Azure para Exchange Online?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Ambas opciones le permiten proporcionar y controlar sus propios claves de cifrado; Sin embargo, el cifrado de servicio con la clave de cliente cifra los datos en reposo, que reside en los servidores de los Office 365 en rest, mientras que BYOK con protección de la información de Azure para Exchange Online cifra los datos en tránsito y proporciona persistente en línea y sin conexión protección de mensajes de correo electrónico y los datos adjuntos para Office 365. Clave de cliente y BYOK con protección de la información de Azure para Exchange Online son complementarias y, si decide usar claves de administrados por el servicio de Microsoft o su propio, cifrar los datos en reposo y en tránsito puede ofrecer una protección adicional de ataques malintencionados.
  
BYOK con protección de la información de Azure para Exchange Online está disponible en las capacidades de cifrado de mensajes de Office 365.
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>¿El cifrado de mensajes de Office 365 y traer su propia clave con protección de la información de Azure cambia el enfoque de Microsoft a las solicitudes de datos de terceros, como su orden?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. Cifrado de mensajes de Office 365 y la opción para ofrecer y controlar sus propios claves de cifrado con Traer su propia clave (BYOK) para protección de información de Azure (AIP) no se ha diseñado para responder a su orden de aplicación de la legislación. Cifrado de mensajes de Office 365 con BYOK para AIP se diseñó para cumplimiento dirigidos a los clientes que necesitan para cumplir sus obligaciones de cumplimiento interno o externo. Microsoft toma muy en serio las solicitudes de terceros para los datos de cliente. Como un proveedor de servicios en la nube, siempre se recomiendan para la privacidad de los datos de cliente. En el caso de que se obtenga una citación, intentaremos siempre redirigir el tercero al cliente para obtener la información. (Lea el blog de Brad Smith: [Protecting los datos de cliente de gobierno fisgonear](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Periódicamente se publica información detallada de la solicitud que recibimos [aquí](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data).
  
Consulte el [Centro de confianza de Microsoft](https://www.microsoft.com/en-us/trustcenter/default.aspx) con respecto a las solicitudes de datos de terceros y "Divulgación de datos de clientes" en [Términos de servicios en línea (OST) ](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)para obtener más información.
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>¿Cifrado de servicio con la clave de cliente cambia el enfoque de Microsoft para las solicitudes de datos de terceros, como su orden?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. Clave de cliente no se diseñó para responder a su orden de aplicación de la legislación. Se diseñó para que los clientes regulados cumplir sus obligaciones de cumplimiento interno o externo. Microsoft toma muy en serio las solicitudes de terceros para los datos de cliente. Como un proveedor de servicios en la nube, siempre se recomiendan para la privacidad de los datos de cliente. En el caso de que se obtenga una citación, intentaremos siempre redirigir el tercero al cliente para obtener la información. (Lea el blog de Brad Smith: [Protecting los datos de cliente de gobierno fisgonear](http://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Periódicamente se publica información detallada de la solicitud que recibimos [aquí](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data).
  
Consulte el [Centro de confianza de Microsoft](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data) con respecto a las solicitudes de datos de terceros y "Divulgación de datos de clientes" en [Términos de servicios en línea (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx) para obtener más información. 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>¿Es el soporte de FastTrack disponibles para implementar la clave de cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. FastTrack solo se usa para recopilar información de configuración de inquilino y servicio que se necesita para registrar para la clave de cliente. La clave de cliente ofrece se publican a través de FastTrack, por lo que es conveniente para los clientes y socios enviar esta información necesaria con el mismo método y para facilitar los datos que proporcionan los clientes en la oferta de archivado.
  
Si necesita compatibilidad adicional más allá de la documentación, póngase en contacto con los servicios de consultoría de Microsoft (MCS), ingeniería de campo Premier (PFE) o un socio de Microsoft para obtener ayuda.
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>Si se destruyen Mis claves, ¿cómo puedo recuperar?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

La clave de disponibilidad le proporciona la capacidad de recuperarse de la pérdida de claves raíz que administre consecuencias. Si pierde las claves raíz, contacto Microsoft Support y Microsoft le ayudará a través del proceso de la habilitación de la clave de disponibilidad. Para migrar a una nueva directiva de cifrado de datos con claves nuevas aprovisionadas por usted, debe usar la clave de disponibilidad. 
  
## <a name="what-is-the-availability-key"></a>¿Qué es la clave de disponibilidad?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

La clave de disponibilidad es una clave de raíz que se ha suministrado al crear una directiva de cifrado de datos. La clave de disponibilidad se almacenan y protegida incluido en Office 365 y es funcionalmente similar a las claves dos raíz suministradas por el usuario para su uso con el cifrado de servicio con la clave de cliente. A diferencia de las claves que puede proporciona y administrar en Azure clave depósito, no se puede tener acceso directamente a la clave de disponibilidad. Almacenamiento y control de la clave de disponibilidad son deliberadamente diferentes de las claves de Azure clave cámara por tres motivos: en primer lugar, la clave de disponibilidad proporciona una capacidad de alta disponibilidad en caso de que los servicios de Office 365 están no puede alcanzar claves hospedadas en clave de Azure Cámara; en segundo lugar, proporciona una capacidad "romper vasos" en la clave de disponibilidad en caso de que las dos claves de Azure clave cámara se pierden; y en tercer lugar, la separación de los controles de lógicas proporciona una defensa en profundidad y protege contra la pérdida de todas las claves de un ataque único o punto de error. Uso compartido de la responsabilidad para proteger las teclas, durante el uso de una gran variedad de protecciones y procesos de administración de claves, en última instancia reduce el riesgo de que todas las claves (y, por tanto, los datos) se pierde o destruye. Microsoft proporciona autoridad único a través de la destrucción de la clave de disponibilidad. Por diseño, en Microsoft nadie tenga acceso a la clave de disponibilidad: sólo es accesible por el código de servicio de Office 365.
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>¿Cuántas directivas de cifrado de datos (depós) se debe crear?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online y Skype para la empresa:** Puede crear hasta 50 depós. 
  
 **SharePoint Online y OneDrive para la empresa:** Una DEP se aplica a los datos en una ubicación geográfica, también denominada un geo. Si usa la característica de multi-ubican de Office 365, puede crear uno DEP por ubican. Si no está utilizando multi-ubican, puede crear una dependencia
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>¿Se puede asignar una directiva de cifrado de datos antes de migrar un buzón a la nube?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Sí. Puede usar el cmdlet Set-MailUser de Windows PowerShell para asignar una directiva de cifrado de datos (DEP) para el usuario antes de migrar el buzón de correo a Office 365. En este caso, el contenido del buzón se cifrarán mediante la característica DEP asignada tal como se migra el contenido. Esto puede ser más eficaz que asignar una DEP después de que ya se ha migrado el buzón de correo y, a continuación, esperando cifrado que tenga lugar, que puede tardar horas o, posiblemente, días. 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>¿Cómo se puede comprobar que se activa el cifrado con clave de cliente y Office 365 ha terminado de cifrado con clave de cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online y Skype para la empresa:** Puede [conectarse a Exchange Online mediante PowerShell remoto](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) y, a continuación, use el cmdlet **[Get-MailboxStatistics]** para cada buzón de correo que se va a comprobar. En el resultado del cmdlet Get-MailboxStatistics, la propiedad _IsEncrypted_ devuelve un valor de **true** si el buzón de correo se cifra y un valor de **false** si no lo está. Si se cifra el buzón de correo, el valor devuelto para la propiedad _DataEncryptionPolicyID_ es el GUID de la característica DEP con la que se cifra el buzón de correo. Para obtener más información acerca de cómo ejecutar este cmdlet, vea [Get-MailboxStatistics](https://technet.microsoft.com/en-us/library/bb124612%28v=exchg.160%29.aspx) y el uso de PowerShell con Exchange Online. 
  
Si no se cifran los buzones de correo después de esperar a 72 horas desde el momento en que asignó la DEP, iniciar un movimiento del buzón. Para hacer esto, [conectarse a Exchange Online mediante PowerShell remoto](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) y, a continuación, use el cmdlet New-MoveRequest y proporcionar el alias del buzón de la siguiente manera: 
  
```
New-MoveRequest <alias>
```

 **SharePoint Online y OneDrive para la empresa:** Se puede [Conectar a SharePoint Online PowerShell](https://technet.microsoft.com/en-us/library/fp161372.aspx)y, a continuación, use el cmdlet **[Get-SPODataEncryptionPolicy]** para comprobar el estado de su inquilino. El ** _estado_** (propiedad) devuelve un valor de **registrado** si está habilitado el cifrado de clave de cliente y se han cifrado todos los archivos en todos los sitios. Si el cifrado todavía está en curso, este cmdlet proporciona información sobre qué porcentaje de sitios está completado. 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>¿Si desea cambiar a un conjunto diferente de claves, cuánto tarda para el nuevo conjunto de claves para proteger mis datos?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online y Skype para la empresa:** Puede tardar hasta 72 horas para proteger un buzón de acuerdo con una nueva directiva de cifrado de datos (DEP) desde el momento en que el nuevo DEP está asignada al buzón. 
  
 **SharePoint Online y OneDrive para la empresa:** Puede tardar hasta cuatro horas para volver a cifrar al inquilino de todo una vez que se ha asignado una nueva clave. 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>¿Se almacenan los datos existentes sin cifrado en cualquier momento mientras se descifrar o cifrado con clave de cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. Siempre se cifran los datos en reposo en el servicio Office 365 con BitLocker y DKM. Para obtener más información, vea la "seguridad, privacidad y cumplimiento de normas información para Office 365" y [cómo Exchange Online protege los secretos de correo electrónico](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376).
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>¿Si ya no desea utilizar las claves de cifrado del cliente administrado, puedo cambiar a claves administradas de Microsoft?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online y Skype para la empresa:** Todavía no. Se admitirá una vez cifrado de servicio en Office 365 con las teclas de Microsoft administrado se ha implantado ampliamente. Esperamos que se lleve a cabo en el servicio después de que se suelte cifrado de servicio con la clave de cliente. 
  
 **SharePoint Online y OneDrive para la empresa:** Sí. Puede volver a usar claves administradas de Microsoft por separado para cada geo (si usa la característica de multi-ubican) o para todos los datos si está en un único ubican. 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>¿Si pierden Mis claves, cuánto se tarda en recuperar la disponibilidad del servicio de uso de la clave de recuperación?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online y Skype para la empresa:** Una vez que llama a usar la clave de disponibilidad, tendrá acceso a los buzones de correo en cuestión de minutos. 
  
 **SharePoint Online y OneDrive para la empresa:** Esta operación es proporcional al número de sitios que tiene. Una vez que se llama a Microsoft para usar la clave de disponibilidad, estará totalmente en línea dentro de cuatro horas. 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>¿Cómo se usa la clave de disponibilidad con Exchange Online?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Hay tres maneras de que se usa la clave de disponibilidad con Exchange Online:
  
- Servicio de disponibilidad - en caso de que no puedo acceder son las claves de cámara de clave de Azure.
    
- Acciones inician por el código de servicio de Office 365, como la creación de índice de búsqueda o movimientos de buzones.
    
- Recuperarse de pérdida de clave - como la pérdida de las dos claves de Azure clave cámara asociado a una única dependencia
    
 **Con la clave de disponibilidad para la disponibilidad del servicio en caso de que no puedo acceder son las claves de cámara de clave de Azure.**
  
Office 365 usa la clave de disponibilidad tanto para la disponibilidad del servicio y la recuperación a partir de un mal estado de clave de cliente de Exchange Online. Hay una jerarquía de teclas usadas por clave de cliente. Esta jerarquía se ilustra en la figura siguiente.
  
![](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
Si no están disponibles las dos claves de Azure clave cámara de una sola directiva de cifrado de datos (DEP), Office 365 puede usar la disponibilidad clave para cambiar a un nuevo DEP Office 365 determina si se utiliza la clave de disponibilidad para la disponibilidad del servicio de forma diferente dependiendo de si un actividad iniciadas por el usuario, por ejemplo, cuando un usuario descarga el correo electrónico para el cliente de Outlook, o una actividad iniciadas por el sistema, como la indización de contenido de buzones de correo, o para las búsquedas de exhibición de documentos electrónicos, desencadena el proceso.
  
Office 365 sigue este proceso en respuesta a las acciones iniciadas por el usuario para determinar si se debe usar la clave de disponibilidad para buzones de usuario:
  
1. Office 365 lee la DEP al que está asignado el buzón de correo con el fin de determinar la ubicación de las claves de dos cliente de cámara de clave de Azure.
    
2. Office 365 aleatoriamente elige una de las claves de dos cliente de la característica DEP y envía una solicitud a Azure clave cámara para liberar la clave de la característica DEP utilizando la clave del cliente.
    
3. Si la solicitud para liberar el DEP clave utilizando la clave del cliente se produce un error y devuelve un error, Office 365 envía una segunda solicitud a Azure clave cámara, este tiempo indicándole que use la alternativa clave de cliente (segundo).
    
4. Si la segunda solicitud para liberar la clave DEP utilizando el se produce un error de clave de cliente y devuelve un error, Office 365 examina los resultados de ambas solicitudes:
    
  - Si el examen determina que los errores no reflejan una acción explícita por una identidad de cliente, Office 365 usa la clave de disponibilidad para descifrar la clave de la característica DEP. A continuación, se usa la clave de la característica DEP para descifrar la clave de buzón de correo y completar la solicitud del usuario.
    
    En este caso, Azure clave Vault es no puede responder o es inaccesible por cualquier motivo. Office 365 no tiene forma de determinar si el cliente ha revocado intencionadamente acceso a las claves.
    
  - Si indica el examen se ha realizado dicha acción deliberada para representar los claves de cliente no está disponible, a continuación, no se usará la clave de disponibilidad, se produce un error en la solicitud del usuario y el usuario recibe un mensaje de error, como error de inicio de sesión.
    
    Cuando esto sucede, el cliente se realiza tener en cuenta que se ve afectado el servicio y la condición de la clave de cliente tiene un estado incorrecto. Por ejemplo, si un cliente está utilizando una único DEP para todos los buzones de la organización, el cliente podría experimentar un error extendido donde los usuarios no pueden tener acceso a sus buzones de correo. Esto garantiza que, cuando las dos claves de cliente están mal Estados, el cliente se realiza tener en cuenta la necesidad de corregir la situación y restaurar el servicio en buen estado.
    
 **Uso de la clave de disponibilidad para acciones iniciadas por el código de servicio de Office 365.**
  
Código de Office 365 servicio siempre tiene un token de inicio de sesión válido y no se pueden bloquear. Por lo tanto, hasta que se ha eliminado la clave de disponibilidad, se puede usar para acciones iniciado por, o interna, de código de servicio de Office 365, como la creación de índices de búsqueda o mover los buzones de correo.
  
 **Usar la clave de disponibilidad para recuperar de pérdida de claves.**
  
Puede usar la clave de disponibilidad para recuperarse de la pérdida de ambas claves de cámara de Azure clave asociadas con el misma DEP, tal como se describe en la respuesta a la entrada de preguntas más frecuentes "si Mis claves se eliminan, ¿cómo puedo recuperar?".
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>¿Cómo se usa la clave de disponibilidad con SharePoint Online y OneDrive para la empresa?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

El SharePoint Online y OneDrive para la arquitectura de negocio e implementación para la clave de la clave del cliente y la disponibilidad son diferentes de Exchange Online y Skype para la empresa.
  
Cuando un cliente se mueve a las claves de cliente administrado, Office 365 crea una clave de nivel intermedia específica de inquilinos (TIK). Office 365 cifra la TIK dos veces, una vez con cada una de las claves de cliente y almacena las dos versiones cifradas de la TIK. Se almacenan solo las versiones cifradas de la TIK y un TIK sólo se puede descifrar con las claves de cliente. El TIK, a continuación, se usa para cifrar las claves de sitio, que, a continuación, se usan para cifrar las claves de blob. Los blobs ellos mismos se cifra y almacena en el servicio de almacenamiento de información de Microsoft Azure Blob.
  
Office 365 sigue este proceso para obtener acceso a un objeto binario que tiene datos de archivo de cliente:
  
1. Descifrar la TIK con la clave de cliente.
    
2. Utilice la TIK descifrado para descifrar una clave de sitio.
    
3. Utilice la clave del sitio descifrado para descifrar una clave de blob.
    
4. Utilice la clave de descifrado blob para descifrar el blob.
    
Al descifrar una TIK, Office 365 emite dos solicitudes de descifrado a Azure clave cámara con un desplazamiento ligero. El primero de ellos a fin proporciona el resultado, cancelar la solicitud de otra.
  
En caso de que el cliente pierde el acceso a sus claves de cliente, Office 365 También cifra la TIK con una clave de disponibilidad y se almacena junto con la TIKs cifradas con la clave de cada cliente. La TIK cifrada con la clave de disponibilidad sólo se utiliza cuando el cliente llama a Microsoft para dar de alta la ruta de acceso de recuperación cuando han perdido acceso a sus claves, accidental o malintencionado.
  
Por motivos de escalabilidad y disponibilidad, TIKs descifrados se almacenan en caché en una caché de memoria de tiempo limitado. Dos horas antes de que se establezca una memoria caché TIK a punto de caducar, Office 365 intenta descifrar cada TIK. Descifrar el TIKs extiende la duración de la memoria caché. Si se produce un error en el descifrado de TIK para una cantidad considerable de tiempo, Office 365 genera una alerta para notificar a ingeniería antes de la expiración de la memoria caché. Sólo si el cliente llama a Microsoft Office 365 iniciará la operación de recuperación, lo que implica descifrar de que la TIK con la clave de disponibilidad almacena en la tienda secreta y la incorporación del inquilino nuevo mediante el descifrado de Microsoft TIK y un nuevo conjunto claves de Azure clave cámara proporcionada por el cliente.
  
A partir de hoy, clave de cliente está implicado en la cadena de cifrado y descifrado de datos de archivo SharePoint Online almacenados en el almacén de blobs de Azure, pero no elementos de lista de SharePoint Online o metadatos almacenados en la base de datos SQL. Office 365 no usa la clave disponibilidad para SharePoint Online o OneDrive para la empresa que no sea el caso en que se ha descrito anteriormente, que se inicia el cliente. Humano acceso a los datos de cliente está protegido por la caja de seguridad del cliente.
  
## <a name="how-is-customer-key-licensed"></a>¿Cómo se licencia clave de cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Clave de cliente está disponible en el conjunto de aplicaciones de empresa de Office 365, "E5" y las SKU de cumplimiento de normas avanzadas. Además, los clientes también deben adquirir la licencia apropiada para el uso de cámara de clave de Azure.
  
Cada usuario al sacar provecho de clave de cliente debe tener licencia si desean que debe estar cubierto por clave de cliente.
  
Para SharePoint Online, el Administrador de Office 365 que configura la clave de cliente también necesita la licencia, para llevar a cabo los pasos del programa de instalación. Además, los usuarios que se benefician de la característica deben contar con licencia: Esto incluye el propietario del sitio y a los usuarios obtener acceso a archivos en uno o más sitios que se cifran mediante la clave del cliente. No es necesario que los usuarios externos se concede bajo licencia para tener acceso a los archivos en uno o más sitios que se cifran mediante la clave del cliente.
  
Para Exchange Online, debe tener licencia buzones "user" y "usuario de correo". Todos los demás, como buzones compartidos, no están necesario tener una licencia para la clave de cliente. Para comprobar que el buzón de Exchange Online es una licencia correctamente, ejecute el siguiente cmdlet:
  
```
(Get-Mailbox <alias >).PersistedCapabilities
```

Si existe la cadena BPOS_S_EquivioAnalytics, a continuación, el buzón de correo está correctamente con licencia. En caso contrario, se debe aplicar la licencia adecuada para poder usar la característica de clave de cliente para este buzón de correo.
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>¿Se puede habilitar la clave del cliente para una suscripción de prueba?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. Por definición, las suscripciones de prueba tienen una duración limitada. Las claves de cifrado que se hospedan en las suscripciones de prueba pueden perderse al final de la duración de la prueba. Debido a que Microsoft no se puede y no impide que los clientes poner los datos de cliente importantes en las suscripciones de prueba, se prohíbe el uso de la clave del cliente con suscripciones de prueba.
  
## <a name="how-much-will-using-customer-key-cost"></a>¿Cuánto va a usar clave de cliente costo?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Además de la administración de licencias necesarios para la clave de cliente, los clientes se incurrir en un costo para el uso de cámara de clave. [Detalles de los precios de Azure clave cámara](https://azure.microsoft.com/en-us/pricing/details/key-vault/) se describe el modelo de costo y le ayudarán a calcular. No hay ninguna forma para predecir el costo exacto que cualquier cliente incurrirá debido a que los patrones de uso pueden variar. La experiencia ha demostrado que el costo es muy bajo y que generalmente se encuentra dentro del intervalo de $0.002 a 0,005 $ por usuario al mes más el costo de las claves con respaldo de HSM. El costo también varían según la configuración del registro elegida por el cliente y la cantidad de almacenamiento de Azure usado para los registros del depósito de clave de Azure. 
  
## <a name="for-more-information"></a>Para obtener más información
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Para empezar con la clave de cliente, vea [controlar los datos de uso de la clave del cliente de Office 365](controlling-your-data-using-customer-key.md).
  

