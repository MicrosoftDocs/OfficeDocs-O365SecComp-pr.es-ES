---
title: Configurar un conector para archivar datos Instant Bloomberg en Office 365 (versión preliminar)
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
ms.openlocfilehash: 0b69ddaa21196bd0e149eba672fec104eabe2e5e
ms.sourcegitcommit: ab16ddf4c050a995471a058150767a0778be0b88
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "35431617"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data-in-office-365-preview"></a>Configurar un conector para archivar datos Instant Bloomberg en Office 365 (versión preliminar)

La característica conector para archivar datos de Bloomberg Instant en Office 365 está en versión preliminar.

Use un conector nativo en el centro de seguridad & cumplimiento en Office 365 para importar y archivar datos de chat de servicios financieros de la herramienta de colaboración [instantánea de Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) . Después de configurar y configurar un conector, se conecta al sitio FTP seguro (SFTP) de su organización una vez al día, convierte el contenido de los mensajes de chat en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a los buzones en Office 365.

Una vez que se almacenan los datos instantáneos de Bloomberg en los buzones de usuario, puede aplicar las características de cumplimiento de Office 365, como retención por juicio, búsqueda de contenido, archivado local, auditoría y políticas de retención de Office 365 a datos Instant Bloomberg. Por ejemplo, puede buscar mensajes instantáneos de chat mediante la búsqueda de contenido o asociar el buzón de correo que contiene los datos de Bloomberg instantáneo con un custodio en un caso de eDiscovery avanzado. Usar un conector de Bloomberg instantáneo para importar y archivar datos en Office 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Información general sobre el archivado de datos de Bloomberg Instant

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de los chats instantáneos de Bloomberg en Office 365. 

![Proceso de importación y archivo instantánea de Bloomberg](media/InstantBloombergDataArchiving.png)

1. Su organización trabaja con Bloomberg para configurar un sitio de SFTP de Bloomberg. También trabajará con Bloomberg para configurar el sitio web Bloomberg para copiar los mensajes de chat en su sitio de SFTP de Bloomberg.

2. Una vez cada 24 horas, los mensajes de chat de Bloomberg instantáneo se copian en el sitio de SFTP de Bloomberg.
    
3. El conector de Bloomberg instantáneo que crea en el centro de seguridad & cumplimiento se conecta al sitio de SFTP de Bloomberg todos los días y transfiere los mensajes de chat de las 24 horas anteriores a un área de almacenamiento seguro de Azure en la nube de Microsoft. El conector también convierte el contenido de un chat en un formato de mensaje de correo electrónico.
    
4. El conector importa los elementos de mensaje de chat al buzón de un usuario específico o a un buzón de correo alternativo. El conector usa el valor de la propiedad *CorporateEmailAddress* . Todos los mensajes de chat contienen esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de chat. El hecho de que un elemento se importe en un buzón de usuario específico o en el buzón de correo alternativo se basa en los criterios siguientes:
    
    a. **Elementos que tienen un valor en la propiedad CorporateEmailAddress que corresponde a una cuenta de usuario de office 365** : Si el conector puede asociar la dirección de correo electrónico de la propiedad *CorporateEmailAddress* a una cuenta de usuario específica en Office 365, el el elemento se copia en la carpeta Bandeja de entrada en el buzón de correo de Office 365 del usuario.
    
    b. **Elementos que tienen un valor en la propiedad CorporateEmailAddress que no se corresponde con una cuenta de usuario de office 365** : Si el conector no puede asociar una dirección de correo electrónico de la propiedad *CorporateEmailAddress* a una cuenta de usuario específica en Office 365, el elemento se copia en la carpeta Bandeja de entrada de un buzón "catch-all" alternativo en Office 365.

## <a name="before-you-begin"></a>Antes de empezar

Muchos de los pasos de implementación necesarios para archivar datos instantáneos de Bloomberg son externos a Office 365 y deben completarse antes de poder crear el conector en el centro de seguridad & cumplimiento.

- Suscríbase a [Blooomberg en cualquier lugar](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Esto es necesario para que pueda iniciar sesión en Bloomberg Anywhere para acceder al sitio Bloomberg SFTP que debe configurar y configurar.

- Configure un sitio Bloomberg SFTP (protocolo seguro de transferencia de archivos). Después de trabajar con Bloomberg para configurar el sitio de SFTP, los datos de Bloomberg instantáneo se cargan al sitio de SFTP todos los días. El conector que se crea en el paso 2 se conecta a este sitio de SFTP y transfiere los datos de chat a los buzones de Office 365. SFTP también cifra los datos de los chats de Bloomberg instantáneos que se envían a los buzones de Office 365 durante el proceso de transferencia.

    Para obtener información sobre Bloomberg SFTP (también denominado *BB-SFTP*):

    - Consulte el documento "estándares de conectividad de SFTP" en el [soporte de Bloomberg](https://www.bloomberg.com/professional/support/documentation/).
    
    - Póngase en contacto con el [soporte al cliente de Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

    Después de trabajar con Bloomberg para configurar un sitio de SFTP, Bloomberg le proporcionará cierta información después de que responda al mensaje de correo electrónico de implementación de Bloomberg. Guarde una copia de la siguiente información. Se usa para configurar un conector en el paso 3.

    - Código de empresa, que es un identificador de su organización y se usa para iniciar sesión en el sitio de SFTP de Bloomberg.

    - Contraseña para el sitio de SFTP de Bloomberg

    - Dirección URL para el sitio de SFTP de Bloomberg (por ejemplo, sftp.bloomberg.com)

    - Número de puerto para el sitio de SFTP de Bloomberg

- La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Para dar su consentimiento a esta solicitud, vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), inicie sesión con las credenciales de un administrador global de Office 365 y, a continuación, acepte la solicitud. Debe completar este paso antes de poder crear correctamente el conector Bloomberg instantáneo en el paso 3.

- El usuario que crea un conector para Bloomberg instantáneo en el paso 3 (y que descarga las claves públicas y la dirección IP en el paso 1) debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Esto es necesario para obtener acceso a la página **archivar datos de terceros** en el centro de seguridad & cumplimiento. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Paso 1: obtener las claves públicas SSH y PGP

El primer paso es obtener una copia de las claves públicas para el shell seguro (SSH) y Pretty Good Privacy (PGP). Estas claves se usan en el paso 2 para configurar el sitio de SFTP de Bloomberg para permitir que el conector (creado en el paso 3) se conecte al sitio de SFTP y transfiera los datos instantáneos de Bloomberg chat a los buzones de Office 365. También puede obtener una dirección IP en este paso, que se usa al configurar el sitio Bloomberg de SFTP.

1. Vaya a <https://protection.office.com> y haga clic en **importación \> de gobierno de datos** y, a continuación, haga clic en archivar **datos de terceros**.

2. En la página **archivar datos de terceros** , haga clic en **Agregar un conector**y, a continuación, en **instantáneo Bloomberg**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. En el paso 1 del **sitio agregar credenciales para Bloomberg SFTP** , haga clic en **descargar la clave ssh** y descargar vínculos de descarga de **clave PGP** para guardar una copia de cada archivo de clave pública en el equipo local. Estos archivos contienen los siguientes elementos que se usarán para configurar el sitio de SFTP de Bloomberg en el paso 2:

   - Clave pública SSH: esta clave se utilizará para configurar Secure Shell (SSH) para habilitar un inicio de sesión remoto seguro cuando el conector se conecta al sitio Bloomberg de SFTP.

   - Clave pública PGP: esta clave se utilizará para configurar el cifrado de datos que se transfieren desde el sitio de SFTP de Bloomberg a Office 365.

   - Dirección IP: el sitio de SFTP de Bloomberg se configurará para aceptar una solicitud de conexión solo desde esta dirección IP, que se usa en el conector de Bloomberg de forma inmediata que se crea en el paso 3. 

5. Haga clic en **Cancelar** para cerrar el asistente. Vuelva a este asistente en el paso 3 para crear el conector.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Paso 2: configurar el sitio de SFTP de Bloomberg

El siguiente paso es usar las claves públicas SSH y PGP y la dirección IP que obtuvo en el paso 1 para configurar la autenticación SSH y el cifrado PGP para el sitio de SFTP de Bloomberg. Esto permite que el conector de Bloomberg instantáneo que ha creado en el paso 3 se conecte al sitio Bloomberg de SFTP y transfiera datos instantáneos de Bloomberg a Office 365. Póngase en contacto [con el soporte al cliente de Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) si necesita ayuda para configurar esto.

1. Inicie sesión en el panel de control de Bloomberg CCN con una cuenta para su organización.

2. Vaya a CCN y haga clic en la pestaña **claves públicas** .

3. Para habilitar la autenticación SSH, haga clic en **Agregar**.

4. En la ventana **Agregar clave pública** , haga clic en la lista desplegable **tipo de clave** y, a continuación, haga clic en Inicio de **sesión**.

5. Copie toda la clave pública del SSH (todos los caracteres entre las comillas dobles, pero sin incluir las comillas) que haya descargado en el paso 1, péguelo en este campo y, a continuación, haga clic en **Enviar** para guardar la clave.
 
    Por ejemplo, debe copiar la siguiente clave pública SSH:

    `
    ssh-rsa
    AAAAB3NzaC1yc2EAAAABIwAAAQEA1dxAyc0JzCmc5NzgyzRYhnj3FGHK5Kd9T2cwZNkmL/9nFhQupQor081rmuw9gACAmeot7y+V/fmijo/q4rxDe3Auu3hfLl1NpWlIssQJHzycms8zimtdQcXbMKwDQOnRthpEocF5ySs76KE72vaYQJTvclAamWWq0D75SUmXDFFr7afvEy57F7KgMD1ecg6lH7q8seSKbiiWxX1Ul0kL15fzpUyhjDP41owb1XC/dF7fJwAmCO1+HZfDLEp62q4tnApLpdd92KoR41LZTryO5dICKhk+S+JxPLkksxL0wm5YevOr2n4ScuRdsBV8mWKZ1Xw+cOss9O6L7cCcEiB3Ow==
    `

6. Para habilitar el cifrado PGP, haga clic en **Agregar** de nuevo en la ficha **claves públicas** , haga clic en la lista desplegable **tipo de clave** y, esta vez, haga clic en **cifrado**.

7. Copie toda la clave pública PGP (todos los caracteres entre las comillas dobles, pero sin incluir las comillas) que haya descargado en el paso 1, péguelo en este campo y, a continuación, haga clic en **Enviar** para guardar la clave. 

    Por ejemplo, debe copiar la siguiente clave pública PGP:

    `
    -----BEGIN PGP PUBLIC KEY BLOCK-----
    Version: BCPG C# v1.7.4137.9688
    nmQENBFz+6UQBCACKC4ilYoVOP5b/F0CO+oQYbag79Ov4NZxM4EKW51lUAvKNExRM\nc1C/gwXm8bghht8GEODckXXqx8qSSXUEeA/ROweXNtD1u1kn7PgYEFUeD/qE739m\nm5lxXF9Vod26AtKQ9Y1EvYoQEltwztAaXg8K8LQzB+tzN079d1cxM5tbiRQLttAh\nOt5amLXuINt8+dWyNas3DfgIBUmwfkwCbUO0ElrIhvvO3A85K97SX9Q6Py0SkfkK\nQpnULuhdjSm+7k7qlVMf0s8e/9jUXYKbMFkxlOoMq052vV0l0VQNSeuKoC+m6+LT\nEPab89AMt6S4Ujum9wTUy1eWNx9vV0y/w8N7ABEBAAG0JDM5MjM4ZTg3LWI1YWIt\nNGVmNi1hNTU5LWFmNTRjNmIwN2I0MokBHAQQAQIABgUCXP7pRAAKCRAJQdjaG//S\nCy70B/wKrR2CcqtZx56yrGJFfVy3niEt16VEA3xJM3D9nX0gmgo85Nh5gkiY3ahH\nnNEmgW5vlCM1gcgFeoZWe8A80G4QoabslSUzLbq9HsHOOAQApsfhrhXpylrAVa4n\nI53XUOxWdOTa4xsOob8hSRADqJbwHPOsoAr2A87TvZ9LSi2Mii5omeTq416CLnoS\nPBAEhelZm+ruy5JhzA1yXvWYFH08wNqSHO3bskdES2yW5SyQmYlcoEztWE0Q0Z+G\nZT3kOa/W2MbcZovFCQIfqhwVfXtIzx5uYUmxgk5cFKUJJMlO0AZK/HwM22xuuIWe\ndMa6OMo/n8tvEBxrLQMdVPlz+hZ6
    =AwmP
    -----END PGP PUBLIC KEY BLOCK-----
    `
8. De nuevo en la ventana principal del panel de control de CCN, en **Agregar su dirección IP aquí**, escriba la siguiente dirección IP (que se incluye en el archivo Keys. txt que ha descargado en el paso 1) en el **campo Agregar dirección**.

   `
   40.124.28.216
   `

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Paso 3: crear un conector de Bloomberg instantáneo

El último paso consiste en crear un conector Bloomberg instantáneo en el centro de seguridad & cumplimiento. El conector usa la información que proporciona para conectarse al sitio Bloomberg de SFTP y transferir los mensajes de chat a los cuadros del buzón de usuario correspondiente en Office 365. 

1. Vaya a <https://protection.office.com> y haga clic en **importación \> de gobierno de datos** y, a continuación, haga clic en archivar **datos de terceros**.

2. En la página **archivar datos de terceros** , haga clic en **Agregar un conector**y, a continuación, en **instantáneo Bloomberg**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. En la página **agregar credenciales para Bloomberg SFTP** , en el paso 3, escriba la información necesaria en los siguientes cuadros y, a continuación, haga clic en **siguiente**.

    - **Código de empresa** : el identificador de la organización y usado como nombre de usuario para el sitio de SFTP de Bloomberg.

    - **Contraseña** : contraseña para el sitio de SFTP de Bloomberg

    - **URL de SFTP** : la dirección URL para el sitio de SFTP de Bloomberg (por ejemplo, SFTP.Bloomberg.com).

    - **Puerto SFTP** : el número de puerto para el sitio de SFTP de Bloomberg. El conector lo usa para conectarse al sitio de SFTP.

5. En la página **buzón alternativo** , escriba la dirección de correo electrónico de un buzón que se usará para almacenar los mensajes de chat de un Bloomberg instantáneo que no se puede asociar con un buzón de usuario en su organización.

   > [!NOTE]
   > Todos los mensajes de chat de todas las conversaciones de Bloomberg instantáneo incluyen una propiedad denominada *CorporateEmailAddress*, que contiene la dirección de correo electrónico de su organización para el participante de chat. Durante el proceso de importación, el conector intenta importar mensajes de chat a un buzón de usuario en Office 365 que tiene las mismas direcciones de correo electrónico que coinciden con la de la propiedad *CorporateEmailAddress* . Si no hay un buzón de correo de Office 365 con la misma dirección que el de la propiedad *CorporateEmailAddress* , el conector importa el mensaje de chat al buzón alternativo que se especifique en esta página. En este momento, los mensajes instantáneos de Bloomberg chat archivados en el buzón de correo alternativo no se supervisan mediante directivas de supervisión en Office 365.

6. Haga clic en **siguiente**, revise la configuración y, a continuación, haga clic en **preparar** para crear el conector.

7. Vaya a la página **archivar datos de terceros** para ver el progreso del proceso de importación del nuevo conector.
