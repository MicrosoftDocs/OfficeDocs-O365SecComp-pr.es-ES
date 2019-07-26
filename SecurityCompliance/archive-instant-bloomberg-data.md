---
title: Configurar un conector para archivar datos Instant Bloomberg en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector nativo para importar datos desde la herramienta instantánea de chat de Bloomberg a Office 365. Esto le permite archivar datos de orígenes de datos de terceros en Office 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: eda68a0fdc887a2042a78683eaef0693264d0684
ms.sourcegitcommit: a550519ca8f2a54712bf0a43be7f954e55675dac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "35902472"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data-in-office-365"></a>Configurar un conector para archivar datos Instant Bloomberg en Office 365

Use un conector nativo en el centro de seguridad & cumplimiento en Office 365 para importar y archivar datos de chat de servicios financieros de la herramienta de colaboración [instantánea de Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) . Después de configurar y configurar un conector, se conecta al sitio FTP seguro (SFTP) de su organización una vez al día, convierte el contenido de los mensajes de chat en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a los buzones en Office 365.

Una vez que se almacenan los datos instantáneos de Bloomberg en los buzones de usuario, puede aplicar las características de cumplimiento de Office 365, como retención por juicio, búsqueda de contenido, archivado local, auditoría y políticas de retención de Office 365 a datos Instant Bloomberg. Por ejemplo, puede buscar mensajes instantáneos de chat mediante la búsqueda de contenido o asociar el buzón de correo que contiene los datos de Bloomberg instantáneo con un custodio en un caso de eDiscovery avanzado. Usar un conector de Bloomberg instantáneo para importar y archivar datos en Office 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Información general sobre el archivado de datos de Bloomberg Instant

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de los chats instantáneos de Bloomberg en Office 365. 

![Proceso de importación y archivo instantánea de Bloomberg](media/InstantBloombergDataArchiving.png)

1. Su organización trabaja con Bloomberg para configurar un sitio de SFTP de Bloomberg. También trabajará con Bloomberg para configurar el sitio web Bloomberg para copiar los mensajes de chat en su sitio de SFTP de Bloomberg.

2. Una vez cada 24 horas, los mensajes de chat de Bloomberg instantáneo se copian en el sitio de SFTP de Bloomberg.
    
3. El conector de Bloomberg instantáneo que crea en el centro de seguridad & cumplimiento se conecta al sitio de SFTP de Bloomberg todos los días y transfiere los mensajes de chat de las 24 horas anteriores a un área de almacenamiento seguro de Azure en la nube de Microsoft. El conector también convierte el contenido de un chat en un formato de mensaje de correo electrónico.
    
4. El conector importa los elementos de mensaje de chat al buzón de un usuario específico o a un buzón de correo alternativo. El conector usa el valor de la propiedad *CorporateEmailAddress* . Todos los mensajes de chat contienen esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de chat. El hecho de que un elemento se importe en un buzón de usuario específico o en el buzón de correo alternativo se basa en los criterios siguientes:
    
    a. **Elementos que tienen un valor en la propiedad CorporateEmailAddress que corresponde a una cuenta de usuario de Office 365:** Si el conector puede asociar la dirección de correo electrónico de la propiedad *CorporateEmailAddress* con una cuenta de usuario específica en Office 365, el elemento se copia en la carpeta Bandeja de entrada en el buzón de Office 365 del usuario.
    
    b. **Elementos que tienen un valor en la propiedad CorporateEmailAddress que no se corresponde con una cuenta de usuario de Office 365:** Si el conector no puede asociar una dirección de correo electrónico de la propiedad *CorporateEmailAddress* con una cuenta de usuario específica en Office 365, el elemento se copia en la carpeta Bandeja de entrada de un buzón "catch-all" alternativo en Office 365.

## <a name="before-you-begin"></a>Antes de empezar

Muchos de los pasos de implementación necesarios para archivar datos instantáneos de Bloomberg son externos a Office 365 y deben completarse antes de poder crear el conector en el centro de seguridad & cumplimiento.

- La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Para dar su consentimiento a esta solicitud, vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), inicie sesión con las credenciales de un administrador global de Office 365 y, a continuación, acepte la solicitud. Debe completar este paso antes de poder crear correctamente el conector Bloomberg instantáneo en el paso 3.

- Suscríbase a [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Esto es necesario para que pueda iniciar sesión en Bloomberg Anywhere para acceder al sitio Bloomberg SFTP que debe configurar y configurar.

- Configure un sitio Bloomberg SFTP (protocolo seguro de transferencia de archivos). Después de trabajar con Bloomberg para configurar el sitio de SFTP, los datos de Bloomberg instantáneo se cargan al sitio de SFTP todos los días. El conector que se crea en el paso 2 se conecta a este sitio de SFTP y transfiere los datos de chat a los buzones de Office 365. SFTP también cifra los datos de los chats de Bloomberg instantáneos que se envían a los buzones de Office 365 durante el proceso de transferencia.

    Para obtener información sobre Bloomberg SFTP (también denominado *BB-SFTP*):

    - Consulte el documento "estándares de conectividad de SFTP" en el [soporte de Bloomberg](https://www.bloomberg.com/professional/support/documentation/).
    
    - Póngase en contacto con el [soporte al cliente de Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

    Después de trabajar con Bloomberg para configurar un sitio de SFTP, Bloomberg le proporcionará cierta información después de que responda al mensaje de correo electrónico de implementación de Bloomberg. Guarde una copia de la siguiente información. Se usa para configurar un conector en el paso 3.

    - Código de empresa, que es un identificador de su organización y se usa para iniciar sesión en el sitio de SFTP de Bloomberg.

    - Contraseña para el sitio de SFTP de Bloomberg

    - Dirección URL para el sitio de SFTP de Bloomberg (por ejemplo, sftp.bloomberg.com)

    - Número de puerto para el sitio de SFTP de Bloomberg

- El usuario que crea un conector para Bloomberg instantáneo en el paso 3 (y que descarga las claves públicas y la dirección IP en el paso 1) debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Esto es necesario para obtener acceso a la página **archivar datos de terceros** en el centro de seguridad & cumplimiento. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Paso 1: obtener las claves públicas SSH y PGP

El primer paso es obtener una copia de las claves públicas para el shell seguro (SSH) y Pretty Good Privacy (PGP). Estas claves se usan en el paso 2 para configurar el sitio de SFTP de Bloomberg para permitir que el conector (creado en el paso 3) se conecte al sitio de SFTP y transfiera los datos instantáneos de Bloomberg chat a los buzones de Office 365. También puede obtener una dirección IP en este paso, que se usa al configurar el sitio Bloomberg de SFTP.

1. Vaya a <https://protection.office.com> y haga clic en **importación \> de gobierno de datos** y, a continuación, haga clic en archivar **datos de terceros**.

2. En la página **archivar datos de terceros** , haga clic en **Agregar un conector**y, a continuación, en **instantáneo Bloomberg**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. En el paso 1 del **sitio de agregar credenciales para Bloomberg SFTP** , haga clic en **Descargar clave ssh**, **Descargar clave PGP**y descargar vínculos de **dirección IP** para guardar una copia de cada archivo en el equipo local. Estos archivos contienen los siguientes elementos que se usan para configurar el sitio Bloomberg de SFTP en el paso 2:

   - Clave pública SSH: esta clave se usa para configurar Secure Shell (SSH) para habilitar un inicio de sesión remoto seguro cuando el conector se conecta al sitio Bloomberg de SFTP.

   - Clave pública PGP: esta clave se usa para configurar el cifrado de datos que se transfieren desde el sitio de SFTP de Bloomberg a Office 365.

   - Dirección IP: el sitio Bloomberg de SFTP está configurado para aceptar una solicitud de conexión solo desde esta dirección IP, que se usa en el conector para Bloomberg instantáneo que se crea en el paso 3. 

5. Haga clic en **Cancelar** para cerrar el asistente. Vuelva a este asistente en el paso 3 para crear el conector.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Paso 2: configurar el sitio de SFTP de Bloomberg

El siguiente paso es usar las claves públicas SSH y PGP y la dirección IP que obtuvo en el paso 1 para configurar la autenticación SSH y el cifrado PGP para el sitio de SFTP de Bloomberg. Esto permite que el conector de Bloomberg instantáneo que crea en el paso 3 se conecte al sitio Bloomberg de SFTP y transfiera datos instantáneos de Bloomberg a Office 365. Debe trabajar con el servicio de soporte al cliente de Bloomberg para configurar su sitio de SFTP. Póngase en contacto con el [soporte al cliente de Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para obtener ayuda. 

> [!IMPORTANT]
> Bloomberg recomienda adjuntar los tres archivos que descargó en el paso 1 a un mensaje de correo electrónico y enviarlo a su equipo de atención al cliente cuando trabaja con ellos para configurar el sitio de SFTP de Bloomberg.

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Paso 3: crear un conector de Bloomberg instantáneo

El último paso consiste en crear un conector Bloomberg instantáneo en el centro de seguridad & cumplimiento. El conector usa la información que proporciona para conectarse al sitio Bloomberg de SFTP y transferir los mensajes de chat a los cuadros del buzón de usuario correspondiente en Office 365. 

1. Vaya a <https://protection.office.com> y haga clic en **importación \> de gobierno de datos** y, a continuación, haga clic en archivar **datos de terceros**.

2. En la página **archivar datos de terceros** , haga clic en **Agregar un conector**y, a continuación, en **instantáneo Bloomberg**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. En la página **agregar credenciales para Bloomberg SFTP** , en el paso 3, escriba la información necesaria en los siguientes cuadros y, a continuación, haga clic en **siguiente**.

    - **Código de empresa:** El identificador de la organización y usado como nombre de usuario para el sitio de SFTP de Bloomberg.

    - **Contraseña:** Contraseña para un sitio de SFTP de Bloomberg

    - **dirección URL de SFTP:** La URL para el sitio de SFTP de Bloomberg (por ejemplo, sftp.bloomberg.com).

    - **Puerto SFTP:** El número de puerto para el sitio de SFTP de Bloomberg. El conector lo usa para conectarse al sitio de SFTP.

5. En la página **buzón alternativo** , escriba la dirección de correo electrónico de un buzón que se usa para almacenar los mensajes de chat de un Bloomberg instantáneo que no estén asociados a un buzón de usuario de la organización.

   > [!NOTE]
   > Todos los mensajes de chat de todas las conversaciones de Bloomberg instantáneo incluyen una propiedad denominada *CorporateEmailAddress*, que contiene la dirección de correo electrónico de su organización para el participante de chat. Durante el proceso de importación, el conector intenta importar mensajes de chat a un buzón de usuario en Office 365 que tiene las mismas direcciones de correo electrónico que coinciden con la de la propiedad *CorporateEmailAddress* . Si no hay un buzón de correo de Office 365 con la misma dirección que el de la propiedad *CorporateEmailAddress* , el conector importa el mensaje de chat al buzón alternativo que se especifique en esta página. En este momento, los mensajes instantáneos de Bloomberg chat archivados en el buzón de correo alternativo no se supervisan mediante directivas de supervisión en Office 365.

6. Haga clic en **siguiente**, revise la configuración y, a continuación, haga clic en **preparar** para crear el conector.

7. Vaya a la página **archivar datos de terceros** para ver el progreso del proceso de importación del nuevo conector.
