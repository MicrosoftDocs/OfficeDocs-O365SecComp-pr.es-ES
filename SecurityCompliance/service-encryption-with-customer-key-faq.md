---
title: Preguntas más frecuentes sobre el cifrado de servicio con la clave de cliente para Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: Además de la línea base, el cifrado de nivel de volumen que se habilita a través de BitLocker y el administrador de claves distribuidas (DKM), Office 365 ofrece una capa agregada de cifrado a nivel de aplicación para el contenido del cliente en Office 365, incluidos los datos de Exchange En línea, Skype empresarial, SharePoint Online y OneDrive para la empresa. Esto se denomina cifrado de servicio.
ms.openlocfilehash: 5e1acca69ccdd8acb986acb4d7a302d4ca3fbe8a
ms.sourcegitcommit: 8a65a29aa3bfe5dcad0ff152a7cd795e02877dd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2019
ms.locfileid: "30936770"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>Preguntas más frecuentes sobre el cifrado de servicio con la clave de cliente para Office 365

Además de la línea base, el cifrado de nivel de volumen que se habilita a través de BitLocker y el administrador de claves distribuidas (DKM), Office 365 ofrece una capa agregada de cifrado a nivel de aplicación para el contenido del cliente en Office 365, incluidos los datos de Exchange En línea, Skype empresarial, SharePoint Online y OneDrive para la empresa. Esto se denomina cifrado de servicio.
  
La clave de cliente se basa en el cifrado del servicio y le permite proporcionar y controlar las claves que se usan para cifrar los datos en reposo en Office 365, tal como se describe en los [términos de servicios en línea (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx). La clave de cliente le ayuda a llevar a cabo sus obligaciones de cumplimiento, ya que es usted quien controla las claves de cifrado que Office 365 usa para descifrar datos.
  
Para proporcionar comentarios sobre la clave de cliente, incluida la documentación, envíe sus ideas, sugerencias y perspectivas a customerkeyfeedback@microsoft.com.
  
## <a name="what-is-service-encryption-with-customer-key"></a>¿Qué es el cifrado de servicio con la clave de cliente?

La clave de cliente mejora la capacidad de su organización para satisfacer las demandas de los requisitos de cumplimiento que especifican la disposición clave con el proveedor de servicios en la nube. Con la clave de cliente, usted proporciona y controla las claves de cifrado para los datos de Office 365 en reposo en el nivel de la aplicación. Como resultado, puede ejercer el control y revocación de las claves de la organización, en caso de que decida salir del servicio. Al revocar las claves, los datos no se leen en el servicio. La revocación clave es el primer paso en la ruta hacia la eliminación de datos.

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>¿Qué datos de Office 365 en reposo están cubiertos por la clave de cliente?
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

Se cubren el contenido del sitio de SharePoint Online y los archivos almacenados en ese sitio y los archivos cargados en OneDrive para la empresa. El contenido del buzón de Exchange Online (cuerpo del correo electrónico, entradas del calendario y contenido de los datos adjuntos del correo electrónico) está cubierto. Las conversaciones de texto de Skype empresarial están cubiertas, pero las grabaciones de difusión de reunión de Skype y las cargas de contenido de reunión de Skype no están cubiertas. La difusión de reunión de Skype y las cargas de contenido de reunión de Skype se cifran junto con el resto del contenido de Office 365, pero actualmente no ofrecemos el control del cliente de las claves de cifrado.
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>¿Cuál es la diferencia entre la clave de cliente y su propia clave (BYOK) con Azure Information Protection para Exchange Online?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Ambas opciones permiten proporcionar y controlar sus propias claves de cifrado; sin embargo, el cifrado de servicios con clave de cliente cifra los datos en reposo, que residen en los servidores de Office 365 en reposo, mientras que BYOK con Azure Information Protection para Exchange Online cifra los datos en tránsito y proporciona un servicio en línea y sin conexión persistente protección de mensajes de correo electrónico y datos adjuntos de Office 365. La clave de cliente y BYOK con Azure Information Protection para Exchange online son complementarias y, si decide usar las claves administradas por servicios de Microsoft o sus propias claves, el cifrado de los datos en reposo y en tránsito puede proporcionar una protección adicional de ataques malintencionados.
  
BYOK con Azure Information Protection para Exchange Online se ofrece en las capacidades de cifrado de mensajes de Office 365.
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>¿El cifrado de mensajes de Office 365 y ofrece su propia clave con Azure Information Protection cambian el enfoque de Microsoft a las solicitudes de datos de terceros, como las citacións?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. El cifrado de mensajes de Office 365 y la opción de proporcionar y controlar sus propias claves de cifrado con la opción de traer su propia clave (BYOK) para Azure Information Protection (AIP) no se diseñó para responder a las inFormaciones de cumplimiento de la ley. El cifrado de mensajes de Office 365 con BYOK para AIP se diseñó para clientes centrados en el cumplimiento que necesitan cumplir sus obligaciones de cumplimiento interno o externo. Microsoft realiza muy en serio solicitudes de terceros para los datos de los clientes. Como proveedor de servicios en la nube, siempre proponemos la privacidad de los datos de clientes. En el caso de que recibamos una citación, siempre intentaremos redirigir a la tercera parte al cliente para obtener la información. (Lea el blog de Brad Martínez: [proteger los datos de clientes de la supervisión gubernamental](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Se publicará periódicamente información detallada de la solicitud que recibimos [aquí](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data).
  
Consulte el [centro de confianza de Microsoft](https://www.microsoft.com/en-us/trustcenter/default.aspx) sobre las solicitudes de datos de terceros y la "revelación de datos de clientes" en los [términos de servicios en línea (OST) ](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)para obtener más información.
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>¿El servicio de cifrado con clave de cliente cambia el enfoque de Microsoft a las solicitudes de datos de terceros, como las citacións?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. La clave de cliente no se diseñó para responder a las inlas citacións legales. Se diseñó para los clientes regulados para cumplir con las obligaciones de cumplimiento interno o externo. Microsoft realiza muy en serio solicitudes de terceros para los datos de los clientes. Como proveedor de servicios en la nube, siempre proponemos la privacidad de los datos de clientes. En el caso de que recibamos una citación, siempre intentaremos redirigir a la tercera parte al cliente para obtener la información. (Lea el blog de Brad Martínez: [proteger los datos de clientes de la supervisión gubernamental](http://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Se publicará periódicamente información detallada de la solicitud que recibimos [aquí](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data).
  
Consulte el [centro de confianza de Microsoft](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data) sobre las solicitudes de datos de terceros y la "revelación de datos de clientes" en los [términos de servicios en línea (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx) para obtener más información. 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>¿Se encuentra disponible la compatibilidad de FastTrack para implementar la clave de cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. FastTrack solo se usa para recopilar información de configuración del servicio y del espacio empresarial que se requiere para registrarse en la clave de cliente. Las ofertas de clave de cliente se publican a través de FastTrack para que sea conveniente para los clientes y socios enviar la información necesaria con el mismo método y para facilitar el archivado de los datos que los clientes proporcionan en la oferta.
  
Si necesita más información sobre la documentación, póngase en contacto con los servicios de consultoría de Microsoft (MCS), el servicio de ingeniería de campo (PFE) de Premier o un socio de Microsoft para obtener ayuda.
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>Si se destruyen las claves, ¿cómo se puede recuperar?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

La clave de disponibilidad le proporciona la capacidad de recuperarse de la pérdida imprevista de las claves raíz que administra. Si pierde las claves raíz, póngase en contacto con el soporte técnico de Microsoft y Microsoft le ayudará en el proceso de habilitar la clave de disponibilidad. Usará la clave de disponibilidad para migrar a una nueva Directiva de cifrado de datos con nuevas claves suministradas por el usuario. 
  
## <a name="what-is-the-availability-key"></a>¿Qué es la clave de disponibilidad?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

La clave de disponibilidad es una clave raíz que se aprovisiona al crear una directiva de cifrado de datos. La clave de disponibilidad se almacena y se protege en Office 365 y es funcionalmente similar a las dos claves raíz que proporciona el usuario para el cifrado de servicio con la clave de cliente. A diferencia de las claves que se proporcionan y se administran en Azure Key Vault, no se puede tener acceso directamente a la clave Availability. El almacenamiento y el control de la clave de disponibilidad son intencionalmente diferentes de las claves de Azure Key Vault por tres motivos: en primer lugar, la clave de disponibilidad proporciona una capacidad de alta disponibilidad en caso de que los servicios de Office 365 no puedan comunicarse con claves hospedadas en la clave de Azure. Almacén en segundo lugar, la clave de disponibilidad proporciona una función de "interrupción de la luna" en el caso de que se pierdan las claves de Azure Key Vault; y en tercer lugar, la separación de los controles lógicos proporciona una defensa en profundidad y protege contra la pérdida de todas las claves de un único ataque o punto de error. Compartir la responsabilidad para proteger las claves, a la vez que se usan varias protecciones y procesos para la administración de claves, reduce el riesgo de que se pierdan o destruyan todas las claves (y, por lo tanto, los datos). Microsoft proporciona autoridad exclusiva sobre la destrucción de la clave de disponibilidad. Por diseño, nadie en Microsoft tiene acceso a la clave de disponibilidad, solo es accesible para el código del servicio de Office 365.
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>¿Cuántas directivas de cifrado de datos (DEPs) puedo crear?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online y Skype empresarial:** Puede crear hasta 50 DEPs. 
  
 **SharePoint Online y OneDrive para la empresa:** Un DEP se aplica a los datos en una ubicación geográfica, también denominada geo. Si usa la característica multigeográfica de Office 365, puede crear un DEP por geo. Si no usa la función multigeográfica, puede crear un DEP.
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>¿Puedo asignar una directiva de cifrado de datos antes de migrar un buzón de correo a la nube?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Sí. Puede usar el cmdlet Set-MailUser de Windows PowerShell para asignar una directiva de cifrado de datos (DEP) al usuario antes de migrar el buzón a Office 365. Al hacerlo, el contenido del buzón se cifrará con el DEP asignado cuando se migre el contenido. Esto puede resultar más eficaz que asignar una DEP después de que ya se haya migrado el buzón de correo y, a continuación, esperar a que se produzca el cifrado, lo que puede tardar horas o posiblemente días. 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>¿Cómo puedo comprobar que el cifrado con la clave de cliente está activado y que Office 365 ha terminado de cifrarse con la clave de cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online y Skype empresarial:** Puede [conectarse a Exchange online mediante PowerShell remoto](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) y, a continuación, usar el cmdlet **[get-MailboxStatistics]** para cada buzón que desee comprobar. En el resultado del cmdlet Get-MailboxStatistics, la propiedad _IsEncrypted_ devuelve un valor **true** si el buzón está cifrado y el valor **false** si no lo está. Si el buzón está cifrado, el valor devuelto para la propiedad _DataEncryptionPolicyID_ es el GUID de la DEP con la que se cifra el buzón. Para obtener más información sobre cómo ejecutar este cmdlet, vea [Get-MailboxStatistics](https://technet.microsoft.com/en-us/library/bb124612%28v=exchg.160%29.aspx) y Using PowerShell with Exchange Online. 
  
Si los buzones no se cifran después de esperar 72 horas desde el momento en que se asignó la DEP, inicie un movimiento de buzón. Para ello, [Conéctese a Exchange online mediante PowerShell remoto](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) y, a continuación, use el cmdlet New-MoveRequest y proporcione el alias del buzón de la siguiente manera: 
  
```
New-MoveRequest <alias>
```

 **SharePoint Online y OneDrive para la empresa:** Puede [conectarse a PowerShell de SharePoint Online](https://technet.microsoft.com/en-us/library/fp161372.aspx)y, a continuación, usar el cmdlet **[get-SPODataEncryptionPolicy]** para comprobar el estado del espacio empresarial. La propiedad * * _State_* * devuelve un valor de **registrado** si el cifrado de clave de cliente está habilitado y todos los archivos de todos los sitios se han cifrado. Si el cifrado todavía está en curso, este cmdlet proporciona información sobre el porcentaje de sitios que se ha completado. 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>Si quiero cambiar a un conjunto de claves diferente, ¿cuánto tiempo necesita el nuevo conjunto de claves para proteger mis datos?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online y Skype empresarial:** Puede tardar hasta 72 horas en proteger un buzón de correo de acuerdo con una nueva Directiva de cifrado de datos (DEP) desde el momento en que se asigna el nuevo DEP al buzón. 
  
 **SharePoint Online y OneDrive para la empresa:** Puede tardar hasta cuatro horas en volver a cifrar todo el inquilino una vez que se haya asignado una nueva clave. 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>¿Mis datos existentes se almacenan sin cifrado en cualquier momento mientras se descifran o cifran con la clave de cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. Los datos siempre se cifran en reposo en el servicio de Office 365 con BitLocker y DKM. Para obtener más información, consulte la información de seguridad, privacidad y cumplimiento de Office 365, y [Cómo Exchange Online protege sus secretos de correo electrónico](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376).
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>Si ya no deseo usar claves de cifrado administradas por el cliente, ¿puedo cambiar a claves administradas por Microsoft?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online y Skype empresarial:** Aún no. Esto será compatible una vez que el cifrado de servicios en Office 365 con claves administradas por Microsoft se implemente en general. Esperamos realizar esta implementación en el servicio después de liberar el cifrado del servicio con la clave de cliente. 
  
 **SharePoint Online y OneDrive para la empresa:** Afirma. Puede optar por volver a usar claves administradas por Microsoft por separado para cada geográfico (si usa la característica multigeográfico) o para todos sus datos si se encuentra en una sola geo. 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>Si pierdo las claves, ¿cuánto tiempo se tarda en recuperar la disponibilidad del servicio con la clave de recuperación?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online y Skype empresarial:** Una vez que llame para usar la clave de disponibilidad, se podrá tener acceso a los buzones en minutos. 
  
 **SharePoint Online y OneDrive para la empresa:** Esta operación es proporcional al número de sitios que tiene. Una vez que llame a Microsoft para usar la clave de disponibilidad, tendrá una conexión completa en unas cuatro horas. 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>¿Cómo se usa la clave de disponibilidad con Exchange Online?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Hay tres formas de usar la clave Availability con Exchange Online:
  
- Disponibilidad del servicio: en el caso de que no se pueda tener acceso a las claves de Azure Key Vault.
    
- Acciones iniciadas por el código del servicio de Office 365, como la creación de índice de búsqueda o los movimientos de buzones.
    
- Recuperación de pérdida de clave, como la pérdida de claves de Azure Key Vault asociadas con una única DEP.
    
 **Usar la clave de disponibilidad para la disponibilidad del servicio en las claves del almacén de claves de Azure del evento son inalcanzables.**
  
Office 365 usa la clave de disponibilidad tanto para la disponibilidad de servicios como para la recuperación de un estado de clave de cliente incorrecto para Exchange Online. Hay una jerarquía de claves usada por la clave de cliente. Esta jerarquía se muestra en la ilustración siguiente.
  
![](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
Si las claves de Azure Key Vault de una única directiva de cifrado de datos (DEP) no están disponibles, Office 365 puede usar la clave de disponibilidad para cambiar a una nueva DEP. Office 365 determina si se debe usar la clave de disponibilidad para la disponibilidad del servicio de forma diferente en función de si una actividad iniciada por el usuario, por ejemplo, cuando un usuario descarga el correo electrónico al cliente de Outlook o una actividad iniciada por el sistema, como la indización contenido del buzón de correo o para búsquedas de eDiscovery, ha desencadenado el proceso.
  
Office 365 sigue este proceso como respuesta a acciones iniciadas por el usuario para determinar si se va a usar la clave de disponibilidad para los buzones de usuario:
  
1. Office 365 lee la DEP a la que está asignado el buzón para determinar la ubicación de las dos claves de cliente en Azure Key Vault.
    
2. Office 365 elige aleatoriamente una de las dos claves de cliente de la DEP y envía una solicitud a Azure Key Vault para desajustar la clave de DEP mediante la clave de cliente.
    
3. Si la solicitud para desencapsular la clave de DEP mediante la clave de cliente da error y devuelve un error, Office 365 envía una segunda solicitud a Azure Key Vault, esta vez le indica que use la clave de cliente alternativa (segundo).
    
4. Si la segunda solicitud para desajustar la clave de DEP mediante la clave de cliente produce un error y devuelve un error, Office 365 examina los resultados de ambas solicitudes:
    
  - Si el examen determina que los errores no reflejan una acción explícita por parte de la identidad de un cliente, Office 365 usa la clave de disponibilidad para descifrar la clave DEP. A continuación, se usa la clave DEP para descifrar la clave de buzón y completar la solicitud del usuario.
    
    En este caso, Azure Key Vault no puede responder o no ser accesible por cualquier motivo. Office 365 no tiene forma de determinar si el cliente ha revocado intencionadamente el acceso a las claves.
    
  - Si el examen indica que se ha realizado una acción deliberada para representar que las claves del cliente no están disponibles, no se usará la clave de disponibilidad, se producirá un error en la solicitud del usuario y el usuario recibirá un mensaje de error, como un error de inicio de sesión.
    
    Cuando esto ocurre, el cliente tiene constancia de que el servicio se ve afectado y la condición de la clave del cliente está en mal estado. Por ejemplo, si un cliente usa un DEP único para todos los buzones de la organización, el cliente puede experimentar un error generalizado en el que los usuarios no pueden tener acceso a sus buzones. Esto garantiza que, cuando ambas claves del cliente sean incorrectos, el cliente tiene constancia de la necesidad de corregir la situación y restaurar el servicio a un estado correcto.
    
 **Uso de la clave de disponibilidad para acciones iniciadas por el código de servicio de Office 365.**
  
El código de servicio de Office 365 siempre tiene un token de inicio de sesión válido y no se puede bloquear. Por lo tanto, hasta que se haya eliminado la clave de disponibilidad, puede usarse para las acciones iniciadas por el código de servicio de Office 365, o de forma interna, como la creación de índice de búsqueda o el movimiento de buzones.
  
 **Uso de la clave de disponibilidad para recuperarse de la pérdida de claves.**
  
Puede usar la clave Availability para recuperar a partir de la pérdida de claves de Azure Key Vault asociadas con el mismo DEP, tal y como se describe en la respuesta a la entrada de preguntas más frecuentes "si mis claves se destruyen, ¿cómo se puede recuperar?".
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>¿Cómo se usa la clave de disponibilidad con SharePoint Online y OneDrive para la empresa?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

La arquitectura y la implementación de SharePoint Online y OneDrive para la empresa para la clave de cliente y la clave de disponibilidad son diferentes de Exchange Online y Skype empresarial.
  
Cuando un cliente se mueve a claves administradas por el cliente, Office 365 crea una clave intermedia específica del espacio empresarial (TIK). Office 365 cifra el TIK dos veces, una vez con cada una de las claves de cliente y almacena las dos versiones cifradas de TIK. Solo se almacenan las versiones cifradas de TIK y un TIK solo se puede descifrar con las claves de cliente. A continuación, el TIK se usa para cifrar las claves del sitio, que se usan para cifrar las claves BLOB. Los blobs en sí se cifran y almacenan en el servicio de almacenamiento de blobs de Microsoft Azure.
  
Office 365 sigue este proceso para acceder a un BLOB que tiene datos de archivos de clientes:
  
1. DesCifre la TIK con la clave de cliente.
    
2. Use la TIK descifrada para descifrar una clave de sitio.
    
3. Use la clave de sitio descifrada para descifrar una clave BLOB.
    
4. Use la clave BLOB descifrada para descifrar el BLOB.
    
Al descifrar un TIK, Office 365 emite dos solicitudes de descifrado a Azure Key Vault con un ligero desplazamiento. La primera para finalizar ofrece el resultado, cancelando la otra solicitud.
  
En caso de que el cliente pierda el acceso a las claves de los clientes, Office 365 también cifra el TIK con una clave de disponibilidad y lo almacena junto con el TIKs cifrado con cada clave de cliente. La TIK cifrada con la clave de disponibilidad solo se usa cuando el cliente llama a Microsoft para dar de alta la ruta de recuperación cuando ha perdido el acceso a sus claves, de forma malintencionada o accidental.
  
Por motivos de disponibilidad y escala, los TIKs descifrados se almacenan en caché en una memoria caché de memoria de tiempo limitado. Dos horas antes de que se establezca la expiración de la memoria caché de TIK, Office 365 intenta descifrar cada TIK. El descifrado de TIKs amplía la duración de la memoria caché. Si se produce un error en el descifrado de TIK durante un período de tiempo significativo, Office 365 genera una alerta para notificar Ingeniería antes de la expiración de la caché. Solo si el cliente llama a Microsoft Office 365 iniciar la operación de recuperación, lo que implica descifrar TIK con la clave de disponibilidad almacenada en el almacén de secretos de Microsoft y volver a incorporar el inquilino mediante el TIK descifrado y un nuevo conjunto de claves de almacén de claves de Azure suministradas por el cliente.
  
A partir de hoy, la clave de cliente está involucrada en la cadena de cifrado y descifrado de los datos de archivo de SharePoint Online almacenados en el almacén de blobs de Azure, pero no en los elementos de lista o metadatos de SharePoint Online almacenados en la base de datos SQL. Office 365 no usa la clave de disponibilidad para SharePoint Online o OneDrive para la empresa distinta del caso descrito anteriormente, que se inicia en el cliente. El acceso humano a los datos de los clientes está protegido por las cajas de caja del cliente.
  
## <a name="how-is-customer-key-licensed"></a>¿Cómo se concede la licencia de la clave de cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

La clave de cliente se ofrece en el conjunto de aplicaciones Office 365 Enterprise, "E5" y la SKU de cumplimiento avanzado. Además, los clientes también deben adquirir la licencia adecuada para usar Azure Key Vault.
  
Cada usuario que se beneficie de la clave de cliente debe tener una licencia si desea ser cubierta por la clave de cliente.
  
Para SharePoint Online, el Office 365 administrador que configura la clave de cliente también debe tener una licencia para poder realizar los pasos de configuración. Además, los usuarios que se benefician de la característica deben tener licencia: Esto incluye el propietario del sitio y los usuarios que tienen acceso a los archivos de uno o varios sitios que se cifran mediante la clave de cliente. No es necesario que los usuarios externos tengan licencia para acceder a los archivos de uno o varios sitios que se cifran mediante la clave de cliente.
  
Para Exchange Online, los buzones "usuario" y "usuario de correo" deben tener una licencia. Los demás, como los buzones compartidos, no necesitan tener una licencia para la clave de cliente. Para comprobar que el buzón de correo de Exchange Online tiene una licencia correcta, ejecute el siguiente cmdlet:
  
```
(Get-Mailbox <alias >).PersistedCapabilities
```

Si la cadena BPOS_S_EquivioAnalytics existe, entonces el buzón tiene una licencia adecuada. Si no es así, debe aplicar la licencia adecuada para poder usar la característica de clave de cliente para este buzón.
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>¿Puedo habilitar la clave de cliente para una suscripción de prueba?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

No. Por definición, las suscripciones de prueba tienen una duración limitada. Las claves de cifrado que se hospedan en suscripciones de prueba se pueden perder al final de la duración de la prueba. Como Microsoft no impide que los clientes coloquen datos importantes de clientes en suscripciones de prueba, se prohíbe el uso de la clave de cliente con suscripciones de prueba.
  
## <a name="how-much-will-using-customer-key-cost"></a>¿Cuánto va a usar el costo de clave de cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Además de las licencias necesarias para la clave de cliente, los clientes incurrirán en un costo por el uso de la bóveda de claves. [Detalles de precios de Azure Key Vault](https://azure.microsoft.com/en-us/pricing/details/key-vault/) describe el modelo de costos y le ayudará a realizar la estimación. No hay ninguna forma de predecir el coste exacto que incurrir a ningún cliente, ya que los patrones de uso varían. La experiencia ha demostrado que el costo es muy bajo y generalmente cae en el intervalo de $0,002 a $0,005 por usuario al mes, además del costo de las claves respaldadas por HSM. El costo también variará en función de la configuración de registro elegida por el cliente y la cantidad de almacenamiento de Azure usado para los registros de Azure Key Vault. 
  
## <a name="for-more-information"></a>Para obtener más información
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Para empezar con la clave de cliente, vea [controlar los datos en Office 365 mediante la clave de cliente](controlling-your-data-using-customer-key.md).
  

