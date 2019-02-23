---
title: Directivas de sesión en Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Las directivas de sesión de seguridad de aplicación de nube de Office 365 permiten la supervisión en tiempo real de los usuarios, lo que le ofrece una visibilidad granular de las aplicaciones de Office 365 y la capacidad de realizar diferentes acciones según la Directiva que establezca para una sesión de usuario. En lugar de permitir o bloquear completamente el acceso, con el control de sesión puede permitir el acceso a la vez que supervisa la sesión o limitar actividades de sesión específicas mediante el uso de las funciones de proxy inverso del control de aplicación de acceso condicional.
ms.openlocfilehash: a57b62073e93c95217a829f8aa381f4a585dacc5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218610"
---
# <a name="session-policies-in-office-365-cloud-app-security"></a>Directivas de sesión en Office 365 Cloud App Security

|Evaluación * *\>**|Planeación * *\>**|Implementación * *\>**|Uso * * * *|
|:-----|:-----|:-----|:-----|
|[Empezar a evaluar](office-365-cas-overview.md) <br/> |[Empezar a planear](get-ready-for-office-365-cas.md) <br/> |Ya está aquí.  <br/> [Siguiente paso](ocas-access-policies.md) <br/> |[Empezar a usar](utilization-activities-for-ocas.md) <br/> |

Las directivas de sesión de seguridad de aplicación de nube de Office 365 permiten la supervisión en tiempo real de los usuarios, lo que le ofrece una visibilidad granular de las aplicaciones de Office 365 y la capacidad de realizar diferentes acciones según la Directiva que establezca para una sesión de usuario. En lugar de permitir o bloquear completamente el acceso, con el control de sesión puede permitir el acceso a la vez que supervisa la sesión o limitar actividades de sesión específicas mediante el uso de las funciones de proxy inverso del control de aplicación de acceso condicional.

Por ejemplo, puede decidir que desde dispositivos no administrados o para sesiones procedentes de ubicaciones específicas, desea permitir que el usuario tenga acceso a la aplicación, pero también limitar la descarga de archivos confidenciales o requerir que determinados documentos estén protegidos tras la descarga. Las directivas de sesión permiten establecer estos controles de sesión de usuario y permitir el acceso y le permiten:

- [Supervisar todas las actividades](#monitor-all-activities)

- [Bloquear todas las descargas](#block-all-downloads)

- [Bloquear actividades específicas](#block-specific-activities)

- [Proteger archivos al descargarlos](#protect-files-on-download)

## <a name="prerequisites-to-using-session-policies"></a>Requisitos previos para usar directivas de sesión

- Licencia de Azure AD Premium P1

- Las aplicaciones de Office 365 relevantes deben [implementarse con el control de aplicación de acceso condicional](ocas-deploy-conditional-access-app-control.md)

- debe haber una  [directiva de acceso condicional de Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)en vigor que redirija a los usuarios a Office 365 Cloud App Security.

## <a name="create-an-azure-ad-conditional-access-policy"></a>Crear una directiva de acceso condicional de Azure AD

Directivas de acceso condicional de Azure Active Directory y directivas de sesión de Cloud App Security trabajan conjuntamente para examinar cada sesión de usuario y tomar decisiones de directiva para cada aplicación. Para configurar una directiva de acceso condicional en Azure AD, siga este procedimiento:

1. Configure una  [Directiva de acceso condicional de Azure ad](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)con asignaciones para un usuario o grupo de usuarios y la aplicación que quiera controlar con el control de aplicación de acceso condicional. Nota: esta directiva solo afectará a las aplicaciones que se implementaron con el  [control de aplicación de acceso condicional](ocas-deploy-conditional-access-app-control.md).

2. enrutar a los usuarios a Office 365 Cloud App Security seleccionando la opción **usar el Control de aplicación de acceso condicional exige restricciones** en la página de la **sesión** .

## <a name="create-a-cloud-app-security-session-policy"></a>Crear una directiva de sesión de Cloud App Security

Para crear una nueva Directiva de sesión, siga este procedimiento:

1. En el portal, seleccione **control** seguido de **directivas**.

2. En la página **directivas** , haga clic en **crear Directiva** y seleccione **Directiva de sesión**.

3. En la ventana **Directiva** de sesión, asigne un nombre a la Directiva.

4. En el campo **tipo** de control de sesión:
    
    - Seleccione **supervisar solo** si solo desea supervisar actividades por parte de los usuarios. Esta selección creará una directiva de supervisión solo para las aplicaciones que haya seleccionado, donde se descargarán todos los inicios de sesión, las descargas heurísticas y los tipos de actividad.
    
    - Seleccione **controlar la descarga del archivo (con DLP)** si desea supervisar las actividades de los usuarios. Puede realizar acciones adicionales, como bloquear o proteger descargas para los usuarios.
    
    - Seleccione **bloquear actividades** para bloquear actividades específicas, que puede seleccionar mediante el filtro **tipo** de actividad. Se supervisarán todas las actividades de las aplicaciones seleccionadas (y se indicará en el registro de actividad). Las actividades específicas que seleccione se bloquearán si selecciona la acción **bloquear** . Las actividades específicas que seleccionó provocarán alertas si selecciona la acción de **prueba** y tiene activadas las alertas.

5. En **origen** de la actividad en las **actividades que coinciden con todas las de la siguiente** sección, seleccione filtros de actividad adicionales para aplicarlos a la Directiva. Estos filtros pueden incluir las siguientes opciones:
    
    - **Etiquetas de dispositivo**: Use este filtro para identificar los dispositivos no administrados.
    
    - **Ubicación**: Use este filtro para identificar ubicaciones desconocidas (y, por lo tanto, arriesgadas).
    
    - **Dirección IP**: Use este filtro para filtrar por direcciones IP o use etiquetas de direcciones IP asignadas previamente.
    
    - **Etiqueta de agente de usuario**: Use este filtro para habilitar la heurística de identificación de aplicaciones móviles y de escritorio. Este filtro se puede establecer como igual o no igual que el **cliente nativo**. Este filtro debe probarse con sus aplicaciones móviles y de escritorio para cada aplicación en la nube.<br>Nota: las directivas de sesión no son compatibles con aplicaciones móviles y de escritorio. Las aplicaciones móviles y las aplicaciones de escritorio también se pueden bloquear o permitir mediante la creación de una directiva de acceso.

6. Si seleccionó la opción para **controlar la descarga de archivos (con DLP)**, en **origen** de la actividad en la sección **archivos que coincidan con todas las opciones** , seleccione filtros de archivo adicionales para aplicar a la Directiva. Estos filtros pueden incluir las siguientes opciones:
        
    - **Etiqueta de clasificación** : Use este filtro si su organización usa Azure Information Protection y sus datos están protegidos por sus etiquetas de clasificación. Puede filtrar los archivos según la etiqueta de clasificación que les haya aplicado. Para obtener más información sobre la integración con Azure Information Protection, vea [integración con Azure Information Protection](https://docs.microsoft.com/cloud-app-security/azip-integration).
        
    - **Nombre de archivo** : Use este filtro para aplicar la Directiva a archivos específicos.
        
    - **Tipo de archivo** : Use este filtro para aplicar la Directiva a tipos de archivo específicos, por ejemplo, bloquear la descarga de todos los archivos. xls.
    
    - En la sección **inspección** de contenido, establezca si desea habilitar el motor de DLP para que analice los documentos y el contenido de los archivos.
    
    - En **acciones**, seleccione uno de los siguientes elementos:
        
        - **Prueba (supervisar todas las actividades)**: establezca esta acción para permitir la descarga explícita de acuerdo con los filtros de directiva que establezca.
        
        - **Bloquear (bloquear la descarga de archivos y supervisar todas las actividades)**: establezca esta acción para bloquear explícitamente la descarga según los filtros de directiva que establezca. Para obtener más información, consulte [how Block download Works](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#block-download).
        
        - **Protect (Apply Classification Label to download and monitor All Activities)**: esta opción solo está disponible si selecciona **controlar la descarga de archivos (con DLP)** en **Directiva de sesión**. Si su organización usa Azure Information Protection, puede establecer una **acción** para aplicar un conjunto de etiquetas de clasificación en Azure Information Protection al archivo. Para obtener más información, vea [Cómo funciona proteger la descarga](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#protect-download).

7. Puede  **crear una alerta para cada evento que coincida con la gravedad de la Directiva**y establecer un límite de alerta. Seleccione si desea la alerta como un correo electrónico, un mensaje de texto o ambos.

## <a name="monitor-all-activities"></a>Supervisar todas las actividades

Al crear una directiva de sesión, cada sesión de usuario que coincida con la Directiva se redirige al control de la sesión en lugar de a la aplicación directamente. El usuario verá un aviso de supervisión para hacerle saber que se están supervisando sus sesiones.

Si no desea notificar al usuario que se está supervisando, puede deshabilitar el mensaje de notificación.

1. En la COG de configuración, seleccione **Configuración general**.

2. A continuación, en **control** de aplicación de acceso condicional, seleccione supervisión de **usuarios**y anule la selección de la casilla **notificar a los usuarios** .

Para mantener al usuario dentro de la sesión, el control de la aplicación de acceso condicional reemplaza todas las direcciones URL relevantes, las secuencias de comandos Java y las cookies dentro de la sesión de la aplicación con las direcciones URL de seguridad de aplicación de Office 365 Cloud. Por ejemplo, si la aplicación devuelve una página con vínculos cuyos dominios terminan `myapp.com`con, el control de la aplicación de acceso condicional reemplaza los vínculos con `myapp.com.us.cas.ms`dominios que terminan por algo como. De esta forma, toda la sesión se supervisa con Office 365 Cloud App Security.

El control de aplicación de acceso condicional registra los registros de tráfico de cada sesión de usuario que se redirige a través de él. Los registros de tráfico incluyen el tiempo, la dirección IP, el agente de usuario, las direcciones URL visitadas y el número de bytes cargados y descargados. Estos registros se analizan y se agrega un informe continuo, un **control de aplicación de acceso condicional de seguridad de la aplicación de nube**, a la lista de informes de detección en la nube del panel de detección en la nube.

### <a name="to-export-these-logs"></a>Para exportar estos registros:

1. Vaya a la configuración COG y haga clic en **control de aplicación de acceso condicional**.

2. En el lado derecho de la tabla, haga clic en el botón exportar.<br>![botón exportar](media/image3.png)<br>

3. Seleccione el rango del informe y haga clic en **exportar**. Este proceso puede tardar cierto tiempo.

### <a name="to-download-the-exported-log"></a>Para descargar el registro exportado:

1. Una vez preparado el informe, vaya a **configuración** y luego a **informes**exportados.

2. En la tabla, seleccione el informe relevante de la lista de **registros de tráfico de control de aplicaciones de acceso condicional**y haga clic en descargar.<br>![botón Descargar](media/image4.png)<br>

## <a name="block-all-downloads"></a>Bloquear todas las descargas

Cuando **bloquear** se establece como la **acción** que desea realizar en la Directiva de sesión de Cloud App Security, el control de aplicación de acceso condicional impide que un usuario descargue un archivo según los filtros de archivo de la Directiva. Office 365 Cloud App Security reconoce un evento de descarga para cada aplicación cuando un usuario inicia una descarga. El control de aplicación de acceso condicional interviene en tiempo real para evitar que se ejecute. Cuando se recibe la señal de que un usuario ha iniciado una descarga, el control de la aplicación **** de acceso condicional devuelve un mensaje restringido descargar al usuario y reemplaza el archivo descargado con un archivo de texto. El mensaje del archivo de texto al usuario se puede configurar y personalizar desde la Directiva de sesión.

## <a name="block-specific-activities"></a>Bloquear actividades específicas

Cuando se establece **actividades** de bloqueo como **tipo de actividad**, puede seleccionar actividades específicas para que se bloqueen en aplicaciones específicas. Todas las actividades de las aplicaciones seleccionadas se supervisarán y se notificarán en el registro de actividades. Las actividades específicas que seleccione se bloquearán si selecciona la acción **bloquear** . Las actividades específicas que seleccionó provocarán alertas si selecciona la acción de **prueba** y tiene activadas las alertas.

**Bloquee actividades** específicas y aplíquela a grupos específicos para crear un modo de solo lectura completo para su organización.

## <a name="protect-files-on-download"></a>Proteger archivos al descargarlos

Seleccione **bloquear actividades** para bloquear actividades específicas, que puede encontrar mediante el filtro **tipo** de actividad. Se supervisarán todas las actividades de las aplicaciones seleccionadas (y se indicará en el registro de actividad). Las actividades específicas que seleccione se bloquearán si selecciona la acción **bloquear** . Las actividades específicas que seleccionó provocarán alertas si selecciona la acción de **prueba** y tiene activadas las alertas.

Cuando se establece **proteger** como la **acción** que se realizará en la Directiva de sesión de Cloud App Security, el control de aplicación de acceso condicional aplica la etiquetación y la posterior protección de un archivo según los filtros de archivo de la Directiva. Las etiquetas se configuran en la consola de Azure Information Protection y es necesario seleccionar **proteger** en la etiqueta para que aparezca como una opción en la Directiva de Cloud App Security. Cuando se selecciona una etiqueta y se descarga un archivo que cumple los criterios de la Directiva de Cloud App Security, la etiqueta y la protección correspondiente (con permisos) se aplican al archivo tras la descarga. El archivo original permanece tal cual en la aplicación en la nube mientras el archivo descargado ya está protegido. Los usuarios que intenten tener acceso al archivo deben cumplir los requisitos de permisos determinados por la protección aplicada.

## <a name="next-steps"></a>Pasos siguientes

- [Obtenga información sobre las directivas de acceso en Office 365 Cloud App Security](ocas-access-policies.md)

- [Bloqueo de descargas en dispositivos no administrados con capacidades de control de aplicación de acceso condicional de Azure AD](https://docs.microsoft.com/en-us/cloud-app-security/use-case-proxy-block-session-aad)

