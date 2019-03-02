---
title: Office 365 cifrado para Skype, OneDrive, SharePoint y Exchange
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 'Resumen: Descripción del cifrado para Skype, OneDrive, SharePoint y Exchange Online.'
ms.openlocfilehash: 55141f671e6cb3d7ea837bfcf9701e37a18fb7ba
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357571"
---
# <a name="office-365-encryption-for-skype-for-business-onedrive-for-business-sharepoint-online-and-exchange-online"></a>Office 365 cifrado para Skype empresarial, OneDrive para la empresa, SharePoint Online y Exchange Online

Office 365 es un entorno muy seguro que ofrece una amplia protección en varias capas: seguridad del centro de datos físico, seguridad de red, seguridad de acceso, seguridad de aplicaciones y seguridad de datos.

## <a name="skype-for-business"></a>Skype Empresarial

Los datos de clientes de Skype empresarial pueden almacenarse en reposo en forma de archivos o presentaciones cargados por los participantes en la reunión. El servidor de conferencia web cifra los datos del cliente mediante AES con una clave de 256 bits. Los datos de cliente cifrados se almacenan en un recurso compartido de archivos. Cada parte de los datos de clientes se cifra con una clave de 256 bits generada de forma aleatoria. Cuando una parte de los datos de clientes se comparte en una conferencia, el servidor de conferencia web indica a los clientes de conferencia que descarguen los datos de clientes cifrados a través de HTTPS. Envía la clave correspondiente a los clientes para que los datos del cliente se puedan descifrar. El servidor de conferencia web también autentica a los clientes de conferencia antes de que los clientes tengan acceso a los datos de clientes de conferencia. Al unirse a una conferencia Web, cada cliente de conferencia establece primero un cuadro de diálogo SIP con el componente de foco de conferencia que se ejecuta dentro del servidor front-end a través de TLS. El enfoque de conferencia pasa al cliente de conferencia una cookie de autenticación generada por el servidor de conferencia Web. A continuación, el cliente de conferencia se conecta al servidor de conferencia web que presenta la cookie de autenticación que el servidor debe autenticar.

## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online y OneDrive para la Empresa

Todos los archivos de clientes de SharePoint Online están protegidos por claves únicas por archivo que siempre son exclusivas para un único inquilino. Las claves las crea y administra el servicio de SharePoint Online, o cuando la clave de cliente la usan, crean y administran los clientes. Cuando se carga un archivo, SharePoint Online realiza el cifrado en el contexto de la solicitud de carga, antes de enviarlo a Azure Storage. Cuando se descarga un archivo, SharePoint Online recupera los datos cifrados del cliente desde Azure Storage en función del identificador de documento único y descifra los datos del cliente antes de enviarlos al usuario. Azure Storage no tiene la capacidad de descifrar, ni tampoco identificar o comprender los datos de los clientes. Todo el cifrado y el descifrado ocurren en los mismos sistemas que exigen el aislamiento de inquilinos, que son Azure Active Directory y SharePoint Online.

Varias cargas de trabajo en Office 365 almacenan datos en SharePoint Online, incluidos Microsoft Teams, que almacena todos los archivos en SharePoint Online y OneDrive para la empresa, que usa SharePoint Online para su almacenamiento. Todos los datos de clientes almacenados en SharePoint Online están cifrados (con una o varias claves de bits AES de 256) y se distribuyen en el centro de datos de la siguiente manera. (Cada paso de este proceso de cifrado es el nivel 2 de FIPS 140-2 validado. Para obtener información adicional acerca del cumplimiento de FIPS 140-2, consulte [fips 140-2 Compliance](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105)).

- Cada archivo se divide en uno o varios grupos, según el tamaño del archivo. Cada fragmento se cifra mediante su propia clave AES 256-bit exclusiva.
- Cuando se actualiza un archivo, la actualización se trata de la misma manera: el cambio se divide en uno o más fragmentos y cada fragmento se cifra con una clave única independiente.
- Estos fragmentos (archivos, fragmentos de archivos y deltas de actualización) se almacenan como blobs en el almacenamiento de Azure y se distribuyen de forma aleatoria en varias cuentas de almacenamiento de Azure.
- El conjunto de claves de cifrado para estos fragmentos de datos de clientes está cifrado.

    - Las claves usadas para cifrar los blobs se almacenan en la base de datos de contenido de SharePoint Online.
    - La base de datos de contenido está protegida por los controles de acceso a base de datos y el cifrado en reposo. El cifrado se realiza con cifrado de [datos transparente](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-tde) (TDE) en [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview). (Azure SQL Database es un servicio de base de datos relacional de propósito general de Microsoft Azure que admite estructuras como datos relacionales, JSON, espacial y XML). Estos secretos están en el nivel de servicio de SharePoint Online, no en el nivel de inquilino. Estos secretos (a veces denominados "claves maestras") se almacenan en un repositorio seguro independiente denominado almacén de claves. TDE proporciona seguridad en reposo para la base de datos activa y para las copias de seguridad de la base de datos y los registros de transacciones.
    - Cuando los clientes proporcionan la clave opcional, la clave de cliente se almacena en Azure Key Vault y el servicio usa la clave para cifrar una clave de inquilino, que se usa para cifrar una clave de sitio, que se usa para cifrar las claves de nivel de archivo. Básicamente, se presenta una nueva jerarquía de claves cuando el cliente proporciona una clave.
- La asignación que se usa para volver a ensamblar el archivo se almacena en la base de datos de contenido junto con las claves cifradas, independientemente de la clave maestra necesaria para descifrarlas.
- Cada cuenta de almacenamiento de Azure tiene sus propias credenciales únicas por tipo de acceso (lectura, escritura, enumeración y eliminación). Cada conjunto de credenciales se almacena en el almacén de claves seguras y se actualiza periódicamente. Como se ha descrito anteriormente, hay tres tipos diferentes de almacenes, cada uno con una función DISTINCT:
    - Los datos de los clientes se almacenan como Blobs cifrados en Azure Storage. La clave de cada fragmento de datos de clientes se cifra y almacena por separado en la base de datos de contenido. Los datos del cliente no tienen pistas sobre cómo se pueden descifrar.
    - La base de datos de contenido es una base de datos de SQL Server. Contiene la asignación necesaria para localizar y volver a ensamblar los blobs de datos del cliente que se hospedan en el almacenamiento de Azure, así como las claves necesarias para cifrar esos BLOBs. Sin embargo, el conjunto de claves se cifra (tal como se explicó anteriormente) y se mantiene en un almacén de claves independiente.
    - El almacén de claves se separa físicamente de la base de datos de contenido y de Azure Storage. Contiene las credenciales de cada contenedor de almacenamiento de Azure y la clave maestra en el conjunto de claves cifradas que se conservan en la base de datos de contenido.

Cada uno de estos tres componentes de almacenamiento (el almacén de blobs de Azure, la base de datos de contenido y el almacén de claves) están físicamente separados. La información contenida en cualquiera de los componentes no puede usarse por sí sola. Sin el acceso a los tres, es imposible recuperar las claves de los fragmentos, descifrar las claves para que se puedan usar, asociar las claves con sus fragmentos correspondientes, descifrar cada fragmento o reconstruir un documento a partir de sus fragmentos constituyentes.

Los certificados de BitLocker, que protegen los volúmenes de discos físicos de los equipos del centro de recursos, se almacenan en un repositorio seguro (el almacén secreto de SharePoint Online) que está protegido por la clave de la granja de servidores.

Las claves TDE que protegen las claves por BLOB se almacenan en dos ubicaciones:

- El repositorio seguro, que hospeda los certificados de BitLocker y está protegido por la clave de la granja de servidores; y
- En un repositorio seguro administrado por Azure SQL Database.

Las credenciales usadas para obtener acceso a los contenedores de almacenamiento de Azure también se conservan en el almacén secreto de SharePoint Online y se delegan en cada granja de servidores de SharePoint Online según sea necesario. Estas credenciales son firmas SAS de Azure Storage, con credenciales separadas que se usan para leer o escribir datos, y con la Directiva aplicada para que estos expiren automáticamente cada 60 días. Se usan diferentes credenciales para leer o escribir datos (no para ambas), y no se conceden permisos para enumerar a las granjas de servidores de SharePoint Online.

> [!NOTE]
> Para los clientes de Office 365 el gobierno de Estados Unidos, los blobs de datos se almacenan en Azure U.S. Government Storage. Además, el acceso a las claves de SharePoint Online en Office 365 U.S. Government se limita al personal de Office 365 que se ha diseñado específicamente. El personal de operaciones del gobierno de Azure Estados Unidos no tiene acceso al almacén de claves de SharePoint Online que se usa para cifrar blobs de datos.

Para obtener más información sobre el cifrado de datos en SharePoint Online y OneDrive para la empresa, consulte [cifrado de datos en onedrive para la empresa y SharePoint Online](https://technet.microsoft.com/en-us/library/dn905447.aspx).

### <a name="list-items-in-sharepoint-online"></a>Elementos de lista en SharePoint Online

Los elementos de lista son fragmentos más pequeños de datos de clientes que se crean ad-hoc o que pueden activarse de forma más dinámica dentro de un sitio, como filas de una lista creada por el usuario, publicaciones individuales en un blog de SharePoint Online o entradas dentro de una página wiki de SharePoint Online. Los elementos de lista se almacenan en la base de datos de contenido (Azure SQL Database) y están protegidos con TDE.

## <a name="encryption-of-data-in-transit"></a>Cifrado de datos en tránsito

En OneDrive para la Empresa y SharePoint Online, hay dos escenarios en los que los datos entran y salen de los centros de datos.

- **La comunicación del cliente con la comunicación del servidor** a OneDrive para la empresa en Internet usa conexiones SSL/TLS. Todas las conexiones SSL se establecen con claves de 2048 bits.
- **Movimiento de datos entre centros de datos** : la principal razón para mover datos entre centros de datos es la replicación geográfica para habilitar la recuperación ante desastres. Por ejemplo, los registros de transacciones de SQL Server y las diferencias de almacenamiento de blobs viajan a lo largo de esta canalización. Aunque estos datos ya se transmiten a través de una red privada, se protegen aún más con el mejor cifrado de su clase.

## <a name="exchange-online"></a>Exchange Online

Exchange online usa BitLocker para todos los datos de buzones y la configuración de BitLocker se describe en [BitLocker para](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)el cifrado. El cifrado de nivel de servicio cifra todos los datos del buzón de correo en el nivel de buzón. 

Además del cifrado de servicio, Office 365 admite la clave de cliente, que se basa en el cifrado de servicio. La clave de cliente es una opción de clave administrada por Microsoft para el cifrado del servicio de Exchange online que también se encuentra en la guía básica de Microsoft. Este método de cifrado proporciona una mayor protección que BitLocker no permite porque proporciona separación entre los administradores de servidores y las claves criptográficas necesarias para el descifrado de datos y porque el cifrado se aplica directamente a los datos (en en contraste con BitLocker, que aplica el cifrado en el volumen de disco lógico), todos los datos de cliente copiados de un servidor Exchange permanecen cifrados.

El ámbito del cifrado del servicio de Exchange online son los datos del cliente almacenados en REST dentro de Exchange Online. (Skype empresarial almacena casi todo el contenido generado por el usuario dentro del buzón de correo de Exchange online del usuario y, por lo tanto, hereda la característica de cifrado de servicio de Exchange Online).
