---
title: Configurar un conector para archivar datos de LinkedIn en Office 365 (versión preliminar)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector nativo para importar datos desde una página de la compañía de LinkedIn a Office 365. Esto le permite archivar datos de orígenes de datos de terceros en Office 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar el cumplimiento de los datos de terceros de la organización.
ms.openlocfilehash: 618cef7c0208378179d41a94f4a274a0bddadee9
ms.sourcegitcommit: ecc823c2a4f1465114cf1d3a4630e31c47779ddc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2019
ms.locfileid: "35079384"
---
# <a name="set-up-a-connector-to-archive-linkedin-data-in-office-365-preview"></a>Configurar un conector para archivar datos de LinkedIn en Office 365 (versión preliminar)

La característica conector para archivar datos de páginas de la compañía de LinkedIn en Office 365 está en versión preliminar.

Use un conector nativo en el centro de seguridad & cumplimiento en Office 365 para importar y archivar datos de las páginas de la compañía de LinkedIn. Después de configurar y configurar un conector, se conecta a la cuenta de la página específica de la empresa de LinkedIn una vez cada 24 horas. El conector convierte los mensajes enviados a la página compañía a un mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón en Office 365.

Una vez que los datos de la página de la compañía de LinkedIn se almacenan en un buzón de correo, puede aplicar las características de cumplimiento de Office 365 como la retención por juicio, la búsqueda de contenido, el archivado local, la auditoría y las directivas de retención de Office 365 a datos de LinkedIn. Por ejemplo, puede buscar estos elementos mediante la búsqueda de contenido o asociar el buzón de almacenamiento a un custodio en un caso de exhibición avanzada de documentos electrónicos. La creación de un conector para importar y archivar datos de LinkedIn en Office 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

## <a name="before-you--begin"></a>Antes de empezar

- La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Para dar su consentimiento a esta solicitud, vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), inicie sesión con las credenciales de un administrador global de Office 365 y, a continuación, acepte la solicitud.

- El usuario que crea un conector de página de la compañía de LinkedIn debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Esto es necesario para obtener acceso a la página **archivar datos de terceros** en el centro de seguridad & cumplimiento. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

- Debe tener las credenciales de inicio de sesión (dirección de correo electrónico o número de teléfono y contraseña) de una cuenta de usuario de LinkedIn que sea un administrador de la página de la compañía de LinkedIn que desea archivar. Use estas credenciales para iniciar sesión en LinkedIn cuando configure el conector.

## <a name="create-a-linkedin-connector"></a>Crear un conector de LinkedIn

1. Vaya a <https://protection.office.com> y haga clic en **importación \> de gobierno de datos** y, a continuación, haga clic en archivar **datos de terceros**.

2. En la página **archivar datos de terceros** , haga clic en **Agregar un conector**y, a continuación, haga clic en **LinkedIn**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. En la página **iniciar sesión con LinkedIn** , haga clic en **iniciar sesión con LinkedIn**.

   Se muestra la página de inicio de LinkedIn.

   ![Página de inicio de sesión de LinkedIn](media/LinkedInSigninPage.png)

5. En la página de inicio de LinkedIn, escriba la dirección de correo electrónico (o el número de teléfono) y la contraseña de la cuenta de LinkedIn asociada a la página de la compañía que desea archivar y, a continuación, haga clic en **iniciar sesión**.

   Se muestra una página del asistente con una lista de todas las páginas de LinkedIn Company asociadas con la cuenta en la que ha iniciado sesión. Un conector solo se puede configurar para una página de la compañía. Si su organización tiene varias páginas de la compañía de LinkedIn, tiene que crear un conector para cada una.

   ![Se muestra una página con una lista de páginas de la compañía de LinkedIn](media/LinkedInSelectCompanyPage.png)

6. Seleccione la página de la compañía desde la que desea archivar elementos y, a continuación, haga clic en **siguiente**.

7. En la página **Establecer filtros** , puede aplicar un filtro para importar inicialmente los elementos que tienen una antigüedad determinada. Seleccione una edad y, a continuación, haga clic en **siguiente**.

8. En la página **establecer cuenta de almacenamiento** , escriba la dirección de correo electrónico de un buzón de correo de Office 365 en el que se importarán los elementos de LinkedIn y, a continuación, haga clic en **siguiente**. Los elementos se importan a la carpeta Bandeja de entrada en este buzón.

9. Revise la configuración del conector y, a continuación, haga clic en **Guardar** para completar la configuración del conector.

Después de crear el conector, puede volver a la página **archivar datos de terceros** (haga clic en **Actualizar** si es necesario para actualizar la lista de conectores) para ver el nuevo conector. El valor de la columna **Estado** está **a la espera de iniciarse**. El proceso de importación inicial tardará hasta 24 horas en iniciarse. Después de que se ejecute el conector por primera vez y se importen los elementos de LinkedIn, el conector se ejecutará una vez cada 24 horas e importará los elementos nuevos que se creen en la página de la compañía de LinkedIn en las 24 horas anteriores.

Para ver más detalles, haga clic en el conector en la lista de la página **archivar datos de terceros** para mostrar la página de control flotante. En **Estado**, el intervalo de fechas que se muestra indica el filtro de antigüedad que se seleccionó cuando se creó el conector. 

## <a name="more-information"></a>Más información

- Los elementos de LinkedIn se importan a la carpeta Bandeja de entrada en el buzón de almacenamiento en Office 365. Aparecen como mensajes de correo electrónico. El nombre para mostrar del remitente del mensaje es el nombre de la página de la compañía de LinkedIn. La dirección de correo electrónico real del remitente es la dirección de correo electrónico del buzón de almacenamiento. El nombre de la página de la compañía también se agrega previamente a la línea de asunto. 

- Debido al comportamiento anterior, puede buscar las propiedades del `from` correo `subject` electrónico o no al usar una herramienta de exhibición de documentos electrónicos de Microsoft para buscar elementos de LinkedIn archivados en Office 365. Por ejemplo, si el nombre de la página compañía es "página contoso Company", puede usar uno de los siguientes pares *Property: Value* en la consulta de búsqueda de palabras clave:
   
   ```
   from:"Contoso Company Page"
   ```

    O bien

   ```
   subject:"Contoso Company Page"
   ```

- Para que sea más fácil localizar o administrar los elementos de LinkedIn importados a Office 365, el propietario del buzón de correo de almacenamiento (o cualquier persona que tenga asignado el permiso FullAccess) puede configurar una regla de bandeja de entrada para mover los elementos de una página de la compañía de LinkedIn a una carpeta específica. Esto es útil si el buzón de almacenamiento se usa para archivar los elementos importados de distintos orígenes de datos de terceros. Por ejemplo, puede crear una regla de bandeja de entrada que mueva todos los elementos que contengan el nombre de una página específica de la compañía de LinkedIn en el campo asunto a una carpeta específica.