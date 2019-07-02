---
title: Usar un conector de ejemplo para archivar datos de Facebook en Office 365 (versión preliminar)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector nativo para importar datos de terceros desde orígenes de datos como páginas empresariales de Facebook, Twitter, páginas de la compañía de LinkedIn y Bloomberg instantáneo. Esto le permite archivar datos de orígenes de datos de terceros en Office 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar el gobierno de los datos de terceros de la organización.
ms.openlocfilehash: 2dde58e4d3ead0064e28c1ba1bfc04485c7a25df
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014709"
---
# <a name="use-a-sample-connector-to-archive-facebook-data-in-office-365-preview"></a>Usar un conector de ejemplo para archivar datos de Facebook en Office 365 (versión preliminar)

La característica conector de ejemplo para archivar datos de Facebook en Office 365 está en versión preliminar.

Use un conector de ejemplo en el centro de seguridad & cumplimiento en Office 365 para importar y archivar datos de las páginas de empresa de Facebook a Office 365. Después de configurar y configurar un conector de ejemplo, se conecta a la página de empresa de Facebook (de forma programada), convierte el contenido de los elementos de Facebook a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón en Office 365.

Una vez importados los datos de Facebook, puede aplicar características de cumplimiento de Office 365, como retención por juicio, búsqueda de contenido, archivado local, auditoría, supervisión y directivas de retención de Office 365 a los datos de Facebook. Por ejemplo, cuando un buzón se coloca en retención por juicio o se asigna a una directiva de retención, los datos de Facebook se conservan. Puede buscar datos de terceros mediante la búsqueda de contenido o asociar el buzón en el que se almacenan los datos de Facebook con un custodio en un caso de exhibición avanzada de documentos electrónicos. El uso de un conector para importar y archivar datos de Facebook en Office 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

> [!NOTE]
> En este momento, solo están disponibles los conectores de ejemplo para las páginas de negocio de Facebook y [Twitter](archive-twitter-data-with-sample-connector.md) en versión preliminar. Pronto estarán disponibles más conectores de muestra.


## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Requisitos previos para configurar un conector para páginas empresariales de Facebook

Debe completar los siguientes requisitos previos antes de poder configurar y configurar un conector de ejemplo en el centro de seguridad & cumplimiento para importar y archivar datos de las páginas de negocio de Facebook de su organización. 

- Necesita una cuenta de Facebook para las páginas empresariales de su organización (debe iniciar sesión en esta cuenta cuando configure el conector). Actualmente, solo puede archivar datos de páginas empresariales de Facebook; no se pueden archivar datos de perfiles de Facebook individuales.

- La organización debe tener una suscripción de Azure válida. Si no tiene una suscripción a Azure existente, puede registrarse en una de estas opciones:

    - [Regístrese para obtener una suscripción gratuita de Azure de un año](https://azure.microsoft.com/free) 

    - [Registrarse para obtener una suscripción de pago de pago a través de la suscripción de Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La [suscripción gratuita de Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) que se incluye con la suscripción a Office 365 no es compatible con los conectores de muestra del centro de seguridad & cumplimiento.

- La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Para dar su consentimiento a esta solicitud, vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), inicie sesión con las credenciales de un administrador global de Office 365 y, a continuación, acepte la solicitud.

- El usuario que configura el conector personalizado en el cumplimiento de la & de seguridad (en el paso 7) debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a>Paso 1: descargar el paquete de aplicación de conector precompilado desde github

El primer paso es descargar el código fuente de la aplicación predefinida de Facebook Connector que usará una API de Facebook para conectarse a las páginas empresariales de Facebook y extraer los datos de Facebook para poder importarlos a Office 365.

1. Vaya a [este sitio de github](https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases). 
2. En la última versión, haga clic en el archivo **SampleConnector. zip** .
3. Guarde el archivo ZIP en una ubicación en el equipo local. Carga este archivo zip en Azure en el paso 4.

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Paso 2: crear una aplicación en Azure Active Directory

El siguiente paso es registrar una nueva aplicación en Azure Active Directory (AAD). Esta aplicación corresponde al recurso de la aplicación web que implementa en el paso 4 para el conector de Facebook. 

Para obtener instrucciones paso a paso, consulte [crear una aplicación en Azure Active Directory](deploy-facebook-connector.md#step-2-create-an-app-in-azure-active-directory).

Al finalizar este paso (mediante las instrucciones paso a paso anteriores), guardará la siguiente información en un archivo de texto. Estos valores se usan en pasos posteriores del proceso de implementación.

- IDENTIFICADOR de la aplicación AAD
- Secreto de la aplicación AAD
- URI de la aplicación AAD
- Identificador de inquilino

## <a name="step-3-create-an-azure-storage-account"></a>Paso 3: crear una cuenta de almacenamiento de Azure

El conector de Facebook que implemente para su organización cargará los elementos de las páginas de empresa de Facebook en la ubicación de almacenamiento de Azure que cree en este paso. Después de crear un conector personalizado en el centro de seguridad & cumplimiento (en el paso 7), el servicio de importación de Office 365 copiará los datos de Facebook desde la ubicación de almacenamiento de Azure a un buzón en Office 365. Como se explicó anteriormente en la sección [requisitos previos](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) , debe tener una suscripción de Azure válida para crear una cuenta de almacenamiento de Azure.

Para obtener instrucciones paso a paso, consulte [crear una cuenta de almacenamiento de Azure](deploy-facebook-connector.md#step-3-create-an-azure-storage-account).

Al finalizar este paso (siguiendo las instrucciones paso a paso), se guarda el URI de la cadena de conexión que se genera. Use esta cadena al crear un recurso de la aplicación web en Azure en el paso 4.

## <a name="step-4-create-a-web-app-resource-in-azure"></a>Paso 4: crear un recurso de aplicación web en Azure

El siguiente paso es crear un recurso de aplicación web en Azure para el conector de Facebook. 

Para obtener instrucciones paso a paso, consulte [crear un nuevo recurso de aplicación web en Azure](deploy-facebook-connector.md#step-4-create-a-new-web-app-resource-in-azure).

Al completar este paso (siguiendo las instrucciones paso a paso), se proporciona la siguiente información (que se ha copiado a un archivo de texto después de completar los pasos anteriores) al crear el recurso de la aplicación Web.

- APISecretKey: este secreto se crea al finalizar este paso; se usa en el paso 7.
- StorageAccountConnectionString: el URI de la cadena de conexión que copió después de crear la cuenta de almacenamiento de Azure en el paso 3.
- tenantId: el identificador de inquilino de su organización de Office 365 que copió después de crear la aplicación de conector de Facebook en Azure Active Directory en el paso 2.

Además, carga el archivo SampleConnector. zip (que descargó en el paso 1) en este paso para implementar el código fuente de la aplicación de conector de Facebook.

Después de completar este paso, asegúrese de copiar la dirección URL del servicio de aplicaciones ( https://fbconnector.azurewebsites.net)por ejemplo,. Debe usarlo para completar los pasos 5, 6 y 7).

## <a name="step-5-register-the-web-app-on-facebook"></a>Paso 5: registrar la aplicación web en Facebook

El siguiente paso es crear y configurar una nueva aplicación en Facebook. El conector personalizado que ha creado en el paso 7 usa la aplicación Web de Facebook para interactuar con la API de Facebook para obtener datos de las páginas de negocio de Facebook de su organización.

Para obtener instrucciones paso a paso, consulte [registrar la aplicación de Facebook](deploy-facebook-connector.md#step-5-register-the-facebook-app).

Al finalizar este paso (siguiendo las instrucciones paso a paso), guarde la siguiente información en un archivo de texto. Los valores se usan para configurar la aplicación de conector de Facebook en el paso 6.

- IDENTIFICADOR de la aplicación de Facebook
- Secreto de la aplicación de Facebook
- Token de comprobación de webhooks de Facebook

## <a name="step-6-configure-the-facebook-connector-app"></a>Paso 6: configurar la aplicación de conector de Facebook

El paso siguiente es agregar opciones de configuración a la aplicación conector de Facebook que cargó cuando creó el recurso de Azure Web App en el paso 4. Para ello, vaya a la Página principal de la aplicación del conector y configure.

Para obtener instrucciones paso a paso, consulte [Step 6: Configure the Connector Web App](deploy-facebook-connector.md#step-6-configure-the-connector-web-app).

Al finalizar este paso (siguiendo las instrucciones paso a paso), se proporciona la siguiente información (que se ha copiado a un archivo de texto después de completar los pasos anteriores):

- IDENTIFICADOR de la aplicación de Facebook (obtenido en el paso 5)
- Secreto de la aplicación de Facebook (obtenido en el paso 5)
- Token de comprobación de webhooks de Facebook (obtenido en el paso 5)
- IDENTIFICADOR de aplicación de Azure Active Directory (el identificador de la aplicación AAD obtenido en el paso 2)
- Secreto de la aplicación de Azure Active Directory (el secreto de la aplicación AAD obtenido en el paso 2)
- URI de la aplicación de Azure Active Directory (el URI de la aplicación de AAD que se obtuvo en el paso 2; por ejemplo,https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>Paso 7: configurar un conector personalizado en el centro de seguridad & cumplimiento

El último paso consiste en configurar el conector personalizado en el centro de seguridad & cumplimiento que se va a importar los datos de las páginas de empresa de Facebook a un buzón especificado en Office 365. Después de completar este paso, el servicio de importación de Office 365 iniciará el proceso de importación de datos de las páginas de empresa de Facebook a Office 365. 

Para obtener instrucciones paso a paso, consulte [configurar un conector personalizado en el centro de seguridad & cumplimiento](deploy-facebook-connector.md#step-7-set-up-a-custom-connector-in-the-security--compliance-center). 

Al finalizar este paso (siguiendo las instrucciones paso a paso), proporciona la siguiente información (que ha copiado en un archivo de texto después de completar los pasos).

- Dirección URL de Azure App Service (obtenida en el paso 4; por ejemplo,https://fbconnector.azurewebsites.net)
- APISecretKey (creado en el paso 4)
