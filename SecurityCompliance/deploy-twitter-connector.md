---
title: Implementar un conector para archivar datos de Twitter en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Los administradores pueden configurar un conector nativo para importar y archivar datos de Twitter a Office 365. Una vez que estos datos se han importado a Office 365, puede usar las características de cumplimiento, como las directivas de retención legal, búsqueda de contenido y retención, para administrar el gobierno de los datos de Twitter de la organización.
ms.openlocfilehash: c3c5af0fc42057d9fc2e8b8e67423398d6ed0ddf
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014779"
---
# <a name="deploy-a-connector-to-archive-twitter-data-in-office-365"></a>Implementar un conector para archivar datos de Twitter en Office 365

Este artículo contiene el proceso paso a paso para implementar un conector que usa el servicio de importación de Office 365 para importar datos de la cuenta de Twitter de su organización a Office 365. Para obtener información general de alto nivel de este proceso y una lista de los requisitos previos necesarios para implementar un conector de Twitter, vea [usar un conector de ejemplo para archivar datos de Twitter en Office 365 (versión preliminar)](archive-twitter-data-with-sample-connector.md). 

## <a name="step-1-download-the-package"></a>Paso 1: descargar el paquete

Descargue el paquete precompilado de la sección de versiones en el repositorio [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)de github en. En la versión más reciente, descargue el archivo zip denominado **SampleConnector. zip**. Carga este archivo zip en Azure en el paso 4.

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Paso 2: crear una aplicación en Azure Active Directory

1. Vaya a <https://portal.azure.com> e inicie sesión con las credenciales de una cuenta de administrador global de Office 365.

   ![](media/TCimage01.png)

2. En el panel de navegación izquierdo, haga clic en **Azure Active Directory**.

   ![](media/TCimage02.png)

3. En el panel de navegación izquierdo, haga clic en **registros de aplicaciones (versión preliminar)** y, a continuación, haga clic en **nuevo registro**.

   ![](media/TCimage03.png)

4. Registrar la aplicación. En **URI de redireccionamiento (opcional)**, seleccione Web en la lista desplegable tipo de <https://portal.azure.com> aplicación y, a continuación, escriba en el cuadro del URI.

   ![](media/TCimage04.png)

5. Copie el identificador de la **aplicación (cliente)** y el **directorio (inquilino)** y guárdelos en un archivo de texto u otra ubicación segura. Estos identificadores se usan en pasos posteriores.

    ![](media/TCimage05.png)

6. Vaya a **certificados & secretos para la nueva aplicación** y, en **secretos de cliente** , haga clic en **nuevo secreto de cliente**.

   ![](media/TCimage06.png)

7. Cree un secreto nuevo. En el cuadro Descripción, escriba el secreto y, a continuación, elija un período de expiración. 

   ![](media/TCimage08.png)

8. Copie el valor del secreto y guárdelo en un archivo de texto u otra ubicación de almacenamiento. Este es el secreto de la aplicación de AAD que se usa en pasos posteriores.

   ![](media/TCimage09.png)

9. Vaya al **manifiesto** y copie identifieruris a (que también se denomina el URI de la aplicación AAD), tal y como se resalta en la siguiente captura de pantalla. Copie el URI de la aplicación de AAD en un archivo de texto u otra ubicación de almacenamiento. Se usa en el paso 6.

    ![](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a>Paso 3: crear una cuenta de almacenamiento de Azure

1.  Vaya a la Página principal de Azure de su organización.

    ![](media/TCimage11.png)

2. Haga clic en **crear un recurso** y escriba la **cuenta de almacenamiento** en el cuadro de búsqueda.

   ![](media/TCimage12.png)

3. Haga clic en **almacenamiento**y, a continuación, en **cuenta de almacenamiento**.

   ![](media/TCimage13.png)

4. En la página **crear cuenta de almacenamiento** , en el cuadro suscripción, seleccione **pay-as-go** o **Free Trial** en función del tipo de suscripción de Azure que tenga. 

   ![](media/TCimage14.png)

5. Seleccione o cree un grupo de recursos.

   ![](media/TCimage15.png)

6. Escriba un nombre para la cuenta de almacenamiento.

   ![](media/TCimage16.png)

7. Revise y, a continuación, haga clic en **crear** para crear la cuenta de almacenamiento.

   ![](media/TCimage17.png)

8. Tras unos minutos, haga clic en **Actualizar** y, a continuación, haga clic en **ir a recurso** para navegar a la cuenta de almacenamiento.

   ![](media/TCimage18.png)

9. Haga clic en **teclas de acceso** en el panel de navegación izquierdo.

   ![](media/TCimage19.png)

10. Copiar una **cadena de conexión** y guardarla en un archivo de texto u otra ubicación de almacenamiento. Se usa al crear un recurso de aplicación web en el paso 4.

    ![](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a>Paso 4: crear un nuevo recurso de aplicación web en Azure

1. En la página **principal** de Azure portal, haga clic en **crear una \> aplicación \> Web de todos los recursos**. En la página **aplicación web** , haga clic en **crear**.

   ![](media/TCimage21.png)

2. Rellene los detalles (como se muestra a continuación) y, a continuación, cree la aplicación Web. El nombre que escriba en el cuadro **nombre** de la aplicación se usa para crear la dirección URL de Azure App Service; por ejemplo, twitterconnector.azurewebsites.net.

   ![](media/TCimage22.png)

3. Vaya al recurso de la aplicación web que acaba de crear y haga clic en configuración de la **aplicación** en el panel de navegación izquierdo. En **configuración**de la aplicación, haga clic en **Agregar nuevo valor** y agregue las tres opciones siguientes. Use los valores (que copió en el archivo de texto de los pasos anteriores): 

    – * * APISecretKey: puede escribir cualquier valor como secreto. Se usa para obtener acceso a la aplicación web del conector en el paso 7.

    – **StorageAccountConnectionString** – el URI de la cadena de conexión que copió después de crear la cuenta de almacenamiento de Azure en el paso 3.

    – **tenantId** : el identificador de inquilino de su organización de Office 365 que copió después de crear la aplicación de conector de Twitter en Azure Active Directory en el paso 2.

    ![](media/TCimage23.png)

4. En **Configuración general**, haga clic **en** junto a **AlwaysOn**. Haga clic en **Guardar** en la parte superior de la página para guardar la configuración de la aplicación.

   ![](media/TCimage24.png)

5. El último paso consiste en cargar el código fuente de la aplicación conector a Azure que ha descargado en el paso 1. En un explorador Web, vaya a https://<AzureAppResourceName>. scm.azurewebsites.net/ZipDeployUi. Por ejemplo, si el nombre del recurso de la aplicación de Azure (que se menciona en el paso 2 de esta sección) es **twitterconnector**, entonces tendría https://twitterconnector.scm.azurewebsites.net/ZipDeployUique hacerlo.

6. Arrastre y coloque el SampleConnector. zip (descargado en el paso 1) en esta página. Una vez que se cargan los archivos y la implementación se realiza correctamente, la página tendrá un aspecto similar al de la siguiente captura de pantalla:

   ![](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a>Paso 5: crear la aplicación de Twitter

1. Vaya a https://developer.twitter.com, inicie sesión con las credenciales de la cuenta de desarrollador de su organización y, a continuación, haga clic en **aplicaciones**.

   ![TCimage25-5. png](media/TCimage25-5.png)
2. Haga clic en **crear una aplicación**.
   
   ![](media/TCimage26.png)

3. En **detalles**de la aplicación, agregue información sobre la aplicación.

   ![](media/TCimage27.png)

4. En el panel del programador de Twitter, seleccione la aplicación que acaba de crear y copie el identificador de aplicación que se muestra y guárdelo en un archivo de texto u otra ubicación de almacenamiento. A continuación, haga clic en **detalles**.
   
   ![](media/TCimage28.png)

5. En la pestaña **claves y tokens** , en **claves** de la API de consumidor, copie la clave secreta de la API y guárdela en un archivo de texto u otra ubicación de almacenamiento. A continuación, haga clic en **crear** para generar un token de acceso y un secreto de token de acceso, y cópielos en un archivo de texto u otra ubicación de almacenamiento.
   
   ![](media/TCimage29.png)

   A continuación, haga clic en **crear** para generar un token de acceso y un secreto de token de acceso, y cópielos en un archivo de texto u otra ubicación de almacenamiento.

6. Haga clic en la pestaña **permisos** y configure los permisos como se muestra en la siguiente captura de pantalla:

   ![](media/TCimage30.png)

7. Una vez que haya guardado la configuración de permisos, haga clic en la pestaña detalles de la **aplicación** y, a continuación, haga clic en **Editar > editar detalles**.

   ![](media/TCimage31.png)

8. Realice las siguientes tareas:

   – Active la casilla para permitir que la aplicación conector inicie sesión en Twitter.
   
   : Agregue el URI de redireccionamiento de OAuth con el siguiente formato: ** \<connectorserviceuri>/views/twitteroauth**, donde el valor de *connectorserviceuri* es la dirección URL de Azure App Service para su organización; por ejemplo, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.

   ![](media/TCimage32.png)

La aplicación de desarrollo de Twitter ya está lista para usarse.

## <a name="step-6-configure-the-connector-web-app"></a>Paso 6: configurar la aplicación web del conector 

1. Vaya a https://\<AzureAppResourceName>. azurewebsites.net (donde **AzureAppResourceName** es el nombre del recurso de la aplicación de Azure que ha nombrado en el paso 4). Por ejemplo, si el nombre es **twitterconnector**, vaya a https://twitterconnector.azurewebsites.net. La Página principal de la aplicación es similar a la siguiente captura de pantalla:

   ![](media/FBCimage41.png)

2. Haga clic en **configurar** para mostrar una página de inicio de sesión.

   ![](media/FBCimage42.png)

3. En el cuadro identificador de inquilino, escriba o pegue el identificador de inquilino (que obtuvo en el paso 2). En el cuadro contraseña, escriba o pegue el APISecretKey (que obtuvo en el paso 2) y, a continuación, haga clic en **establecer valores de configuración** para mostrar la página Detalles de la **configuración** .

   ![](media/TCimage35.png)

4. En **detalles de configuración**, especifique las siguientes opciones de configuración 

   – **Clave de API de Twitter** : el identificador de la aplicación de Twitter que creó en el paso 5.
   – **Clave secreta** de la API de Twitter: clave secreta de la API para la aplicación de Twitter que creó en el paso 5.
   – **Token de acceso de Twitter** : el token de acceso que se creó en el paso 5.
   - **Secreto de token de acceso de Twitter** : el secreto de token de acceso que creó en el paso 5.
   : **Identificador de la aplicación AAD** : el identificador de la aplicación de la aplicación de Azure Active Directory que creó en el paso 2 – secreto de la **aplicación AAD** : el valor del secreto APISecretKey que creó en el paso 4.
   – **URI de la aplicación AAD** : el URI de la aplicación AAD obtenido en el paso 2; por ejemplo, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.
   : **Clave de instrumentación de App Insights** : Deje este cuadro en blanco.

5. Haga clic en **Guardar** para guardar la configuración del conector.

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a>Paso 7: configurar un conector personalizado en el centro de seguridad y cumplimiento

1.  Vaya a <https://protection.office.com> y, a continuación, haga clic en **datos de terceros de importación \> \> de gobierno de datos**.

    ![](media/TCimage36.png)

2. Haga clic en **Agregar un conector** y, a continuación, en **Twitter**.

   ![](media/TCimage37.png)

3. En la página **Agregar aplicación de conector** , escriba la siguiente información y, a continuación, haga clic en **validar conector**.

    : En el primer cuadro, escriba un nombre para el conector, como **Twitter**.
    : En el segundo cuadro, escriba o pegue el valor de la APISecretKey que agregó en el paso 4.
    – En el tercer cuadro, escriba o pegue la dirección URL de Azure App Service; por ejemplo, **https://twitterconnector.azurewebsites.net**.

   Una vez validado correctamente el conector, haga clic en **siguiente**.

   ![](media/TCimage38.png)

4. Haga clic en **iniciar sesión con la aplicación conector**.

   ![](media/TCimage39.png)

5. Escriba o pegue el APISecretKey de nuevo y, a continuación, haga clic en **iniciar sesión en el servicio de conector**.

   ![](media/TCimage40.png)


6. Haga clic en **continuar con Twitter**.

7. En la página inicio de sesión de Twitter, inicie sesión con las credenciales de la cuenta de Twitter de su organización.

   ![](media/TCimage42.png)

   Después de iniciar sesión, la página de Twitter mostrará el siguiente mensaje de error "el trabajo del conector de Twitter se configuró correctamente".

8. Haga clic en **Finalizar** para completar la configuración del conector de Twitter.

9. En la página **Establecer filtros** , puede aplicar un filtro para importar (y archivar) los elementos que tengan una antigüedad determinada. Haga clic en **Siguiente**.

   ![](media/TCimage44.png)

10. En la página **establecer cuenta de almacenamiento** , escriba la dirección de correo electrónico de un buzón de correo de Office 365 al que se importarán los elementos de Twitter.

    ![](media/TCimage45.png)

11. Revise la configuración y, a continuación, haga clic en **Finalizar** para completar la configuración del conector en el centro de seguridad & cumplimiento.

    ![](media/TCimage46.png)

    ![](media/TCimage47.png)

12. Vaya a la página **archivar datos de terceros** para ver el progreso del proceso de importación.

    ![](media/TCimage48.png)
