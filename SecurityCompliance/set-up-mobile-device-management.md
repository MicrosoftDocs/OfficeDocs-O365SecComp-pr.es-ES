---
title: Establecer seguridad Mobile Device Management (MDM) en Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_OverviewMDM
- 'O365E_OverviewMDM '
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: dd892318-bc44-4eb1-af00-9db5430be3cd
description: La administración de dispositivos móviles integrada para Office 365 le ayuda a proteger y administrar los dispositivos móviles como iPhone, iPad, Androids, los usuarios y teléfonos de Windows. Para empezar, siga estos pasos para activar y configurar la administración de dispositivos móviles para Office 365.
ms.openlocfilehash: c92290170b2937067e7407787282eaaa368b25b7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272365"
---
# <a name="set-up-mobile-device-management-mdm-in-office-365"></a>Establecer seguridad Mobile Device Management (MDM) en Office 365

La integrada Mobile Device Management (MDM) para Office 365 le ayuda a proteger y administrar los dispositivos móviles como iPhone, iPad, Androids, los usuarios y teléfonos de Windows. Puede crear y administrar las directivas de seguridad de dispositivo, remotamente borrar un dispositivo y ver los informes de detallada de los dispositivos.
  
¿Tiene preguntas? Hemos recopilado [una preguntas más frecuentes para ayudar a las preguntas más frecuentes de dirección](frequently-asked-questions-about-mdm.md). Tenga en cuenta que no se puede usar un [socios: administración delegada de oferta](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e) para administrar la administración de dispositivos móviles para Office 365. 
  
Administración de dispositivos es parte de la seguridad &amp; centro de cumplimiento, por lo que tendrá que ir allí para iniciar el programa de instalación MDM.
  
Para configurar la administración de dispositivos móviles para Office 365 necesitará para:
  
1. [Activar el servicio de administración de dispositivos móviles](#activate-the-mobile-device-management-service)  
2. [Configurar la administración de dispositivos móviles](#set-up-mobile-device-management)
3. [Asegúrese de que los usuarios inscribirse sus dispositivos](#step-4-recommended-manage-device-security-policies)
  
## <a name="activate-the-mobile-device-management-service"></a>Activar el servicio de administración de dispositivos móviles

1. Inicie sesión en Office 365 con su cuenta profesional o educativa. 
    
2. Vaya a [seguridad &amp; centro de cumplimiento](https://protection.office.com).
    
3. Navegue a la **prevención de pérdida de datos** \> **administración de dispositivos** y haga clic en **vamos a empezar** a iniciar el proceso de activación. 
    
    ![Configuración de administración de dispositivos móviles para Office 365](media/368e1026-9aa5-431b-a722-8f7cf528f263.png)
  
4. Hemos creado una directiva de seguridad predeterminada para ayudarle a empezar a trabajar. Actualizar el nombre de la directiva de seguridad en esta página y, a continuación, haga clic en **iniciar el programa de instalación**.
    
    ![Establecer la directiva de seguridad de administración de dispositivos móviles](media/5619a2d1-f900-4268-9050-5d7eb57429a5.png)
  
5. Verá la pantalla del programa de instalación que muestra el progreso de la configuración del servicio.
    
    ![Progreso de la instalación MDM](media/db45d1bb-d247-4ac0-9deb-1b0c1ace9bfa.png)
  
> [!TIP]
> También puede localizar **El programa de instalación de MDM** a través de la búsqueda. En el centro de administración de Office 365 \> página **principal** , administración de dispositivos móviles de tipo en el cuadro de **búsqueda** . > ![Búsqueda para administración de dispositivos móviles en el centro de administración](media/cd0ebf15-ef79-4eaa-ab5b-041ac0bd4e5b.png)
  
Puede tardar un poco para activar la administración de dispositivos móviles para Office 365, pero cuando termine, recibirá un correo electrónico que se explica los pasos que deben seguirse siguiente.
  
## <a name="set-up-mobile-device-management"></a>Configurar la administración de dispositivos móviles

Cuando el servicio está listo, complete los siguientes cuatro pasos para finalizar la instalación. Es posible que necesite haga clic en [Administrar la configuración](https://portal.office.com/EAdmin/Device/IntuneInventory.aspx) en la página de **administración de dispositivos** en la seguridad &amp; centro de cumplimiento para ver los valores siguientes. 
  
![Configurar la administración de dispositivos móviles pasos necesarios y recomendados](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
### <a name="step-1-required-configure-domains-for-mdm"></a>Paso 1: Dominios configurar (obligatorio) para MDM

Si no dispone de un dominio personalizado asociado con Office 365, o si no administra los dispositivos de Windows, puede omitir esta sección. De lo contrario, necesitará agregar registros DNS para el dominio en el host de DNS. Si ha agregado los registros ya, como parte de la configuración de su dominio con Office 365, está listo. Después de agregar los registros, se redirigen los usuarios de Office 365 en su organización que iniciar sesión en sus dispositivos de Windows con una dirección de correo electrónico que usa su dominio personalizado para inscribirse en MDM para Office 365.
  
¿Necesita ayuda para configurar los registros? Busque al registrador de dominios en la lista proporcionada en [crear registros DNS para Office 365 al administrar sus registros DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23) y seleccione el nombre de registrador para ir a ayuda paso a paso para la creación de registros DNS. Use las instrucciones para agregar los dos registros siguientes: 
  
|**Nombre de host**|**Tipo de registro**|**Dirección**|**TTL**|
|:-----|:-----|:-----|:-----|
|EnterpriseEnrollment  <br/> |CNAME  <br/> |EnterpriseEnrollment.manage.microsoft.com  <br/> |3600  <br/> |
|EnterpriseRegistration  <br/> |CNAME  <br/> |EnterpriseRegistration.windows.net  <br/> |3600  <br/> |
   
Después de agregar los dos registros, vuelva a la seguridad &amp; centro de cumplimiento y navegue a **administración de dispositivos** \> **Administrar la configuración** para llevar a cabo el siguiente paso. 
  
### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Paso 2: (Obligatorio) Configure un certificado APN para dispositivos iOS

Para administrar dispositivos iOS como iPad e iPhone, debe crear un certificado APN.
  
Para ello, siga los pasos de los vínculos de **Configurar** en la **página de administración de dispositivo móvil del programa de instalación**.
  
1. Junto a **configurar un certificado APN para dispositivos iOS**, seleccione **Configurar**.
    
2. Seleccione **descargar el archivo CSR** y guarde la solicitud de firma de certificado a en algún lugar en el equipo que sea fácil de recordar. 
    
    ![Instalar el cuadro de diálogo certificado APN](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. Seleccione **siguiente**.
    
4. Cree un certificado APN.
    
  - Seleccione **Apple APN Portal** para abrir el Portal de certificados de inserción de Apple. 
    
    ![Instalar el cuadro de diálogo de notificación APN cert con Apple APN Portal seleccionado](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - Iniciar sesión con un identificador de Apple.
    
    > [!IMPORTANT]
    > Use una compañía que Apple identificador asociado con una cuenta de correo electrónico que permanecerá con la organización, incluso si sale el usuario que administra la cuenta. Guarde este identificador porque debe usar el mismo identificador cuando es el momento de renovar el certificado. 
  
  - Seleccione **crear un certificado** y acepte los **Términos de uso**.
    
  - **Vaya** a la solicitud de firma de certificado descargado en el equipo de Office 365 y seleccione **cargar**.
    
  - **Descargar** el certificado APN creado por el Portal del certificado de inserción de Apple en su equipo. 
    
    > [!TIP]
    > Si tiene problemas para descargar el certificado, actualice el explorador. 
  
5. Vuelva a Office 365 y seleccione **siguiente** para ir a la página **cargar APN certificado** . 
    
6. Busque el certificado APN que ha descargado desde el Portal de certificados de inserción de Apple.
    
    ![Haga clic en el botón Examinar para seleccionar cert APN que descargó de Apple](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. Seleccione **Finalizar**.
    
Después de agregar APN certificado, vuelva a la seguridad &amp; centro de cumplimiento y navegue a **administración de dispositivos** \> **Administrar la configuración** para llevar a cabo el siguiente paso. 
  
### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Paso 3: (Recomendado) configurar la autenticación multifactor

Si no ve la autenticación multifactor (MFA) en **los pasos recomendados**, puede omitir esta sección. Si esta opción está en la lista, se recomienda que activar MFA en el portal de Azure AD para aumentar la seguridad de la administración de dispositivos móviles para el proceso de inscripción de Office 365. Está desactivado de forma predeterminada.
  
MFA ayuda a proteger el iniciar sesión en Office 365 para inscripción del dispositivo móvil al requerir un segundo formulario de autenticación. Los usuarios son necesarios para confirmar una llamada telefónica, el mensaje de texto o la notificación de la aplicación en su dispositivo móvil después de escribir correctamente su contraseña de la cuenta de trabajo. Sólo puede inscribirse su dispositivo una vez finalizada esta segunda forma de autenticación. Después de que los dispositivos de los usuarios se inscriben en administración de dispositivos móviles para Office 365, los usuarios pueden tener acceso a los recursos de Office 365 con su cuenta del trabajo.
  
Junto a **Configurar la autenticación multifactor**, seleccione **Configurar**. Para obtener información sobre cómo activar MFA en el portal de Azure AD, vea [Configurar la autenticación multifactor](https://go.microsoft.com/fwlink/p/?LinkId=519255).
  
Una vez configurado MFA, vuelva a la seguridad &amp; centro de cumplimiento y navegue a **administración de dispositivos** \> **Administrar la configuración** para llevar a cabo el siguiente paso. 
  
### <a name="step-4-recommended-manage-device-security-policies"></a>Paso 4: Las directivas de seguridad de dispositivo administrar (recomendado)

El siguiente paso es crear e implementar directivas de seguridad de dispositivo para ayudar a proteger los datos de su organización de Office 365. Por ejemplo, puede ayudar a evitar la pérdida de datos si un usuario pierde su dispositivo mediante la creación de una directiva en los dispositivos de bloqueo después de 5 minutos de inactividad y tienen dispositivos limpiar después de errores de inicio de sesión 3.
  
En la **seguridad &amp; centro de cumplimiento**, vaya a **las directivas de seguridad** \> **las directivas de seguridad de dispositivo** para crear directivas de seguridad de dispositivo y las reglas de acceso. 
  
![Agregar una directiva de seguridad de dispositivo](media/69a027f5-fbfb-482a-b850-9ccb280b8c62.png)
  
Para obtener instrucciones paso a paso acerca de cómo crear una nueva directiva, consulte [crear e implementar directivas de seguridad de dispositivo](create-device-security-policies.md).
  
> [!TIP]
>  Cuando se crea una nueva directiva, es posible que desee establecer la directiva para permitir infracción de directiva de acceso y el informe donde el dispositivo del usuario no es compatible con la directiva. Esto le permite ver cuántos dispositivos móviles se verá afectados por la directiva sin bloquear el acceso a Office 365. > Antes de implementar una nueva directiva a todos los usuarios de la organización, se recomienda que probarla en los dispositivos utilizados por un número reducido de usuarios. > También, antes de implementar las directivas, informar a su organización los impactos potenciales de inscripción de un dispositivo en MDM para Office 365. Dependiendo de cómo configurar las directivas, los dispositivos que no cumplen con ellos (que no son compatibles con dispositivos) podrían ser bloqueados el acceso a Office 365. También es posible que tienen dispositivos que no son compatibles con apps instaladas, fotografías y otra información personal que, en un dispositivo inscrito, puede eliminarse si se borra el dispositivo. Más información: [Borrar un dispositivo móvil en Office 365](wipe-a-mobile-device.md). 
  
## <a name="make-sure-users-enroll-their-devices"></a>Asegúrese de que los usuarios inscribirse sus dispositivos

Una vez que ha creado e implementado una directiva de administración de dispositivos móviles, cada usuario de Office 365 con licencia de la organización que se aplica la directiva de dispositivo recibirá un mensaje de inscripción la próxima vez que inicie sesión en Office 365 desde su dispositivo móvil. Deben completar los pasos de inscripción y activación antes de tener acceso a documentos y correo electrónico de Office 365. Vea [su dispositivo móvil para el trabajo o escuela de inscripción](enroll-your-mobile-device.md).
  
> [!IMPORTANT]
> Si el idioma preferido del usuario no es compatible con el proceso de inscripción, los usuarios pueden recibir notificación de inscripción y los pasos en sus dispositivos móviles en otro idioma. No todos los idiomas compatibles con Office 365 se admiten actualmente para el proceso de inscripción en dispositivos móviles. 
  
Los usuarios con dispositivos Android o iOS son necesarios para instalar la aplicación de Portal de la compañía como parte del proceso de inscripción.
  
## <a name="related-topics"></a>Temas relacionados

[Capacidades de administración de dispositivos móviles](capabilities-of-mobile-device-management.md)
  
[Crear e implementar directivas de seguridad de dispositivos](create-device-security-policies.md)
  

