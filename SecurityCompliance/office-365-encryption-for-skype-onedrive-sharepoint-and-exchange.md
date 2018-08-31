---
title: Cifrado de Office 365 para Skype, OneDrive, SharePoint y Exchange
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Una descripción del cifrado de Skype, OneDrive, SharePoint y Exchange Online.'
ms.openlocfilehash: 5b839b8d290306f2334d3ca3278d0d5dac20a56f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536208"
---
# <a name="office-365-encryption-for-skype-for-business-onedrive-for-business-sharepoint-online-and-exchange-online"></a>Cifrado de Office 365 para Skype para la empresa, OneDrive para la empresa, SharePoint Online y Exchange Online

Office 365 es un entorno de alta seguridad que ofrece una amplia protección en varios niveles: seguridad, seguridad de red, seguridad de acceso, seguridad de aplicaciones y seguridad de los datos del centro de datos físicos.

## <a name="skype-for-business"></a>Skype Empresarial
Skype para datos de los clientes empresariales puede almacenarse en reposo con el formato de archivos o presentaciones que se cargan por los participantes de la reunión. El servidor de conferencia Web cifra los datos de cliente mediante AES con una clave de 256 bits. Los datos del cliente cifrada se almacenan en un recurso compartido de archivos. Cada unidad de datos del cliente se cifra mediante una clave de 256 bits generada de forma aleatoria diferente. Cuando se comparte un fragmento de datos de cliente en una conferencia, el servidor de conferencia Web indica a los clientes de conferencia para descargar los datos del cliente cifradas a través de HTTPS. Envía la clave correspondiente a los clientes de modo que se pueden descifrar los datos del cliente. El servidor de conferencia Web también autentica a los clientes de conferencia antes de que permite a los clientes de acceso a datos de clientes de conferencia. Al unirse a una conferencia Web, cada cliente de conferencia establece un cuadro de diálogo SIP con el componente de enfoque de conferencias ejecutando dentro del servidor front-end a través de TLS en primer lugar. El enfoque de conferencia pasa al cliente de conferencia una cookie de autenticación generada por el servidor de conferencia Web. El cliente de conferencia, a continuación, se conecta al servidor de conferencia Web que presenta la cookie de autenticación para autenticar con el servidor.

## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online y OneDrive para la Empresa
Todos los archivos de cliente de SharePoint Online se protegen mediante claves por archivo único, que siempre son exclusivas de un inquilino único. Las claves se creado y administrado por el servicio en línea de SharePoint o cuando se usa la clave de cliente, creado y administrado por los clientes. Cuando se carga un archivo, el cifrado se realiza por SharePoint Online dentro del contexto de la solicitud de carga, antes de enviarse al almacenamiento de Azure. Cuando se descarga un archivo, SharePoint Online recupera al cliente cifrado datos desde el almacenamiento de Azure según el identificador único de documento y descifra los datos del cliente antes de enviar al usuario. Almacenamiento de Azure no tiene capacidad para descifrar, o incluso identificar o comprender los datos del cliente. Todo el cifrado y descifrado que suceda en los mismos sistemas que exigir la aplicación de aislamiento de inquilinos, que son Azure Active Directory y SharePoint Online.

Varias cargas de trabajo en Office 365 almacenan datos en SharePoint Online, incluidos Microsoft Teams, que almacena todos los archivos en SharePoint Online y OneDrive para la empresa, que usa SharePoint Online para su almacenamiento. Todos los datos del cliente almacenados en SharePoint Online se cifra (con una o más claves AES de 256 bits) y distribuidos en el centro de datos de la siguiente manera. (Cada paso de este proceso de cifrado es FIPS 140-2 nivel 2 validado. Para obtener información adicional acerca de la compatibilidad con FIPS 140-2, vea [cumplimiento de FIPS 140-2](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105))).
- Cada archivo se divide en fragmentos de uno o más, según el tamaño de archivo. Cada fragmento se cifra con su propia clave AES de 256 bits único.
- Cuando se actualiza un archivo, la actualización se administra de la misma manera: el cambio se divide en uno o más fragmentos, y cada fragmento se cifra con una clave única independiente.
- Estos fragmentos – archivos, fragmentos de archivos y diferencias de actualización – se almacenan como blobs en almacenamiento de Azure a los que se distribuyen de forma aleatoria a través de varias cuentas de almacenamiento de Azure. 
- El conjunto de claves de cifrado para estos fragmentos de datos de cliente está cifrada.
   - Las teclas usadas para cifrar los blobs se almacenan en la base de datos de contenido en línea de SharePoint.
   - La base de datos de contenido está protegido por acceso a controles de base de datos y el cifrado en reposo. Cifrado se lleva a cabo mediante el [Cifrado de datos transparente](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-tde) (TDE) en la [Base de datos de SQL Azure](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview). (Base de datos de SQL azure es un servicio de base de datos relacional de propósito general de Microsoft Azure que admite estructuras como datos relacionales, JSON, espacial y XML). Estos secretos están en el nivel de servicio de SharePoint Online, no en el nivel de inquilino. Estos secretos (a veces denominados como las claves maestras) se almacenan en un repositorio seguro independiente denominado el almacén de claves. TDE proporciona seguridad en reposo para la base de datos activa y las copias de seguridad de base de datos y los registros de transacciones. 
   - Cuando los clientes proporcionan la clave opcional, la clave del cliente se almacena en Azure clave de cámara y el servicio usa la clave para cifrar una clave de inquilino, que se usa para cifrar una clave de sitio, que, a continuación, se usa para cifrar las claves de nivel de archivo. Básicamente, se presenta una jerarquía de claves de nuevo cuando el cliente proporciona una clave.
- El mapa se usa para volver a ensamblar el archivo se almacena en la base de datos de contenido junto con las claves cifradas, independientemente de la clave maestra necesaria para descifrar los archivos.
- Cada cuenta de almacenamiento de Azure tiene sus propias credenciales únicos por tipo de acceso (lectura, escritura, enumerar y eliminar). Cada conjunto de credenciales se encuentra en el almacén de clave segura y se actualiza con regularidad. Como se describió anteriormente, hay tres tipos diferentes de almacenes, cada uno con una función distinta:
- Datos de cliente se almacenan como objetos BLOB cifrados en almacenamiento de Azure. La clave para cada fragmento de datos de clientes se cifra y se almacena por separado en la base de datos de contenido. Los datos del cliente no contiene ninguna pista acerca de cómo se puede descifrar.
- La base de datos de contenido es una base de datos de SQL Server. Contiene el mapa de necesario para localizar y volver a montar el BLOB de datos de cliente se conserva en el almacenamiento de Azure, así como las claves necesarias para cifrar los blobs. Sin embargo, el conjunto de claves es en sí mismo cifrado (como se explicó anteriormente) y se conserva en un almacén independiente de la clave.
- El almacén de clave es físicamente independiente del almacenamiento de base de datos de contenido y de Azure. Contiene las credenciales para cada contenedor de almacenamiento de Azure y la clave maestra para el conjunto de claves cifrados que se conserva en la base de datos de contenido.

Cada uno de estos tres componentes de almacenamiento de información: el almacén de blobs de Azure, la base de datos de contenido y el almacén de claves – es físicamente independiente. La información contenida en cualquiera de los componentes es no se puede usar en su propio. Sin acceso a las tres, es imposible recuperar las claves a los fragmentos, descifrar las claves para que se pueda utilizar, asociar las claves con sus correspondientes fragmentos, descifrar cada fragmento o reconstruir un documento desde sus fragmentos constituyentes.

Certificados de BitLocker, que protegen los volúmenes de disco físico en los equipos en el centro de datos, se almacenan en un repositorio seguro (el almacén de SharePoint Online secreto) que está protegido por la clave de la granja de servidores.

Las claves TDE que protección las claves por blob se almacenan en dos ubicaciones:
- El repositorio seguro, que alberga los certificados de BitLocker y está protegido por la clave de la granja de servidores; y
- En un repositorio seguro administrado por base de datos de SQL Azure.

También se conservan las credenciales usadas para tener acceso a los contenedores de almacenamiento de Azure en SharePoint Online secreto de almacenar y delegar en cada granja de servidores de SharePoint Online según sea necesario. Estas credenciales son las firmas SAS de almacenamiento de Azure, con independientes credenciales usadas para leer o escribir datos y con la directiva aplicada para que auto-caducan cada 60 días. Diferentes credenciales se usan para leer o escribir datos (no ambos) y granjas de servidores de SharePoint Online no se les deben conceder permisos para enumerar.

> Los clientes de nota para Office 365 gobierno de Estados Unidos, objetos binarios de datos se almacenan en almacenamiento de gobierno de Estados Unidos de Azure. Además, el acceso a las claves de SharePoint Online en el gobierno de Estados Unidos de Office 365 está limitado a Office 365 para el personal que evaluada específicamente. Personal de operaciones de gobierno de Estados Unidos Azure no tienen acceso a la tienda de SharePoint Online clave que se usa para cifrar los objetos binarios de datos.

Para obtener más información acerca del cifrado de datos en SharePoint Online y OneDrive para la empresa, consulte [Cifrado de datos en OneDrive para empresas y SharePoint Online](https://technet.microsoft.com/en-us/library/dn905447.aspx).

### <a name="list-items-in-sharepoint-online"></a>Elementos de lista de SharePoint Online
Elementos de lista son más pequeños fragmentos de datos que se crean ad-hoc o que pueden live más dinámicamente dentro de un sitio, como las filas de una lista creada por el usuario, las publicaciones individuales en un blog de SharePoint Online, o las entradas dentro de una página wiki de SharePoint Online de cliente. Elementos de lista se almacenan en la base de datos (base de datos de SQL Azure) y protegidos con TDE.

## <a name="encryption-of-data-in-transit"></a>Cifrado de datos en tránsito
En OneDrive para la Empresa y SharePoint Online, hay dos escenarios en los que los datos entran y salen de los centros de datos.
- La **comunicación del cliente con el servidor** - comunicación a OneDrive para la empresa a través de Internet utiliza las conexiones SSL/TLS. Todas las conexiones SSL se establecen mediante claves de 2048 bits.
- **Movimiento de datos entre centros de datos** - la razón principal para mover los datos entre centros de datos es para que la replicación geo habilitar la recuperación ante desastres. Por ejemplo, los registros de transacciones de SQL Server y las diferencias de almacenamiento de blobs de viajes a lo largo de esta canalización. Mientras estos datos ya se transmiten a través de una red privada, está aún más protegido con cifrado en su clase.


## <a name="exchange-online"></a>Exchange Online
Exchange Online usa BitLocker para todos los datos de buzón de correo, y se describe la configuración de BitLocker en [BitLocker para el cifrado](office-365-bitlocker-and-distributed-key-manager-for-encryption.md). El cifrado de nivel de servicio cifra todos los datos de buzón de correo en el nivel de buzón de correo. 

Además de cifrado de servicio, Office 365 admite la clave de cliente, que se fundamentan en servicio de cifrado. Clave de cliente es una opción de clave administrada por Microsoft para el cifrado de servicio Exchange Online que también está en la guía básica de Microsoft. Este método de cifrado proporciona mayor protección que no se consigue con BitLocker porque proporciona la separación de los administradores del servidor y las claves criptográficas necesarias para el descifrado de datos, y debido a que el cifrado se aplica directamente a los datos (de contraste con BitLocker, que se aplica el cifrado en el volumen de disco lógico) permanece cifrado cualquier dato del cliente copiada desde un servidor de Exchange.

El ámbito para el cifrado de servicio Exchange Online es datos de cliente que se almacenan en reposo dentro de Exchange Online. (Skype para la empresa almacena casi todo generados por el usuario el contenido de buzón de Exchange Online del usuario y, por tanto, hereda la característica de cifrado de servicio de Exchange Online.)
