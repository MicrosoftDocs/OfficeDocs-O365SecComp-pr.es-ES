---
title: Restringir el acceso al contenido mediante el cifrado en las etiquetas de confidencialidad
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Al crear una etiqueta de confidencialidad, puede restringir el acceso al contenido al que se aplique la etiqueta. Las etiquetas de confidencialidad pueden utilizar el cifrado para proteger el contenido.
ms.openlocfilehash: 69deeed69a5b2970d387c30b01a062c6c068c567
ms.sourcegitcommit: 799a958fcac643f62dfac6fa04020f2f4758635c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30997046"
---
# <a name="restrict-access-to-content-by-using-encryption-in-sensitivity-labels"></a>Restringir el acceso al contenido mediante el cifrado en las etiquetas de confidencialidad

Al crear una etiqueta de confidencialidad, puede restringir el acceso al contenido al que se aplique la etiqueta. Por ejemplo, con las opciones de encriptación de una etiqueta de confidencialidad, se puede proteger el contenido para que:

- Solo los usuarios de su organización puedan abrir un correo electrónico o documentos confidenciales.
- Solo los usuarios del departamento de marketing puedan editar e imprimir documentos o correos electrónicos de anuncios de promociones, mientras que todos los demás usuarios de su organización solo puedan leerlos.
- Los usuarios no puedan reenviar un correo electrónico o copiar información que contenga noticias sobre una reorganización interna.
- La lista de precios actual que se envía a socios comerciales no pueda abrirse tras una fecha especificada.

Cuando se encripta un documento o correo electrónico, el acceso al contenido está restringido, por lo que:

- Se puede desencriptar solo por los usuarios autorizados por la configuración de encriptado de la etiqueta.
- Permanece encriptado independientemente de dónde resida, dentro o fuera de su organización, incluso si cambia el nombre del archivo.
- Se encripta tanto en reposo (por ejemplo, en una cuenta de OneDrive) como y en tránsito (por ejemplo, un correo electrónico enviado).

La configuración de cifrado está disponible cuando se crea una etiqueta de confidencialidad en el Centro de cumplimiento de Microsoft 365, Centro de seguridad de Microsoft 365 o el Centro de seguridad y cumplimiento de Office 365.

## <a name="how-encryption-works"></a>Cómo funciona la encriptación

La encriptación usa Azure Rights Management (Azure RMS). Azure RMS usa directivas de identidad, cifrado y autorización. Para obtener más información, consulte [¿Qué es Azure Rights Management?](https://docs.microsoft.com/es-ES/azure/information-protection/what-is-azure-rms)

## <a name="how-to-turn-on-encryption-for-a-sensitivity-label"></a>Cómo activar la encriptación para una etiqueta de confidencialidad

Para empezar, solo tiene que cambiar **Encriptación** a **Activado** y, después, use las siguientes opciones para controlar quién puede acceder al correo o documentos a los que se aplica esta etiqueta. Puede:

1. **Aplicar la encriptación a correo electrónico y documentos, o solo al correo.** Si elige solo correo, los mensajes con esta etiqueta se cifrarán en Outlook, pero los documentos con esta etiqueta no se cifrarán en otras aplicaciones, como Word o PowerPoint. 
2. **Permitir que el acceso al contenido con la etiqueta expire**, ya sea en una fecha específica o tras un número determinado de días después de aplicar la etiqueta. Después de ese momento, los usuarios no podrán abrir el elemento con la etiqueta. Si especifica una fecha, se activará en la medianoche de esa fecha, en la zona horaria actual. (Tenga en cuenta que algunos clientes de correo electrónico pueden no aplicar la expiración y mostrar correos electrónicos una vez pasada dicha fecha, debido a otros mecanismos de almacenamiento en caché).
3. **Permitir el acceso sin conexión** nunca, siempre o durante un número concreto de días después de aplicar la etiqueta. Si restringe el acceso sin conexión a nunca o a un número de días, cuando se alcance el umbral, los usuarios deberán volver a autenticarse y se registrará el acceso. Para obtener más información, vea la siguiente sección sobre la licencia de uso de administración de derechos.

![Configuración de cifrado en las etiquetas de confidencialidad](media/Sensitivity_Encryption_settings_for_sensitivity_label.png)

### <a name="rights-management-use-license-for-offline-access"></a>Licencia de uso de administración de derechos para el acceso sin conexión

Cuando un usuario abre un documento o correo electrónico sin conexión que esté protegido por una etiqueta de confidencialidad, se concede una licencia de uso de Azure Rights Management para el usuario. Esta licencia es un certificado que contiene los derechos de uso del usuario para el documento o correo electrónico y la clave de cifrado que se usó para cifrar el contenido. La licencia de uso también contiene una fecha de vencimiento si se ha configurado y el tiempo durante el que la licencia es válida.

Si no se ha establecido ninguna fecha de expiración, el período predeterminado de validez de licencia de uso para un espacio empresarial es 30 días. Durante la duración de la licencia de uso, el usuario no se vuelve a autenticar o autorizar para ver el contenido. Esto permite que el usuario pueda abrir el documento o correo electrónico protegido sin conexión a Internet. Cuando la validez de la licencia de uso expire, la próxima vez que el usuario acceda a un documento o correo electrónico protegido, el usuario debe ser autorizado y autenticarse de nuevo.

Además de volver a hacer la autenticación, se vuelven a evaluar la pertenencia a grupos de usuario y la directiva. Esto significa que los usuarios podrían experimentar resultados diferentes de acceso para el mismo documento si hay cambios en la directiva o pertenencia a grupos con respecto al último momento en que se accedió acceso al contenido.

Para obtener información sobre cómo cambiar la configuración de 30 días predeterminada, vea [Licencia de uso de administración de derechos](https://docs.microsoft.com/es-ES/azure/information-protection/configure-usage-rights#rights-management-use-license).

## <a name="assign-permissions-to-specific-users-or-groups"></a>Asignar permisos a usuarios o grupos específicos

Puede conceder permisos a usuarios específicos para que solo pueden interactuar con el contenido con la etiqueta.

Es un proceso de dos pasos sencillos:

1. Primero agrega usuarios o grupos a los que se asignarán permisos para el contenido con la etiqueta.
2. Después elige qué permisos obtienen los usuarios para el contenido con la etiqueta.

![Opciones para asignar permisos a usuarios](media/Sensitivity_Assign_permissions_settings.png)

### <a name="add-users-or-groups"></a>Agregar usuarios o grupos

Al asignar permisos, puede elegir:

- Todos los usuarios de su organización (todos los miembros del espacio empresarial). Esta configuración excluye cuentas de invitado.
- Cualquier usuario específico o grupo de seguridad habilitado para correo electrónico, grupo de distribución, grupo de Office 365 o grupo de distribución dinámico. 
- Cualquier dirección de correo electrónico o dominio fuera de su organización, como gmail.com, outlook.com o hotmail.com.

Cuando elige a todos los miembros del espacio empresarial o busca en el directorio, los usuarios o grupos deben tener una dirección de correo electrónico.

Se recomienda usar grupos en lugar de usuarios. Esta estrategia mantiene la configuración más sencilla.

### <a name="choose-permissions"></a>Elegir permisos

Al elegir qué permisos permitir para los usuarios o grupos, puede seleccionar entre:

- Un [nivel de permiso predefinido](https://docs.microsoft.com/es-ES/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) con un grupo de derechos preestablecido, como coautor o revisor.
- Un grupo personalizado de derechos, donde elije los permisos que quiere.

Para obtener más información sobre cada permiso específico, consulte [Derechos y descripciones de uso](https://docs.microsoft.com/es-ES/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).  

![Opciones para elegir permisos predefinidos o personalizados](media/Sensitivity_Choose_permissions_settings.png)

Tenga en cuenta que la misma etiqueta puede conceder diferentes permisos a diferentes usuarios. Por ejemplo, una sola etiqueta puede asignar a algunos usuarios como revisor y a otros usuarios como coautor, como se muestra a continuación.

Para ello, agregue usuarios o grupos, asigne sus permisos y guarde las opciones de configuración. Luego repita estos pasos, agregue usuarios y asigne permisos para guardar la configuración de nuevo. Puede hacerlo tantas veces como sea necesario para definir permisos diferentes para distintos usuarios.

![Usuarios distintos con permisos diferentes](media/Sensitivity_Multiple_users_permissions.png)

### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a>El emisor de administración de derechos (el usuario que aplica la etiqueta de confidencialidad) siempre tiene control total

El cifrado para una etiqueta de confidencialidad utiliza Azure RMS. Cuando un usuario aplica una etiqueta de confidencialidad para proteger un documento o correo electrónico mediante Azure RMS, ese usuario pasa a ser el emisor de administración de derechos para ese contenido.

El emisor de administración de derechos siempre obtiene permisos de control total para el documento o correo electrónico y además:

- Si la configuración de protección incluye una fecha de expiración, el emisor de administración de derechos puede abrir y editar el documento o correo electrónico después de esa fecha.
- El emisor de administración de derechos siempre puede acceder al documento o correo electrónico sin conexión.
- El emisor de administración de derechos puede seguir abriendo un documento después de que se revoque.

Para obtener más información, vea [Emisor de administración de derechos y propietario de administración de derechos](https://docs.microsoft.com/es-ES/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).

## <a name="storing-encrypted-content-in-onedrive-and-sharepoint"></a>Almacenar contenido cifrado en OneDrive y SharePoint

Tenga en cuenta que cuando se aplica el cifrado a los archivos almacenados en OneDrive y SharePoint, el servicio no puede procesar el contenido de estos archivos. Esto significa que algunas características como la coautoría, eDiscovery, la búsqueda, Delve y otras características colaborativas no funcionan. Además, las directivas de prevención de pérdida de datos (DLP) solo pueden trabajar con los metadatos (incluidas las etiquetas de Office 365), pero no con el contenido de archivos encriptados (como números de tarjeta de crédito incluidos en los archivos).

Esto se aplica solo al contenido almacenado en OneDrive y SharePoint. En Exchange Online, las reglas de flujo de correo (también denominadas reglas de transporte) usan la [super cuenta de usuario](https://docs.microsoft.com/es-ES/azure/information-protection/configure-super-users) para poder examinar el contenido cifrado y aplicar directivas DLP.

## <a name="important-prerequisites"></a>Requisitos previos importantes

Para poder usar el cifrado, es posible que deba realizar estas tareas.

### <a name="activating-azure-rights-management"></a>Activar Azure Rights Management

Para usar el cifrado en etiquetas de confidencialidad, el servicio de Azure Rights Management debe activarse en el espacio empresarial. En los espacios empresariales más recientes, el servicio está activado de forma predeterminada, pero es posible que deba activar manualmente el servicio. Para obtener más información, vea [Activar Azure Rights Management](https://docs.microsoft.com/es-ES/azure/information-protection/activate-service).

### <a name="configure-exchange-for-azure-information-protection"></a>Configurar Exchange para Azure Information Protection

Exchange no tiene que estar configurado para Azure Information Protection antes de que los usuarios puedan aplicar etiquetas en Outlook para proteger los mensajes. Sin embargo, hasta que Exchange no esté configurado para Azure Information Protection, no obtendrá toda la funcionalidad del uso de la protección de Azure Rights Management con Exchange.
 
Por ejemplo, los usuarios no pueden ver mensajes de correo electrónico protegidos en teléfonos móviles o con Outlook en la Web, no se puede indizar mensajes de correo electrónico protegidos para la búsqueda y no puede se configura Exchange Online DLP para la protección de administración de derechos. 

Para asegurarse de que Exchange puede admitir estos escenarios adicionales, vea lo siguiente:

- Para Exchange Online, consulte las instrucciones de [Exchange Online: configuración de IRM](https://docs.microsoft.com/es-ES/azure/information-protection/configure-office365#exchange-online-irm-configuration).
- Para Exchange local, debe implementar el [conector RMS y configurar los servidores de Exchange](https://docs.microsoft.com/es-ES/azure/information-protection/deploy-rms-connector). 
